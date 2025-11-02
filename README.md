# 🧩 LLM-Powered API Builder Documentation


---

## 📋 Table of Contents

1. [Overview](#overview)
2. [Features](#features)
3. [Prerequisites](#prerequisites)
4. [Installation & Setup](#installation--setup)
5. [Usage Guide](#usage-guide)
6. [Architecture](#architecture)
7. [API Examples](#api-examples)
8. [Generated Code Structure](#generated-code-structure)
9. [Troubleshooting](#troubleshooting)
10. [Advanced Configuration](#advanced-configuration)
11. [FAQ](#faq)

---

## 🎯 Overview

The **LLM-Powered API Builder** is a revolutionary tool that automatically generates production-ready REST APIs from natural language descriptions. Simply describe what you want to build, and the system generates:

- ✅ Complete database schemas (SQLAlchemy models)
- ✅ Full REST API with CRUD operations (FastAPI)
- ✅ Input validation (Pydantic)
- ✅ API documentation (Swagger/OpenAPI)
- ✅ Error handling and best practices
- ✅ Ready-to-deploy code

### Why This Tool?

- **100% FREE** - Uses Groq's free LLM API
- **No Coding Required** - Just describe in plain English
- **Production Ready** - Generates clean, working code
- **Learning Tool** - See how professional APIs are built
- **Time Saver** - Minutes instead of hours/days

---

## 🌟 Features

### Core Features

| Feature | Description |
|---------|-------------|
| **Natural Language Input** | Describe your API in plain English |
| **Smart Schema Generation** | AI creates optimized database models |
| **Complete CRUD APIs** | All Create, Read, Update, Delete operations |
| **Vector Database** | Learns from similar patterns |
| **Multi-Model Support** | Generates multiple related tables |
| **Relationship Handling** | Automatic foreign keys and relationships |
| **Input Validation** | Pydantic schemas for data validation |
| **Error Handling** | Proper HTTP exceptions and status codes |
| **API Documentation** | Auto-generated Swagger/ReDoc docs |
| **Download & Deploy** | Get complete project files |

### Technical Features

- **Free LLM**: Groq API (Llama 3.3 70B)
- **Free Embeddings**: HuggingFace (all-MiniLM-L6-v2)
- **Vector Store**: ChromaDB for pattern matching
- **Web Framework**: FastAPI with async support
- **ORM**: SQLAlchemy with declarative base
- **Validation**: Pydantic v2
- **UI**: Streamlit with custom styling
- **Tunneling**: Ngrok for public access

---

## 📦 Prerequisites

### Required Accounts (All FREE)

1. **Groq Account**
   - Website: https://console.groq.com
   - Sign up: Free, no credit card required
   - Get API Key: Console → API Keys → Create Key
   - Rate Limit: 30 requests/minute (free tier)

2. **Ngrok Account**
   - Website: https://dashboard.ngrok.com/signup
   - Sign up: Free tier available
   - Get Token: Dashboard → Your Authtoken
   - Features: Public URLs, HTTPS tunneling

3. **Google Colab**
   - Website: https://colab.research.google.com
   - Requirements: Google account
   - Resources: Free GPU/CPU, 12 hours runtime

### System Requirements

- **Browser**: Chrome, Firefox, Safari, or Edge
- **Internet**: Stable connection required
- **Storage**: ~500MB for dependencies
- **RAM**: 2GB+ recommended

---

## 🚀 Installation & Setup

### Step 1: Get API Keys

#### Get Groq API Key

1. Go to https://console.groq.com
2. Sign up or log in
3. Navigate to **API Keys** section
4. Click **Create API Key**
5. Copy the key (starts with `gsk_...`)

#### Get Ngrok Token

1. Go to https://dashboard.ngrok.com/signup
2. Sign up (free tier)
3. Go to **Your Authtoken** page
4. Copy the token

### Step 2: Setup in Google Colab

#### Option A: Using Colab Secrets (Recommended)

1. Open your Colab notebook
2. Click the **🔑 key icon** in left sidebar
3. Add secrets:
   - Name: `GROQ_API_KEY`, Value: Your Groq key
   - Name: `NGROK_AUTH_TOKEN`, Value: Your Ngrok token
4. Toggle "Notebook access" ON

#### Option B: Manual Input

The script will prompt you to enter keys if not found in secrets.

### Step 3: Run the Code

1. **Create a new Colab notebook**
2. **Copy the entire code** into a single cell
3. **Run the cell** (Ctrl+Enter or click Play)
4. **Wait for setup** (~2-3 minutes first time)
5. **Click the ngrok URL** that appears

---

## 📖 Usage Guide

### Quick Start Example

1. **Access the application** via the ngrok URL
2. **Choose an example** from the sidebar OR describe your own API
3. **Enter API name** (e.g., `rental_api`, `shop_api`)
4. **Click "🚀 Generate API"**
5. **Wait for generation** (~30-60 seconds)
6. **Review the code** in the tabs
7. **Download files** by clicking "💾 Save Files"

### Example Descriptions

#### 🏠 Rental Management System
```
Build a rental property management API with properties 
(address, price, bedrooms, status), bookings (check-in, 
check-out, property_id, user_id, status), users (name, 
email, phone, role), payments (amount, booking_id, 
payment_method, status), and reviews (rating, comment, 
property_id, user_id)
```

#### 🛒 E-commerce Platform
```
Create an e-commerce API with products (name, description, 
price, stock, category_id), orders (user_id, total, status, 
order_date), customers (name, email, address, phone), 
cart_items (user_id, product_id, quantity), and inventory 
(product_id, warehouse, quantity, last_updated)
```

#### 📝 Blog Platform
```
Build a blog platform API with posts (title, content, 
author_id, published_date, status), comments (content, 
post_id, user_id, created_at), users (username, email, 
bio, avatar_url), categories (name, description), and 
tags (name) with post_tags junction table
```

#### ✅ Task Management
```
Create a task management API with projects (name, 
description, owner_id, deadline), tasks (title, 
description, status, priority, project_id, assignee_id, 
due_date), users (name, email, role, department), and 
task_comments (content, task_id, user_id, timestamp)
```

#### 🍕 Restaurant Ordering
```
Build a restaurant ordering system with menu_items 
(name, description, price, category, is_available), 
orders (customer_id, total, status, order_time, 
delivery_address), customers (name, phone, address, 
email), order_items (order_id, menu_item_id, quantity, 
special_instructions), and delivery (order_id, driver_name, 
estimated_time, status)
```

### Best Practices for Descriptions

#### ✅ DO:
- Be specific about table names and fields
- Mention relationships (foreign keys)
- Include important field types (dates, status, amounts)
- Describe the business logic clearly
- Mention any special requirements

#### ❌ DON'T:
- Be too vague ("build a website")
- Use ambiguous terminology
- Forget to mention relationships
- Omit critical fields
- Mix multiple unrelated systems

---

## 🏗️ Architecture

### System Components

```
┌─────────────────────────────────────────────────────────┐
│                    User Interface                        │
│                   (Streamlit Web App)                    │
└─────────────────┬───────────────────────────────────────┘
                  │
                  ▼
┌─────────────────────────────────────────────────────────┐
│                  LLM Processing Layer                    │
│  ┌──────────────┐  ┌──────────────┐  ┌──────────────┐  │
│  │     Groq     │  │  HuggingFace │  │   ChromaDB   │  │
│  │  LLM API     │  │  Embeddings  │  │  Vector DB   │  │
│  └──────────────┘  └──────────────┘  └──────────────┘  │
└─────────────────┬───────────────────────────────────────┘
                  │
                  ▼
┌─────────────────────────────────────────────────────────┐
│                Code Generation Layer                     │
│  ┌──────────────────┐      ┌──────────────────┐        │
│  │ Schema Generator │      │  API Generator   │        │
│  │  (SQLAlchemy)    │──────▶   (FastAPI)      │        │
│  └──────────────────┘      └──────────────────┘        │
└─────────────────┬───────────────────────────────────────┘
                  │
                  ▼
┌─────────────────────────────────────────────────────────┐
│                   Output Files                           │
│   models.py  │  main.py  │  requirements.txt  │  README │
└─────────────────────────────────────────────────────────┘
```

### Data Flow

1. **User Input** → Natural language description
2. **Vector Search** → Find similar API patterns
3. **Schema Generation** → LLM creates database models
4. **API Generation** → LLM creates FastAPI code
5. **File Export** → Download complete project

### Technology Stack

| Layer | Technology | Purpose |
|-------|-----------|---------|
| **LLM** | Groq (Llama 3.3 70B) | Code generation |
| **Embeddings** | HuggingFace | Semantic search |
| **Vector DB** | ChromaDB | Pattern matching |
| **Web Framework** | FastAPI | REST API |
| **ORM** | SQLAlchemy | Database modeling |
| **Validation** | Pydantic | Data validation |
| **UI** | Streamlit | Web interface |
| **Database** | SQLite | Default database |
| **Tunneling** | Ngrok | Public access |

---

## 📝 API Examples

### Generated Endpoints

For a **Rental Management** system, the generated API includes:

#### Properties Endpoints

```bash
POST   /properties          # Create property
GET    /properties          # List all properties (paginated)
GET    /properties/{id}     # Get specific property
PUT    /properties/{id}     # Update property
DELETE /properties/{id}     # Delete property
```

#### Bookings Endpoints

```bash
POST   /bookings            # Create booking
GET    /bookings            # List all bookings
GET    /bookings/{id}       # Get specific booking
PUT    /bookings/{id}       # Update booking
DELETE /bookings/{id}       # Delete booking
```

#### Users Endpoints

```bash
POST   /users               # Create user
GET    /users               # List all users
GET    /users/{id}          # Get specific user
PUT    /users/{id}          # Update user
DELETE /users/{id}          # Delete user
```

### Example API Calls

#### Create a Property

```bash
POST http://localhost:8000/properties
Content-Type: application/json

{
  "address": "123 Main St, San Francisco",
  "price": 2500.00,
  "bedrooms": 2,
  "bathrooms": 2,
  "status": "available"
}
```

#### List Properties with Pagination

```bash
GET http://localhost:8000/properties?skip=0&limit=10
```

#### Update a Property

```bash
PUT http://localhost:8000/properties/1
Content-Type: application/json

{
  "status": "rented",
  "price": 2600.00
}
```

#### Delete a Property

```bash
DELETE http://localhost:8000/properties/1
```

### Response Examples

#### Success Response (200)

```json
{
  "id": 1,
  "address": "123 Main St, San Francisco",
  "price": 2500.00,
  "bedrooms": 2,
  "bathrooms": 2,
  "status": "available",
  "created_at": "2025-11-02T10:30:00",
  "updated_at": "2025-11-02T10:30:00"
}
```

#### Error Response (404)

```json
{
  "detail": "Property not found"
}
```

#### Validation Error (422)

```json
{
  "detail": [
    {
      "loc": ["body", "price"],
      "msg": "field required",
      "type": "value_error.missing"
    }
  ]
}
```

---

## 📁 Generated Code Structure

### Project Structure

```
rental_api/
├── models.py           # Database models (SQLAlchemy)
├── main.py             # FastAPI application
├── requirements.txt    # Python dependencies
├── README.md          # Setup instructions
└── database.db        # SQLite database (created on first run)
```

### models.py Structure

```python
from sqlalchemy import create_engine, Column, Integer, String, Float, DateTime, ForeignKey
from sqlalchemy.ext.declarative import declarative_base
from sqlalchemy.orm import relationship, sessionmaker
from datetime import datetime

Base = declarative_base()

class Property(Base):
    __tablename__ = 'properties'
    
    id = Column(Integer, primary_key=True, index=True)
    address = Column(String(500), nullable=False)
    price = Column(Float, nullable=False)
    bedrooms = Column(Integer)
    bathrooms = Column(Integer)
    status = Column(String(50), default='available')
    created_at = Column(DateTime, default=datetime.utcnow)
    updated_at = Column(DateTime, default=datetime.utcnow, onupdate=datetime.utcnow)
    
    # Relationships
    bookings = relationship("Booking", back_populates="property")
    reviews = relationship("Review", back_populates="property")
    
    def __repr__(self):
        return f"<Property(id={self.id}, address='{self.address}')>"

# ... more models ...

# Database initialization
engine = create_engine('sqlite:///database.db')
Base.metadata.create_all(engine)
```

### main.py Structure

```python
from fastapi import FastAPI, HTTPException, Depends
from pydantic import BaseModel
from sqlalchemy.orm import Session
from typing import List, Optional
from models import Base, Property, engine, sessionmaker

app = FastAPI(
    title="Rental Management API",
    description="Auto-generated API for rental management",
    version="1.0.0"
)

# Database session
SessionLocal = sessionmaker(autocommit=False, autoflush=False, bind=engine)

def get_db():
    db = SessionLocal()
    try:
        yield db
    finally:
        db.close()

# Pydantic schemas
class PropertyCreate(BaseModel):
    address: str
    price: float
    bedrooms: int
    bathrooms: int
    status: Optional[str] = "available"

class PropertyResponse(PropertyCreate):
    id: int
    created_at: datetime
    updated_at: datetime
    
    class Config:
        from_attributes = True

# CRUD Endpoints
@app.post("/properties", response_model=PropertyResponse, status_code=201)
def create_property(property: PropertyCreate, db: Session = Depends(get_db)):
    db_property = Property(**property.dict())
    db.add(db_property)
    db.commit()
    db.refresh(db_property)
    return db_property

@app.get("/properties", response_model=List[PropertyResponse])
def list_properties(skip: int = 0, limit: int = 10, db: Session = Depends(get_db)):
    properties = db.query(Property).offset(skip).limit(limit).all()
    return properties

# ... more endpoints ...

if __name__ == "__main__":
    import uvicorn
    uvicorn.run(app, host="0.0.0.0", port=8000)
```

---

## 🔧 Troubleshooting

### Common Issues

#### 1. Model Deprecation Error

**Error:**
```
Error code: 400 - model_decommissioned
```

**Solution:**
Update the model name in the code:
```python
# Change from:
model="llama-3.1-70b-versatile"
# To:
model="llama-3.3-70b-versatile"
```

#### 2. Ngrok Connection Failed

**Error:**
```
ERR_NGROK_108: ngrok gateway error
```

**Solution:**
- Check your ngrok token is correct
- Verify your internet connection
- Try restarting the cell
- Check ngrok status: https://status.ngrok.com

#### 3. Groq Rate Limit

**Error:**
```
Rate limit exceeded
```

**Solution:**
- Free tier: 30 requests/minute
- Wait 60 seconds and try again
- Consider upgrading to paid tier for higher limits

#### 4. ChromaDB Error

**Error:**
```
Could not connect to ChromaDB
```

**Solution:**
```bash
# Restart runtime and reinstall
!pip install --force-reinstall chromadb
```

#### 5. Streamlit Port Already in Use

**Error:**
```
Port 8501 already in use
```

**Solution:**
- Stop other running cells
- Restart Colab runtime
- Use a different port:
  ```python
  "--server.port", "8502"
  ```

### Debug Mode

Enable detailed logging:

```python
import logging
logging.basicConfig(level=logging.DEBUG)
```

### Getting Help

1. **Check Logs**: Read error messages carefully
2. **GitHub Issues**: Report bugs
3. **Groq Discord**: https://discord.gg/groq
4. **Stack Overflow**: Tag `groq`, `fastapi`, `streamlit`

---

## ⚙️ Advanced Configuration

### Custom Models

Change the LLM model:

```python
@st.cache_resource
def get_llm():
    return ChatGroq(
        model="mixtral-8x7b-32768",  # Alternative model
        temperature=0.5,              # Higher = more creative
        max_tokens=8000              # Token limit
    )
```

### Available Groq Models

| Model | Speed | Quality | Context | Best For |
|-------|-------|---------|---------|----------|
| llama-3.3-70b-versatile | Medium | High | 8k | General (Default) |
| llama-3.1-8b-instant | Fast | Good | 8k | Quick tasks |
| mixtral-8x7b-32768 | Medium | High | 32k | Long context |
| gemma2-9b-it | Fast | Good | 8k | Lightweight |

### Custom Embeddings

Use different embedding models:

```python
@st.cache_resource
def get_embeddings():
    return HuggingFaceEmbeddings(
        model_name="sentence-transformers/all-mpnet-base-v2",  # Better quality
        # model_name="all-MiniLM-L6-v2",  # Faster, smaller
    )
```

### Database Configuration

Switch to PostgreSQL:

```python
# In models.py
engine = create_engine('postgresql://user:password@localhost/dbname')
```

Switch to MySQL:

```python
# In models.py
engine = create_engine('mysql+pymysql://user:password@localhost/dbname')
```

### API Configuration

Customize FastAPI settings in generated code:

```python
app = FastAPI(
    title="My Custom API",
    description="Custom description",
    version="2.0.0",
    docs_url="/documentation",  # Change docs URL
    redoc_url="/redoc",
    openapi_url="/openapi.json"
)
```

### Add Authentication

Extend generated API with JWT auth:

```python
from fastapi.security import HTTPBearer, HTTPAuthorizationCredentials

security = HTTPBearer()

@app.get("/protected")
def protected_route(credentials: HTTPAuthorizationCredentials = Depends(security)):
    # Verify token
    return {"message": "Authenticated"}
```

---

## ❓ FAQ

### General Questions

**Q: Is this really 100% free?**  
A: Yes! Groq offers free API access, Ngrok has a free tier, and Google Colab is free.

**Q: Can I use this for production?**  
A: The generated code is production-ready, but review and test it thoroughly. Consider adding authentication, rate limiting, and monitoring.

**Q: How accurate is the generated code?**  
A: Very accurate for standard CRUD APIs. Complex business logic may need manual adjustments.

**Q: Can I modify the generated code?**  
A: Absolutely! Download the files and customize as needed.

### Technical Questions

**Q: What databases are supported?**  
A: SQLite (default), PostgreSQL, MySQL, MariaDB - any SQLAlchemy-compatible database.

**Q: Can I deploy the generated API?**  
A: Yes! Deploy to:
- Heroku
- AWS (EC2, Lambda, ECS)
- Google Cloud (Cloud Run, App Engine)
- Azure (App Service, Container Instances)
- Digital Ocean
- Railway
- Render

**Q: How do I add authentication?**  
A: Use FastAPI's security utilities:
```python
from fastapi.security import OAuth2PasswordBearer, OAuth2PasswordRequestForm
```

**Q: Can I generate APIs in other languages?**  
A: Currently Python/FastAPI only. But you can modify the prompts to generate Node.js/Express, Go/Gin, etc.

**Q: How long does generation take?**  
A: 30-60 seconds typically, depending on complexity and API load.

### Limitations

**Q: What are the limitations?**  
A:
- Free tier rate limits (30 req/min Groq)
- Colab session timeout (12 hours)
- Generated code may need refinement
- No built-in authentication (you add it)
- SQLite limitations for scale

**Q: Can it generate microservices?**  
A: Generate each service separately, then configure them to communicate.

**Q: Does it support GraphQL?**  
A: No, REST only currently. But you can modify prompts to generate GraphQL.

---

## 📚 Additional Resources

### Documentation Links

- **FastAPI**: https://fastapi.tiangolo.com
- **SQLAlchemy**: https://docs.sqlalchemy.org
- **Pydantic**: https://docs.pydantic.dev
- **Streamlit**: https://docs.streamlit.io
- **Groq**: https://console.groq.com/docs
- **LangChain**: https://python.langchain.com

### Tutorials

- **FastAPI Tutorial**: https://fastapi.tiangolo.com/tutorial/
- **SQLAlchemy ORM**: https://docs.sqlalchemy.org/en/20/orm/
- **API Design Best Practices**: https://restfulapi.net

### Community

- **Groq Discord**: https://discord.gg/groq
- **FastAPI Discord**: https://discord.com/invite/VQjSZaeJmf
- **Reddit r/FastAPI**: https://reddit.com/r/FastAPI

---

## 🎓 Learning Path

### Beginner
1. Use example prompts
2. Review generated code
3. Run locally with SQLite
4. Test endpoints in Swagger UI

### Intermediate
1. Modify generated code
2. Add custom endpoints
3. Implement authentication
4. Deploy to cloud platform

### Advanced
1. Create custom prompts
2. Add complex business logic
3. Implement microservices
4. Add monitoring and logging
5. Scale with PostgreSQL/Redis

---

## 📄 License

This tool is open source. Generated code is yours to use commercially or personally without restrictions.

---

## 🤝 Contributing

Found a bug? Have a feature request?

1. Fork the repository
2. Create a feature branch
3. Submit a pull request

---

## 📞 Support

Need help? 

- **Documentation**: Read this guide thoroughly
- **Issues**: Check troubleshooting section
- **Community**: Join Groq Discord
- **Updates**: Check for model deprecations

---

**Last Updated**: November 2025  
**Version**: 1.0.0  

---


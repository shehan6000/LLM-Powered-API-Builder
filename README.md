# 🧩 LLM-Powered API Builder Documentation



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



---


# 🛍️ AI Shopping Assistant

An AI-powered shopping assistant built with **Python, LangChain, Groq, Streamlit, and SQLite**. It helps users discover products, compare ratings, analyze product images, and place orders through a conversational interface.

## ✨ Features

- **🔎 Intelligent Product Search:** Search products by keywords, with optional price and organic-status filters.
- **⭐ Product Ratings:** Retrieve average customer ratings and review counts for products.
- **🖼️ Image-Based Product Analysis:** Upload a product image and use a vision model to extract product attributes for searching.
- **🛒 Order Placement:** Place orders for selected products and save order details in an SQLite database.
- **💬 Conversational Interface:** Interact with the shopping assistant through a Streamlit chat interface.
- **🗄️ Database Integration:** Store and retrieve product and order information using SQLite.

## 🧰 Tech Stack

| Technology | Purpose |
|---|---|
| Python | Core application logic |
| LangChain | Agent orchestration and tool calling |
| Groq | Access to language and vision models |
| Streamlit | Interactive web interface |
| SQLite | Product and order database |
| Python-dotenv | Environment variable management |

## 📁 Project Structure

```text
6_project_shopping_agent/
├── app.py              # Streamlit chat interface
├── shopping_agent.py   # Agent, tools, and model configuration
├── reviews_api.py      # Product rating and review functions
├── store.db            # Local SQLite database (not committed)
├── .env                # API credentials (not committed)
└── .gitignore          # Files excluded from Git
```

## ⚙️ Getting Started

### 1. Clone the repository

```bash
git clone https://github.com/ananion1/ai-shopping-assistant.git
cd ai-shopping-assistant
```

### 2. Create and activate a virtual environment

```bash
python -m venv .venv
```

**Windows:**

```bash
.venv\Scripts\activate
```

### 3. Install dependencies

Install the packages used by the project:

```bash
pip install streamlit langchain langchain-core langchain-groq python-dotenv
```

### 4. Configure environment variables

Create a `.env` file in the project root and add your Groq API key:

```env
GROQ_API_KEY=your_groq_api_key_here
```

Replace the placeholder with your own API key. Never publish your actual API key.

### 5. Set up the database

The application uses a local SQLite database named `store.db`. The database is excluded from this repository, so you must create or obtain a compatible database before running the application.

The database should contain the tables and columns expected by the application:

- **`products`** — product IDs, names, categories, prices, descriptions, and organic status.
- **`reviews`** — product review information used by the rating functions.
- **`orders`** — order IDs, product IDs, product names, and prices.

Use the project's database initialization script or create the required tables and sample data before proceeding.

### 6. Run the application

```bash
streamlit run app.py
```

Streamlit will provide a local URL where you can interact with the shopping assistant.

## 🧠 How It Works

1. The user describes a product they want or uploads a product image.
2. The agent searches the product database using the available search tool.
3. Product ratings are retrieved to help evaluate matching products.
4. The assistant presents suitable products and their IDs.
5. After explicit user confirmation, the agent calls the checkout tool.
6. The order is saved in the SQLite database.

## 🔐 Security Notes

- Keep API keys in `.env` and exclude the file from Git.
- Do not publish private customer information or sensitive order records.
- The SQLite database is excluded from version control; provide safe sample data or database setup instructions for reproducibility.

## 🚀 Future Improvements

- Add product recommendations based on user preferences.
- Implement product filtering and sorting by rating and price.
- Add order history and order tracking.
- Improve error handling and input validation.
- Add automated tests for search, ratings, and checkout.
- Provide a reproducible database initialization script.

## 👨‍💻 Author

**Ananya**

GitHub: [@ananion1](https://github.com/ananion1)

---

*Built as a hands-on project exploring AI agents, tool calling, multimodal models, and database integration.*

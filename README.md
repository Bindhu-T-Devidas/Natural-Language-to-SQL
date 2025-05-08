
# Text-to-SQL RAG App

This application leverages **Retrieval-Augmented Generation (RAG)** to convert natural language queries into SQL statements. It integrates the **Gemini LLM** for SQL generation and supports various databases including **SQLite, PostgreSQL, and MySQL**.

## Features

* **Multi-Database Support:** SQLite, PostgreSQL, and MySQL.
* **Flexible Query Modes:**

  * **LangChain RAG**: Uses LangChain for SQL generation.
  * **Manual FAISS RAG**: Uses FAISS index for retrieval.
  * **Schema Only**: Direct SQL generation from schema.
* **Schema Visualization:** Automatically generates ER diagrams for uploaded databases.
* **Real-Time Execution:** Runs generated SQL queries and displays the results.

---

## 📂 Project Structure

```
Text-to-SQL RAG App/
├── app7.py                     # Main Streamlit app
├── requirements.txt            # Dependencies list
├── utils/                      # Utility scripts
│   ├── er_diagram.py           # ER diagram generator
│   ├── llm_sql_generator.py    # SQL generation using Gemini
│   ├── schema_extractor.py     # Extracts schema from databases
│   └── vector_store.py         # FAISS-based vector store
└── vectorstore/                # Stores FAISS index and metadata
```

---

##  Installation

1. **Clone the Repository:**

   ```bash
   git clone https://github.com/Bindhu-T-Devidas/Text-to-SQL-RAG.git
   cd Text-to-SQL-RAG
   ```

2. **Install Dependencies:**

   ```bash
   pip install -r requirements.txt
   ```

3. **Set Up Environment Variables:**
   Create a `.env` file:

   ```
   GEMINI_API_KEY=your_gemini_api_key
   ```

   Replace `your_gemini_api_key` with your actual API key.

---

## Usage

1. **Run the Streamlit App:**

   ```bash
   streamlit run app7.py
   ```

2. **Upload a Database:**

   * Choose between **SQLite**, **PostgreSQL**, or **MySQL**.
   * Upload the file or enter database credentials.

3. **Generate SQL Query:**

   * Enter your natural language query.
   * Choose the query mode:

     * 🔁 **LangChain RAG**
     * 🛠️ **Manual FAISS RAG**
     * 📄 **No RAG (schema only)**
   * Click **"🚀 Generate SQL"**.

4. **View Results:**

   * The generated SQL query will be displayed.
   * If the query executes successfully, the result table will be shown.

---

## Technologies Used

* **Python**: Core programming language.
* **Streamlit**: Frontend for interactive query generation.
* **LangChain**: RAG pipeline for SQL generation.
* **Gemini LLM**: SQL generation engine.
* **FAISS**: Vector store for semantic retrieval.
* **SQLAlchemy**: Database connection handling.
* **Graphviz**: Visualizes ER diagrams.

---

## ER Diagram Generation

The application uses the `Graphviz` library to generate ER diagrams from the uploaded database schemas.

---

## 🌐 Supported Database Types

1. **SQLite (.db, .sqlite, .sql)**
2. **PostgreSQL**
3. **MySQL**

---

## Query Modes

1. **LangChain RAG:** Uses the LangChain library to generate SQL based on natural language input.
2. **Manual FAISS RAG:** Uses FAISS to retrieve relevant columns and tables for SQL generation.
3. **No RAG (Schema Only):** Directly generates SQL from the schema without using RAG techniques.

---

## 📊 Output Example

* **SQL Query:**

  ```sql
  SELECT * FROM tracks WHERE genre = 'Rock';
  ```
* **Results:**

  | TrackID | Name          | Genre |
  | ------- | ------------- | ----- |
  | 1       | Thunderstruck | Rock  |
  | 2       | Back in Black | Rock  |

---





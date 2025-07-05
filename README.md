# 🧠 SQL-LLM: Voice-Driven SQL Assistant

## Project Description
SQL-LLM is an intelligent, voice-powered assistant that allows users to query their SQL databases using natural language. Speak your question, and the app will transcribe your speech, generate the appropriate SQL query using an LLM (Large Language Model), execute it, and display the results—complete with automatic data visualizations.

This project is designed for ease of use and extensibility, making it a great starting point for anyone who wants to build natural language interfaces for databases.

---

## Features
- 🎤 **Voice-to-SQL**: Speak your query, get instant results.
- 🗣️ **Multi-language Support**: Choose from several languages for speech recognition.
- 🤖 **LLM-Powered SQL Generation**: Uses an LLM to convert natural language to SQL.
- 📊 **Automatic Data Visualization**: Results are visualized with Plotly (bar, line, scatter, histogram, etc.).
- 🛠️ **Easy to Extend**: Modular code for adding new databases, LLMs, or UI features.

---

## Demo
![Demo Screenshot](demo_screenshot.png)

---

## Getting Started

### 1. **Clone the Repository**
```sh
git clone https://github.com/yourusername/SQL-LLM.git
cd SQL-LLM
```

### 2. **Install Dependencies**
Make sure you have Python 3.8+ and `pip` installed.

```sh
pip install -r requirements.txt
```

#### **Windows Users:**
If you have trouble installing `pyaudio`, run:
```sh
pip install pipwin
pipwin install pyaudio
```

### 3. **Configure Your Database**
- Edit the `.env` file or `config.py` to set your `DATABASE_URI` (MySQL, PostgreSQL, etc.).
- Example for MySQL:
  ```env
  DATABASE_URI = "mysql+pymysql://user:password@localhost/dbname"
  ```
- Example for PostgreSQL:
  ```env
  DATABASE_URI = "postgresql+psycopg2://user:password@localhost/dbname"
  ```

### 4. **Add Your LLM API Key (if needed)**
- If your LLM provider requires an API key, add it to your `.env` file or `config.py`.

### 5. **Run the App**
```sh
streamlit run app.py
```

---

## Usage
1. **Select your language** for speech recognition from the dropdown.
2. **Click the "Start Listening" button** and speak your query (e.g., "Show me all customers from last month").
3. The app will transcribe your speech, generate SQL, run the query, and display the results and a visualization.
4. If speech recognition fails, you can also type your query (if enabled).

---

## Project Structure
```
SQL-LLM/
├── app.py                # Main Streamlit app
├── config.py             # Database and LLM configuration
├── utills.py             # Utility functions (DB schema, LLM call, SQL execution)
├── prompt_template.txt   # Prompt template for LLM
├── requirements.txt      # Python dependencies
├── README.md             # This file
└── ...
```

---

## Customization & Extending
- **Add new languages**: Update the `language_map` in `app.py`.
- **Change LLM provider**: Edit `call_euri_llm` in `utills.py`.
- **Support more databases**: Update `DATABASE_URI` and install the right drivers.
- **Improve visualization**: Tweak the Plotly code in `app.py`.

---

## Troubleshooting
- **Microphone not working?**
  - Make sure you have a working mic and have allowed browser/system access.
  - On Windows, use `pipwin` to install `pyaudio`.
- **Speech not recognized?**
  - Try a different language/accent setting.
  - Speak clearly and minimize background noise.
- **Database connection errors?**
  - Double-check your `DATABASE_URI` and credentials.
- **LLM errors?**
  - Make sure your API key is set and you have internet access.

---

## Contributing
Pull requests and suggestions are welcome! Please open an issue or PR if you have ideas or improvements.

---

## License
[MIT License](LICENSE)

---

## Credits
- [Streamlit](https://streamlit.io/)
- [SpeechRecognition](https://pypi.org/project/SpeechRecognition/)
- [Plotly](https://plotly.com/python/)
- Your favorite LLM provider 
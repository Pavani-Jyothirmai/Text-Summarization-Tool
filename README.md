# Text Summarization Tool

A powerful web-based application that helps you quickly summarize text using advanced AI models and traditional NLP techniques. This tool supports multiple summarization methods and can process various file formats.

## Features

### 🤖 Summarization Methods

1. **AI-Powered Methods**
   - **BART (Facebook)**: Uses Facebook's BART model for context-rich and fluent summaries. Ideal for long documents and reports.
   - **T5 (Google)**: Uses Google's T5 model for lightweight and effective summarization. Works well with most types of text.

2. **Traditional Methods**
   - **NLTK (Natural Language Toolkit)**: Uses sentence tokenization and lemmatization for basic summarization.
   - **SpaCy**: Advanced NLP library that provides named entity recognition and text processing.
   - **TF-IDF (Term Frequency-Inverse Document Frequency)**: Smart scoring system that identifies important sentences based on word frequency and uniqueness.
   - **WordNet Lemmatizer**: Converts words to their base form to improve accuracy.

### 📄 File Support

- **Text Input**
  - Paste text directly into the text area
  - Supports plain text input of any length

- **Document Processing**
  - **PDF Files**: Reads and processes PDF documents using PyPDF2
  - **DOCX Files**: Processes Word documents using python-docx
  - **TXT Files**: Handles plain text files

### 🎯 Customizable Options

1. **Summary Length Control**
   - **Short**: Generates concise 3-5 sentence summaries
   - **Medium**: Creates balanced 5-7 sentence summaries
   - **Long**: Provides detailed 7-10 sentence summaries
   - **Custom**: Allows user-defined number of sentences (1-50)

2. **PDF Formatting**
   - **Paragraph Style**: Clean, continuous text format
   - **Bulleted List**: Organized list format with bullet points

3. **Output Options**
   - Editable summary text area
   - Live preview of formatted summary
   - Download in PDF format with custom styling
   - Download in TXT format for plain text use

### 🧠 Smart Features

1. **Text Processing**
   - Automatic language detection
   - Sentence tokenization and lemmatization
   - Named entity recognition
   - Stop word removal

2. **Summary Generation**
   - Context-aware summarization
   - Important sentence extraction
   - Maintaining text coherence
   - Proper punctuation and formatting

3. **Quality Enhancements**
   - Sentence ordering optimization
   - Named entity preservation
   - TF-IDF based importance scoring
   - Lemmatization for better word matching

## Technical Details

### NLP Processing Pipeline

1. **Text Preprocessing**
   ```python
   # Example of text preprocessing
   text = "Your input text here"
   sentences = sent_tokenize(text)  # Split into sentences
   words = word_tokenize(text)      # Split into words
   lemmas = [lemmatizer.lemmatize(word) for word in words]  # Convert to base form
   ```

2. **TF-IDF Scoring**
   ```python
   # Example of TF-IDF scoring
   vectorizer = TfidfVectorizer(stop_words='english')
   tfidf_matrix = vectorizer.fit_transform(lemmatized_sentences)
   tfidf_scores = tfidf_matrix.sum(axis=1).A1
   ```

3. **Named Entity Recognition**
   ```python
   # Example of SpaCy NER
   doc = nlp(text)
   named_entities = set(ent.text.lower() for ent in doc.ents if ent.label_)
   ```

## Getting Started

### Option 1: Using Docker (Recommended)

1. Build and run the Docker container:
```bash
# Build the Docker image
docker build -t text-summarizer .

# Run the container
docker run -p 8501:8501 text-summarizer

# Or use docker-compose (easier)
docker-compose up --build
```

2. Open your web browser and navigate to:
http://localhost:8501

### Option 2: Local Installation

1. Install the required dependencies:
```bash
pip install -r requirements.txt
```

2. Run the application:
```bash
streamlit run app.py
```

3. Open your web browser and navigate to the URL shown in the terminal (usually http://localhost:8501)

## Usage

1. Choose your input method:
   - Paste text directly into the text area
   - Upload a PDF, DOCX, or TXT file

2. Select your summarization preferences:
   - Choose a summarization method (BART, T5, or Traditional)
   - Set the desired summary length
   - Select PDF formatting style

3. Click "Generate Summary" to create your summary

4. Edit the generated summary if needed

5. Download your summary in PDF or TXT format

## Requirements

- Python 3.8+
- Streamlit 1.35.0 or higher
- Required Python packages listed in requirements.txt

## Project Structure

```
Text-Summarizarion-Tool/
├── app.py              # Main application file
├── requirements.txt    # Python dependencies
├── sample_text.txt     # Example text for testing
└── README.md          # This file
```

## Contributing

1. Fork the repository
2. Create your feature branch
3. Commit your changes
4. Push to the branch
5. Create a new Pull Request

## License

This project is licensed under the MIT License - see the LICENSE file for details

## Acknowledgments

- Thanks to the Hugging Face team for their amazing transformers library
- Thanks to the Streamlit team for their excellent web framework
- Thanks to all contributors who have helped improve this tool

## Support

For support, please open an issue in the GitHub repository.
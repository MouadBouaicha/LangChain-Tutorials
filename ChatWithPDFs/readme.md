# Chat with PDF Streamlit Application

This Streamlit application allows you to upload multiple PDF files and ask questions based on their content. It leverages various AI technologies to provide detailed and accurate answers from the uploaded PDFs.

## Technologies Used

- **Streamlit**: For building the interactive web application.
- **PyPDF2**: For extracting text from PDF files.
- **Langchain**: For managing and processing text chunks.
- **FAISS**: For creating a vector store and performing similarity searches.
- **Google Generative AI**: For generating embeddings and handling conversational queries.
- **Dotenv**: For managing environment variables.

## Installation

### Prerequisites

- Python 3.10 or higher
- Conda package manager

### Setup Instructions

1. **Clone the Repository**:

   ```sh
   git clone https://github.com/yourusername/ChatWithPDFs.git
   cd ChatWithPDFs
   ```

2. **Create a Conda Environment**:

   ```sh
   conda create -p venv python==3.10 -y
   conda activate ./venv
   ```

3. **Install Required Packages**:

   ```sh
   pip install -r requirements.txt
   pip install -U langchain-community

   ```

4. **Configure Environment Variables**:

   Create a `.env` file in the root directory of the project and add your Google API key:

   ```env
   GOOGLE_API_KEY=your_google_api_key_here
   ```

## Running the Application

1. **Start the Streamlit Application**:

   ```sh
   streamlit run main.py
   ```

2. **Upload PDF Files and Ask Questions**:

   - Use the sidebar to upload multiple PDF files.
   - Click on the "Submit & Process" button to process the PDFs.
   - Enter your question in the text input field and receive answers based on the content of the PDFs.

## Main Functions and Workflow

### `get_pdf_text(pdf_docs)`

Extracts text from the uploaded PDF documents.

### `get_text_chunks(text)`

Splits the extracted text into manageable chunks for processing.

### `get_vector_store(text_chunks)`

Creates a vector store using FAISS and Google Generative AI embeddings and saves it locally.

### `get_conversational_chain()`

Sets up the conversational AI chain using a custom prompt template and the Google Generative AI model.

### `user_input(user_question)`

Handles user questions, performs a similarity search on the vector store, and retrieves the answer using the conversational AI chain.

### `main()`

Main function that sets up the Streamlit application layout and handles user interactions.

## Contributing

Feel free to fork this repository and contribute by submitting a pull request. For major changes, please open an issue first to discuss what you would like to change.

## License

This project is licensed under the MIT License.

# Qwen-2.5-7B-Instruct Gradio Chatbot with File Upload

This repository contains the code for a powerful and interactive chatbot built with Gradio, leveraging the Qwen-2.5-7B-Instruct model. The application provides a user-friendly web interface for conversational AI, enhanced with the capability to upload and analyze various file types, including PDFs, DOCX, and plain text.

![Chatbot Screenshot](httpshttps://i.imgur.com/your-screenshot-url.png) <!-- It's highly recommended to add a screenshot of your running application -->

## Features

-   **Interactive Chat Interface**: A clean and responsive chat UI built with Gradio.
-   **Powered by Qwen-2.5-7B**: Utilizes the high-performance Qwen-2.5-7B-Instruct model for intelligent and context-aware responses.
-   **Multi-Format File Upload**: Users can upload documents (`.pdf`, `.docx`, `.txt`, etc.) to provide context for their questions.
-   **Text Extraction**: Automatically extracts text from uploaded files to be included in the conversation.
-   **Customizable Generation Parameters**: The UI includes sliders and options to adjust model parameters like temperature, max tokens, top-p, top-k, and repetition penalty.
-   **GPU Accelerated**: Optimized for running on CUDA-enabled GPUs for faster inference.
-   **Model & System Information**: Displays details about the loaded model and the available hardware.

## Technology Stack

-   **Model**: `Qwen/Qwen2.5-7B-Instruct`
-   **Framework**: `Gradio`
-   **Core Libraries**: `PyTorch`, `transformers`
-   **File Handling**: `PyPDF2`, `python-docx`

## Setup and Installation

### Prerequisites

-   Python 3.10 or higher
-   NVIDIA GPU with CUDA installed (for GPU acceleration)
-   `pip` and `virtualenv`

### Installation Steps

1.  **Clone the repository:**
    ```bash
    git clone https://github.com/SakibAhmedShuva/Qwen-2.5-Gradio-Chatbot-with-File-Upload.git
    cd Qwen-2.5-Gradio-Chatbot-with-File-Upload
    ```

2.  **Create and activate a virtual environment:**
    ```bash
    python -m venv venv
    source venv/bin/activate  # On Windows, use `venv\Scripts\activate`
    ```

3.  **Install the required Python packages:**
    ```bash
    pip install -r requirements.txt
    ```
    *Note: If a `requirements.txt` file is not available, you can install the necessary packages listed in the `Qwen_2.5.ipynb` notebook.*

    ```bash
    pip install gradio torch transformers PyPDF2 python-docx Pillow
    ```

## Usage

1.  **Run the application:**
    Execute the Python script or the Jupyter notebook cells. If running from a `.py` file:
    ```bash
    python your_script_name.py
    ```
    If using the Jupyter Notebook (`Qwen_2.5.ipynb`), run all the cells.

2.  **Access the web interface:**
    The application will start a local web server. You can access the chatbot interface by opening the local URL (e.g., `http://127.0.0.1:7860`) provided in the console output. A public link will also be generated for temporary sharing.

3.  **Interact with the Chatbot:**
    -   **Send a message**: Type your message in the input box and press Enter or click the "Send" button.
    -   **Upload files**: Click the "📎" button to upload one or more documents. The content of these files will be added to the context of your next message.
    -   **Adjust settings**: Use the sliders and text areas in the "Model Settings" panel on the right to fine-tune the model's behavior.
    -   **Clear the conversation**: Click the "Clear" button to reset the chat history.

## How It Works

The application loads the `Qwen/Qwen2.5-7B-Instruct` model and its tokenizer using the `transformers` library. When a user sends a message, with or without uploaded files, the following happens:
1.  If files are present, their text content is extracted and appended to the user's prompt.
2.  The conversation history, system prompt, and the new user message are formatted into a single prompt using the model's chat template.
3.  The model generates a response based on this context.
4.  The response is streamed back to the Gradio interface and displayed to the user.

## License

This project is open-source and available under the [MIT License](LICENSE).

## Acknowledgements

-   The [Qwen Team](https://github.com/QwenLM) at Alibaba Cloud for developing the Qwen models.
-   The teams behind [Hugging Face](https://huggingface.co/) and [Gradio](https://www.gradio.app/) for their invaluable tools and platforms.

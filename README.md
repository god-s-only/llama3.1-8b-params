# Fine-Tuned LLaMA 3.1 Model on Hausa Dataset

## Overview

This repository contains a fine-tuned LLaMA 3.1 model that is optimized for processing and generating text in Hausa. The fine-tuning ensures the model responds appropriately to Hausa prompts while avoiding repetitive or nonsensical outputs. A REST API was developed and deployed using **FastAPI** and **ngrok** for seamless access.

## Features

- **Fine-Tuned Model:** Customized for Hausa language understanding and generation.
- **REST API:** Accessible endpoints for interaction with the model.
- **Deployment with ngrok:** Enables secure public access to the local FastAPI server.

## Project Structure

```
├── LLAMA_3_1_HAUSA_TO_ENGLISH.ipynb  # Jupyter notebook for fine-tuning and deployment
```

## Setup and Installation

### Prerequisites

- Python 3.10 or higher
- GPU with CUDA support for running the model efficiently
- ngrok installed

### Installation Steps

1. **Clone the repository:**

   ```bash
   git clone https://github.com/your-username/llama3.1-8b-params.git
   cd llama3.1-8b-params
   ```

2. **Set up a virtual environment:**

   ```bash
   python -m venv venv
   source venv/bin/activate  # On Windows: venv\Scripts\activate
   ```

3. **Install dependencies:**

   ```bash
   pip install -r requirements.txt
   ```

4. **Start the FastAPI server:**

   ```bash
   python main.py
   ```

5. **Expose the server using ngrok:**

   ```bash
   ngrok http 8000
   ```

   Copy the ngrok URL provided and use it to access the API.

## API Endpoints

### Base URL

Replace `BASE_URL` with your ngrok URL (e.g., `https://1234-5678-abcdef.ngrok.io`).

### Endpoints

1. **Generate Text**

   - **URL:** `POST /generate`
   - **Description:** Generate Hausa text based on input text.
   - **Request Body:**
     ```json
     {
       "input_text": "Enter your input text here"
     }
     ```
   - **Response:**
     ```json
     {
       "generated_text": "Generated Hausa response"
     }
     ```

2. **Health Check**

   - **URL:** `GET /health`
   - **Description:** Check if the server is running.
   - **Response:**
     ```json
     {
       "status": "ok"
     }
     ```

## Additional Information

- **Fine-Tuning:** The model was fine-tuned using the [Hugging Face Transformers library](https://huggingface.co/docs/transformers).
- **Memory Optimization:** The model is loaded in 8-bit precision to reduce memory usage.
- **Dataset Note:** The dataset used for fine-tuning is not included in this repository due to privacy considerations.

## Future Enhancements

- Add more endpoints for advanced interactions.
- Expand the dataset for improved model performance.
- Deploy the API to a cloud service for enhanced availability.

## Contributing

Contributions are welcome! Feel free to open issues or submit pull requests for improvements.

## License

This project is licensed under the MIT License. See the `LICENSE` file for more details.

## Acknowledgments

- [Hugging Face](https://huggingface.co/) for the Transformers library.
- [FastAPI](https://fastapi.tiangolo.com/) for creating a fast and robust API.
- [ngrok](https://ngrok.com/) for providing an easy-to-use tunneling solution.


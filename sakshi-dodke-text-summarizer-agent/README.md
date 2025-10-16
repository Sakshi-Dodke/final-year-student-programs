## Public link
https://text-summarizer-agent.onrender.com/
## Your Name
Sakshi Rajendra Dodke
## Agent Name as per the PDF
Text Summarizer Agent
## Which LLM API are you using for generation?
Hugging Face Inference API with `facebook/bart-large-cnn` (primary) and `sshleifer/distilbart-cnn-12-6` (backup)
## What suggestion did Pritesh give you?
He suggested combining the two separate buttons “Refine Summary” and “Summary” into a single unified button. Initially, the UI was built using Streamlit, but he recommended switching to a more basic web interface using HTML, CSS, and JavaScript
## What was the challenge you faced?
Initially, I considered using the Google or OpenAI APIs for text summarization, but they are paid services. After researching alternatives, I discovered the Hugging Face Inference API, which provides free access to powerful pre-trained summarization models.
## Screenshot for your implementation.
![Text Summarizer Agent Screenshot](https://github.com/user-attachments/assets/262419bd-170b-4eb8-b37e-9cbb4dcd1e06)
## Email Address
sakshidodke04@gmail.com
## Give stepwise flow of what your agent does
1. The user opens the web interface and enters or pastes the text to be summarized.
2. The frontend sends a POST request to the Flask backend endpoint `/summarize` with the text data.
3. The backend counts the number of sentences in the input to determine adaptive summary length (`min_length` and `max_length`).
4. The backend formats the text with the prompt `Summarize the following text:` and prepares the request payload for the Hugging Face API.
5. The backend sends the request to the primary Hugging Face model (`facebook/bart-large-cnn`).
6. If the primary model fails or returns an error, the backend automatically tries the backup model (`sshleifer/distilbart-cnn-12-6`).
7. The backend receives the summarized text from the API response.
8. The summary is sent back as JSON to the frontend.
9. The frontend displays the summarized text to the user in the web interface.
## Your tech-stack?
- Backend: Python, Flask
- Models: Hugging Face Inference API (`facebook/bart-large-cnn` as primary, `sshleifer/distilbart-cnn-12-6` as backup)
- Frontend: HTML, CSS, JavaScript
- Hosting / Deployment (optional): Render
## Github Profile
https://github.com/Sakshi-Dodke

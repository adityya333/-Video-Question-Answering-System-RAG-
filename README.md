# Video Transcript RAG

This project is a Retrieval-Augmented Generation (RAG) application that answers questions about the content of a specific YouTube video. Instead of asking an LLM to answer directly, the application first finds the most relevant parts of the video's transcript and then uses the LLM to generate a final response based on that information.

## How it works

The project follows these steps:

1. Convert the video into audio using **FFmpeg**.
2. Generate a transcript from the audio using **OpenAI Whisper** running locally.
3. Split the transcript into smaller text chunks.
4. Generate embeddings for each chunk using the **BGE-M3** embedding model through **Ollama**.
5. When the user asks a question, convert the question into an embedding.
6. Use **Cosine Similarity** to find the transcript chunks that are most relevant to the user's question.
7. Convert those matching chunks back into text and send them, along with the user's question, to the LLM.
8. The LLM generates the final response based only on the retrieved transcript.

Most of the work in this project is focused on preparing and retrieving the correct context for the LLM. The LLM is mainly responsible for refining the retrieved information into a natural response.

## Technologies Used

* Python
* Flask
* HTML & CSS
* OpenAI Whisper
* Ollama
* BGE-M3 Embedding Model
* scikit-learn (Cosine Similarity)
* FFmpeg
* Pandas

## Features

* Ask questions about a specific video's content.
* Local audio transcription using Whisper.
* Local embedding generation using Ollama.
* Semantic search using vector embeddings.
* Simple Flask web interface for interacting with the RAG system.

## Project Structure

* `app.py` - Flask application
* `RAG_core/` - Core retrieval and response generation logic
* `templates/` - HTML templates
* `static/` - CSS files

## Note

This project was built to understand how a Retrieval-Augmented Generation (RAG) pipeline works from scratch by implementing each stage of the process, from transcription and embedding generation to semantic retrieval and response generation.

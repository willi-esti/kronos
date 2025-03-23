# AI-powered Error Tracking and Solution Management System

This system is designed to help track errors, store solutions, and allow an AI assistant to help find solutions and update the database with new error information. It uses vector databases like Weaviate or Qdrant to store the vectors and related metadata.

## Features

- **Web-based UI**:
  - Users can upload documents (text, PDFs, etc.) to add to the system.
  - The system extracts relevant information, generates vectors, and stores them in the vector database.
- **AI-powered Conversations**:
  - The AI infers error data from the conversation (error type, system, logs, etc.).
  - The AI will show what it plans to add to the database and ask for confirmation before storing it.
  - The system will present the solution to the error and offer the option to explain the solution in more detail.
- **Database**:
  - The vector database (Weaviate or Qdrant) stores metadata, including title, description, and other custom fields.
  - The AI assistant can search for similar errors using vector similarity.
  - New errors can be added by the AI based on the conversation, and users can confirm before storage.

## Installation

1. **Install the required dependencies**:

   ```bash
   pip install -r requirements.txt
   ```

2. **Start the Vector Database** (Weaviate or Qdrant):
   Follow the official documentation of [Weaviate](https://weaviate.io/docs) or [Qdrant](https://qdrant.tech/documentation/) to set up and run the vector database.

3. **Start the Web UI**:

   ```bash
   npm install
   npm run dev
   ```

4. **Configure AI Assistant**:
   Set up the AI assistant (based on OpenAI GPT or similar) with the required API keys and integrate it into the conversation flow.

## Usage

- **Upload Documents**: Use the file upload feature to add new documents. These documents will be processed, and vectors will be generated and stored.
- **Start Conversations**: Chat with the AI assistant about errors you’ve encountered or are currently working on.
  - The AI will infer details from your conversation and display the data it will add to the database.
  - It will ask for confirmation before storing any new error data.
- **Retrieve Solutions**: If a known error is queried, the system will return the relevant solution, and you can click a button to view a detailed explanation.
- **Update Solutions**: If the AI detects new information during conversations, it will update existing records (with confirmation).

## Technical Architecture

- **Vector Database**: Weaviate or Qdrant stores embeddings, metadata, and custom fields such as error type, system, solution, and more.
- **AI Model**: The assistant uses an AI model (like GPT) to interact with users, infer data, and guide conversations.
- **Web UI**: A simple interface where users can upload documents, chat with the AI, and view results.
- **Backend**: The backend handles database interactions, querying the vector database, and managing AI communication.

## Future Improvements

- **Multimodal Support**: Extend support for more data types, such as images or videos.
- **Advanced Search**: Improve search functionality to allow filtering based on metadata fields like error type, system, and time of occurrence.
- **User Profiles**: Allow users to maintain profiles and track errors across different systems.

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

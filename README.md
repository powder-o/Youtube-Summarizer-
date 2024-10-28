# YouTube Video Summarizer - Overview

My friends asked me to post something that would help them to learn stuff like this without actually spending hours on tutorials from various source. So I made this as descriptive as possible so even a beginner might understand. This notebook combines my learnings from various sources.

I hope this helps.

This project demonstrates multiple methods to effectively summarize YouTube video transcripts. It utilizes four distinct techniques, each offering a unique approach to generating meaningful summaries:

1. **TF-IDF Summarization**
2. **BART Transformer Model**
3. **LangChain Stuff Method**
4. **LangChain Map Reduce Method**

## TF-IDF Summarization

The TF-IDF (Term Frequency-Inverse Document Frequency) method identifies important sentences within the transcript. It assigns scores based on term frequency and document frequency, helping extract the most relevant information for the summary. This method is straightforward and works well for shorter content but may struggle with longer, more complex transcripts.

## BART Transformer Model

The BART transformer model from Hugging Face's `transformers` library is used to generate natural language summaries. As an encoder-decoder model, it is specifically designed for text summarization. BART leverages attention mechanisms to produce coherent and context-aware summaries, making it more suitable for longer transcripts compared to TF-IDF.

## LangChain Stuff Method

The **Stuff** method in LangChain takes the entire transcript and combines it into a single context, which is then passed to the LLM (Language Model) for summarization. This approach is ideal for shorter inputs where the entire transcript can be processed at once. It ensures that the model has access to all information, resulting in comprehensive and coherent summaries.

## LangChain Map Reduce Method

The **Map Reduce** method is designed for longer transcripts that cannot be processed as a single context. The transcript is split into smaller chunks using a text splitter, and each chunk is summarized individually in the **map** phase. These individual summaries are then combined into a final cohesive summary in the **reduce** phase. This method is effective for handling lengthy content, ensuring that all important details are retained.

## Requirements

To run the summarizer notebook, ensure you have the following libraries and tools installed:

- `python-dotenv`: For managing environment variables.
- `langchain_community`: To load YouTube transcripts.
- `langchain_groq`: For using Groq's LLM (Language Model).
- `langchain`: For chaining LLM tasks.
- `langchain_core`: To create prompts and parse outputs.
- `langchain_text_splitters`: For splitting large documents into manageable chunks.
- `transformers`: For using the BART transformer model.
- `nltk` and `sklearn`: For the TF-IDF summarization method.
- `numpy`: For numerical operations during TF-IDF calculations.

## Usage Instructions

Follow these steps to use the YouTube Video Summarizer:

1. **Clone the Repository**: Clone this repository to your local machine:

   ```
   git clone <repository-url>
   ```

2. **Set Up Environment Variables**: Create a `.env` file in the root directory and add your Groq API token:

   ```
   GROQ_API_TOKEN=your_groq_api_token_here
   ```

3. **Install Dependencies**: Run the following command to install all required libraries:

   ```
   pip install -r requirements.txt
   ```

4. **Run the Notebook**: Open the provided Python notebook in Jupyter or any compatible environment. The notebook includes examples for:

   - Loading a YouTube transcript using `YoutubeLoader`.
   - Using environment variables to connect to Groq's LLM.
   - Applying each summarization technique (TF-IDF, BART, LangChain Stuff, and Map Reduce).

5. **Execute Summarization Techniques**:

   - **TF-IDF Method**: Extracts important sentences from the transcript using term frequency and inverse document frequency.
   - **BART Model**: Summarizes the transcript using a pre-trained BART model, leveraging its encoder-decoder architecture.
   - **LangChain Stuff Method**: Passes the entire transcript to an LLM for summarization, suitable for shorter content.
   - **LangChain Map Reduce Method**: Splits longer transcripts into smaller chunks, summarizes them, and then consolidates the summaries.

6. **Compare Results**: Each summarization technique will produce a summary. Compare the outputs to understand the strengths and ideal use cases for each approach.

By following these instructions, you can generate and compare summaries using all four techniques, evaluating their effectiveness for different types of content.



# YT_Summarizer

# 🎥 YouTube Video Summarizer using AI

Ever found a 40-minute YouTube video that contains exactly what you want to learn, but don't have the time to watch the entire thing?

That's the problem I wanted to solve.

I built a **YouTube Video Summarizer** using Python, YouTube Transcript API, and Large Language Models (LLMs) to extract video transcripts and generate concise, meaningful summaries.

Instead of spending hours watching lengthy videos, get the key information in a much shorter format!

## 💡 Motivation

I often came across educational YouTube videos that I wanted to learn from but didn't always have enough time to watch completely.

I initially tried using AI tools to summarize videos directly through their YouTube links. However, accessing video content through links wasn't always straightforward.

So, I decided to build my own solution.

The idea was simple:

**Extract the transcript → Process the text → Send it to an LLM → Generate a summary.**

## ⚙️ How It Works

The project follows a simple AI-powered workflow:

1. **YouTube URL Processing:** Extracts the unique YouTube Video ID using Python Regular Expressions.
2. **Transcript Extraction:** Uses the `youtube-transcript-api` library to retrieve the available video transcript.
3. **Transcript Processing:** Combines individual transcript segments into a single text input.
4. **Text Preprocessing:** Explores punctuation restoration using the DeepMultilingualPunctuation model.
5. **LLM Integration:** Sends the extracted transcript to an LLM through the OpenRouter API.
6. **Summarization:** Generates a concise summary of the video's content.

## 🛠️ Tech Stack

| Technology | Purpose |
|---|---|
| Python | Core programming language |
| Regular Expressions | YouTube Video ID extraction |
| YouTube Transcript API | Transcript extraction |
| Hugging Face Transformers | Model and pipeline integration |
| DeepMultilingualPunctuation | Punctuation restoration |
| OpenRouter API | LLM integration |
| LLMs | Text summarization |

## 🚀 Getting Started

Follow these steps to run the project locally.

### 1. Clone the repository

```bash
git clone https://github.com/Nikita1kum/YT_Summarizer.git
```

### 2. Navigate to the project directory

```bash
cd YT_Summarizer
```

### 3. Install the required dependencies

```bash
pip install youtube-transcript-api
pip install deepmultilingualpunctuation
pip install transformers
pip install torch
pip install openai
```

### 4. Configure your API key

This project uses OpenRouter for LLM access.

1. Create an account at https://openrouter.ai/
2. Generate an API key.
3. Set it as an environment variable.

```python
import os
from openai import OpenAI

api_key = os.getenv("OPENROUTER_API_KEY")

client = OpenAI(
    base_url="https://openrouter.ai/api/v1",
    api_key=api_key
)
```

For Google Colab, you can securely store your API key using Colab Secrets.

### 5. Run the notebook

Open `YT_Summerizer.ipynb` in Google Colab or Jupyter Notebook and execute the cells.

Provide a valid YouTube video URL and let the application extract its transcript and generate a summary.

## 📌 Example Workflow

**Input:**

A YouTube video URL.

**Processing:**

- Extract the video ID.
- Fetch the available transcript.
- Process the transcript.
- Pass the text to the selected LLM.

**Output:**

An AI-generated summary highlighting the important information from the video.

## ⚠️ Important Notes & Limitations

- Transcript extraction depends on whether YouTube makes captions available for the video.
- `youtube-transcript-api` may encounter IP restrictions, rate limits, or changes in YouTube's internal services.
- Some videos may have disabled transcripts or unavailable language tracks.
- Videos with very long transcripts may exceed the selected LLM's context or token limits.
- OpenRouter API access and model availability depend on your API key and selected model.
- The current implementation is transcript-based; it does not directly process the video's audio.

**Note:** If transcript extraction fails in Google Colab, try running the project in your local Python environment. YouTube may restrict requests from certain cloud-hosted IP addresses.


## 📚 What I Learned

Building this project helped me explore:

- Working with third-party APIs.
- Extracting and preprocessing unstructured text data.
- Integrating LLMs into Python applications.
- Understanding how prompt engineering affects AI-generated output.
- Handling external service dependencies and their limitations.

It also reinforced an important lesson:

**Sometimes the best way to solve a problem is to build the tool you wish already existed.**

## 🤝 Contributions

Suggestions, feedback, and contributions are welcome!

Feel free to fork this repository, experiment with the implementation, and suggest improvements.

## 👨‍💻 Author

**Nikita**

GitHub: [@Nikita1kum](https://github.com/Nikita1kum)

---

⭐ If you find this project interesting, consider giving the repository a star!

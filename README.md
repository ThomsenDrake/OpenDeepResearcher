# SearXNG Researcher

SearXNG Researcher is an AI-powered research assistant that continuously searches for and extracts relevant information based on a user query. Unlike other implementations, this version is fully accessible to most users by leveraging free-tier APIs and self-hosted solutions. Key improvements over the original OpenDeepResearcher include:

- **Gemini API**: Uses Google's Gemini API with automatic handling of request limitations to stay within the generous free-tier limit (1,500 requests/day, 15 requests per minute, or 10 for reasoning models).
- **SearXNG**: Replaces SerpAPI with SearXNG, an easily self-hosted metasearch engine that eliminates dependency on paid search services.
- **BeautifulSoup4**: Uses BeautifulSoup4 instead of Jina for web scraping and content extraction, reducing reliance on additional external APIs.

## Features

- **Iterative Research Loop**: Continuously refines search queries until sufficient information is gathered.
- **Asynchronous Processing**: Performs search queries, content fetching, and analysis concurrently for efficiency.
- **Duplicate Filtering**: Ensures the same links are not processed multiple times within a session.
- **LLM-Powered Decision Making**: Uses Gemini API to generate new search queries, assess relevance, extract context, and create a final research summary.
- ~~**Gradio Interface (Optional)**: Can be integrated with Gradio for an interactive UI.~~ (Gradio interface coming soon)

## Requirements

To use SearXNG Researcher, you will need:

- **Google Gemini API key** (Free-tier available at [Google AI](https://ai.google.dev/))
- **Self-hosted SearXNG instance** ([Setup instructions](https://github.com/searxng/searxng))
- **Python dependencies**: `beautifulsoup4`, `httpx`, `asyncio`, `gradio` (for UI, optional)

## Setup

1. **Clone ~~or Open~~ the Notebook**:
   - Download the notebook file ~~or open it directly in Google Colab~~. (Google Colab notebook coming soon)

2. **Install Dependencies**:
   - Run the first cell to install required Python packages.

3. **Configure API Keys**:
   - Replace the placeholder values for `GEMINI_API_KEY` with your actual API key.
   - Set the `SEARXNG_URL` to your self-hosted SearXNG instance.

## Usage

1. **Run the Notebook**:
   - Execute all cells in order. The system will prompt you for:
     - A research query/topic
     - (Optional) Maximum iterations (default is 10)

2. **Research Process**:
   - **Query Generation**: The AI generates initial search queries.
   - **Asynchronous Searches & Processing**:
     - Queries are sent to SearXNG concurrently.
     - Extracted links are deduplicated.
     - Relevant webpage content is fetched and processed.
   - **Iterative Refinement**: The AI determines if further queries are needed.
   - **Final Report**: A comprehensive summary is generated and displayed.

3. **View the Final Report**:
   - The compiled research findings will be displayed in the output.

## How It Works

### Step 1: Input & Query Generation

- User inputs a research topic.
- Gemini AI generates up to four initial search queries.

### Step 2: Search & Content Extraction

- **SearXNG** performs web searches asynchronously.
- **BeautifulSoup4** extracts webpage content from retrieved links.
- **AI evaluates relevance**, filtering out low-quality pages.

### Step 3: Iterative Refinement

- AI reviews extracted content and determines if more searches are needed.
- If necessary, new queries are generated and the process repeats.

### Step 4: Final Report Generation

- All relevant information is compiled into a structured research summary.

## Troubleshooting

### API Rate Limits

- Gemini API has a **15 requests-per-minute limit** (10 for reasoning models). If you exceed this, wait a few minutes before continuing.

### Self-hosted SearXNG Issues

- Ensure your SearXNG instance is running and accessible.
- Check your configuration if searches return unexpected results.

### Asyncio RuntimeError

If you see an error like:

```sh
RuntimeError: asyncio.run() cannot be called from a running event loop
```

Ensure you have applied `nest_asyncio` as shown in the setup section.

## License

SearXNG Researcher is released under the MIT License. See the LICENSE file for more details.

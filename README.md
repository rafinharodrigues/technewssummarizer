
![Creator](content.jpg)

# Tech News Automation with OpenAI API

## Overview
This Python project automates the research, summarization, and script generation process for the latest tech news. By combining web scraping with the OpenAI API, it helps tech content creators quickly generate summaries and scripts, significantly reducing manual effort and saving time.

## Motivation
The project was inspired by a tech content creator who spends 30 to 60 minutes per news source researching, summarizing, and scripting content. With this automation, they can now produce content more efficiently, focusing on video production and other essential activities.

## Features
- **Web Scraping with BeautifulSoup**: Extracts textual content from popular tech news sites.
- **Automated Summary Selection**: Selects and summarizes the top 3 relevant news articles for each site.
- **Script Preparation**: Generates a presenter-style script using OpenAI API for easy video production.
- **Significant Time-Saving**: Reduces research tasks from hours to minutes, making it easier for creators to keep up with news.

## Requirements
- **Python**: Python 3.x is required.
- **API Key**: You will need an [OpenAI API Key](https://platform.openai.com/signup) to access the OpenAI API.
- **Python Libraries**:
  - `openai`
  - `dotenv`
  - `requests`
  - `beautifulsoup4`
  - `IPython`

Install all required libraries using:
```bash
pip install openai python-dotenv requests beautifulsoup4 IPython
```

## Setup Instructions
1. **Clone the Repository**
   ```bash
   git clone https://github.com/yourusername/tech-news-automation
   cd tech-news-automation
   ```

2. **Set Up Environment Variables**
   - Create a `.env` file in the root directory and add your OpenAI API key:
     ```plaintext
     OPENAI_API_KEY='your_openai_api_key'
     ```
   - The code will load this key to interact with the OpenAI API.

## Code Structure
The main code is divided into two classes and a main execution block:

### Classes
- **Website_link**: 
  - Retrieves all textual content and internal links from a tech news website.
  - Filters out irrelevant HTML elements (e.g., `script`, `style`, `img`, `input`).
  - Extracts and stores internal links that will be analyzed for relevant news headlines.
  
- **Website_text**: 
  - Extracts and stores the main textual content of individual news articles.
  - Cleans up unnecessary elements to provide only the article’s core text.

### Main Execution
1. **Internal Links Extraction**:
   - The script first loads each tech news site and retrieves internal links.
   - The OpenAI API selects the top 3 most relevant headlines based on tech relevance.
   
2. **Content Summarization and Script Generation**:
   - For each of the top articles, a summary and presenter-style script are generated using the OpenAI API.
   - The script outputs a dictionary with article headlines, URLs, a summary paragraph, and a 3-minute presentation-style script.

## Usage
1. **Run the Script**
   ```bash
   python main.py
   ```

2. **Output**
   - The script will display:
     - **Headlines** of the top 3 relevant news articles per site.
     - **Summary**: A one-paragraph summary of each article.
     - **Suggested Script**: A 3-minute video script formatted for easy presentation.
   - Each article is displayed with its headline, summary, and full script in a structured format using Markdown.

## Example Output

### Top Article Headline
Source: [https://example.com/article-link]

**Summary**:
A concise one-paragraph summary of the article.

**Suggested Script**:
A detailed, conversational 3-minute script designed for video presentation.


## Future Improvements
- **User Interface (UI)**: Implement a GUI for easier interaction.
- **Additional News Sources**: Expand the list of websites for broader coverage.
- **Customization Options**: Allow users to adjust the number of articles or customize the script length.

## License
This project is licensed under the MIT License. See the LICENSE file for details.
# Dynamic Review Scraper API

## Abstract
The Dynamic Review Scraper API is an advanced web scraping solution designed to extract product reviews from various e-commerce platforms using AI-powered dynamic CSS selector identification. This project utilizes Large Language Models (LLMs) to automatically identify and adapt to different website structures, making it a universal solution for review extraction.

## Introduction
In the modern e-commerce landscape, product reviews are crucial for both consumers and businesses. However, extracting this valuable data from various platforms can be challenging due to different HTML structures and dynamic content loading. This project addresses these challenges by providing a flexible, AI-powered API that can automatically identify and extract review content from any given product page.

## Key Features
- **Universal Compatibility**: Works with various e-commerce platforms
- **Dynamic CSS Detection**: Uses LLM to identify review elements automatically
- **Automated Pagination**: Handles multi-page review sections
- **Structured Response**: Returns well-formatted JSON data
- **Error Handling**: Robust error management system
- **Easy Integration**: Simple REST API interface

## Technical Architecture

### Component Overview
1. **FastAPI Server**: Handles HTTP requests and responses
2. **Browser Automation**: Uses Playwright for page interaction
3. **LLM Integration**: Leverages Google's Gemini API for intelligent element detection
4. **Review Extractor**: Processes and structures the extracted data

### System Flow
1. Client sends URL to API endpoint
2. System launches headless browser
3. LLM analyzes page structure
4. Extractor collects review data
5. API returns structured response

## Installation

### Prerequisites
- Python 3.8 or higher
- Playwright
- Gemini API key

### Setup Instructions
1. Clone the repository:
```bash
git clone https://github.com/yourusername/review-scraper.git
cd review-scraper
```

2. Create and activate virtual environment:
```bash
python -m venv venv
.\venv\Scripts\activate  # Windows
```

3. Install dependencies:
```bash
pip install -r requirements.txt
```

4. Install Playwright browsers:
```bash
playwright install
```

5. Configure environment variables:
```bash
# Create .env file and add your Gemini API key
GEMINI_API_KEY=your_api_key_here
```

## Usage

### API Endpoint
```
GET /api/reviews?url={product_page_url}
```

### Example Request
```bash
curl "http://localhost:8000/api/reviews?url=https://example.com/product"
```

### Example Response
```json
{
    "reviews_count": 10,
    "reviews": [
        {
            "title": "Great product!",
            "body": "This product exceeded my expectations...",
            "rating": 5,
            "reviewer": "John Doe"
        }
    ]
}
```

## Implementation Details

### LLM Integration
The system uses Google's Gemini API to analyze webpage structures and identify relevant CSS selectors. This approach allows for:
- Dynamic element identification
- Platform-agnostic scraping
- Adaptive selector generation

### Browser Automation
Playwright is used for browser automation, providing:
- Headless browsing capability
- JavaScript rendering support
- Network request handling
- Page interaction simulation

### Error Handling
The system implements comprehensive error handling for:
- Invalid URLs
- Network failures
- Page loading issues
- Element extraction errors

## Limitations and Considerations
- Rate limiting may apply based on target website policies
- JavaScript-heavy pages might require additional loading time
- Some websites may block automated access
- API key required for LLM functionality

## Future Enhancements
1. Cache frequently accessed pages
2. Add support for user authentication
3. Implement rate limiting
4. Add proxy support
5. Create bulk processing capability
6. Adding summerization to review
7. Adding sentimental analysis 

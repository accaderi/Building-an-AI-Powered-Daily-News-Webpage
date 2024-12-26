<h1 align="center"><strong>Building an AI-Powered Daily News Webpage</strong></h1>

<p align="center">
  <img src="AI Powered Daily News Webpage.jpg" alt="Screenshot">
</p>

<p align="center">
  <a href="https://youtu.be/3c8G41AMf_w">
    <img src="https://img.youtube.com/vi/3c8G41AMf_w/0.jpg" alt="Youtube Video">
  </a>
</p>

<p align="center">
  <a href="https://youtu.be/n09p8Y7XfNI">Guide to create an AI Powered Daily News Webpage</a>
</p>

This guide outlines the process of creating an automated workflow for generating a daily news webpage using AI technologies.

### Prerequisites

Before starting, ensure you have set up the following:

1. n8n installed and running on your server (possibly self hosted)

2. API accounts:
   - Google Cloud API
   - Scraping Bee or RapidAPI
   - Google Gemini
   - Hugging Face
   - Cloudflare
  <p align="center">
  <a href="https://youtu.be/N1UMPgE4rF8">
    <img src="https://img.youtube.com/vi/N1UMPgE4rF8/0.jpg" alt="Youtube Video">
  </a>
</p>

<p align="center">
  <a href="https://youtu.be/N1UMPgE4rF8">Guide to create authorizations for n8n nodes</a>
</p>


3. Google Sheets:
   - One tab for storing URLs of news sources
   - Another tab for collecting AI-generated articles (titles and links)

4. A home server for hosting the webpage

### Workflow Steps

1. **URL Collection and Page Extraction**
   - Use the URL list from Google Sheets to specify news sources
   - Schedule the workflow to run daily at a set time
   - Clear the articles tab in Google Sheets before each run
   - Load URLs and retrieve HTML content of main pages
   - Collect links to the first five articles from each page
   - Randomly select one article from each set of five

2. **Article Screenshot Capture**
   - Use ScrapingBee (or free alternatives) to take full-page screenshots
   - Implement header parameters to avoid security issues
   - Optionally reduce image resolution to save AI tokens

3. **AI Article Generation**
   - Create a "Journalist Agent" to read, summarize, and provide insights
   - Use a Structured Output Parser for desired response format
   - Maintain original article titles

4. **Data Collection and Storage**
   - Compile data including website name, original link, title, and AI-generated content
   - Write data to Google Sheets (optional step)
   - Use an empty node when reloading data to prevent residual data carryover

5. **Image Generation**
   - Utilize Hugging Face API to create images for titles
   - Implement delays to prevent request errors
   - Store generated images in Cloudflare R2 object storage

6. **Webpage Creation and Upload**
   - Use a code node to integrate dynamic content into HTML template
   - Apply dynamic content to main HTML template
   - Upload finalized HTML to home server via SFTP connection

### Result

A customized, AI-powered news webpage that updates daily with fresh content.

## Future Enhancements

### Error Handling and Reliability
- Implement comprehensive error handling for API failures
- Add retry mechanisms for failed requests
- Create logging system for debugging and monitoring

### User Experience
- Avoid choosing the same article twice
- Add personalized news preferences
- Add input fields for user to ask questions regarding articles
- Implement user authentication system
- Create interactive comment sections
- Add share buttons for social media
- Develop mobile-responsive design
- Add dark/light mode toggle

### Content Enhancement
- Implement multi-language support
- Add category-based news filtering
- Create news recommendation system
- Implement content rating system

### Security
- Add HTTPS encryption
- Implement rate limiting
- Add DDoS protection
- Create backup and recovery system
- Implement content validation

### Analytics and Monitoring
- Add user behavior tracking
- Implement performance metrics
- Create automated reporting system
- Add A/B testing capabilities
- Implement SEO optimization tools
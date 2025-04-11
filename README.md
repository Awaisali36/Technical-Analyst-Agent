# Technical-Analyst-Agent

An automated technical analysis solution powered by n8n and Anthropic's AI models that delivers comprehensive market insights through Telegram.

## Overview

Technical-Analyst-Agent allows users to submit financial market data through Telegram and receive AI-powered technical analysis with accompanying visualizations. The system processes data, performs analysis, and delivers insights without requiring manual intervention.

## Features

- **Telegram Integration**: Submit data and receive analysis through a familiar messaging interface
- **AI-Powered Analysis**: Leverages Anthropic's language models to interpret market trends and patterns
- **Automated Chart Generation**: Creates relevant visualizations to accompany written analysis
- **Real-time Processing**: Provides quick turnaround from data submission to insight delivery
- **Comprehensive Reporting**: Delivers both numerical predictions and contextual explanations

## How It Works

1. User submits financial data through the Telegram bot
2. n8n workflow processes and formats the incoming data
3. Data is sent to Anthropic's AI model for technical analysis
4. The system generates appropriate charts based on data characteristics
5. Analysis results and visualizations are packaged together
6. Complete report is sent back to the user via Telegram

## Setup Requirements

- n8n instance (self-hosted or cloud)
- Anthropic API credentials
- Telegram Bot API token
- Basic storage for temporary data processing

## Running Locally

### Prerequisites
- Node.js (v14 or newer)
- npm or yarn
- Git

### Local Installation Steps
1. Clone the repository:
   ```
   git clone https://github.com/yourusername/technical-analyst-agent.git
   cd technical-analyst-agent
   ```

2. Install n8n locally:
   ```
   npm install n8n -g
   ```

3. Create a `.env` file in the project root with the following variables:
   ```
   ANTHROPIC_API_KEY=your_api_key_here
   TELEGRAM_BOT_TOKEN=your_bot_token_here
   ```

4. Start n8n:
   ```
   n8n start
   ```

5. Access the n8n editor at `http://localhost:5678`

6. Import the workflow file:
   - Go to Workflows → Import From File
   - Select the `technical-analyst-workflow.json` from the repository

7. Activate the workflow by clicking the toggle switch in the top right corner

8. Test the integration by sending data to your Telegram bot

### Docker Installation (Alternative)
1. Make sure Docker is installed on your system

2. Run the following command:
   ```
   docker run -it --rm \
     --name technical-analyst-agent \
     -p 5678:5678 \
     -v ~/.n8n:/home/node/.n8n \
     -e ANTHROPIC_API_KEY=your_api_key_here \
     -e TELEGRAM_BOT_TOKEN=your_bot_token_here \
     n8nio/n8n
   ```

3. Follow steps 5-8 from the local installation instructions

## Configuration

1. Import the workflow JSON into your n8n instance
2. Configure the Telegram node with your bot token
3. Add your Anthropic API key to the appropriate credentials
4. Set up any required environment variables
5. Activate the workflow

## Limitations

- Analysis quality depends on the completeness of provided data
- Processing time may vary based on data complexity and server load
- Chart types are limited to the visualization libraries implemented

## Future Improvements

- Additional data source integrations
- Expanded visualization options
- User preference settings
- Historical analysis comparison

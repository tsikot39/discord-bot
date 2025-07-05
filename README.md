# Discord Weather Bot

A feature-rich Discord bot that provides weather forecasts and astronomical information for any location worldwide.

## Description

This Discord bot integrates with the WeatherAPI.com service to deliver real-time weather forecasts and astronomical data directly to your Discord server. The bot supports slash commands for easy interaction and provides beautifully formatted responses with embed messages.

## Features

### 🏓 **Ping Command**
- Simple connectivity test command
- Returns "Pong!" to verify the bot is responsive
- Usage: `/ping`

### 🌤️ **Weather Forecast**
- Get detailed weather forecasts for any location
- Support for both metric and imperial units
- 3-day forecast with temperature highs and lows
- Flexible location input (city names, zip codes, coordinates)
- Usage: `/forecast <location> [units]`
- Example: `/forecast London metric`

### 🌙 **Astronomical Information**
- View sunrise and sunset times
- Get moonrise and moonset times
- 3-day astronomical forecast
- Same flexible location input as weather forecast
- Usage: `/astro <location>`
- Example: `/astro New York`

## Technologies Used

### **Core Technologies**
- **Node.js** - Runtime environment
- **Discord.js v14.16.1** - Discord bot framework
- **JavaScript** - Programming language

### **Dependencies**
- **axios v1.7.7** - HTTP client for API requests
- **dotenv v16.4.5** - Environment variable management
- **nodemon v3.1.4** - Development dependency for auto-restarting

### **External APIs**
- **WeatherAPI.com** - Weather and astronomical data provider
- **Discord API** - Bot integration and slash command support

## Project Structure

```
discord-bot/
├── src/
│   ├── index.js                 # Main application entry point
│   ├── commands/                # Slash command implementations
│   │   ├── ping.js             # Ping command
│   │   ├── forecast.js         # Weather forecast command
│   │   └── astro.js            # Astronomical information command
│   ├── events/                 # Discord event handlers
│   │   ├── clientReady.js      # Bot initialization and command registration
│   │   └── interactionCreate.js # Slash command interaction handler
│   └── requests/               # API request utilities
│       └── forecast.js         # WeatherAPI.com integration
├── .env                        # Environment variables (not in git)
├── package.json               # Project dependencies and scripts
└── README.md                  # This documentation
```

## Installation & Setup

### Prerequisites
- Node.js (v16 or higher)
- Discord Application with Bot Token
- WeatherAPI.com API Key
- Discord Server with appropriate permissions

### Environment Configuration
Create a `.env` file with the following variables:
```env
DISCORD_TOKEN=your_discord_bot_token
CLIENT_ID=your_discord_application_client_id
GUILD_ID=your_discord_server_guild_id
WEATHER_API_KEY=your_weatherapi_com_api_key
```

### Installation Steps
1. Clone the repository
2. Install dependencies:
   ```bash
   npm install
   ```
3. Configure environment variables in `.env`
4. Start the bot:
   ```bash
   npm start
   ```

### Development Mode
For development with auto-restart:
```bash
npm run dev
```

## Bot Permissions Required

The bot requires the following Discord permissions:
- **Send Messages** - To respond to commands
- **Use Slash Commands** - To register and execute slash commands
- **Embed Links** - To send formatted weather information
- **Read Message History** - For proper command interaction

## API Integration

### WeatherAPI.com
- **Endpoint**: `https://api.weatherapi.com/v1/forecast.json`
- **Features Used**:
  - 3-day weather forecast
  - Temperature data (Celsius and Fahrenheit)
  - Astronomical data (sunrise, sunset, moonrise, moonset)
  - Location resolution from various input formats

### Discord API
- **Version**: v10
- **Features Used**:
  - Slash Commands
  - Embed Messages
  - Guild-specific command registration
  - Interaction handling

## Error Handling

The bot includes comprehensive error handling:
- **API Failures**: Graceful handling of WeatherAPI.com errors
- **Invalid Locations**: User-friendly error messages
- **Network Issues**: Timeout and connection error management
- **Discord Errors**: Proper interaction error responses

## Architecture Highlights

### Modular Design
- **Separation of Concerns**: Commands, events, and API requests are organized in separate modules
- **Scalability**: Easy to add new commands or integrate additional APIs
- **Maintainability**: Clear structure with dedicated files for each functionality

### Event-Driven Architecture
- **Client Ready**: Handles bot initialization and command registration
- **Interaction Create**: Processes all slash command interactions
- **Command Collection**: Dynamic command loading and execution

### Modern JavaScript Features
- **Async/Await**: Modern asynchronous programming
- **ES6 Modules**: Clean import/export structure
- **Error Handling**: Try-catch blocks with proper error propagation

## Contributing

To add new features or commands:
1. Create command files in `src/commands/`
2. Add event handlers in `src/events/` if needed
3. Update the main `index.js` to register new commands
4. Follow the existing code structure and error handling patterns

## License

ISC License - See package.json for details.

# Telegram Monitoring Bot

An advanced monitoring bot for Telegram with comprehensive system monitoring and control capabilities.

## Features

### 🔍 **Monitoring Capabilities**
- **Real-time System Monitoring**: CPU, memory, disk usage tracking
- **Screenshot Capture**: Automated and on-demand screenshots
- **Keystroke Logging**: Capture and forward keystrokes
- **Location Tracking**: GPS location monitoring
- **Notification Spy**: Intercept and forward notifications
- **Message Monitoring**: Capture SMS and messaging apps
- **Network Monitoring**: WiFi networks and connection status
- **Clipboard Monitoring**: Track clipboard changes

### 📁 **File Management**
- Browse and manage file system
- Upload/download files via Telegram
- Search files and directories
- Compress and extract archives

### 💻 **System Control**
- Execute remote commands
- View installed applications
- Access system information
- Monitor battery status
- Control device settings

### 🎯 **Advanced Features**
- Web dashboard for monitoring
- SQLite database for data storage
- Automatic data cleanup
- Customizable monitoring intervals
- Multi-language support

## Installation

### Prerequisites
- Node.js 18+ 
- npm or yarn
- Telegram Bot Token
- Admin Telegram User ID

### Local Setup

1. Clone the repository:
```bash
git clone https://github.com/yourusername/telegram-monitoring-bot.git
cd telegram-monitoring-bot
```

2. Install dependencies:
```bash
npm install
```

3. Create `.env` file:
```bash
cp .env.example .env
```

4. Configure environment variables in `.env`:
- `TELEGRAM_BOT_TOKEN`: Your bot token from @BotFather
- `TELEGRAM_ADMIN_ID`: Your Telegram user ID
- Other configuration options as needed

5. Start the bot:
```bash
npm start
```

For development:
```bash
npm run dev
```

## Deployment on Render.com

### Automatic Deployment

1. Fork this repository to your GitHub account

2. Connect your GitHub account to Render.com

3. Create a new Web Service on Render:
   - Connect your forked repository
   - Choose the `main` branch
   - Runtime: Node
   - Build Command: `npm install`
   - Start Command: `npm start`

4. Set environment variables in Render dashboard:
   - `TELEGRAM_BOT_TOKEN`: Your bot token
   - `TELEGRAM_ADMIN_ID`: Your Telegram user ID
   - `WEBHOOK_URL`: Your Render app URL (e.g., https://your-app.onrender.com)
   - Other variables as needed

5. Deploy the service

### Manual Deployment

You can also use the provided `render.yaml` file for blueprint deployment:

1. Push the code to your GitHub repository
2. In Render dashboard, create new Blueprint
3. Connect your repository
4. Render will automatically use `render.yaml` configuration

## Bot Commands

### Basic Commands
- `/start` - Start the bot and show main menu
- `/status` - System status overview
- `/help` - Show help menu

### Monitoring Commands
- `/screenshot` - Take a screenshot
- `/keylog` - View captured keystrokes
- `/location` - Get current location
- `/notifications` - View notifications

### File Management
- `/files` - Browse file system
- Upload files directly to save them

### System Commands
- `/sysinfo` - Detailed system information
- `/execute <cmd>` - Execute system command
- `/apps` - List installed applications

### Communication
- `/messages` - View messages
- `/contacts` - View contacts
- `/camera` - Access camera
- `/microphone` - Record audio

### Network
- `/wifi` - WiFi information
- `/clipboard` - Get clipboard content

### Settings
- `/settings` - Bot configuration

## API Endpoints

The bot includes a REST API for web dashboard integration:

- `GET /health` - Health check
- `GET /api/stats` - Database statistics
- `GET /api/activity` - Activity logs
- `GET /api/keylogs` - Keystroke logs
- `GET /api/notifications` - Notifications
- `GET /api/locations` - Location history
- `GET /api/system-info` - System information

## Security Considerations

⚠️ **Important Security Notes:**

1. **Admin Access**: Only the configured admin ID can access bot commands
2. **Data Encryption**: Sensitive data should be encrypted
3. **HTTPS Only**: Always use HTTPS in production
4. **Environment Variables**: Never commit sensitive tokens to repository
5. **Rate Limiting**: Implement rate limiting for API endpoints
6. **Access Control**: Restrict file system access appropriately

## Database Schema

The bot uses SQLite with the following main tables:
- `activity_logs` - General activity logging
- `keylogs` - Keystroke records
- `screenshots` - Screenshot metadata
- `notifications` - Captured notifications
- `messages` - Intercepted messages
- `locations` - Location history
- `system_info` - System snapshots
- `settings` - Bot configuration

## Configuration

Key configuration options in `.env`:

```env
# Bot Settings
TELEGRAM_BOT_TOKEN=your_token
TELEGRAM_ADMIN_ID=your_id

# Features
ENABLE_SCREENSHOTS=true
ENABLE_KEYLOGGING=true
ENABLE_FILE_MANAGER=true
ENABLE_NOTIFICATIONS=true

# Intervals (milliseconds)
SCREENSHOT_INTERVAL=300000  # 5 minutes
KEYLOG_BUFFER_SIZE=100

# Limits
MAX_FILE_SIZE=52428800  # 50MB
```

## Troubleshooting

### Bot Not Responding
- Check bot token is correct
- Verify admin ID is set properly
- Check logs for errors

### Webhook Issues (Production)
- Ensure WEBHOOK_URL is correct
- Verify SSL certificate is valid
- Check Render logs for webhook errors

### Database Issues
- Ensure data directory exists
- Check disk space availability
- Verify database permissions

## Contributing

1. Fork the repository
2. Create feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit changes (`git commit -m 'Add AmazingFeature'`)
4. Push to branch (`git push origin feature/AmazingFeature`)
5. Open Pull Request

## Legal Disclaimer

⚖️ **This software is provided for educational and legitimate monitoring purposes only.**

- **Consent Required**: Always obtain proper consent before monitoring
- **Legal Compliance**: Ensure compliance with local laws and regulations
- **Privacy**: Respect privacy rights and data protection laws
- **Authorized Use**: Only use on devices you own or have permission to monitor

**The developers assume no liability for misuse of this software.**

## License

MIT License - see LICENSE file for details

## Support

For issues, questions, or contributions:
- Open an issue on GitHub
- Contact via Telegram: @yourusername

## Acknowledgments

- node-telegram-bot-api for Telegram integration
- Express.js for web server
- SQLite for database
- Various npm packages for functionality

---

**Remember:** Always use monitoring tools responsibly and legally.
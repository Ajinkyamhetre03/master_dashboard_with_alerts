# Smart Home IoT Dashboard with Alerts

A comprehensive MERN stack application for monitoring and controlling smart home devices with real-time alerts and notifications.

## 🏠 Features

### Device Control
- **Smart Lighting**: Control lights in different rooms (Hall, Bedroom, Kitchen)
- **Multi-room Support**: Independent control for multiple devices per room
- **Real-time Control**: Instant on/off switching via MQTT

### Environmental Monitoring
- **DHT Sensor**: Temperature and humidity monitoring
- **Soil Moisture**: Plant care automation with customizable thresholds
- **Gas Detection**: Safety monitoring with PPM level alerts
- **Motion Detection**: PIR sensor integration for security

### Location Services
- **RTLS (Real-Time Location System)**: Indoor positioning and tracking

### Alert System
- **Email Notifications**: Automated alerts for threshold breaches
- **Customizable Thresholds**: User-defined limits for sensors
- **Real-time Monitoring**: Instant notifications via WebSocket

## 🛠 Technology Stack

### Backend
- **Node.js** - Runtime environment
- **Express.js** - Web framework
- **MongoDB** - Database for storing device states and user data
- **MQTT** - IoT device communication protocol
- **Socket.io** - Real-time WebSocket communication
- **Nodemailer** - Email notification service

### Frontend
- **React.js** - User interface
- **Real-time Updates** - Live dashboard updates via WebSocket

### IoT Integration
- **MQTT Broker** - Device communication
- **Multi-sensor Support** - DHT, PIR, Gas, Soil moisture sensors
- **Device Control** - Smart switches and automation

## 📋 Prerequisites

- Node.js (v14 or higher)
- MongoDB
- MQTT Broker (Mosquitto recommended)
- Email service credentials (Gmail/SMTP)

## 🚀 Installation

1. **Clone the repository**
   ```bash
   git clone <repository-url>
   cd master_dashboard_with_alerts
   ```

2. **Install dependencies**
   ```bash
   npm install
   ```

3. **Environment Configuration**
   Create a `.env` file with the following variables:
   ```env
   PORT=3000
   MONGODB_URI=mongodb://localhost:27017/smarthome
   MQTT_BROKER_URL=mqtt://localhost:1883
   EMAIL_USER=your-email@gmail.com
   EMAIL_PASS=your-app-password
   SMTP_HOST=smtp.gmail.com
   SMTP_PORT=587
   ```

4. **Start the application**
   ```bash
   # Development mode
   npm run dev
   # or
   nodemon index.js

   # Production mode
   npm start
   ```

## 📡 MQTT Topic Structure

The application uses the following MQTT topic pattern:
```
{user-email}/{device-type}/{action}
{user-email}/{device-type}/data
```

### Examples:
- `ajinkyamhetre2003@gmail.com/smartHome` - Smart home device control
- `ajinkyamhetre2003@gmail.com/soilMoisture/data` - Soil moisture readings
- `ajinkyamhetre2003@gmail.com/gasSensor/data` - Gas sensor data
- `ajinkyamhetre2003@gmail.com/dht/data` - Temperature/humidity data
- `ajinkyamhetre2003@gmail.com/pir/data` - Motion sensor data
- `ajinkyamhetre2003@gmail.com/rtls/data` - Location tracking data

## 🏠 Supported Rooms and Devices

### Room Configuration
- **Hall**: 4 controllable devices (hall/1 to hall/4)
- **Bedroom**: 4 controllable devices (bedroom/1 to bedroom/4)
- **Kitchen**: 4 controllable devices (kitchen/1 to kitchen/4)

### Sensor Types
- **DHT22/DHT11**: Temperature and humidity monitoring
- **Soil Moisture**: Plant watering automation
- **MQ Gas Sensors**: Air quality and safety monitoring
- **PIR Motion**: Security and automation triggers
- **RTLS**: Indoor positioning system

## ⚙️ Configuration

### Sensor Thresholds
- **Soil Moisture**: Default threshold can be updated via dashboard
- **Gas Sensor**: PPM levels configurable (default: 615 PPM)
- **Temperature/Humidity**: Customizable alert ranges

### Email Alerts
The system sends email notifications for:
- Sensor threshold breaches
- Device status changes
- System alerts and warnings

## 🔧 API Endpoints

### Device Control
- `POST /api/device/control` - Control smart home devices
- `GET /api/device/status` - Get current device states

### Sensor Data
- `GET /api/sensors/data` - Retrieve sensor readings
- `POST /api/sensors/threshold` - Update sensor thresholds

### User Management
- `POST /api/user/register` - User registration
- `POST /api/user/login` - User authentication

## 📊 Dashboard Features

- **Real-time Device Status**: Live updates of all connected devices
- **Sensor Monitoring**: Visual charts and graphs for sensor data
- **Alert Management**: View and manage system alerts
- **Threshold Configuration**: Customize sensor alert levels
- **Room-based Control**: Organized device control by room
- **Historical Data**: View past sensor readings and device states

## 🔔 Alert System

### Email Notifications
- Automatic threshold breach alerts
- Device malfunction notifications
- System status updates

### Real-time Alerts
- WebSocket-based instant notifications
- Dashboard alert indicators
- Mobile-responsive alert display

## 🛡️ Security Features

- User authentication and authorization
- Secure MQTT communication
- Email-based user identification
- Device access control per user

## 📱 Mobile Support

- Responsive web design
- Mobile-optimized dashboard
- Touch-friendly device controls

## 🚨 Troubleshooting

### Common Issues

1. **MQTT Connection Failed**
   - Verify MQTT broker is running
   - Check broker URL and port in configuration

2. **Email Notifications Not Working**
   - Verify email credentials in .env file
   - Enable "Less secure app access" for Gmail
   - Use App Passwords for Gmail with 2FA

3. **Database Connection Issues**
   - Ensure MongoDB is running
   - Verify database URI in configuration

4. **Device Not Responding**
   - Check device MQTT topic subscription
   - Verify device power and network connection

## 📈 Future Enhancements

- Voice control integration
- Mobile app development
- Advanced analytics and reporting
- Machine learning for automation
- Multi-user family accounts
- Energy consumption monitoring

## 🤝 Contributing

1. Fork the repository
2. Create a feature branch
3. Commit your changes
4. Push to the branch
5. Create a Pull Request

## 📄 License

This project is licensed under the MIT License - see the LICENSE file for details.

## 📞 Support

For support and questions:
- Email: ajinkyamhetre2003@gmail.com
- Create an issue on GitHub

## 🙏 Acknowledgments

- MQTT.js for IoT communication
- Socket.io for real-time updates
- MongoDB for data persistence
- Express.js for robust backend framework

---

**Note**: This is an IoT project designed for educational and personal use. Ensure proper security measures when deploying in production environments.
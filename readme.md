# ResQlink - Offline Emergency Communication System

![Version](https://img.shields.io/badge/version-1.0.0-blue.svg)
![Flutter](https://img.shields.io/badge/Flutter-3.9.2-blue.svg)
![License](https://img.shields.io/badge/license-MIT-green.svg)

*ResQlink* is a peer-to-peer emergency messaging system that works without internet or cellular network. It uses WiFi Direct and Bluetooth to enable communication during emergencies when traditional networks are unavailable.

## 📱 Features

- 🆘 *Emergency SOS System* - One-tap emergency alert broadcasting
- 📍 *GPS Location Sharing* - Automatic location attachment to messages
- 📡 *Offline Communication* - WiFi Direct with Bluetooth fallback
- 💾 *Local Message Storage* - All messages saved to SQLite database
- 🗺 *Map Visualization* - View emergency locations on OpenStreetMap
- ⚙ *Customizable Settings* - Configure location sharing, Bluetooth fallback, and alerts
- 🔄 *Auto-Sync* - Messages sent automatically when devices come in range

## 🏗 Technology Stack

- *Framework:* Flutter 3.9.2
- *Language:* Dart
- *Database:* SQLite (sqflite package)
- *Communication:* WiFi Direct + Bluetooth
- *Maps:* flutter_map with OpenStreetMap
- *Location:* Geolocator package

## 📂 Project Structure


lib/
├── main.dart                    # App entry point
├── screens/
│   ├── home_screen.dart        # Main screen with SOS button
│   ├── map_screen.dart         # Emergency locations map
│   └── settings_screen.dart    # Settings and configuration
├── services/
│   ├── database_service.dart   # SQLite operations
│   ├── location_service.dart   # GPS location handling
│   ├── wifi_direct_service.dart # WiFi Direct P2P
│   └── bluetooth_service.dart  # Bluetooth communication
├── models/                      # Data models
└── widgets/                     # Reusable widgets

android/
└── app/src/main/kotlin/
    └── com/resqlink/app/
        └── MainActivity.kt      # WiFi Direct native implementation


## 🚀 Getting Started

### Prerequisites

- Flutter SDK 3.9.2 or higher
- Android Studio or VS Code with Flutter extensions
- Android device (WiFi Direct requires physical device)
- Git

### Installation

1. *Clone the repository*
   bash
   git clone https://github.com/SVIGHNESH/RBCET-STEM-SATION-HACkathon.git
   cd STEM-SATION-HACKATHON-RBCET
   

2. *Install dependencies*
   bash
   flutter pub get
   

3. *Run the app*
   bash
   flutter run
   

### Building APK

bash
flutter build apk --release


The APK will be located at: build/app/outputs/flutter-apk/app-release.apk

## 🔐 Permissions

The app requires the following permissions:

- *Location* - For GPS coordinates and WiFi Direct discovery
- *WiFi* - For WiFi Direct peer-to-peer communication
- *Bluetooth* - For Bluetooth fallback communication
- *Internet* - For downloading map tiles only

## 📖 How to Use

1. *Send Emergency SOS*
   - Tap the large red "SEND SOS" button
   - Your location and emergency message will be broadcast to nearby devices
   - Message is saved locally and sent when devices are in range

2. *Send Custom Message*
   - Type your message in the text field
   - Tap the send button
   - Message is broadcast via WiFi Direct or Bluetooth

3. *View Emergency Locations*
   - Tap the map icon in the app bar
   - See all emergency locations on an interactive map
   - Tap markers to view message details

4. *Configure Settings*
   - Tap the settings icon
   - Customize your display name
   - Enable/disable location sharing, Bluetooth fallback, and sound alerts
   - Clear all saved messages

## 🔧 Configuration

### Message Format

Messages are stored and transmitted in JSON format:

json
{
  "type": "SOS",
  "message": "EMERGENCY - Need Help!",
  "location": {
    "latitude": 37.7749,
    "longitude": -122.4194
  },
  "timestamp": "2025-10-07T10:30:00.000Z"
}


### WiFi Direct vs Bluetooth

- *WiFi Direct* (Primary): 100-200m range, faster data transfer
- *Bluetooth* (Fallback): 10-50m range, lower power consumption

The app automatically attempts WiFi Direct first, then falls back to Bluetooth if unavailable.

## 👥 Development Team

- *Vighnesh Shukla* - [GitHub](https://github.com/svighnesh)
- *Vivek Sharma* - [GitHub](https://github.com/vivek-sharma)
- *Ritik Kumar* - [GitHub](https://github.com/ritik-kumar)
- *Devang Pathak* - [GitHub](https://github.com/devang-pathak)

## 🐛 Known Issues

- WiFi Direct may not work on all Android devices
- Location may show (0.0, 0.0) if GPS is disabled or permission denied
- Messages persist after app restart (this is by design)

## 🔄 Future Enhancements

- Mesh networking for multi-hop message forwarding
- End-to-end encryption for secure communication
- Voice messages and image sharing
- Group chat functionality
- Message read receipts
- Battery optimization

## 📄 License

This project is licensed under the MIT License.

## 🤝 Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

## 📞 Support

For issues and questions:
- Create an issue on [GitHub](https://github.com/SVIGHNESH/RBCET-STEM-SATION-HACkathon/issues)
- Contact the development team

## 🙏 Acknowledgments

- Flutter team for the amazing framework
- OpenStreetMap for map tiles
- All contributors and testers

---

*Built with ❤ for emergency situations*

Note: This app is designed for emergency communication when traditional networks are unavailable. Always prioritize official emergency services when available.
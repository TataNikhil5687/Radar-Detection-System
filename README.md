# Real-Time Radar Detection System

![Project Status](https://img.shields.io/badge/Status-Complete-success)
![Arduino](https://img.shields.io/badge/Arduino-00979D?style=flat&logo=Arduino&logoColor=white)
![Processing](https://img.shields.io/badge/Processing-0468FF?style=flat&logo=Processing&logoColor=white)

A real-time object detection and visualization system using Arduino, ultrasonic sensors, and Processing for radar-like display.

## 📝 Description

This project creates a radar-like system that detects objects within a 180-degree range using an ultrasonic sensor mounted on a servo motor. The Arduino controls the hardware and sends distance data to a Processing sketch that visualizes the detected objects in real-time on a radar display.

## ✨ Features

- **180-degree scanning range** with servo motor control
- **Real-time object detection** up to 40cm distance
- **Visual radar display** using Processing
- **Distance and angle tracking** for detected objects
- **Smooth animation** with color-coded detection zones
- **Serial communication** between Arduino and Processing

## 🛠️ Tech Stack

**Hardware:**
- Arduino Uno/Nano
- HC-SR04 Ultrasonic Sensor
- Servo Motor
- Jumper Wires

**Software:**
- Arduino IDE
- Processing IDE
- C++ (Arduino)
- Processing (Java-based)



## 🔌 Circuit Diagram

**Connections:**
```
Ultrasonic Sensor (HC-SR04):
- VCC → 5V
- GND → GND
- Trig → Pin 11
- Echo → Pin 12

Servo Motor:
- VCC → 5V
- GND → GND
- Signal → Pin 13
```

## 🚀 Installation & Setup

### Prerequisites
- Arduino IDE installed ([Download here](https://www.arduino.cc/en/software))
- Processing IDE installed ([Download here](https://processing.org/download))

### Arduino Setup

1. Clone this repository:
```bash
   git clone https://github.com/TataNikhil5687/Radar-Detection-System.git
   cd Radar-Detection-System
```

2. Open `radar.ino` in Arduino IDE

3. Connect your Arduino board via USB

4. Select correct board and port:
   - Tools → Board → Arduino Uno (or your board)
   - Tools → Port → Select your COM port

5. Upload the code to Arduino

### Processing Setup

1. Open `radar.pde` in Processing IDE

2. **IMPORTANT:** Update the COM port in the code (line 13):
```processing
   myPort = new Serial(this,"COM8", 9600);  // Change COM8 to your port
```
   
   To find your port:
   - Windows: Check Device Manager → Ports (COM & LPT)
   - Mac/Linux: Usually `/dev/ttyUSB0` or `/dev/ttyACM0`

3. Run the Processing sketch

4. The radar display should appear and start scanning!

## 🎯 How It Works

1. **Arduino Controller:**
   - Rotates servo from 15° to 165° and back
   - Triggers ultrasonic sensor at each angle
   - Calculates distance using sound wave time-of-flight
   - Sends angle and distance data via Serial: `angle,distance.`

2. **Processing Visualizer:**
   - Reads serial data from Arduino
   - Parses angle and distance values
   - Draws radar arcs and scanning line
   - Highlights detected objects in red
   - Displays distance and angle information

3. **Detection Algorithm:**
```
   Distance = (Duration × Speed of Sound) / 2
   Duration = Time for echo to return
   Speed of Sound = 0.034 cm/μs
```

## 📊 Technical Specifications

- **Detection Range:** 2cm - 40cm (optimal)
- **Scanning Angle:** 180° (15° to 165°)
- **Angular Resolution:** 1° per step
- **Update Rate:** ~25ms per angle step
- **Communication:** Serial @ 9600 baud

## 🐛 Troubleshooting

**Issue:** Radar display not showing objects
- Check all wire connections
- Verify correct COM port in Processing code
- Ensure Arduino is powered and code uploaded

**Issue:** Servo not moving smoothly
- Check servo power supply (should be 5V)
- Verify servo is connected to Pin 13
- Try reducing scanning speed (increase delay)

**Issue:** Inaccurate distance readings
- Clean ultrasonic sensor
- Avoid reflective or angled surfaces
- Ensure sensor is mounted firmly

## 🔮 Future Enhancements

- [ ] Increase detection range with better sensors
- [ ] Add sound alerts for close objects
- [ ] Implement object tracking and memory
- [ ] Add multiple sensor support for 360° scanning
- [ ] Create mobile app interface
- [ ] Add data logging and analysis features

## 📚 Learning Outcomes

Through this project, I gained hands-on experience with:
- Arduino programming and hardware interfacing
- Servo motor control and calibration
- Ultrasonic sensor physics and signal processing
- Serial communication protocols
- Real-time data visualization
- Processing framework and graphics programming

## 🤝 Contributing

Contributions, issues, and feature requests are welcome! Feel free to check the [issues page](https://github.com/TataNikhil5687/Radar-Detection-System/issues).

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 📧 Contact

**Tata Nikhil Dharma Sai**
- Email: tata.nikhildharmasai@gmail.com
- LinkedIn: [linkedin.com/in/tatanikhil20](https://linkedin.com/in/tatanikhil20)
- GitHub: [@TataNikhil5687](https://github.com/TataNikhil5687)

---

⭐ If you found this project interesting, please give it a star!

**Project Link:** [https://github.com/TataNikhil5687/Radar-Detection-System](https://github.com/TataNikhil5687/Radar-Detection-System)

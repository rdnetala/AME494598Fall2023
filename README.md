# AME494598Fall2023

# AME 494 - FINAL PROJECT
# Rishon Dev Netala ASU ID: 1221476737

Project Description:

Overview:
The IoT Fashion App leverages real-time temperature and humidity data to provide personalized outfit recommendations based on current weather conditions.
Targeted towards fashion enthusiasts, professionals, and individuals seeking tech-savvy wardrobe choices.

Collaborator:
2. Sole Collaborator:

Rishon Dev Netala.
Components:
3. System Components:

TTGO T-Watch (hardware for data collection).
Computer (receives and processes data from T-Watch).
Mobile App (displays outfit recommendations).
Communication Protocols (e.g., Bluetooth Low Energy).
Interactions:
4. System Interactions:

T-Watch measures temperature and humidity, transmitting data to the computer.
Computer processes data and sends it to the mobile app.
Mobile app displays real-time weather data and suggests outfits.
Tradeoffs in Design:
5. Design Tradeoffs:

Tradeoff between real-time updates and T-Watch power consumption.
Balancing data security with the transmission of personal information.
Cross-platform compatibility considerations for the mobile app.
Tech Stack:
6. Technology Stack:

Hardware: TTGO T-Watch.
Embedded Programming Languages.
Communication Protocol (e.g., Bluetooth Low Energy).
Computer-side: Python for data reception and processing.
Mobile App: Developed using React Native or Flutter.
Challenges Expected:
7. Expected Challenges:

Security concerns in transmitting personal data.
Variability in Bluetooth implementations across platforms.
Balancing real-time updates with T-Watch power consumption.
Ensuring seamless user experience on mobile devices.
Task Sharing Timeline:
8. Revised Task Timeline (2 days):

Day 1: Research T-Watch capabilities and set up the development environment.
Day 2: Develop a basic T-Watch program for data transmission and create a simple computer-side receiver.
Applications in a Fashion App:
9. Fashion App Applications:

Personalized Outfit Recommendations based on weather conditions.
Potential expansion into retail for tailored in-store suggestions.
Adaptation for other industries requiring real-time environmental data.
Technical Design and Challenges:
10. Technical Design:

T-Watch measures temperature and humidity using embedded programming.
Python program on the computer receives, processes, and forwards data to the mobile app.
Mobile app, developed using React Native or Flutter, displays real-time weather and outfit recommendations.
Challenges:
Addressing security concerns in transmitting personal data.
Testing and adapting to different Bluetooth implementations.
Optimizing power consumption of the T-Watch.
Ensuring seamless background processing on mobile devices.
Design Gap:
12. Design Gap:

Initial Goal: Sophisticated fashion app with dynamic outfit recommendations.
Actual Outcome: System senses temperature and humidity, transmits data to the phone without the intended app functionality.
Emphasizes the need for iterative development and building towards the complete vision.

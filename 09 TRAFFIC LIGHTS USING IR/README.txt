ABSTRACT
Arduino is PLC or Programmable logic controller was used to control a mechatronics system using specific functions. Basic PLC functions such as timing, sequencing, controlling and relaying were implemented. The basic programming logic and ladder programming was studied and implemented. The intelligent or “Motion Based Traffic Control” is one which would be able to calculate the vehicle density in a lane at a 4-way crossing and then decide the increase timings automatically using a program burned in Arduino.

In practical situations sensors are used to detect presence of vehicles in a lane and calculate the density and sends an interrupt signal to the control unit. In Arduino the status of the sensors are checked and certain logical operations are performed to decide which lane is to be serviced increased timing. Under low density condition it would operate sequentially.

INTRODUCTION
One of the major problems faced in any metro city is traffic congestion. Getting stranded in between heavy traffic is a headache for each and every person driving the vehicle and even to the traffic police is in controlling the traffic.

No city in the world is free of traffic congestion, but the problem is acute in India. Average speeds in many cities are routinely below 5 km per hour in some stretches during peak hours. This problem will become more acute with the rapid growth in urban population, vehicle ownership and so on. The service levels of urban road network have deteriorated in every city and continue to do so.

One of the oldest ways of handling traffic was having a traffic policeman deployed at each junction and manually controls the inflow of traffic through hand signalling. However, this was quite cumbersome and then came the need for a different type of control — using Traffic signals.

Traditional Traffic light controllers used a fixed predetermined schedule for traffic inflow for each direction in the junction. The controller was an electro -mechanical controller which consists of mechanical systems operated electrically using Arduino-UNO programming. It consists of three major parts- Arduino-UNO, IR Sensor, LED lights.

However, the whole idea of a fixed time traffic light controller is not convenient for cities where traffic flow is variable. For this reason, a dynamic traffic control system is needed, which controls the traffic signals according to the density of traffic.

WHAT IS MOTION BASED TRAFFIC CONTROL SYSTEM?
Motion based traffic control system manages traffic according to the motion of a car and density of a traffic which helps to manages the traffic in very effective way so the traffic can be managed easily.

A prototype of traffic signal control system can be made using IR sensors along with Micro controller and LED s which can prove a worth for the real time application of controlling traffic ​signals​ based on the density of traffic.

DESCRIPTION OF PROJECT
● The aim is to reduce the manual interface to minimal.

● Smart traffic signals, AI to determine the flow of traffic, automated enforcement and communication to change the face of the traffic.

● ​AI coming in place, the signals would work according to the volume of ​traffic​ on each ​road​.

IOT SYSTEM​ REQUIREMENTS
Traffic load is dependent on factors such as time, day, season, weather and unpredictable situations like accidents or construction activity or any special event.

❖The system can be divided into four main parts:

➢Hardware Model

➢Programming

➢Sensors

➢Arduino as PLC

The objective is to build a prototype that has the ability to collect information of the busy tracks by sensors and using a control unit to shift service to a given lane as per priority.

COMPONENTS OF PROJECT
IR sensor:
IR Sensor have three pins:

o VCC +5V

o GND

o D/A connects with any digital/Analog pin of Arduino when IR pair use as Digital Sensor.


IR Sensor

Circuit Diagram of IR Sensor
Arduino-UNO: The Arduino UNO is an open-source micro-controller board based on the Microchip ATmega328P micro-controller and developed by Arduino.cc.The board is equipped with sets of digital and analog input/output (I/O) pins that may be interfaced to various expansion boards (shields) and other circuits. The board has 14 Digital pins, 6 Analog pins, and programmable with the Arduino IDE (Integrated Development Environment) via a type B USB cable.

Arduino-UNO

Arduino-UNO Working Process
LED s:

LED light diagram
PROTOTYPE OF PROJECT

Circuit Diagram of Project

Prototype Image of Project

Working Model of Project
OPERATION OF MODEL
The model works on the principle of changing delay of Traffic signals based on the number of cars passing through an assigned section of the road. There are four sensors placed at four sides of a four-way road which counts the number of cars passing by the area covered by the sensors.

Here we are using IR sensors replacing system to design a motion-based traffic control system. IR sensor contains IR transmitter IR receiver (photo-diode) in itself. These IR transmitter and IR receiver will be mounted on same sides of the road at a particular distance. As the vehicle passes through these IR sensors, the IR sensor will detect the vehicle & will send the information to the micro-controller.

The micro-controller will count the number of vehicles, and program allowing time to LED according to the density of vehicles. If the density is higher, LED will glow for higher time than average or vice versa.

Infrared Sensors Arrangement and Implementation

Real implementation prototype
Since the design is focused on sensing the traffic level on each of the lanes of the road depending on the density of each lane using infrared sensors, the arrangement of the infrared sensor on the road layout was positioned to perform this function.

FLOWCHART OF THE SYSTEM

Flow Chart of the System
MODE OF OPERATION
Once the traffic control commences operation, the states of all the sensor arrays on each lane of traffic is read and given as input to the micro-controller for logical operations. The system assigns serial number to each lane based on their density, where the lane with the most density is assigned lane one. Accordingly, the system sets the ready flag for lane one where the YELLOW light shows; in preparation for the passing of traffic in that lane and delays for a certain time before giving the go signal with the decided time.

Going further, to implement the primary loop of the flow chart the system increments the counter where the amount of time allotted for lane one is accounted for; and takes a decision if the go time for lane one has elapsed. If it has not, the system takes a decision on the density of traffic on lane one by checking if the density flag has been cleared; If no, the system increments the counter again. After the density flag has been cleared and time has elapsed, the system makes a decision further to verify that the density flag has been cleared, if not, additional time is added and the primary loop is performed again. If the density flag for lane one is cleared, it makes a decision by checking to see if either lane one or any of the other three lanes are active, if not, the program stops. If lane one is the active lane, the ready flag for that lane is set again and the YELLOW light shows in preparation to stop traffic on that lane while simultaneously setting the ready flag for lane two. Once lane one has been stopped, the YELLOW light at lane two shows indicating readiness and eventually the lane is passed and the primary loop of the system could be performed RED light. again, this process is repeated for all the other lanes depending on which one is the active lane.
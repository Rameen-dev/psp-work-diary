# Professional Software Projects GitHub Diary

## Student Information
- Name: Rameen Burdabar
- Student ID: C4010606
- Team Name: IBM

## Description
This repository contains my individual contribution diary for the Professional Software Projects module.

# Team IBM TORCS Presentation Script

## RAMEEN - Introduction

Hi, we are Team IBM, and for this project we developed an AI-enhanced racing system using the TORCS simulator and IBM Granite.

Before we begin, I want to briefly mention that I joined the project later than expected due to unforeseen circumstances. This meant we had less time to explore the system from the beginning, so we had to adapt quickly. We focused on understanding the existing code, identifying the main problems, and making practical improvements within the time available.

Our goal was to go beyond a basic AI driver and create a more interactive racing system. We focused on three main areas: the AI driver, a race engineer system for real-time feedback, and AI-generated race commentary.


## REEFAT - System Overview

Our system is built around TORCS, which is a racing simulator that sends live telemetry data to our Python program.

In the code, this is handled through the telemetry client, which receives information such as speed, angle, track position, RPM, gear, fuel, damage, lap time and opponent data. This telemetry is then passed into the main driving function, where the car decides how to steer, accelerate, brake and change gears.

On top of the driving system, we integrated IBM Granite through Ollama. This allowed us to add two AI communication features: a race engineer that responds to user questions, and live commentary that describes race events as they happen.

Overall, the project combines real-time car control with AI-generated communication, making the simulation more interactive and closer to a motorsport environment.


## RAMEEN - AI Driver and Technical Work

One of the main areas we worked on was improving and tuning the AI driver.

The main driver logic is inside the `championship_driver()` function in `main.py`. This function takes the telemetry data from TORCS and uses it to calculate four main outputs: steering, acceleration, braking and gear.

For example, the function reads values like `angle` and `trackPos` to work out whether the car is pointing in the right direction and whether it is close to the edge of the track. It also uses speed and track sensor data to decide whether the car should keep accelerating or slow down for corners.

During testing, the car showed unstable behaviour. It sometimes steered left and right too aggressively, drifted wide, spun out, or became unstable near walls. This made lap times inconsistent and affected the reliability of the system.

To investigate this, we used the control logs printed during the race. These logs showed values such as speed, track position, angle, RPM, steering, acceleration and braking. This helped us understand that some of the instability came from steering sensitivity, overcorrection and recovery logic.

We made practical improvements to the driver logic. We adjusted steering sensitivity, added smoother steering transitions using the previous steering value, tuned acceleration and braking, added gear-changing logic, and included basic opponent avoidance so the car would try not to drive directly into other racers.

We also compared the main driver with the simpler `novice_wrapper.py` driver. That version was useful because it had a simpler steering and throttle structure, so we used it as a reference when trying to make the main driver more stable.

The driver is not perfect, but we made progress in understanding and improving its behaviour. This showed us how small changes in telemetry-based control can have a major impact in a real-time AI system.


## REEFAT - Race Engineer and Commentary

In addition to the driver, we developed two AI-powered features using IBM Granite.

The first feature is the race engineer. In the code, this is handled through the `RaceEngineerAgent` class. The race engineer receives the current telemetry and builds a short prompt using values such as speed, RPM, gear, track position, lap time, fuel and damage.

The user can type questions during the race, such as asking about speed, damage, lap time or general performance. The system then passes the question and current telemetry into the engineer, which uses Granite to generate a short race-engineer style response.

The second feature is AI-generated commentary. This is handled in `commentary_manager.py`. The commentary system first turns raw telemetry into a short race context, such as whether the car is on the racing line, close to the edge, damaged, or near another racer. That context is then sent to Granite, which generates a live commentary sentence.

These features were important because they moved the project beyond simply controlling a car. They added explanation, interaction and presentation, which made the simulation feel more complete and more engaging for a user.


## RAMEEN - Challenges and Problem Solving

One of the biggest challenges was balancing multiple components in a real-time system.

The AI driver needed to make fast control decisions every frame, while the race engineer and commentary systems also needed accurate telemetry to produce useful responses. If the driver behaved unpredictably, the commentary and engineer feedback became less realistic.

The most difficult technical issue was driver stability. Sometimes a change improved performance on straights but made corners worse. Other times, recovery logic helped after going off track but caused the car to overcorrect or get stuck.

We approached this through iterative testing. Instead of making one large change, we reviewed telemetry logs, identified specific failure points, adjusted the logic, and tested again. For example, if the car was close to the wall and steering the wrong way, we could look at the `trackPos`, `angle` and steering output to understand why that was happening.

A key lesson was that adding more logic does not always make an AI system better. In some cases, simplifying the behaviour and reducing conflicting rules made the system easier to understand and more reliable.


## REEFAT - Reflection and Learning

Through this project, we developed a better understanding of how AI can be integrated into a real-time simulation.

We gained experience working with telemetry data, tuning control behaviour, using IBM Granite through Ollama, and combining multiple AI components into one system.

We also learned how important it is to separate responsibilities in the code. The telemetry client receives data, the driver function controls the car, the race engineer answers questions, and the commentary manager generates live race descriptions. This made the system easier to understand and test.

The system did not work perfectly straight away, and some improvements created new problems. However, by analysing the results and adapting our approach, we were able to make meaningful progress.

Working under time constraints also helped us prioritise. Instead of trying to build every possible feature, we focused on the areas that mattered most: driver behaviour, race engineer interaction, live commentary, and having a clear demonstration of AI integration.


## RAMEEN - Conclusion

In conclusion, we developed an AI-enhanced racing system that combines telemetry-based driving, real-time race engineer feedback, and live AI-generated commentary.

From a technical point of view, the system works by receiving live TORCS telemetry, passing it into the driver logic for control decisions, and also using that same telemetry to provide AI-generated feedback and commentary through IBM Granite.

The system demonstrates how AI can be applied in a practical and engaging simulation environment. While there is still room for refinement, especially in making the driver more consistent across different tracks and race situations, the project shows clear progress in combining real-time control with generative AI features.

Most importantly, we learned how to analyse AI behaviour, respond to technical challenges, and improve a system through testing and iteration.

Thank you for listening.

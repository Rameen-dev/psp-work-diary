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

Before we begin, I want to briefly mention that I joined the project later than expected due to unforeseen circumstances. This meant we had less time to explore the system from the beginning, so we had to adapt quickly. We focused on understanding the existing project, identifying the key problems, and making practical improvements within the time available.

Our goal was to go beyond a basic AI driver and create a more interactive racing system. We focused on three main areas: the AI driver, a race engineer system for real-time feedback, and AI-generated race commentary.


## REEFAT - System Overview

Our system is built around TORCS, which is a racing simulator that allows an AI-controlled car to receive live telemetry data.

The telemetry includes speed, angle, track position, RPM, gear, fuel, damage, lap time and opponent information. The driver uses this data to make decisions about steering, acceleration, braking and gear changes.

On top of the driving system, we integrated IBM Granite through Ollama to add intelligent communication features. This allowed us to build a race engineer that can respond to user questions, as well as live commentary that describes race events as they happen.

Overall, the project combines real-time car control with AI-generated communication, making the simulation more interactive and closer to a motorsport environment.


## RAMEEN - AI Driver and Technical Work

One of the main areas we worked on was improving and tuning the AI driver.

During testing, the car showed unstable behaviour. It sometimes steered left and right too aggressively, drifted wide, spun out, or became unstable near walls. This made lap times inconsistent and affected the overall reliability of the system.

To investigate this, we used telemetry logs from the live simulation. We looked at values such as speed, angle, track position, steering input, acceleration, braking, gear and damage. This helped us understand that some of the instability came from steering sensitivity, overcorrection, and conflicting recovery behaviour.

We made practical improvements to the driver logic. We adjusted steering sensitivity, added smoother steering transitions, tuned acceleration and braking, added gear-changing logic, and included basic opponent avoidance so the car would try not to drive directly into other racers.

We also compared the main driver with the simpler `novice_wrapper.py` driver, because that version behaved more reliably in some tests. We reused ideas from that simpler logic, especially around steering and speed control, while continuing to adapt the main driver.

The driver is not perfect, but we made progress in understanding and improving its behaviour. This was valuable because it showed how small changes in telemetry-based control can have a major impact in a real-time AI system.


## REEFAT - Race Engineer and Commentary

In addition to the driver, we developed two AI-powered features using IBM Granite.

The first feature is the race engineer. This allows the user to interact with the system by asking questions during the race. For example, the user can ask about the car’s speed, damage, lap time, stability or general performance. The system then uses the current telemetry context to generate a short race-engineer style response.

The second feature is AI-generated commentary. The commentary system reads the live telemetry and generates race-style descriptions of what is happening. For example, it can describe the car’s pace, track position, damage, or nearby rivals.

These features were important because they moved the project beyond simply controlling a car. They added explanation, interaction and presentation, which made the simulation feel more complete and more engaging for a user.


## RAMEEN - Challenges and Problem Solving

One of the biggest challenges was balancing multiple components in a real-time system.

The AI driver needed to make fast control decisions, while the race engineer and commentary systems also needed accurate telemetry to produce useful responses. If the driver behaved unpredictably, the commentary and engineer feedback became less realistic.

The most difficult technical issue was driver stability. Sometimes a change improved performance on straights but made corners worse. Other times, recovery logic helped after going off track but caused the car to overcorrect or get stuck.

We approached this through iterative testing. Instead of making one large change, we reviewed telemetry logs, identified specific failure points, adjusted the logic, and tested again. This helped us understand the relationship between steering, speed, track position and stability.

A key lesson was that adding more logic does not always make an AI system better. In some cases, simplifying the behaviour and reducing conflicting rules made the system easier to understand and more reliable.


## REEFAT - Reflection and Learning

Through this project, we developed a better understanding of how AI can be integrated into a real-time simulation.

We gained experience working with telemetry data, tuning control behaviour, using IBM Granite through Ollama, and combining multiple AI components into one system.

We also learned the importance of testing and reflection. The system did not work perfectly straight away, and some improvements created new problems. However, by analysing the results and adapting our approach, we were able to make meaningful progress.

Working under time constraints also helped us prioritise. Instead of trying to build every possible feature, we focused on the areas that mattered most: driver behaviour, race engineer interaction, live commentary, and having a clear demonstration of AI integration.


## RAMEEN - Conclusion

In conclusion, we developed an AI-enhanced racing system that combines telemetry-based driving, real-time race engineer feedback, and live AI-generated commentary.

The system demonstrates how AI can be applied in a practical and engaging simulation environment. While there is still room for refinement, especially in making the driver more consistent across different tracks and race situations, the project shows clear progress in combining real-time control with generative AI features.

Most importantly, we learned how to analyse AI behaviour, respond to technical challenges, and improve a system through testing and iteration.

Thank you for listening.

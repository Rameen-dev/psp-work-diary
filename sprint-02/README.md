# Sprint Week - Day 1

## What I worked on
- Began implementing AI-driven race commentary to describe race events in real time
- Connected live TORCS telemetry so race data could be displayed during testing
- Tested the commentary feature in the live TORCS simulation

## Plans for the next day
- Improve the accuracy of commentary outputs
- Begin analysing AI driving behaviour to improve stability

## Challenges
- The AI driver showed unstable behaviour, especially unexpected left and right swerving
- This affected the realism of both the commentary and race engineer feedback

## Solutions
- Identified that steering inputs were too sensitive and likely caused overcorrection
- Began analysing telemetry data such as angle, speed and track position


# Sprint Week - Day 2

## What I worked on
- Focused on improving the steering behaviour of the AI driver
- Adjusted steering sensitivity and tested smoother steering transitions
- Compared the main driver logic with the simpler novice wrapper logic

## Plans for the next day
- Improve braking and cornering performance
- Continue testing the driver on straights and turns

## Challenges
- The AI still struggled to maintain a stable racing line, especially on straights
- Some fixes helped in one area but caused new problems elsewhere

## Solutions
- Reduced steering gain and tested incremental adjustments
- Used telemetry logs to review speed, track position, angle, steering, acceleration and braking


# Sprint Week - Day 3

## What I worked on
- Implemented braking logic to improve handling during corners
- Adjusted acceleration behaviour to prevent excessive speed when approaching turns
- Continued live testing using TORCS telemetry logs

## Plans for the next day
- Improve overall lap time consistency
- Reduce crashes, spin-outs and recovery issues

## Challenges
- The AI driver was still losing control during sharper turns
- Recovery logic sometimes made the car worse by steering too aggressively or getting stuck

## Solutions
- Added conditional braking based on speed, angle and track position
- Began simplifying the driver logic after finding that too many fixes were clashing


# Sprint Week - Day 4

## What I worked on
- Focused on improving race consistency and reducing lap time variation
- Tested the system across different race situations, including straights, turns and traffic
- Reused some stable logic from `novice_wrapper.py` inside `main.py`

## Plans for the next day
- Finalise the most stable version possible for the demo
- Keep the driver fast while reducing random swerving and crashes

## Challenges
- The car sometimes drove well, then suddenly swerved or spun out
- Multiple features clashed once merged together

## Solutions
- Moved towards a simpler driver approach based on the working novice wrapper
- Reduced aggressive recovery behaviour and focused on smoother steering and throttle control


# Sprint Week - Day 5

## What I worked on
- Continued trying to finalise the AI driving improvements
- Tested fixes for swerving near walls and on straights
- Added basic opponent avoidance so the car tries not to hit nearby racers directly
- Added straight-line stabilisation to reduce unnecessary steering

## Challenges
- The driver was still not fully reliable
- Keeping the car fast while preventing crashes was difficult
- Some features worked individually but were less stable when combined

## Solutions
- Prioritised stability over adding more complex behaviour
- Simplified the active driver logic in `main.py`
- Used telemetry logs to identify specific problems, such as steering the wrong way near the wall

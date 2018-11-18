# Zipline Data Scientist Take Home Project

## Introduction

Zipline operates the world’s only drone delivery system at national scale to send urgent medicines like blood transfusions and vaccines to those in need – no matter where they live. We’re at the forefront of a logistics revolution, designing, manufacturing, and operating our own battery powered autonomous aircraft fleet to overcome the challenges of delivering just-in-time, lifesaving medical supplies around the world.

From our distribution center in Muhanga, we serve rural hospitals in the western half of Rwanda, delivering blood transfusions used to treat conditions like malaria anemia and postpartum hemorrhaging. After an order is placed, an electromechanically actuated launcher accelerates one of our aircraft — known internally as a "Zip" — at 5 g's from 0 to 30 m/s (67 mph) in less than a second. From there, the plane autonomously navigates a pre-defined route to the delivery site, drops its package, and returns to the distribution center to recover. For an example of what this looks like, here's a [video from CNBC](https://www.youtube.com/watch?v=FeSCEalMOL8).

A Zip is made up of three components — a battery, wing, and body. For each flight, a flight operator selects one of each component, "asembling" the Zip immediately prior to flight, as our fulfillment operators prepare the package before it's placed in the assembled Zip.

## The Dataset

In this directory, you'll find:
- This readme
- A `flight_XXXXX.csv` file for each flight in the dataset. Each file contains the following signals from 5 seconds prior to launch, to 15 seconds after launch, logged at approximately 50Hz:

Name | Units | Description
--- |:---:| -----:
`seconds_since_launch` | seconds | time since launch
`position_ned_m[0]` | meters | position of the zip relative to a fixed reference point in the north direction
`position_ned_m[1]` | meters | position of the zip relative to a fixed reference point in the east direction
`position_ned_m[2]` | meters | position of the zip relative to a fixed reference point in the down direction
`velocity_ned_mps[0]` | meters/second | velocity of the zip, in the north direction
`velocity_ned_mps[1]` | meters/second | velocity of the zip, in the east direction
`velocity_ned_mps[2]` | meters/second | velocity of the zip, in the down direction
`accel_body_mps2[0]` | meters/second^2 | acceleration of the zip, in the body-forward direction
`accel_body_mps2[1]` | meters/second^2 | acceleration of the zip, in the body-right direction
`accel_body_mps2[2]` | meters/second^2 | acceleration of the zip, in the body-down direction
`orientation_rad[0]` | radians | Euler (Tait-Bryan) roll of the zip
`orientation_rad[1]` | radians | Euler (Tait-Bryan) pitch of the zip
`orientation_rad[2]` | radians | Euler (Tait-Bryan) yaw of the zip
`angular_rate_body_radps[0]` | radians/second | Angular velocity of the zip, about the body-forward direction
`angular_rate_body_radps[1]` | radians/second | Angular velocity of the zip, about the body-right direction
`angular_rate_body_radps[2]` | radians/second | Angular velocity of the zip, about the body-down direction
`position_sigma_ned_m[0]` | meters | estimated standard error of position_ned_m[0], i.e. positional uncertainty in the north direction
`position_sigma_ned_m[1]` | meters | estimated standard error of position_ned_m[1], i.e. positional uncertainty in the east direction
`position_sigma_ned_m[2]` | meters | estimated standard error of position_ned_m[2], i.e. positional uncertainty in the down direction

- A `summary_data.csv` file containing the following data for each flight in the dataset:

Name | Units | Description
--- |:---:| -----:
`flight_id` | n/a | unique identifier for the flight
`battery_serial_number` | n/a | serial number of the battery
`body_serial_number` | n/a | serial number of the body
`wing_serial_number` | n/a | serial number of the wing
`commit` | n/a | git commit SHA representing the version of software
`launch_airspeed` | meters/second | airspeed of the plane during launch
`launch_groundspeed` | meters/second | groundspeed of the plane during launch
`launch_timestamp` | n/a | time string `YYYT-MM-DD HH:MM:SS CAT` where CAT, i.e. Central Africa Time, is the timezone
`preflight_voltage` | volts | dc voltage of the battery immediately prior to launch
`air_temperature` | celsius | air temperature during launch
`rel_humidity` | percentage | relative humidity during launch
`static_pressure` | pascals | static air pressure during launch
`wind_direction` | degrees | direction of the wind during launch, with 0 blowing to the north, 90 blowing to the east
`wind_magnitude` | meters/second | magnitude of the wind during launch

## The Project

1. Visualize the launches in an informative way, and write a few words describing your work and what you found.
1. BONUS: Identify any "outlier" launches that an engineer should look over, and why.
1. DOUBLE BONUS: Identify any interesting patterns in the data, e.g. weather seasonality, poorly performing parts, etc.

Once you've completed the project, please attach any code, figures, and other documents to an email sent to matt@flyzipline.com. Bonus points for code that runs, interactive visualizations, and Jupyter notebooks!

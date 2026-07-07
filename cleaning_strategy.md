# Assignment 03 Cleaning Strategy

## Order of Operations

1. Determine if there are null entries and if so, attempt to fill in null values with values with values from vehicles with the same make and model.
    - This works for some features, but not all. Features like mileage are not going to be able to be recovered, whereas seating capacity and fuel capacity (among others) could be.
    - Values that can't be recovered from the car's model are dropped, the columns Engine, Max Power, Max Torque, Drivetrain, Length,  Width, Height, Seating Capacity, and Fuel Tank Capacity are all important to a customer's decision.

2. Clean up enginer parameters
    - `Max Power` contains data of the format "x bhp @ y rpm", and `Max Torque` contains data formatted as "x Nm @ y rpm". These can be split into `Max Power BHP`, `Max Power RPM`, `Max Torque Nm`, and `Max Torque RPM` respectively to allow them to be evaluated continuously in the regression.
    
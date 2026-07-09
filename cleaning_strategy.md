# Assignment 03 Cleaning Strategy

## Order of Operations

1. Determine if there are null entries and if so, attempt to fill in null values with values with values from vehicles with the same make and model.
    - This works for some features, but not all. Features like mileage are not going to be able to be recovered, whereas seating capacity and fuel capacity (among others) could be.
    - Values that can't be recovered from the car's model are dropped, the columns Engine, Max Power, Max Torque, Drivetrain, Length,  Width, Height, Seating Capacity, and Fuel Tank Capacity are all important to a customer's decision.

2. Clean up engine parameters
    - `Max Power` contains data of the format "x bhp @ y rpm", and `Max Torque` contains data formatted as "x Nm @ y rpm". These can be split into `Max Power BHP`, `Max Power RPM`, `Max Torque Nm`, and `Max Torque RPM` respectively to allow them to be evaluated continuously in the regression.

3. Combine Trims into Base Models
    - Many cars are listed as different models, which gives a large amount of unique results, when in reality the dataset has fewer base models, which could present good features for regression.
    - By taking the first word, or first two words for a limited set of cases, we can greatly reduce the number of unique models into a smaller set of base models that customers are more likely to base their selection on.

## Features 

| Column | Info |
| --- | --- |
| Make | Car manufacturers split into dummies |
| Model Base | Base model for each car split into dummies |
| Fuel Type | Split into dummies
| Transmission | Split into dummies |
| Location | Split into dummies |
| Color | Split into dummies |
| Owner | First, second, third, four or more. Split into dummies |
| Seller Type | Individual or Corporate, split into dummies |
| Drivetrain | Split into dummies |
| Year | Year of manufacture |
| Kilometers | Number of kilometers driven |
| Max Power BHP | Maximum power output in horsepower |
| Max Power RPM | RPM of engine at max power output |
| Max Torque Nm | Maximum torque of engine |
| Max Torque RPM | RPM of engine at max torque output |

## Target

| Column | Info |
| --- | --- |
| Price | Price of vehicle listed on WheelsBazaar in Rupees (₹) |
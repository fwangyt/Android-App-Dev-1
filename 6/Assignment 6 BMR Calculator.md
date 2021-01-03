## Assignment 6: BMR Calculator

### Objectives

- Buttons in Android Studio: CheckBox, RadioGroup, and Switch.

- To become familiar with Button/EditText/TextView.

### Requirements

- On this assignment, you are to create a simple [Basal Metabolic Rate](https://en.wikipedia.org/wiki/Basal_metabolic_rate) (BMR) calculator app. Start your UI design with ConstraintLayout (use infer constraints).

- You are encouraged to design your own UI (color, style, etc.). An example of a simple BMR calculator app is shown below.

  <img src="https://github.com/fwangyt/Android-App-Dev-1/raw/master/6/images/assignment_1.png" alt="assignment_1" style="zoom: 80%;" />

- Height/Weight/Age Edit Text

  - Four EditTexts: to obtain height (feet), height (inches), weight, and age.

  - Specify the inputType to numberDecimal and numberSigned.

- Gender RadioGroup

  - One gender RadioGroup with two RadioButtons: Male and Female.

- Activity CheckBox

  - One CheckBox: Activity.

  - When Activity CheckBox is checked, multiplying the BMR result by a factor 1.2. That is, BMR = BMR (from the equation) × 1.2.

- Calculate Button and Clear Button

  - Calculate Button: to show BMR result.

  - Clear Button: to reset UI.

  <img src="https://github.com/fwangyt/Android-App-Dev-1/raw/master/6/images/assignment_2.png" alt="assignment_2" style="zoom:80%;" />

- Error Handling

  - Use AlertDialog to handle missing field errors (four required fields: height, weight, age, and gender).
- *See Example 3: AlertDialog*
  
  <img src="https://github.com/fwangyt/Android-App-Dev-1/raw/master/6/images/assignment_2.png" alt="assignment_2" style="zoom:80%;" />

### Bonus: Units conversion Switch

- When Switch is unchecked (off), convert all US units to metric units.

  - height (ft) -> height (m)
  - height (in) -> height (cm)
  - weight (lbs) -> weight (kg)

  <img src="https://github.com/fwangyt/Android-App-Dev-1/raw/master/6/images/assignment_4.png" alt="assignment_4" style="zoom: 67%;" />

  

### Submission

- Zip your Android project and submit it via Canvas.

### Grading (100 points)

- BMR calculation and display (40 points).
- Height/Weight/Age EditText (20 points, 5 points each). 
- Calculate/Clear Button (10 points, 5 points each).
- Gender RadioGroup (10 points).
- Activity CheckBox (10 points).
- Exception handling (10 points).
- Bonus: unit conversion Switch (+10 points).

### Supplements

- Demo video: https://www.youtube.com/watch?v=qsIT3SM5Vs8

### The Mifflin - St Jeor BMR equations
- The Mifflin - St Jeor BMR Equation (US Units)
  - Men:       BMR = (4.536 × weight in pounds) + (15.88 × height in inches) - (5 × age in years) + 5
  - Women: BMR = (4.536 × weight in pounds) + (15.88 × height in inches) - (5 × age in years) - 161
- The Mifflin - St Jeor BMR Equation (Metric Units)
  - Men:       BMR = (10 × weight in kg) + (6.25 × height in cm) - (5 × age in years) + 5
  - Women: BMR = (10 × weight in kg) + (6.25 × height in cm) - (5 × age in years) - 161
- Unit Conversion
  - pound(lb), foot(ft), inch(in), kilogram(kg), meter(m), centimeter(cm).
  - 1 ft = 0.3048 m          1 m = 3.28084 ft
  - 1 in = 2.54 cm            1 cm = 0.393701 in
  - 1 ft = 12 in                  1 in = 0.0.083333 ft
  - 1 m = 100 cm             1 cm = 0.01m
  - 1 lb = 0.453592 kg     1 kg = 2.20462 lbs
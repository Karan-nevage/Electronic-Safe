# Electronic Safe Using Arduino Uno

## Overview
This project implements an electronic safe using an Arduino Uno, an LCD display, a servo motor, and a keypad. The safe can be locked and unlocked using a secret code entered via the keypad. The state of the safe (locked/unlocked) and the secret code are managed by the `SafeState` class.

## Components
- **Arduino Uno**
- **16x2 LCD Display**
- **Servo Motor**
- **4x4 Keypad**
- **Wires and Breadboard**

## Circuit Diagram
Refer to the provided circuit diagram for wiring details.


## Working

This program implements a safe lock system using an Arduino, a keypad, an LCD display, and a servo motor. The system allows the user to lock and unlock the safe by entering a secret code. The main components and their functions are as follows:

- **Servo Motor**: Controls the locking and unlocking mechanism.
- **LCD Display**: Provides user interface messages.
- **Keypad**: Allows the user to input the secret code.
- **SafeState**: Manages the state of the safe (locked or unlocked) and the secret code.

## Algorithm

1. **Initialization**:
    - Initialize the LCD display, servo motor, and serial communication.
    - Attach the servo motor to the specified pin.
    - Display a startup message on the LCD.
    - Check the initial state of the safe (locked or unlocked) and set the servo position accordingly.

2. **Main Loop**:
    - Continuously check the state of the safe.
    - If the safe is locked, execute the `safeLockedLogic` function.
    - If the safe is unlocked, execute the `safeUnlockedLogic` function.

3. **Locking the Safe**:
    - Set the servo to the locked position.
    - Update the safe state to locked.

4. **Unlocking the Safe**:
    - Set the servo to the unlocked position.

5. **Displaying Messages**:
    - Show a startup message when the system is initialized.
    - Show a wait screen with a progress bar during certain operations.
    - Show an unlock message when the safe is successfully unlocked.

6. **Inputting the Secret Code**:
    - Prompt the user to enter a 4-digit secret code using the keypad.
    - Display asterisks on the LCD as the user inputs the code.
    - Return the entered code as a string.

7. **Setting a New Code**:
    - Prompt the user to enter a new secret code.
    - Prompt the user to confirm the new code.
    - If the codes match, update the safe state with the new code.
    - If the codes do not match, display an error message.

8. **Safe Locked Logic**:
    - Display a locked message on the LCD.
    - Prompt the user to enter the secret code.
    - If the entered code is correct, unlock the safe and display an unlock message.
    - If the entered code is incorrect, display an access denied message.

9. **Safe Unlocked Logic**:
    - Display an unlocked message on the LCD.
    - Prompt the user to press '#' to lock the safe or 'A' to set a new code.
    - If the user chooses to set a new code, execute the `setNewCode` function.
    - If the user chooses to lock the safe, lock the safe and display a wait screen.

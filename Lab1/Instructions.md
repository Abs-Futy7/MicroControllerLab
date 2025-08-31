# Lab 1: Introduction to Microcontrollers & GPIO

**Instructor:** Dr. Shabbir Ahmed  
**Time:** 2:01 PM

---

## Objectives

By the end of this lab, students will be able to:

- Understand the basic architecture of a microcontroller.
- Set up a development environment (IDE, compiler, programmer).
- Configure GPIO pins as input and output.
- Write, upload, and debug basic microcontroller programs.
- Implement a simple input–output control system (button → LED).

---

## Required Equipment

- Microcontroller board (Arduino Uno / STM32 Nucleo / ESP32 / PIC board)
- USB cable & programmer/debugger (if needed)
- Breadboard & jumper wires
- LED (1–2 pcs), push button (1 pc)
- Resistors: 220 Ω (for LED), 10 kΩ (for button pull-down)
- Computer with IDE installed (Arduino IDE / STM32CubeIDE / MPLAB X depending on MCU)

---

## Pre-lab Preparation

- Read about the differences between microcontrollers and microprocessors.
- Review microcontroller architecture: CPU, Flash memory, RAM, I/O ports.
- Install the required IDE and drivers for your platform.

---

## Lab Activities

### Part A: Toolchain Setup (30 min)

1. Connect the microcontroller board to your computer.
2. Open the IDE, select the correct board and COM port.
3. Upload a sample “Hello World” program (LED blink).

**Example (Arduino C code):**
```c
void setup() {
    pinMode(13, OUTPUT);   // Set pin 13 as output
}
void loop() {
    digitalWrite(13, HIGH); // LED ON
    delay(1000);            // Wait 1 sec
    digitalWrite(13, LOW);  // LED OFF
    delay(1000);            // Wait 1 sec
}
```

---

### Part B: Digital Input (45 min)

1. Wire a push button to pin 2 with a pull-down resistor.
2. Modify the code to read the button state.
3. Print button status to the Serial Monitor.

**Example snippet:**
```c
int buttonPin = 2;
void setup() {
    pinMode(buttonPin, INPUT);
    Serial.begin(9600);
}
void loop() {
    int state = digitalRead(buttonPin);
    Serial.println(state);
    delay(200);
}
```

---

### Part C: Input → Output Control (1 hr)

1. Connect LED to pin 8.
2. Write a program where the LED turns ON only when the button is pressed.
3. Extend: Press → LED toggles state (like a switch).

---

### Part D: Debugging Practice (30 min)

1. Use `Serial.print()` (or debugger breakpoints) to observe variable values.
2. Introduce deliberate error (wrong pin, missing resistor) → troubleshoot.

---

## Assessment Questions

1. What is the main difference between microcontrollers and microprocessors?
2. Why do we need a pull-down resistor on the button input?
3. If you press the button quickly, why might the LED not always respond? (hint: bouncing)
4. Modify your program so that the LED stays ON for 5 seconds after a button press.

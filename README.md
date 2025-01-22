# cRF433_REMOTE: 433MHz RF Remote Receiver Library

This repository contains a library for 433MHz RF remote receivers. It is designed to work with almost all available remotes, with a few exceptions. This library is a simplified version of the RCRemote library for Arduino, converted and simplified to pure C.

## Features

- Compatible with most 433MHz RF remote controls
- Simplified and lightweight
- Works with external interrupts (RISING_FALLING/CHANGE)
- Requires a `micros()` function for timing, which can be implemented using a timer interrupt or systick timer

## Usage

To use this library, include the header file and implement the required `micros()` function. The `micros()` function should return the current time in microseconds. This can be achieved using a timer interrupt or systick timer.

### Example

```c
#include "cRF433_REMOTE.h"

// Implement the micros() function
unsigned long micros() {
    // Your implementation here
}

void setup() {
    // Initialize the RF remote receiver
    cRF_init();
    
    // Set up external interrupt for RF remote receiver
    attachInterrupt(digitalPinToInterrupt(RECEIVER_PIN), cRF_handleInterrupt, CHANGE);
}

void loop() {
    // Your main code here
}
```

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.

## Acknowledgements

This library is based on the RCRemote library for Arduino.

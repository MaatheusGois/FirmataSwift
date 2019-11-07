# SwiftFirmata 

A Swift wrapper on CFirmata.

This project support [Swift 5.1](https://swift.org/blog/swift-5-1-released/).

The idea is to provide a framework to control Arduino using Swift, by implementing a [Firmata protocol](firmata.org/wiki/V2.3ProtocolDetails) client.

Heavily inspired on: https://github.com/marciok/SwiftFirmata


## Building The Project:

### Step 1

Install in Arduino the Standard Firmata [Tutorial](https://www.instructables.com/id/Arduino-Installing-Standard-Firmata/).

### Step 2

Install the package in your project [Tutorial](https://www.ralfebert.de/ios/swift-package-manager-for-ios-projects/).

### Step 3

Be Happy!


## Example:

```swift
import SwiftFirmata

// Blink led hooked on pin 13
let firmata = try! SwiftFirmata(connect: "/dev/cu.usbmodem1421", baud: 57600)
let pin = Pin(number: 13, mode: .Output)
firmata.configure(pin)

while (true) {
  firmata.digitalWrite(pin, level: .High)
  sleep(2)
  firmata.digitalWrite(pin, level: .Low)
  sleep(2)
}
```

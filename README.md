# espdht22

This is a simple library for ESP8266(EX) chips to pull sensor data from the DHT22 temperature sensors

## Features

 * Easy to use.
 * Supports multiple requests in parallel.
 * Tested with Espressif SDK v1.1.1

## Building
If you don't have a toolchain yet, install one with <https://github.com/pfalcon/esp-open-sdk> then get Espressif's SDK.

### The submodule way
If your project looks like esphttpd from Sprite_tm:
```bash
git clone https://github.com/jpenninkhof/espsaphcp.git
cd esphttpd
git submodule add https://github.com/jpenninkhof/espdht22.git lib/espdht22
git submodule update --init
```

Now append `lib/espdht22` to the following `Makefile` line and you should be ready:
```
MODULES = driver user lib/espdht22
```

### The dirty way
Alternatively you could create a simple project:
```bash
git clone https://github.com/esp8266/source-code-examples.git
cd source-code-examples/basic_example
# Set your Wifi credentials in user_config.h
# I could not test this because of the UART baud rate (74880)
```

Then download this library and move the files to `user/`:
```bash
git clone https://github.com/jpenninkhof/espdht22.git
mv espsaphcp/*.* user/
```

## Usage
Include `dht22.h` from `user_main.c` then call one of these functions:
```
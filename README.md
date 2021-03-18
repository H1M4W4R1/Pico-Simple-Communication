# How to use
```c
// You need to create uart object
UART uart;

// Then begin it on specific hardware UART
//uart.begin(<interface>, <baudrate>) eg.
uart.begin(uart0, 115200);

// Then you can write data
uint a = 32;
uart.write_uint(a);

int b = -125;
uart.write_int(b);

float c = 12.5f;
uart.write_float(c);

uart.write("\r\n");

uart.write("Easy?");
```

To read data you can use
```
uint8_t number0 = uart.peek(); // Peeks UART without removing number from data queue
uint8_t number1 = uart.read(); // reads 8-bit number
uint64_t number2 = uart.parse_uint(); // Reads unsigned integer written as text
int64_t number3 = uart.parse_int(); // Reads signed interger written as text
```

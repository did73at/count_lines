# Function Line Counter

This script analyzes C source files and counts the number of lines for each function according to the Epita coding style. 

## Prerequisites
- The script only takes `*.c` files as arguments.
- All files must be formatted with `clang-format` before being processed by this script.

## Installation

You can get the script by cloning the repository or by executing the following command:
```sh
curl --remote-name https://raw.githubusercontent.com/did73at/count_lines/refs/heads/main/count_lines
```

To run the script from anywhere on your system, you can place it in your local binaries directory (`/usr/local/bin`).
Run the following commands in your terminal:
```sh
sudo cp count_lines /usr/local/bin/
sudo chmod +x /usr/local/bin/count_lines
```

## Usage
The script accepts an optional line limit as its first argument, followed by any number of .c files.
```sh
count_lines [N] <file1.c> [file2.c] ...
```
- `N` *(optional)*: The maximum allowed number of lines per function. If not specified, the default value is 30.
- `<file.c>`: An unlimited number of C source files to analyze.

## Output
Running the script will output the filename, followed by each function's signature and its line count.
If a function's line count strictly exceeds the limit N, its output will be displayed in red. 

A final warning message will also be displayed in red at the bottom if any functions exceeded the limit, detailing the total number of functions that are too long.

# File Headling:

## What is a File?
A file is a digital container used to store information such as text, images, audio, video, or programs on a computer.

## Types of Files

### Text Files
- Store data as plain text, represented in the form of characters.  
- **Examples:** `.txt` files and other plain-text formats.

### Binary Files
- Store data in binary format (as bytes), which is not directly human-readable.  
- **Examples:**  
  - Audio files (`.mp3`)  
  - Video files (`.mp4`)  
  - Image files (`.jpg`, `.png`)  
  - Document files (`.pdf`)  

## What is File Handling?

File handling refers to the process of creating, reading, writing, and managing files in a computer system. It involves three main steps:  
1. **Opening a file**  
2. **Performing operations on the file** (reading, writing, etc.)  
3. **Closing the file**  

## What is a File Object in Python?

A file object is a reference to a file that allows you to interact with it. It is used to read or write data to a file. In Python, you can create a file object using the `open()` function:

```python
file = open("example.txt", "r")  # Opens a file in read mode
content = file.read()  # Reads file content
file.close()  # Closes the file
```

## What Happens If We Don’t Close a File?
If a file is not explicitly closed, Python's garbage collector will automatically destroy the file object and close the file at the end of the program. However, it is a good practice to close files manually to free up system resources promptly.

```
f = open("data.txt",mode='r', encoding='utf-8')

print("file name is ",f.name) 
print("file mode is ",f.mode)
print("file encoding is ",f.encoding)
print("is file closed ",f.closed)
f.close()
print("is file closed ",f.closed)

output:
file name is data.txt
file mode is r
file encoding is utf-8
is file closed False
is file closed True

```
# File Object Methods

## `readable()` and `writable()`
These methods are used to check whether a file is readable or writable.  

- **`readable()`**: Returns `True` if the file is readable, otherwise `False`.  
- **`writable()`**: Returns `True` if the file is writable, otherwise `False`.  

## Example Program for `readable()` and `writable()`
```python
# Opening a file in read mode
f = open("data.txt", mode='r')
print(f.readable())  # True, since the file is opened in read mode
print(f.writable())  # False, as writing is not allowed in read mode
f.close()

# Opening a file in read and write mode
f = open("data.txt", mode='r+')  # Use 'w+' for write and read mode
print(f.readable())  # True, since 'r+' allows reading
print(f.writable())  # True, since 'r+' also allows writing
f.close()
```

# Check if a File Exists

To check whether a file exists, use the `os.path.isfile()` method.  

### Key Points:
- Belongs to the `path` module, which is a submodule of the `os` module.
- Returns a Boolean (`True` if the file exists, `False` otherwise).  

## Example Program for File Existence Check:
```python
import os

# Checking if the file exists
if os.path.isfile("data.txt"):
    print("File exists")
    f = open("data.txt")
    # Perform operations on the file
    f.close()
else:
    print("File does not exist")
```

# Ways to Close Files in Python

## 1. Normal Way (Using `f.close()`)
- Manually closing the file using `f.close()`.
- **Drawback**: If an error occurs before `f.close()` is called, the file may remain open.

### Example:
```python
f = open("data.txt", mode='r')
data = f.read()
print(data)
f.close()  # Manually closing the file
```

## 2. Using Exception Handling
- Ensures the file is closed even if an error occurs during the file operation.
- Use a `try...finally` block or handle exceptions explicitly.

### Example:
```python
try:
    # Open the file in write mode
    file_path = "example.txt"
    file = open(file_path, "w")
    file.write("Hello, this is a test.")  # Perform operations
except Exception as e:
    print(f"An error occurred: {e}")
finally:
    # Ensure the file is closed
    if file and not file.closed:
        file.close()
        print("File closed successfully.")
```

## 3. Using the `with` Statement
- The best and most reliable way to handle files.
- The `with` statement ensures the file is **automatically closed** after the operations are complete, even if an error occurs.

### Example:
```python
with open("data.txt", mode='r') as f:
    data = f.read()
    print(data)  # File will be closed automatically after this block
```

# File Modes in Python

## Text Modes:
- **`r` (Read)**: Opens the file for reading. The file must exist.
- **`w` (Write)**: Opens the file for writing, clearing any existing content. Creates a new file if it doesn’t exist.
- **`a` (Append)**: Opens the file for appending new data at the end. Creates a new file if it doesn’t exist.
- **`r+` (Read/Write)**: Opens the file for both reading and writing. The file must exist.
- **`w+` (Write/Read)**: Opens the file for writing and reading. Clears existing content. Creates a new file if it doesn’t exist.
- **`a+` (Append/Read)**: Opens the file for appending and reading. Adds new data at the end. Creates a file if it doesn’t exist.

## Binary Modes:
- **`rb` (Read Binary)**: Opens the file for reading in binary mode. The file must exist.
- **`wb` (Write Binary)**: Opens the file for writing in binary mode, clearing existing content. Creates a new file if it doesn’t exist.
- **`ab` (Append Binary)**: Opens the file for appending in binary mode. Adds new data at the end. Creates a file if it doesn’t exist.
- **`rb+` (Read/Write Binary)**: Opens the file for both reading and writing in binary mode. The file must exist.
- **`wb+` (Write/Read Binary)**: Opens the file for writing and reading in binary mode. Clears existing content. Creates a file if it doesn’t exist.
- **`ab+` (Append/Read Binary)**: Opens the file for appending and reading in binary mode. Adds new data at the end and creates a file if it doesn’t exist.

## Key Differences Between Text and Binary Modes

| Aspect               | **Text Mode (t)**                                                                 | **Binary Mode (b)**                                                |
|----------------------|-----------------------------------------------------------------------------------|--------------------------------------------------------------------|
| **Data Representation** | Treats file data as strings (characters) based on character encoding (e.g., UTF-8). | Treats file data as raw bytes without any encoding or decoding.    |
| **Encoding/Decoding**  | Python handles encoding when writing and decoding when reading automatically.    | No encoding or decoding is applied. Data is read and written as-is. |
| **Suitable For**       | Human-readable files (e.g., .txt, .csv).                                         | Non-human-readable files (e.g., images, audio, executables).       |
| **Example Usage**      | Reading or writing text content.                                                 | Handling binary content such as media or binary executables.       |

## Reading in text mode
```
with open('text_file.txt', 'rt') as file:
    content = file.read()  # Reads as a string
    print(content)

## Writing in text mode
with open('text_file.txt', 'wt') as file:
    file.write('Hello, this is a text file.')
```

## Reading in binary mode
```
with open('binary_file.bin', 'rb') as file:
    content = file.read()  # Reads as raw bytes
    print(content)

## Writing in binary mode
with open('binary_file.bin', 'wb') as file:
    file.write(b'\x48\x65\x6C\x6C\x6F')  # Writes binary data (ASCII for 'Hello')
```

## Summary:
- Text Mode: Used for human-readable content, applies character encoding.
- Binary Mode: Used for non-human-readable content, no encoding or decoding applied.
- Choose the mode based on whether you are working with text-based or binary data.

### `tell()` Method
**Purpose:** The `tell()` method is used to find the current position of the file pointer from the beginning of the file.  
**Pointer Behavior:** The file pointer position starts at 0 (similar to indexing in strings).  
**Syntax:**
```python
file_object.tell()

Example:
Suppose the content of data.txt is:
Hello
World
bye

f = open('data.txt', mode='r')

print(f.tell())  # Initially, the cursor starts at 0
print(f.read(3))  # Reads the first 3 characters: 'Hel'
print(f.tell())  # The pointer is now at position 3
f.close()

Output:
0
Hel
3

```

### `seek()` Method
**Purpose:** The `seek()` method is used to change the position of the file pointer.  
**Pointer Behavior:** The file pointer is always counted from the beginning of the file unless explicitly specified.  
**Syntax:**
```python
file_object.seek(offset, whence=0)

f = open("data.txt", mode='r')

print(f.tell())  # Initially, the cursor starts at 0
print(f.read(4))  # Reads the first 4 characters: 'Hell'
print(f.tell())  # The pointer is now at position 4

# Reset the pointer to the beginning of the file
f.seek(0)
print(f.read())  # Reads the entire file content: 'Hello\nWorld\nbye'
f.close()

Output:
0
Hell
4
Hello
World
bye

```

## Writing Data in a File
To write data into a file, the file must be opened in a mode that allows writing, such as `w`, `a`, or `w+`.

### 1. Writing with `w` Mode
**Purpose:** Opens the file for writing.  
- If the file exists, its content is overwritten.  
- If the file does not exist, it creates a new file.

#### Methods:
- `write()`: Writes a single string to the file.
- `writelines()`: Writes multiple strings (from a list/tuple/set) to the file.

### `write()` Method
**Purpose:** Used to  Write a single string to the file
```
# Writing to a file using write()
f = open("data.txt", mode='w')
f.write("Hello everyone, how are you?")
f.write(" Hello world.")
f.close()

# Content of data.txt:
# Hello everyone, how are you? Hello world.

# Overwriting the file
f = open("data.txt", mode='w')
f.write("Hello world")
f.close()

# Content of data.txt after overwriting:
# Hello world
```

## writelines() Method
**Purpose:** Used to write a group of strings (stored in a list, tuple, or set) into a file.
```
# Writing multiple lines using writelines()
f = open("data.txt", mode='w')

lines_list = ['Ram\n', 'Raj\n', 'Rajesh']
f.writelines(lines_list)
f.close()

# Content of data.txt:
# Ram
# Raj
# Rajesh
```

### Complete Example with Exception Handling

```
try:
    # Open the file in write mode
    f = open("data.txt", mode='w')
    
    # Writing multiple lines using writelines()
    lines_list = ['Ram\n', 'Raj\n', 'Rajesh']
    f.writelines(lines_list)
    print("File written successfully")
except Exception as e:
    print(f"An error occurred: {e}")
finally:
    # Ensure the file is closed
    if 'f' in locals() and not f.closed:
        f.close()
        print("File is closed")
```

### Exclusive Write Mode (`x`)

**Purpose:** Opens a file for writing only if it does not exist.  
If the file exists, it raises a `FileExistsError`.  
**Use Case:** Ensures no accidental overwriting of existing files.

```
try:
    # Open a file in exclusive write mode
    f = open("new_file.txt", mode='x')
    data = "Hello everyone"
    f.write(data)
    print("Data written successfully")
except FileExistsError:
    print("File already exists. Cannot write in 'x' mode.")
finally:
    if 'f' in locals() and not f.closed:
        f.close()
        print("File is closed")
```

## Reading Data from a File

### Methods to Read File Content:

- **`read()`**: Reads the entire file content or a specified number of characters.
- **`readline()`**: Reads a single line or a specific number of characters from a line.
- **`readlines()`**: Reads all lines and returns them as a list of strings.


## 1. read() Method:
**Purpose:** Reads the entire file or a specific number of characters.
```
Example:
# Read full file content
f = open("data.txt", mode='r')
data = f.read()
print(data)  # Entire content of the file
f.close()

# Read specific number of characters
f = open("data.txt", mode='r')
data1 = f.read(3)  # Reads first 3 characters
data2 = f.read(2)  # Reads the next 2 characters
print(data1)  # Output: first 3 characters
print(data2)  # Output: next 2 characters
f.close()
```

## 2. readline() Method:
**Purpose:** Reads a single line from the file.
```
Example:
# Read a full line
f = open("data.txt", mode='r')
data = f.readline()
print(data)  # Reads the first line
f.close()

# Read specific characters from the first line
f = open("data.txt", mode='r')
data = f.readline(5)  # Reads the first 5 characters of the first line
print(data)
f.close()
```

## 3. readlines() Method:
**Purpose:** Reads all lines from the file and returns a list of lines.
```
f = open("data.txt", mode='r')
data = f.readlines()  # Returns all lines as a list
print(data)  # Example: ['Ram\n', 'Raj\n', 'Rajesh\n']
f.close()

# Iterating through the list of lines
for line in data:
    print(line.strip())  # Removes newline characters
```

## Copy Content from One File to Another
```
# Open the source and destination files
f1 = open("data.txt", mode='r')
f2 = open("copy.txt", mode='w')

# Read data from the source file
data = f1.readlines()

# Write data to the destination file
for line in data:
    f2.write(line)

# Close both files
f1.close()
f2.close()

print("Content copied successfully!")
```

## Difference between `r+` and `w+` Modes

| Mode  | Behavior                                              | File Creation               | Content Handling                               |
|-------|-------------------------------------------------------|-----------------------------|------------------------------------------------|
| `r+`  | Opens the file for both reading and writing.          | Raises an error if the file doesn't exist. | Does not truncate (overwrite) the content; modifies the file. |
| `w+`  | Opens the file for both reading and writing.          | Creates a new file if it doesn't exist. | Truncates (overwrites) the file content to empty before writing. |



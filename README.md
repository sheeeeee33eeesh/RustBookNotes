# Starter Stuff

## Installation
```bash
curl --proto '=https' --tlsv1.2 https://sh.rustup.rs -sSf | sh

```

## Setting Up Projects

**Create Project Directory**
```bash
cargo new <projectName>
cd <projectName>
```

**Compile Project**
```bash
cargo build # Quicker Compile, But Not Optimized
cargo build --release # Slower Compile, But Optimized

cargo run # Unoptimized Compile followed by execution of compiled program
```

## Adding Dependencies

Modify Cargo File `nvim Cargo.toml`
```toml
[package]
name = "ProjectName"
version = "0.1.0"
edition = "2024"

[dependencies]
rand = "0.8.5"
```


---
# Data Types
## Integers
|Length|Signed|Unsigned|
|---|---|---|
|8-bit|i8|u8|
|16-bit|i16|u16|
|32-bit|i32|u32|
|64-bit|i64|u64|
|128-bit|i128|u128|

### Converting Binary Signed Integers

#### i8 Positive Number

|SignBit|64|32|16|8|4|2|1|
|---|---|---|---|---|---|---|---|
|0|0|0|0|0|1|0|1|
- First identify if the first binary value is 0 which lets us know it's a positive number then we can just add the values
- Calculate the sum of the values (4 + 1 = 5)

#### i8 Negative Number
| |Sign Bit|64|32|16|8|4|2|1|
|---|---|---|---|---|---|---|---|---|
|Binary Format|1|1|1|1|1|0|1|1|
|Reversed|0|0|0|0|0|1|0|0|
- First identify if the first binary value is 1 which lets us know it's a negative number.
- Reverse The Binary Values 0->1 1->0
- Calculate the sum of the values and add 1 (4 + 1 = 5)
- Append The Negative Sign To The Value (-5)

>   **Calculating Ranges Of Numbers**
>   n = Bit Length
>   Start Range: -(2^(n-1))
>   End Range: 2^(n-1)-1

### Unsigned Integers
**Same Process As Positive Signed Signed Integers(The First Binary Value Is Added To The Sum Opposed To Being Used To Identify A Positive Or Negative Number)**
|128|64|32|16|8|4|2|1|
|---|---|---|---|---|---|---|---|
|1|0|1|0|1|0|1|1|

128+32+8+2+1 = 171

## Floats
|Float Type|Name|Bytes|
|---|---|---|
|f32|Single Float|4B|
|f64|Double|8B|


## Numeric Operaions
``` rust
fn main() {
    // addition
    let sum = 5 + 10;

    // subtraction
    let difference = 95.5 - 4.3;

    // multiplication
    let product = 4 * 30;

    // division
    let quotient = 56.7 / 32.2;
    let truncated = -5 / 3; // Results in -1

    // remainder
    let remainder = 43 % 5;
}
```

## Booleans
```rust
fn main() {
    let t = true;
    let t: bool = true;

    let f = false;
    let f: bool = false;
}
```

## Char
**Must Use Single Quotes**
```rust
fn main() {
    let c = 'z';
    let z: char = 'ℤ'; // with explicit type annotation
    let heart_eyed_cat = '😻';
}
```

## Tuples
**Length Of Tuples Cannot Change After Declaration**
```rust
fn main() {
    let tup: (i32, f64, u8) = (-500, 6.4, 3);

    // Destructuring A tuple
    let (x, y, z) = tup;
    // x = -500
    // y = 6.4
    // z = 3

    // Directory Access A Tuple
    let x = tup.0
    let y = tup.1
    let z = tup.2
}
```

## Arrays
**Explicitly Stored On Stack**
**Length Of Tuples Cannot Change After Declaration**
```rust
fn main() {
    // Creating Arrays
    let array = [ 1, 2, 3, 4, 5 ];

           // Five i32 Values
    let a: [i32; 5] = [ 1, 2, 3, 4, 5];

           // Five Values Set To 5
    let a = [3; 5];    

    // Accessing Arrays
    let array = [ 1, 2, 3, 4, 5 ];

    let val_one = a[0];
    let val_two = a[1];
}
```

# Functions
```rust
// Basic Function
fn function_name() {
    println!("Hello");
}

fn main() {
    function_name();
}

// One Parameter
fn function_name(x: i32) {
    println!("{x}");
}
fn main() {
    function_name(5);
}

// Multiple Parameters
fn function_name(x: i32, b: char) {
    print("{x} {b}");
}
fn main() {
    function_name(5, "C");
}

// Return Values
fn return_five() -> i32 {
    5 // Being this line is an expression as it doesn't end with a semi-colon the value will be returned within this scope
}
fn main() {
    let x = return_five();
}
```

# Comments
```rust
// Single Line Comment

/* 
Multi
Line
Comment
*/
```

# Control Flow
[Operators](https://doc.rust-lang.org/book/appendix-02-operators.html)


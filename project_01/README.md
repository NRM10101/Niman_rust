
# Rust Variables and Loops:

## 1. How do you declare a variable in Rust?
```rust
let x = 10; // Immutable by default
```

## 2. How do you make a variable mutable in Rust?
```rust
let mut x = 10; // Mutable variable
x = 15; // Now you can modify the value
```

## 3. What happens if you try to change an immutable variable?
Rust will throw a **compile-time error**, ensuring safety by preventing unintended modifications.

## 4. What are constants in Rust, and how are they different from immutable variables?
- **Constants**: Declared using `const`, must have a type, and are always immutable. They are defined outside functions and are evaluated at compile time.
  ```rust
  const PI: f64 = 3.1415;
  ```
- **Immutable variables**: Declared with `let` and evaluated at runtime.

## 5. What is shadowing in Rust?
Shadowing allows you to declare a new variable with the same name, effectively "hiding" the old one.
```rust
let x = 5;
let x = x + 1; // New variable shadows the old one
```

## 6. Can a variable's type change in Rust when shadowing?
Yes, shadowing can change the variable's type.
```rust
let x = "hello";
let x = x.len(); // Changes type from &str to usize
```

## 7. What are the default values for uninitialized variables in Rust?
Rust does **not** allow uninitialized variables. You must always initialize variables before use.

## 8. What is the difference between `let` and `let mut`?
- `let`: Immutable by default.
- `let mut`: Allows you to modify the value of the variable.

## 9. Can you make parts of a data structure mutable in Rust?
Yes, by using mutable references or `let mut`.
```rust
struct Data { value: i32 }
let mut data = Data { value: 10 };
data.value = 20;
```

## 10. Can variables be defined outside a function in Rust?
Yes, global constants or statics can be defined outside functions.
```rust
const GLOBAL: i32 = 42;
static mut COUNTER: i32 = 0;
```

## 11. What is `ref` and `&` in Rust variable handling?
- `&`: Borrow a reference to a value.
- `ref`: Pattern-matching syntax for borrowing.
```rust
let x = 10;
let ref y = x; // Borrow x as y
```

## 12. How does ownership affect variables in Rust?
- When ownership is transferred (moved), the original variable can no longer be used unless it's a `Copy` type.
```rust
let s1 = String::from("hello");
let s2 = s1; // Ownership moved
// println!("{}", s1); // Error
```

## 13. What is the difference between stack and heap variables?
- **Stack**: Fast, fixed-size data like primitives.
- **Heap**: Dynamically allocated, slower, and used for large or growing data like `String`.

## 14. How do variables interact with closures?
Closures can **capture** variables by reference, mutable reference, or by value, depending on the usage.

## 15. What are aliases and how do they work with variables?
Aliases (`&T`) allow multiple references to the same variable without taking ownership.

## 16. How do you create an infinite loop in Rust?
```rust
loop {
    // Code
}
```

## 17. How do you break out of a loop in Rust?
```rust
loop {
    break;
}
```

## 18. How do you continue to the next iteration of a loop in Rust?
```rust
for i in 1..10 {
    if i % 2 == 0 {
        continue;
    }
}
```

## 19. How do you work with nested loops in Rust?
Use labeled loops to control flow.
```rust
'label: loop {
    loop {
        break 'label;
    }
}
```

## 20. How do you break from a nested loop in Rust?
Use a label with `break`.
```rust
'label: loop {
    loop {
        break 'label;
    }
}
```

## 21. How do you iterate over a vector using a for loop in Rust?
```rust
let v = vec![1, 2, 3];
for val in &v {
    println!("{}", val);
}
```

## 22. What is the difference between iterating by reference and by value in a for loop?
- By reference: Borrows each element.
- By value: Consumes the vector, taking ownership of elements.

## 23. How do you use `iter()` and `iter_mut()` in Rust loops?
- `iter()`: Immutable reference.
- `iter_mut()`: Mutable reference.
```rust
for val in v.iter() {}
for val in v.iter_mut() {}
```

## 24. How can you optimize loops in Rust?
Use iterators and avoid unnecessary allocations or computations inside loops.

## 25. How does the for loop differ in performance from a while loop in Rust?
Performance is generally equivalent; differences depend on the implementation details.

## 26. True/False: Rust variables are immutable by default.  
**Answer**: True

## 27. Rust program declaring a mutable variable:
```rust
fn main() {
    let mut x = 10;
    x += 5;
    println!("{}", x); // Output: 15
}
```

## 28. Convert the formula \( y = 3x^2 + 2x + 1 \):
```rust
fn main() {
    let x = 2; // Example value
    let y = 3 * x.pow(2) + 2 * x + 1;
    println!("{}", y); // Output: 15
}
```

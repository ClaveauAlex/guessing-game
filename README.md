# Guess Game

With this project, you can see many concepts of Rust.

## Storing Values with Variables

We create inside our programm a variable to store the user input, like this:

`let mut guess = String::new()`

Now the program is getting interesting! There’s a lot going on in this little line. We use the let statement to create the variable. Here’s another example:

`let apples = 5;`

This line creates a new variable named apples and binds it to the value 5. In Rust, variables are immutable by default, meaning once we give the variable a value, the value won’t change. We’ll be discussing this concept in detail in the “Variables and Mutability” section in Chapter 3. To make a variable mutable, we add mut before the variable name:

```rust
let apples = 5; // immutable
let mut bananas = 5; // mutable
```

In full, the let mut guess = String::new(); line has created a mutable variable that is currently bound to a new, empty instance of a String. Whew!

## Receiving User Input

Recall that we included the input/output functionality from the standard library with use std::io; on the first line of the program. Now we’ll call the stdin function from the io module, which will allow us to handle user input:

```rust
io::stdin()
  .read_line(&mut guess)
```

If we hadn’t imported the io library with **use std::io;** at the beginning of the program, we could still use the function by writing this function call as **std::io::stdin**. The **stdin** function returns an instance of **std::io::Stdin**, which is a type that represents a handle to the standard input for your terminal.

Next, the line **.read_line(&mut guess)** calls the **read_line** method on the standard input handle to get input from the user. We’re also passing &mut guess as the argument to read_line to tell it what string to store the user input in. The full job of read_line is to take whatever the user types into standard input and append that into a string (without overwriting its contents), so we therefore pass that string as an argument. The string argument needs to be mutable so the method can change the string’s content.

The **&** indicates that this argument is a reference, which gives you a way to let multiple parts of your code access one piece of data without needing to copy that data into memory multiple times. References are a complex feature, and one of Rust’s major advantages is how safe and easy it is to use references. You don’t need to know a lot of those details to finish this program. For now, all you need to know is that, like variables, references are immutable by default. Hence, you need to write &mut guess rather than &guess to make it mutable. (Chapter 4 will explain references more thoroughly.)

# Handling potential Failure with Result

<!-- TODO inside Programming a Guessing game ! -->

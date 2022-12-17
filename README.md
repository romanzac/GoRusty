# GoRusty
### Rust learning curve flattener for Go developers


While Golang is a powerful language with carefully selected defaults, Rust is the exact opposite. 
Adopting Rust for Go developer could be a true nightmare. 
Rust is strict in memory allocation, variable lifetime, and racing conditions, while allowing to write 
same thing in many ways. My intention here is to share coding practice I found most efficient, leaving Rust compiler 
silent most of the time.  

 
### Assignments and Primitive Types
- Variables in Go are generally mutable, while Rust defaults to immutable. 
- Rust compiler has no default allocation values, those have to come from developer.
- Go variable could be declared upfront and allocated later, while in Rust we could do the same, it is not considered best practice, as uninitialized variables are in undefined state.

##### <p style="color:#33D1FF">- Go</p>
```go
var number int 

var x, y, z int

var s string = "Hello, World!"

var v uint64 = 100
```


##### <p style="color:#FF5833">- Rust</p>
```rust
let number = 0; // Type inferred as i32

let (x, y, z) = (0, 0, 0);

let s: &str = "Hello, World!";
let s: String = "Hello, World!".to_string();

let mut v = 100u64; // mut keyword tells compiler mutation is allowed
```

### Strings and Runes
- Strings in Go and Rust are both UTF8 encoded. Rust additionally introduces a slice of String called "str". Whenever we would like to pass an immutable string to a function, we use reference to &str type.

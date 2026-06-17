# CR libcbind

This is a bindings library for libc in Rust with libc automatically linked when compiling, as you dont need explicity linking against libc, the only thing needed is `rustc main.rs --extern cr_libcbind=/usr/share/cr/lib/libcr_libcbind.rlib`.

But what truly make this differ from the libc crate or any other method is that it provides native Rust types support, which means that if you want to run C functions in Rust, instead of having to do:

```rust
let message = CString::new("Hello World").unwrap();
unsafe {
    libc::printf(message.as_ptr(), pid);
}
```

Which is ugly and inconvenient, you can just do:

```rust
unsafe {
    cr_libcbind::printf("Hello World");
}
```

The CR libcbind will automatically handle the type conversion for you, allowing you to use libc in Rust smoothly.

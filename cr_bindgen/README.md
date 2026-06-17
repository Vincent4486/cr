# CR bindgen

This tool, unlike cr_libcbind is not just focused on 1 library, but it automatically generates Rust bindings from C header files and creates a `.rlib` file for you so that you can call C functions in Rust by including the `.rlib` file and _just calling them_, no need for extern, no need for type conversion.

You can use this tool by just doing:

```bash
cr_bindgen my_headers.h -o ./my_bindings.rlib
```

But this tool only creates the bindings, when you are compiling your Rust code, you still have to explicitly link against the pre-compiled libraries to make it work, like so:

```bash
rustc main.rs -L native=/path/to/libs -l static=foo
```

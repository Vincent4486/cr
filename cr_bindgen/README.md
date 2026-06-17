# CR bindgen

This tool, unlike cr_libcbind is not just focused on 1 library, but it automatically generates Rust bindings from C header files and creates a `.rlib` file for you so that you can call C functions in Rust by including the `.rlib` file and _just calling them_, no need for extern, no need for type conversion.

You can use this tool by just doing:

```bash
cr_bindgen my_headers.h -o ./my_bindings.rlib
```

But this tool also can instruct the Rust compiler to link to that library when compiling your source code so you don't have to explicitly do so, by just specifying the library associated with the header file.

# CR

CR (C+Rust), is a common library and compiler interface that _almost_ removes the friction from compiling/linking C code such as libc with Rust, and calling C functions in Rust code. This also removes all bloat from the Rust Cargo builders and Crates system.

I got fed up with how Rust restricts you with the build system as you can only use Cargo, and you have to write ugly bindings, and you are forced to compile all dependencies from source instead of just linking the already compiled system libraries.

The project has taken inspiration from Alexey Kutepov's [Crust](https://github.com/tsoding/Crust), but this project still _cares about your memory safety_ depending on how you interpret it.

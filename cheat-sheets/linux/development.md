# The Linux Development Cheat Sheet



## List exported symbols of libraries



###  nm

- -D: show dynamic symbols (dynamic libraries)
- -C: demangle (show C++ source identifiers)
- -U: show defined symbols only
- -g: show external only (static libraries)



### objdump

- -T: show dynamic symbols (dynamic libraries)
- -C: demangle (show C++ source identifiers)



### readelf

- -W: wide output (do not break lines into 80 columns)
- -s: show symbols
- --dyn-syms: show dynamic symbols (dynamic libraries)
- --demangle: demangle (show C++ source identifiers)

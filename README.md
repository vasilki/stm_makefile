# stm_makefile
Base makefile project

Information from:
https://eax.me/stm32-dev-environment/
http://mainloop.ru/stm32/stm32-stlink-linux.html
https://github.com/texane/stlink/issues/478

Environment:
STM32 NUCLEO-F401RE
Linux Mint 18.2 Sonya
STM32Cube_1.0 version 4.24.0.Repository is STM32Cube_FW_F4_V1.19.0.

For linking it is necessary to remove duplicates sources from the C_SOURCES variable of makefile (it is a bug of STM32CubeMX).
I should run "export LD_LIBRARY_PATH=/usr/local/lib" command in terminal, because have an error:
  st-info: error while loading shared libraries: libstlink.so.1: cannot open shared object file: No such file or directory.

This error could be checked by command "ldd /usr/local/bin/st-info":
	linux-gate.so.1 =>  (0xb776d000)
	libstlink.so.1 => not found
	libc.so.6 => /lib/i386-linux-gnu/libc.so.6 (0xb7597000)
	/lib/ld-linux.so.2 (0x800c6000)

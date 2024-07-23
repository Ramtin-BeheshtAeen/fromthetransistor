
# Projects based on .. recomendation:
#### Section 1: Intro: Cheating our way past the transistor -- 0.5 weeks
1. Describe how FPGAs are buildable using transistors.
2. Understand the LUTs and stuff.
3. Emulation -- Building on real hardware limits the reach of this course. Using something like Verilator will allow anyone with a computer to play.

#### Section 2: Bringup: What language is hardware coded in? -- 0.5 weeks
4. Blinking an LED(Verilog, 10) -- Your first little program! Getting the simulator working. Learning Verilog.
5. Building a UART(Verilog, 100) -- An intro chapter to Verilog, copy a real UART, introducing the concept of MMIO, though the serial port may be semihosting. Serial test echo program and led control.

#### Section 3: Processor: What is a processor anyway? -- 3 weeks
6. Coding an assembler(Python, 500) -- Happens in parallel with the CPU building. Teaches you ARM assembly. Initially outputs just binary files, but changed when you write a linker.
7. Building a ARM7 CPU(Verilog, 1500) -- Break this into subchapters. A simple pipeline to start, decode, fetch, execute. How much BRAM do we have? We need at least 1MB, DDR would be hard I think, maybe an SRAM. Simulatable and synthesizable.
8. Coding a bootrom(Assembler, 40) -- This allows code download into RAM over the serial port, and is baked into the FPGA image. Cute test programs run on this.

#### Section 4: Compiler: A “high” level language -- 3 weeks
9. Building a C compiler(Haskell, 2000) -- A bit more interesting, cover the basics of compiler design. Write in haskell. Write a parser. Break this into subchapters. Outputs ARM assembly.
10 Building a linker(Python, 300) -- If you are clever, this should take a day. Output elf files. Use for testing with QEMU, semihosting.
11. libc + malloc(C, 500) -- The gateway to more complicated programs. libc is only half here, things like memcpy and memset and printf, but no syscall wrappers.
12. Building an ethernet controller(Verilog, 200) -- Talk to a real PHY, consider carefully MMIO design.
13. Writing a bootloader(C, 300) -- Write ethernet program to boot kernel over UDP. First thing written in C. Maybe don’t redownload over serial each time and embed in FPGA image.

#### Section 5: Operating System: Software we take for granted -- 3 weeks
14. Building an MMU(Verilog, 1000) -- ARM9ish, explain TLBs and other fun things. Maybe also a memory controller, depending on how the FPGA is, then add the init code to your bootloader.
15. Building an operating system(C, 2500) -- UNIXish, only user space threads. (open, read, write, close), (fork, execve, wait, sleep, exit), (mmap, munmap, mprotect). Consider the debug interface you are using, ranging from printf to perhaps a gdbremote stub into kernel. Break into subchapters.
16. Talking to an SD card(Verilog, 150) -- The last hardware you have to do. And a driver
17. FAT(C, 300) -- A real filesystem, I think fat is the simplest
18. init, shell, download, cat, ls, rm(C, 250) -- Your first user space programs.

#### Section 6: Browser: Coming online -- 1 week
20. Building a TCP stack(C, 500) -- Probably coded in the kernel, integrate the ethernet driver into the kernel. Add support for networking syscalls to kernel. (send, recv, bind, connect)
21. telnetd, the power of being multiprocess(C, 50) --  Written in C, user can connect multiple times with telnet. Really just a bind shell.
22. Space saving dynamic linking(C, 300) -- Because we can, explain how dynamic linker is just a user space program. Changes to linker required.
23. So about that web(C, 500+) -- A “nice” text based web browser, using ANSI and terminal niceness. Dynamically linked and nice, nice as you want.

#### Section 7: Physical: Running on real hardware -- 1 week
24. Talking to an FPGA(C, 200) -- A little code for the USB MCU to bitbang JTAG.
25. Building an FPGA board -- Board design, FPGA BGA reflow, FPGA flash, a 50mhz clock, a USB JTAG port and flasher(no special hardware, a little cypress usb mcu to do jtag), a few leds, a reset button, a serial port(USB-FTDI) also powering via USB, an sd card, expansion connector(ide cable?), and an ethernet port. Optional, expansion board, host USB port, NTSC TV out, an ISA port, and PS/2 connector on the board to taunt you. We provide a toaster oven and a multimeter thermometer to do reflow. 
26. Bringup -- Compiling and downloading the Verilog for the board


# My Personal Road Map and resources
## Section 1: Intro
### Courses:
FPGA Design and Development (Coursera or Udacity)
Digital Design with Verilog (edX)
### Books:
FPGA-Based System Design by Wayne Wolf
Digital Design: Principles and Practices by John F. Wakerly

## Section 2: Bringup
### Courses:
Introduction to Verilog (Online platforms like Coursera)
Digital Logic Design (edX or MIT OpenCourseWare)
### Books:
Verilog HDL by Samir Palnitkar
The Verilog Hardware Description Language by Donald G. Bailey

## Section 3: Processor
### Courses:
1.Computer Architecture (Coursera or edX)
2.ARM Assembly Language Programming (Udacity)
### Books:
1.Computer Organization and Design by David A. Patterson and John L. Hennessy
2.Programming in ARM Assembly Language by Stephen Smith

## Section 4: Compiler
### Courses:
Compilers (Coursera or edX)
Programming Languages (Stanford Online)
### Books:
Compilers: Principles, Techniques, and Tools by Alfred V. Aho, Monica S. Lam, Ravi Sethi, Jeffrey D. Ullman
Modern Compiler Implementation in C/Java/ML by Andrew W. Appel

## Section 5: Operating System
### Courses:
Operating Systems and You (Coursera)
Operating Systems (MIT OpenCourseWare)
### Books:
Operating System Concepts by Abraham Silberschatz, Peter B. Galvin, and Greg Gagne
Linux Kernel Development by Robert Love

## Section 6: Browser
### Courses:
Networking Fundamentals (Cisco Networking Academy)
Web Development Basics (FreeCodeCamp)
### Books:
Computer Networking: A Top-Down Approach by James Kurose and Keith Ross
HTTP: The Definitive Guide by David Gourley

## Section 7: Physical
### Courses:
FPGA Design and Implementation (edX or Coursera)
Embedded Systems (Coursera or Udacity)
### Books:
The Art of Electronics by Paul Horowitz and Winfield Hill
FPGA Prototyping By VHDL Examples by Pong P. Chu


# Long-Term Reading and Viewing Plan

## Months 1-2: FPGA and Digital Design Fundamentals
- **Books:**
  - *FPGA-Based System Design* (Chapters 1-5)
  - *Digital Design: Principles and Practices* (Chapters 1-4)
- **Videos:**
  - FPGA Design and Development (Coursera)
  - Digital Logic Design (edX)
- **Activities:**
  - Complete basic FPGA projects using simulators.
  - Experiment with basic digital circuits.

## Months 3-4: Verilog and Hardware Description Languages
- **Books:**
  - *Verilog HDL* (Chapters 1-6)
- **Videos:**
  - Introduction to Verilog (Online Course)
- **Activities:**
  - Write and simulate Verilog programs (e.g., simple modules, LED blinking).

## Months 5-6: Computer Architecture Basics
- **Books:**
  - *Computer Organization and Design* (Chapters 1-4)
- **Videos:**
  - Computer Architecture (Coursera)
- **Activities:**
  - Build a simple ARM architecture model or simulator.

## Months 7-8: Assembly Language and Low-Level Programming
- **Books:**
  - *Programming in ARM Assembly Language* (Chapters 1-5)
- **Videos:**
  - ARM Assembly Language Programming (Udacity)
- **Activities:**
  - Develop small programs in ARM assembly to reinforce learning.

## Months 9-10: Compiler Design Basics
- **Books:**
  - *Compilers: Principles, Techniques, and Tools* (Chapters 1-5)
- **Videos:**
  - Compilers (Coursera)
- **Activities:**
  - Create a simple compiler or parser using Haskell.

## Months 11-12: Operating Systems Fundamentals
- **Books:**
  - *Operating System Concepts* (Chapters 1-6)
- **Videos:**
  - Operating Systems (MIT OpenCourseWare)
- **Activities:**
  - Implement simple OS functionalities and system calls in C.

## Months 13-14: Networking Principles
- **Books:**
  - *Computer Networking: A Top-Down Approach* (Chapters 1-5)
- **Videos:**
  - Networking Fundamentals (Cisco Networking Academy)
- **Activities:**
  - Set up networking projects (e.g., client-server applications).

## Months 15-16: Advanced FPGA and Embedded Systems
- **Books:**
  - *The Art of Electronics* (Chapters 1-6)
- **Videos:**
  - FPGA Design and Implementation (edX)
- **Activities:**
  - Design and build an embedded system project integrating multiple components.

## Months 17-18: Integration and Application
- **Activities:**
  - Review and synthesize knowledge from all previous sections.
  - Work on a comprehensive project that encompasses FPGA design, low-level programming, and OS development.
  - Engage in forums and communities to share progress and seek feedback.


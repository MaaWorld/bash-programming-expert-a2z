---
icon: window
layout:
  width: wide
  title:
    visible: true
  description:
    visible: true
  tableOfContents:
    visible: true
  outline:
    visible: true
  pagination:
    visible: true
  metadata:
    visible: true
  tags:
    visible: true
  actions:
    visible: true
---

# Application

## Computer Program <a href="#page-title" id="page-title"></a>

We’ve now gotten acquainted with operating systems. They are responsible for starting and running computer programs. The programs solve the user’s application tasks. For example, a text editor allows users to work with text.

A program is a set of elementary steps, called instructions. The computer performs these steps sequentially. It follows a strict order of actions and copes with complex tasks. Let’s consider how the computer launches and executes a program in detail.

### Computer memory <a href="#computer-memory" id="computer-memory"></a>

A hard disk stores all the program’s instructions. If the program is relatively small and simple, it fits in a single file. Complex applications, meanwhile, occupy several files.

Let’s suppose that we have a single file program. When we launch it, the OS loads the file into the computer memory, or the random-access memory (RAM). Then, the OS allocates a part of the processor’s time for the new task. This way, the processor performs the program’s instructions at specified intervals.

Let’s see how the OS loads the program into the RAM. We’ll start with how computer memory works.

#### Introduction to bytes and bits <a href="#introduction-to-bytes-and-bits" id="introduction-to-bytes-and-bits"></a>

The single unit of the computer memory is a **byte**. The byte is the minimum amount of information that the processor can reference and load into its memory.

The CPU can handle smaller amounts of data if we apply special techniques. We operate on bits, in this case. A **bit** is the smallest amount of information we cannot divide. We can imagine the bit as a single logical state that has one of two possible values. There are several ways to interpret them:

* 0 or 1
* True or False
* Yes or No
* \+ or -
* On or Off

Another way to imagine one bit is to compare it to a lamp switch. It has two possible states:

* The switch closes the circuit. Then, the lamp is on.
* The switch opens the circuit. Then, the lamp is off.

Eight bits make up a memory block of one byte.

<figure><img src="../.gitbook/assets/Screenshot 2026-06-17 082324.png" alt=""><figcaption></figcaption></figure>

#### The history of bits and bytes <a href="#the-history-of-bits-and-bytes" id="the-history-of-bits-and-bytes"></a>

Packaging bits in bytes raises questions. Operations with individual bits are possible. Why can the processor not refer to a specific bit in memory? This limitation has historical reasons.

The earliest computers mainly did arithmetic calculations. An example is the calculation of ballistic tables. We should use integers and fractional numbers to solve such a task. The computer does the same. However, a single bit is not enough to store a number in memory. Therefore, the computer needs memory blocks to store numbers. The bytes became such blocks.

Introducing bytes affected the architecture of processors. Engineers expected that the CPU would perform most operations over numbers. Therefore, they added a feature to load and process all bits of the number at once. This solution increased computers’ performance by orders of magnitude. At the same time, the loading of a single bit in the CPU is rare. This is because supporting this feature in hardware creates significant overhead. So, engineers excluded it from modern processors.

#### Why does a byte consist of eight bits? <a href="#why-does-a-byte-consist-of-eight-bits" id="why-does-a-byte-consist-of-eight-bits"></a>

The byte was equal to six bits in the first computers. Such a memory block was enough to encode all the English alphabet characters in uppercase and lowercase, numbers, punctuation marks, and mathematical operations. Over time, this size became insufficient.

**ASCII table**

Six-bits encodings were insufficient to represent control and box-drawing characters. So, these encodings were extended to seven bits in the early 1960s. The **ASCII** encoding appeared at that moment. It then became the standard for encoding characters. ASCII defines characters for codes from 0 to 127. The maximum seven-bit number, 127, limits this range.

Then, IBM released the computer IBM System/360 in 1964. In this computer, the size of a byte was eight bits. IBM chose this size to support old character encodings from past projects. The IBM System/360 computer was popular and widespread. Eventually, eight-bit packaging became the industry standard.

### Units of information <a href="#units-of-information" id="units-of-information"></a>

The table below shows frequently used units of information.

| **Title** | **Abbreviation** | **Number of bytes** | **Number of bits** |
| --------- | ---------------- | ------------------- | ------------------ |
| kilobyte  | KB               | 1000                | 8000               |
| megabyte  | MB               | 1000000             | 8000000            |
| gigabyte  | GB               | 1000000000          | 8000000000         |
| terabyte  | TB               | 10000000000         | 8000000000000      |

And the table below shows standard storage devices and their capacity.

| **Storage device** | **Capacity** |
| ------------------ | ------------ |
| Floppy disk 3.5"   | 1.44 MB      |
| Compact disk       | 700 MB       |
| DVD                | up to 17 GB  |
| USB flash drive    | up to 2 TB   |
| Hard disk drive    | up to 16 TB  |
| Solid State Drive  | up to 100 TB |

***

### Levels of Computer Memory

Learn why a computer needs different levels of memory for executing programs.

### Why the OS loads instructions into the RAM <a href="#why-the-os-loads-instructions-into-the-ram" id="why-the-os-loads-instructions-into-the-ram"></a>

In theory, the CPU can read program instructions directly from the disk drive. However, this never actually happens. Instead, the OS loads the instruction into RAM first. Then, the processor executes them. Why does this happen?

A modern computer has four levels in the memory hierarchy. Each level matches the red rectangle, as shown in the figure on the right. Each rectangle matches a separate device. The only exception is the CPU chip, which contains both registers and a memory cache. Those are separate modules of the chip.

The arrows in the figure represent data flows. Data transfer occurs only between adjacent memory levels. The processor works with data from its registers only. If the CPU needs something from the disk drive, it’s loaded in the following way:

1. Disk drive to RAM
2. RAM to the processor cache
3. Processor cache to processor registers

<figure><img src="../.gitbook/assets/image (1).png" alt="" width="325"><figcaption><p>Memory hierarchy</p></figcaption></figure>

When the CPU writes data back to the disk, it does so in reverse order of the steps above.

The memory levels differ from each other by the following parameters:

1. **Access speed** defines the amount of data we can read or write to the device per unit of time. Its units of measure are bytes per second (KBps).
2. **Capacity** is the maximum amount of data that a device can store. The units are bytes.
3. **Cost** is the price of a device in relation to its capacity. The units are dollars or cents per byte or bit.
4. **Access time** is the time between the moment the processor needs some data from the device, and when it receives it. Its units are the clock signals of the CPU.

These parameters vary for devices on each level of the memory hierarchy. The table below shows the ratio of parameters for modern storage devices.

| **Level** | **Memory**                            | **Capacity**              | **Access speed**     | **Access time**         | **Cost**          |
| --------- | ------------------------------------- | ------------------------- | -------------------- | ----------------------- | ----------------- |
| 1         | CPU registers                         | up to 1000 bytes          | -                    | 1 tick                  | -                 |
|           |                                       |                           |                      |                         |                   |
| 2         | CPU cache                             | from one KB to several MB | from 700 to 100 GBps | from 2 to 100 cycles    | -                 |
|           |                                       |                           |                      |                         |                   |
| 3         | RAM                                   | dozens of GB              | 10 GBps              | up to 1000 clock cycles | $ 10−910−9 /byte  |
|           |                                       |                           |                      |                         |                   |
| 4         | Disk drive (hard drive or solid drive | several TB                | 2000 Mbps            | up to 10000000 cycles   | $ 10−1210−12/byte |

The table above raises questions. We can read the data from the disk drive at high speed. Why is there no way to directly read this data to the CPU registers? Actually, there is a way. However, it leads to a significant performance drawback.

The high speed of accessing memory storage is not so crucial for performance in practice. The critical parameter here is the access time. It measures the idle time of the CPU until it receives the required data. We can measure this idle time in clock signals or cycles. Such a signal synchronizes all operations of the processor. The CPU requires roughly between 1 to 10 clock cycles to execute one instruction of the program.

Let’s suppose that the processor reads the program instructions directly from the hard disk. In this case, the execution of the simplest algorithm would take weeks. During most of this time, the processor would idle while it waits to read the operations. The hierarchical organization of memory speeds up access to the data that the processor needs.

### Memory level for a program <a href="#memory-level-for-a-program" id="memory-level-for-a-program"></a>

Let’s consider data flow between memory levels by example. Let’s suppose that we launch a simple program. It reads a file from the hard disk and displays its contents on the screen. Reading data from the disk occurs in the following steps:

1. The program reads data from the disk into the RAM.
2. The program loads data from the RAM to the CPU cache. The caching mechanism guesses which data the CPU will need next.
3. The processor reads the required data from the cache to the registers.
4. The CPU calls an API function of the system library.
5. The function receives the data to print on the screen.
6. The CPU provides the data to the function.
7. The system library refers to the video card driver, which displays the data on the screen.

The problem may occur when the processor calls a function and passes data to it. If the data is in the cache but not in registers, the CPU waits from 2 to 100 cycles, as shown in the table above. If data is in the RAM, the waiting time increases by an order of magnitude (up to 1000 cycles).

Let’s suppose that the read file is too big, and does not fit into the RAM entirely. The CPU can refer to the part of the file that’s not in the RAM. In this case, the CPU idle time increases by four orders of magnitude (up to 10,000,000 clock cycles). For comparison, the CPU could execute about 1,000,000 program instructions during this time.

Both CPU and disk drives use hardware caching mechanisms. The idea of caching for disk drives is to store some data in the small and fast access memory. This speeds up the process of reading and writing blocks of data. There are caching mechanisms on the software level, too. They are parts of the OS, in most cases.

All caching mechanisms significantly increase a computer’s performance. When such mechanisms make a mistake, it may lead to a CPU idle. Such a mistake is called a **cache miss**. Any cache miss is expensive from the performance’s point of view. Therefore, we must remember the memory hierarchy and caching mechanisms, and consider them when we develop algorithms. Some algorithms and data structures cause more cache misses than others.

The storage devices with lower access times are placed closer to the CPU. The figure on the right side demonstrates this principle.

For example, registers and cache form the internal CPU memory. They are part of the processor’s chip. The RAM is located next to the CPU on the motherboard, and the high-frequency data bus connects them. This data bus provides low access time.

The motherboard is the printed circuit board that connects computer components. We can plug in some chips right into the motherboard. However, there are devices that we should connect via cables there. The disk drive is an example of such a device. It connects to the motherboard via a relatively slow interface. There are several standards for such an interface: ATA, SATA, SCSI, PCI Express, and so on.

<figure><img src="../.gitbook/assets/image (2).png" alt="" width="395"><figcaption><p>PC motherboard</p></figcaption></figure>

The old motherboard models have an embedded chip that transfers data between the CPU and the RAM. This chip is called **northbridge**. Due to improved technology for chip manufacturing, the CPU has taken over the northbridge’s functions since 2011.

The **southbridge** is another motherboard chip. It is still in use today. The southbridge transfers data between the RAM and devices that are connected via slow interfaces like PCI, USB, SATA, and so on.

## Machine Code <a href="#page-title" id="page-title"></a>

### Computing process

Let’s suppose that the OS loads the contents of an executable file into the RAM. This file contains both the instructions and data of the program. Examples of the data are text strings, box-drawing characters, predefined constants, and so on.

Program instructions are called **machine code**. The processor executes them, one by one. A single instruction is an elementary operation on the data from the CPU registers.

The CPU has logical blocks to execute each type of instruction. The available blocks determine the operations that the CPU can perform. If the processor does not have an appropriate logical block to accomplish a specific instruction, it combines several blocks to do this job. The execution takes more clock cycles, in this case.

When the OS loads the program instructions and its data into the RAM, it allocates the CPU time slots for that. From this moment onwards, the program becomes a **computing process**, or **process**. The process refers to the running program, and the resources it uses. Examples of the resources are the memory area and OS objects.

#### Hex editors and binary code <a href="#hex-editors-and-binary-code" id="hex-editors-and-binary-code"></a>

There are some special programs to read and edit executable files. They are called **hex editors**. Such editors represent the program’s machine code in a **hexadecimal numeral system**.

The actual content of the executable file is **binary code**. This code is a sequence of zeros and ones. The hex editor translates them into hexadecimal for readability. The processor receives the instructions and data in binary code.

There are advanced programs to read machine code. They are called **disassemblers**. These programs guess how the program instructions look in terms of the CPU commands. We can get a better representation of the program using the disassembler, rather than the hex editor.

The same number appears differently in different numeral systems. The system determines the symbols and their order to write a number. For example, binary code allows 0 and 1 symbols only.

The figure on the right shows a set of numbers represented in binary (BIN), decimal (DEC), and hexadecimal (HEX).

<figure><img src="../.gitbook/assets/image (3).png" alt="" width="492"><figcaption><p>Numbers in decimal, hexadecimal and binary</p></figcaption></figure>

### Why a binary number system is used in programming <a href="#why-a-binary-number-system-is-used-in-programming" id="why-a-binary-number-system-is-used-in-programming"></a>

The binary numeral system and Boolean algebra are the basis of digital electronics. An electrical signal is the smallest portion of the information there.

When we work with such signals, we need a way to encode them. **Encoding** means associating specific numbers with the signal states. The signal has two states only. It can be present, or absent. Therefore, the simplest way to encode the signal is to take the first two integers: zero and one. Then, we use zero when there is no signal. Otherwise, we use number one. Such encoding is very compact. We can use one bit to encode one signal.

The basic element of digital electronics is a **logic gate**. It converts electrical signals. We can implement the logic gate through various physical devices. Examples of such devices include an electromagnetic relay, a vacuum tube, and a transistor. Each device has its own physics in the background. However, they work in the same way in terms of signal processing. This processing contains two steps:

1. Receive one or more signals as input
2. Transmit the resulting signal to the output

The signal processing follows the rules of Boolean algebra. This algebra has an elementary operation for each type of logic gate. When we combine logic gates together, we can calculate the result using a Boolean expression. Combining logic gates provides a complex behavior. We need it if our digital device follows some non-trivial logic. For example, the CPU is a huge network of logic gates.

When we deal with digital electronics, we should apply the binary numeral system. This way, we convert signal states to logical values that Boolean algebra operates. Then, we can calculate the resulting signals. The level of signals and logic gates is close to the computer hardware. We have to work on this level sometimes when we program. We can say that the hardware design dictates us to use the binary numeral system.

### Need of the hexadecimal system <a href="#need-of-the-hexadecimal-system" id="need-of-the-hexadecimal-system"></a>

The hardware works in the binary numeral system. Why do we need the hexadecimal system, then?

When we develop a program, we need decimal and binary systems only. Decimal is convenient for writing a general logic of the program. For example, we count repeating the same action in decimal.

We need the binary system when our program deals with computer hardware. For example, we send data to a device in binary format. There is one problem with binary. It is hard for humans to write, read, memorize, and pronounce the numbers in this system. Moreover, the conversion from decimal to binary takes effort.

The hexadecimal system solves both problems of representing and converting numbers. It is as compact and convenient as the decimal system. At the same time, we can easily convert a number from hexadecimal to binary form. Let’s convert a hexadecimal number to binary.

### Converting a binary number to hexadecimal <a href="#converting-a-binary-number-to-hexadecimal" id="converting-a-binary-number-to-hexadecimal"></a>

Let’s follow these steps to convert a number from binary to hexadecimal form:

1. Split the number into groups of four digits. Start the splitting from the end of the number.
2. If the last group is less than four digits, add zeros to the left side of the group.
3. Use the above table to replace each four-digit group with one hexadecimal number.

Here is an example of converting the binary number 110010011010111:

```
110010011010111 = 110 0100 1101 0111 = 0110 0100 1101 0111 = 6 4 D 7 = 64D7
```

<figure><img src="../.gitbook/assets/image (4).png" alt="" width="521"><figcaption><p>Binary number conversion to hexadecimal</p></figcaption></figure>

### Executing files of a program <a href="#executing-files-of-a-program" id="executing-files-of-a-program"></a>

Let’s come back to executing the program. The OS loads its executable file from the disk drive into the RAM. Then, the OS loads all libraries that the program requires. The special OS component, called the **loader**, performs both these tasks.

Due to preloading libraries, the CPU does not idle too much when the program accesses them. The instructions of the required library are already in the RAM. Therefore, the CPU waits for a few hundred clock cycles to access them. When the loader finishes their job, the program becomes a process. The CPU then executes it, starting from the first instruction.

The program’s instructions, resources, and required libraries occupy the RAM area while it runs. The OS clears this memory area when the program finishes. Then, other applications can use it.

## Source Code <a href="#page-title" id="page-title"></a>

#### Solving the human-readability issue <a href="#solving-the-human-readability-issue" id="solving-the-human-readability-issue"></a>

Machine code is a low-level representation of a program. This format of instructions and data is convenient for the processor. However, it’s hard for a human to write a program in machine code. It became even more complicated as computers’ performance increased, which allowed greater program complexity.

There are two types of special applications to solve this problem: **compilers** and **interpreters**. They translate the program from a human-readable language into machine code. Compilers and interpreters solve this task differently.

#### Programming languages <a href="#programming-languages" id="programming-languages"></a>

Nowadays, programs are written in **programming languages**. They differ from the **natural languages** that humans use to communicate.

Programming languages are formal and very limited. Using them, we can express only actions that a computer can perform. There are strict rules on how we should write these actions. For example, we can use a small set of words and combine them in specific orders.

The **source code** is the text of the program that is written in a programming language.

### Compiler and interpreter <a href="#compiler-and-interpreter" id="compiler-and-interpreter"></a>

The compiler and interpreter process source code differently. The **compiler** reads the entire program text, generates machine code instructions, and saves them on a disk drive. The compiler does not execute the resulting program on its own.

<figure><img src="../.gitbook/assets/image (22).png" alt=""><figcaption><p>How a compiler works</p></figcaption></figure>

The **interpreter** reads the source code in parts, generates machine code instructions, and executes them immediately. The interpreter temporarily stores its results in the RAM. When the program finishes, we lose these results.

<figure><img src="../.gitbook/assets/image (23).png" alt=""><figcaption><p>How an interpreter works</p></figcaption></figure>

{% stepper %}
{% step %}
### Compiler

#### Compilation process&#xD;

Let’s consider how the compiler works, step by step. Let’s suppose that we wrote a program. We saved its source code to a file on the hard disk. Then, we ran a compiler that fits the language we used.

Each programming language has a corresponding compiler or interpreter. The compiler reads our file, processes it, and writes the resulting machine code in the executable file on a disk. Now, we have two files: one with the source code, and one with the machine code. Every time we change the source code file, we should generate the new executable file. We can run the executable file to launch our program.

The figure below shows how the compiler handles a program written in C or C++.

<figure><img src="../.gitbook/assets/image (24).png" alt=""><figcaption><p>Compilation process</p></figcaption></figure>

#### Steps of compilation <a href="#steps-of-compilation" id="steps-of-compilation"></a>

The compilation process consists of two steps. The compiler does the first step. The second step is called **linking**. A special program, called the **linker**, performs it. The compiler creates intermediate **object files**. The linker uses them to produce an executable file.

Why can’t the compiler and the linker be combined into one program? There are several problems that keep that from happening: RAM size and dependencies.

#### Reaching RAM limit <a href="#reaching-ram-limit" id="reaching-ram-limit"></a>

The limited RAM size causes the first problem. There is a common practice to split source code into several files. Each file matches a separate part of the program that solves a specific task. This way, we simplify our work with the source code. The compiler processes these files separately. It produces an object file for each source code file, and they store the intermediate results of compilation.

If we combine the compiler and linker into one application, it becomes a tricky decision to store the intermediate results on the disk. If we do it, we get a bottleneck due to slow disk operations. In theory, we can keep all our data in the RAM and get good performance. However, we cannot do it. When we deal with a big program, the compilation process consumes all our RAM and crashes.

Let’s suppose that we have a combined compiler-linker that stores temporary files on the disk. In this case, storing temporary files creates performance overhead. At the same time, we do not get any benefits from it. This way, we avoid the RAM limitation. However, we can get the benefit by splitting the compiler and linker. Then, we simplify both applications and make it cheaper to support them. Therefore, the developers of compilers chose this way.

#### Resolving dependencies <a href="#resolving-dependencies" id="resolving-dependencies"></a>

The second problem of the compiler-linker application is to resolve dependencies. There are blocks of commands that call each other in the source code. Such references are called **dependencies**. Tracking them is the linker’s job.

When the compiler produces the object files, they contain machine code but not the source code. It’s simpler for the linker to track dependencies in the machine code.

If we combine the compiler and linker, we need extra passes through the whole program source code to resolve dependencies. The compiler needs much more time for a single pass over the source code than the linker needs to process the machine code. Therefore, when we have the compiler and linker separated, we speed up the overall compilation process.

The program can call blocks of commands from the library. The linker processes the library file together with the object files of our program, in this case. The compiler cannot process the library. Its file contains machine code, but not the source code. Therefore, the compiler does not understand it. Splitting the compilation into two steps resolves the task of using libraries, too.
{% endstep %}

{% step %}
### Interpreter&#xD;

#### Interpreting the program <a href="#interpreting-the-program" id="interpreting-the-program"></a>

Now, let’s suppose that we choose an interpreter to execute our program. We have the file with its source code on the disk drive. The file is ready for execution. When we run it, the OS loads the interpreter first. Then, the interpreter reads our source code file into the RAM and executes it line by line.

The translation of source code commands to machine code instructions happens in the RAM. Some interpreters save files with an intermediate representation of the program to the disk drive. It speeds up the program execution if we restart it. However, we always need to run an interpreter first to execute our program.

The figure below shows the process of interpreting the program.

The figure above implies that the interpreter works the same way as the compiler and linker combined into one application. The interpreter loads source code files into the RAM and translates them into machine code. Why are there no problems with the RAM overflow and dependency resolution?

The interpreter avoids problems because it processes the source code differently than the compiler does. The interpreter processes and executes the program code line by line. Therefore, it does not store the machine code of the whole program in memory. The interpreter processes the parts of the source code file that it requires at the moment. When the interpreter executes them, it unloads these parts and frees the corresponding RAM area.

Interpreting the program looks more convenient for software development than compiling. However, it has some drawbacks.

#### Interpreters work slowly <a href="#interpreters-work-slowly" id="interpreters-work-slowly"></a>

All interpreters work slowly. It happens because every time we run the program, the interpreter translates its source code to machine code. This process takes some time.

Another reason for the low performance of interpreters is disk operations. Loading the program’s source code from the disk drive into the RAM causes the CPU to idle. It may take up to 10,000,000 clock cycles to load.

Finally, the interpreter itself is a complex program. It requires some portion of the computer’s hardware resources to launch and work. Therefore, the computer executes both the interpreter and our program in parallel and shares resources between them. It is extra overhead that reduces the performance of our program.

#### Using the interpreter vs. the compiler <a href="#using-the-interpreter-vs-the-compiler" id="using-the-interpreter-vs-the-compiler"></a>

Interpreting the program is a slow process. Does this mean that compilation is better? The compiler generates an executable file with machine code. Therefore, we reach almost the program’s performance when we compile it or write machine code on our own. However, we pay for using the programming language at the compilation stage. A couple of seconds and a few megabytes of RAM are enough to compile a small program. When we compile a large project, such as the Linux kernel, it takes several hours. If we change the source code, we have to recompile the project and wait again for hours.

We must keep the overhead of interpreters and compilers in mind when we choose a programming language for our project. The interpreter is a good choice in the following cases:

* We want to develop a program quickly.
* We do not care about the program’s performance.
* We’re working on a small and relatively simple project.

The compiler is better in the following cases:

* We’re working on a complex and large project.
* Our program needs to work as fast as possible.
* We want to speed up the debugging of our program.

### Are programming languages worth using? <a href="#are-programming-languages-worth-using" id="are-programming-languages-worth-using"></a>

Both compilers and interpreters have overhead. Does it then make sense to discard a programming language and write a program in machine code? We do not waste our time waiting for compilation, in this case. Our program works as fast as possible. These benefits sound reasonable. However, we shouldn’t make hasty conclusions.
{% endstep %}
{% endstepper %}

## Development Tools <a href="#page-title" id="page-title"></a>

#### Choosing a language <a href="#choosing-a-language" id="choosing-a-language"></a>

Programming is an applied skill. If we want to learn it, we should choose a programming language and solve tasks. This is the only way to acquire practical skills.

We will use the Bash language in this course. This language is convenient for automating computer administration tasks. Here are a few examples of what we can do with Bash:

* Create data backups
* Manipulate directories and files
* Run programs and transfer data between them

Bash was developed in the Unix environment. So, it bears the imprint of the Unix philosophy. Despite its roots, we can also use Bash on Windows and macOS.

A Bash interpreter and a terminal emulator are needed to run the examples available on the Educative’s platform. Let’s discuss how to install them:

* If we want to run the examples locally, we can install a Bash interpreter and a terminal emulator on all modern operating systems. If we use Linux or macOS, we have a pre-installed Bash interpreter.
* For Windows, we can use the Minimal SYStem (MSYS). It is the MinGW (Minimalist GNU for Windows) component that includes Bash, a terminal emulator, and GNU utilities. They can be installed by following the steps [here](https://viewin.devpath.com/courses/guide-to-bash-programming/bash-on-windows).

### Bash Interpreter <a href="#bash-interpreter" id="bash-interpreter"></a>

Bash is a script programming language with the following features:

1. It is an interpreted language.
2. It operates existing programs or high-level commands.
3. We can use it as a shell to access the OS functions.

### Terminal emulator <a href="#terminal-emulator" id="terminal-emulator"></a>

Bash shell is not a regular GUI application. It does not even have its own window. When we need the shell, we launch the terminal emulator program. Then, we can work with Bash in the terminal window.

An **emulator** is a program that mimics the behavior of another program, OS, or device. The emulator solves the compatibility task. For example, let’s say we want to run a Windows program on Linux. There are several ways to do that. One option is to use an emulator of the Windows environment for Linux. One is called **Wine**. Wine provides its own version of the Windows system libraries. When we run our Windows program on Linux using Wine, Wine uses these libraries and runs normally as if it were working on Windows.

The terminal emulator solves the compatibility task, too. Command-line programs are designed to work through a terminal device. Nobody uses such devices today. Cheap personal computers and laptops replaced them. However, there are still many programs that require a terminal to work. We can run them by using the terminal emulator. It uses the shell to pass data to the program. When the program returns some results, the shell passes them to the terminal emulator. Then, the emulator displays the results on the screen.

The figure below explains the interaction between input and output devices, the terminal emulator, the shell, and the command-line program.

<figure><img src="../.gitbook/assets/image (25).png" alt=""><figcaption><p>The workflow of the terminal emulator</p></figcaption></figure>

## Command Interpreter <a href="#page-title" id="page-title"></a>

#### Modes of interpreters <a href="#modes-of-interpreters" id="modes-of-interpreters"></a>

All interpreters have two working modes: non-interactive and interactive.

When we choose the **non-interactive mode**, the interpreter loads the source code file from the disk and executes it. We do not need to type any commands or control the interpreter. It does everything on its own.

When we choose the **interactive mode**, we type each command to the interpreter manually. If the interpreter is integrated with the OS and works in the interactive mode, it is called a **command shell** or shell.

A command shell provides access to the settings and functions of the OS. We can perform the following tasks using it:

* Run programs and system services
* Manage the file system
* Control peripherals and internal devices
* Access the kernel features

## Command-line Interface <a href="#page-title" id="page-title"></a>

Demand for the CLI

Why would somebody learn the command-line interface (CLI) today? It appeared 40 years ago for computers that are thousands of times slower than those of today. Then, the graphical interface supplanted CLI on PCs and laptops. Everybody prefers to use a GUI nowadays.

The CLI seems to be outdated technology. However, this statement is incorrect. There must be a reason why developers include Bash in all modern macOS and Linux distributions.

CLI

Windows also has a command shell called **Cmd.exe**. Microsoft replaced Cmd.exe with **PowerShell** in 2006. Just think about this for a moment. The developer of the most popular desktop OS created a new command shell in the 2000s. All these points confirm that CLI is still in demand

### Shell capabilities <a href="#shell-capabilities" id="shell-capabilities"></a>

What tasks does the shell perform in modern OSs? First of all, it’s a tool for system administration. The OS consists of the kernel and software modules. These modules are libraries, services, and system utilities. Most of the modules have settings and special modes of operation. We do not need them in our daily work. Therefore, we cannot access these settings via GUI in most cases.

> The Bash shell has good integration with Linux and macOS. We can access most OS functions using Bash there. However, it does not work as smoothly with Windows. Microsoft offers us their own PowerShell, but we’ll study Bash in this course for two reasons.

> * First, it’s compatible with the POSIX standard.
> * Second, Bash is more common than PowerShell. We can use it on all modern OSes.

If the OS fails, we need system utilities to recover it. They have a command-line interface because a GUI often is not available after the failure.

Besides the administrative tasks, we need a CLI when we connect computers over a network. There are GUI programs for such connections—for example, TeamViewer and Remote Desktop-but they require a stable and fast network connection to work well.

If our connection is not reliable, GUI programs are slow and often fail. The command-line interface does not have such a limitation. The remote server receives our command even if the link is poor.

We might say that a regular user does not deal with administrative tasks and network connections. Even if we don’t personally have such tasks, using command shell speeds up our daily work with the computer. Here are few things that we can do more effectively with CLI than with GUI:

* Operations on files and directories
* Creating data backups
* Downloading files from the internet
* Collecting statistics about our computer’s resource usage

A few things that we can do more effectively with CLI

### Strength of CLI <a href="#strength-of-cli" id="strength-of-cli"></a>

Let’s go over an example to explain the effectiveness of CLI. Let’s suppose we rename several files on the disk. We add the same suffix to their names. If we have dozens of files, we can do this task with Windows Explorer in a couple of minutes.

Now, let’s imagine that we rename thousands of files this way. We will spend the whole day doing that with Explorer. If we use the shell, we need to launch a single command and wait for several seconds. It will rename all our files automatically.

The example with renaming files shows that the strength of the CLI is scalability. **Scalability** means that the same solution handles both small and large amounts of input data well. The solution here refers to a command when we’re talking about the shell. The command renames both ten or a thousand files with the same speed.

### Benefits of learning CLI <a href="#benefits-of-learning-cli" id="benefits-of-learning-cli"></a>

Let’s go through a few benefits of learning CLI.

#### Changing multiple files <a href="#changing-multiple-files" id="changing-multiple-files"></a>

Experience with the command-line interface is a great benefit for any programmer. When we develop a complex project, we manage plenty of text files with the source code. We use the GUI editor to change a single file. It works well until we do not need to introduce the same change in many files.

For example, maybe we need to insert the new version of the license information in the file headers. We waste our time solving such a task with the editor. Command-line utilities make this change much faster.

We need to understand the CLI to deal with compilers and interpreters. These programs usually do not have a graphical interface. We should run them via the command line and pass the names of the source code files. The reason for such workflow is the poor scalability of the GUI. If we have plenty of source code files, we cannot handle them effectively via the GUI.

#### Integrated development environments <a href="#integrated-development-environments" id="integrated-development-environments"></a>

There are special programs to edit and compile source code. Such programs are called **integrated development environments (IDEs)**. We can compile a big project using an IDE and its GUI.

However, an IDE calls the compiler via the command line internally. Therefore, we should deal with the compiler’s CLI if we want to change its options or working mode.

#### Helper utilities <a href="#helper-utilities" id="helper-utilities"></a>

If we don’t have much programming experience, knowing the CLI encourages us to develop helper utilities. This happens because writing a program with a command interface is much faster than with a GUI. The speed of development is essential when solving one-off tasks.

Here is an example situation when we would need to write a helper utility. Let’s suppose that we have to make a massive change in the source code of our project. We can do it with an IDE by repeating the same action many times.

Another option is to spend time writing a utility that will do this job. We should compare the required time for both ways of solving our task. If we write a GUI helper utility, it takes more time than for a CLI utility. This can lead us to the wrong decision to solve the task manually using an IDE. Automating our job is the best option in most cases. It saves our time and helps us avoid mistakes.

It’s up to us to decide if we need to learn the CLI. We have only considered a few examples of its benefits. It’s hard to switch from using a GUI to a CLI. We have to re-learn many things that we do with Windows Explorer regularly. But once we get the hang of the command shell, our new productivity levels may surprise us.<br>

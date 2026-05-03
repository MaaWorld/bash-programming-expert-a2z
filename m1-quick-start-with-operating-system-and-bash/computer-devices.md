---
description: >-
  Learn about internal and peripheral devices. We’ll also discuss a component of
  the Windows OS.
icon: computer-mouse
---

# Computer Devices

### Peripheral and internal devices <a href="#peripheral-and-internal-devices" id="peripheral-and-internal-devices"></a>

What is the difference between peripheral and internal devices?

**Peripherals** are all devices that are responsible for permanently inputting, outputting, and storing data. Some examples are as follows:

* Keyboard
* Mouse
* Microphone
* Monitor
* Speakers
* Hard drive

**Internal** devices are responsible for processing data—in other words, for executing programs. Some examples are as follows:

* Central Processing Unit (CPU)
* Random-Access Memory (RAM)
* Video card or graphics processing unit (GPU)

<figure><img src="../.gitbook/assets/image (12).png" alt="" width="496"><figcaption></figcaption></figure>

The OS provides access to the computer’s hardware. At the same time, the OS also provides functionality besides the hardware management to share with users’ applications. The system libraries grow from the program modules to serve the devices. However, some libraries of modern OSs provide complex algorithms for processing data. Let’s consider an example.

### Graphics device interface <a href="#graphics-device-interface" id="graphics-device-interface"></a>

The **Graphics Device Interface (GDI)** is a component of the Windows OS. It provides algorithms to manipulate graphic objects. The GDI lets us create a user interface for our application with minimal effort. Then, we can use the monitor to display this interface.

The system libraries with useful algorithms (like GDI) are the software resources of the OS. These resources are already installed on our computer. We just need to know how to use them. Besides this, the OS provides access to third-party libraries and their algorithms. We can install these libraries separately and use them in our applications.

### OS tasks <a href="#os-tasks" id="os-tasks"></a>

The OS manages hardware and software resources. Also, it organizes the joint work of running programs. The OS performs several non-trivial tasks to launch an application. Then, the OS tracks its work. If the application violates some agreements, like memory usage, the OS terminates it. It also launches and executes programs, which we will later consider in detail.

### OS features <a href="#os-features" id="os-features"></a>

If the OS is multi-user, it controls access to the data. This is an important security feature. This feature lets us access the following file system objects:

* Files and directories we own
* Files and directories that somebody shares with us

A multi-user OS allows several people to use the same computer safely.

1. In summary, the modern OS has the following features:
2. It provides and manages access to the computer’s hardware resources.
3. It provides its own software resources.
4. It launches applications.
5. It organizes the interaction of applications with each other. It controls access to users’ data.

It is impossible to launch several applications in parallel without the OS. When we develop an application, we have no idea how a user will launch it. The user can launch our application together with another one. In such cases, the OS responds by launching all applications. This means that the OS has enough information to allocate computer resources properly.

### Modern OSs <a href="#modern-oss" id="modern-oss"></a>

Now, let’s consider modern operating systems. Today, we can pick any OS and get very similar features. However, their developers follow different approaches. This leads to implementation differences that can be important for some users.

The software architecture refers to the implementation aspects of specific software and the solutions that led to them.

#### Features of modern OSs <a href="#features-of-modern-oss" id="features-of-modern-oss"></a>

All modern OSs have two features that determine the way users interact with them. These features are:

* Multitasking
* Graphical user interface

### Multitasking <a href="#multitasking" id="multitasking"></a>

All modern OSs support multitasking. This means they can execute multiple programs in parallel. The systems with this feature displaced the OSs without it. Why is multitasking so important?

#### Efficient usage of computers <a href="#efficient-usage-of-computers" id="efficient-usage-of-computers"></a>

The challenge of efficient usage of computers arose in the 1960s. Computers were relatively expensive at that time. Only large companies and universities were able to buy them. These organizations counted every minute they worked with their machines. They could not accept any idle time of the hardware because of its huge cost.

### Batch processing <a href="#batch-processing" id="batch-processing"></a>

Earlier operating systems executed programs one after another without delays. This approach saved time originally spent switching computer tasks. If we were to use such an OS, we would need to prepare several programs and their input data in advance. Then, we would have to write the programs and their data onto a storage device, like a magnetic tape, and load the tape into the computer’s reading device. Afterward, the computer would execute the programs sequentially and print their results to an output device—for example, a printer. This mode of operation is called **batch processing**.

Batch processing increased the efficiency of computers in the 1960s. by automating program loading. Therefore, human operators became unnecessary for this task. However, the computers still faced **bottlenecks**.

> A bottleneck is a component or resource of an information system that limits its overall performance or bandwidth.

The computational power of processors increased significantly every subsequent year. However, the speed of peripherals remained almost the same. This difference in speed led to CPUs often idling while waiting for input or output.

#### Why the CPU waits <a href="#why-the-cpu-waits" id="why-the-cpu-waits"></a>

Why did the CPU idle and wait for peripheral devices? Let’s go over an example that can clarify this. Imagine that a computer from the 1960s runs programs one by one. It reads data from a magnetic tape and prints the results on the printer. The OS loads each program and executes its instructions. Then, it loads the next one, and so on.

The problem occurs when the computer reads the data and prints the results. At the CPU’s scale, a huge amount of time is required to read the data on the magnetic tape. This time is enough for the processor to perform many calculations. However, the processor does not do that. The reason is that the currently loaded program occupies all computer resources. The same CPU idling happens when the computer prints the results because the printer is a slow mechanical device.

### Multiprogramming <a href="#multiprogramming" id="multiprogramming"></a>

Slow peripheral devices cause the CPU to idle. This problem led OS developers to the concept of **multiprogramming**. This concept implies that the OS loads several programs into the computer memory at the same time. The first program works as long as all resources it needs are available. It stops execution once a required resource is busy. Then, the OS switches to another program.

We’ll go over an example. Let’s suppose that our application wants to read data from our hard disk. While the disk controller reads the data, it’s busy. It cannot process the following requests from the program. So, the application waits for the controller. In this case, the OS stops executing it and switches to the second program. The computer then executes the second program to its end or until it has all the required resources. When the second program finishes or stops, the OS switches tasks again.

Multiprogramming differs from modern OSs’ multitasking. Multiprogramming fits the batch processing mode very well. However, this load balancing concept is not suitable for interactive systems.

### What is an interactive system? <a href="#what-is-an-interactive-system" id="what-is-an-interactive-system"></a>

An **interactive system** considers each user action—for example, a keystroke—an event. The system should process events as they happen. Otherwise, the user cannot work with the system.

We’ll go over an example of workflow with an interactive system. Let’s suppose that we type text in a document. We press a key and expect to see the corresponding symbol on the screen. If the computer requires several seconds to process our keystroke and display the symbol, we cannot work efficiently. Most times, we will wait and check if the computer processed our keystroke or not.

Multiprogramming cannot handle events in the interactive system. This is because we cannot predict when task switching occurs. The OS switches tasks when a program finishes or when it requires a busy resource. Let’s suppose that our text editor is not an active program now. Then, we don’t know when it will process our keystroke. It can happen in a second, or in several minutes. This is unacceptable for a good user interface.

### Task scheduler <a href="#task-scheduler" id="task-scheduler"></a>

The multitasking concept solves the task of processing events in interactive systems. There were several versions of multitasking before it reached its current state. Modern OSs displace multitasking with pseudo-parallel task processing. The idea behind it is to allow the OS to choose an appropriate task for execution at the given moment. The OS takes into account the priorities of the running programs. Therefore, a higher priority program receives hardware resources more often than a lower priority one. The OS kernel provides this task-switching mechanism. It is called a **task scheduler**.

### Pseudo-parallel processing <a href="#pseudo-parallel-processing" id="pseudo-parallel-processing"></a>

**Pseudo-parallel processing** means that the computer executes one task only at any given time. However, the OS switches tasks so quickly that we can suppose the processing of several programs at once. This concept allows the OS to react immediately to any event, even though every program and OS component uses hardware resources at strictly defined moments.

There are computers with multiple processors, or with multi-core processors. Only these computers can execute several programs at once. The number of the running programs is approximately the number of cores of all processors.

The preemptive multitasking mechanism with constant task switching works well on such systems. It’s a universal approach that balances the load regardless of the number of cores. This way, the computer responds to the user’s actions quickly, and the number of processor cores does not matter.

\-----x-----x-----x-----x-----x-----x------x-----x-----x-----x-----x-----x-----x-----x-----x-----x-----

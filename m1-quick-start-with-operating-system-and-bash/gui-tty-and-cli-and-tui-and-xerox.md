---
icon: rectangle-terminal
---

# GUI: TTY & CLI & TUI & Xerox | OS Versions

### User interface <a href="#user-interface" id="user-interface"></a>

We will consider OSs for PCs and notebooks only. Apart from multitasking, they provide a **graphic user interface (GUI)**. This interface is the way to interact with the system: we launch applications, configure computer devices and OS components, all via the user interface. Let’s take a look at its history and how it reached its current state.

### History of UI <a href="#history-of-ui" id="history-of-ui"></a>

Nobody worked with commercial computers interactively before 1960. Digital Equipment Corporation implemented the interactive mode for their minicomputer **PDP-1** in 1959. It was a fundamentally new approach. Before that, IBM computers dominated the market in the 1950s. They worked in batch processing mode only. This mode automated program loading and provided high performance for tasks involving calculation.

#### The SAGE project <a href="#the-sage-project" id="the-sage-project"></a>

The idea of interactive work with computers appeared first in the SAGE (Semi-automatic Ground Environment) military project by the US Air Force. The goal of the project was to develop an automated air defense system to detect Soviet bombers.

When working on the SAGE project, engineers faced an interesting problem. The user of the system needed to analyze data from radars in real-time and react as quickly as possible. However, existing methods of interaction with computers didn’t fit this task. They did not let the computer show information to the user in real-time and receive the user’s input at any moment.

Engineers then came to the idea of interactive mode. They implemented it in the first interactive computer **AN/FSQ-7** in 1955. The figure below shows this computer.

<figure><img src="../.gitbook/assets/Screenshot 2026-05-03 093324.png" alt="" width="563"><figcaption><p>AN/FSQ-7 used a monitor with a cathode-ray tube to display information from radar</p></figcaption></figure>

The computer used a monitor with a cathode-ray tube to display information from radar. The light pen allowed the user to command the system.

#### Benefits of interactive mode <a href="#benefits-of-interactive-mode" id="benefits-of-interactive-mode"></a>

The software development workflow differs when we use an interactive mode. We prepare our program and load it to the computer. Then, it launches the program and shows us results. Immediately, we can analyze a possible error, fix it, and relaunch the program. This workflow significantly accelerates the processes of software development and debugging tasks. Now, we spend a few hours on a task that would require days with batch processing.

#### Challenges of the interactive mode <a href="#challenges-of-the-interactive-mode" id="challenges-of-the-interactive-mode"></a>

Interactive mode brought new challenges for computer engineers. This mode required a system that reacted to user actions immediately. Also, providing a short reaction time required a new load-balancing mechanism. The concept of multitasking became a solution to this problem.

#### Alternatives to the interactive mode <a href="#alternatives-to-the-interactive-mode" id="alternatives-to-the-interactive-mode"></a>

There are alternatives to multitasking that still provide an interactive mode. For example, there are interactive single-tasking OSs like MS-DOS. MS-DOS was the system for cheap PCs of the 1980s.

<figure><img src="../.gitbook/assets/Screenshot 2026-05-03 093538.png" alt="" width="375"><figcaption></figcaption></figure>

However, it was inadvisable to apply single-tasking in the 1960s when computers were too expensive. These computers executed many programs in parallel in a concept called **time-sharing**. It allowed several users to share expensive hardware resources. The single-tasking approach does not fit such a use case because it is not compatible with time-sharing.

### Single-tasking OSs <a href="#single-tasking-oss" id="single-tasking-oss"></a>

When the first relatively cheap personal computers appeared in the 1980s, they used single-tasking OSs. Such systems required fewer hardware resources than their analogs with multitasking. Despite their simplicity, single-tasking OSs supported interactive mode for the currently running program. This mode became especially attractive for PC users.

When interactive mode became more and more popular, computer engineers faced a new challenge. The existing devices to interact with computers turned out to be inconvenient. Magnetic tapes and printers were widespread through the 1950s and early 1960s. They did not fit interactive mode absolutely.

## TTY and CLI <a href="#page-title" id="page-title"></a>

Learn about teletype and command-line interface.

### Teletype <a href="#teletype" id="teletype"></a>

The **Teletype (TTY)** became a prototype of a device for interactive work with a computer. The figure on the right shows the Model 33 Teletype, one of the most popular devices of the 1960s. It is an electromechanical typewriter. Once two teletypes are connected, operators can send text messages to each other. The sender types text on their device. The keystrokes are transmitted to the receiver’s device, which prints out each received letter on paper.

Computer engineers connected the Teletype to computers. This solution allowed the user to send text commands to the machine and receive results. Such a workflow became known as a **command-line interface (CLI)**.

The Teletype used the printer as an output device. It worked very slowly and required around 10 seconds to print a single line. The next step to develop the user interface was to replace the printer with the monitor.

<figure><img src="../.gitbook/assets/image (13).png" alt="" width="375"><figcaption></figcaption></figure>

This increased the data output speed by several times. The new device with a keyboard and monitor was called the **terminal**. It replaced Teletypes in the 1970s.

### The command-line interface <a href="#the-command-line-interface" id="the-command-line-interface"></a>

The figure below shows a modern command-line interface. We can see the **terminal emulator** application there. This application emulates the terminal device for the sake of compatibility. It allows us to run programs that work with the real terminal only.

The emulator application in the figure below is called the terminal. The Bash command-line interpreter is running in the terminal window. The window displays the results of the `ping` and `ls` programs.

<figure><img src="../.gitbook/assets/image (16).png" alt="" width="563"><figcaption><p>Command-line interface</p></figcaption></figure>

#### Pros of the CLI <a href="#pros-of-the-cli" id="pros-of-the-cli"></a>

The command-line interface is still in demand today. It has several advantages over the graphical interface, such as the following:

* The CLI does not require as many resources as the GUI.
* The CLI runs reliably on low-performance embedded computers, as well as on powerful servers.
* If we use the CLI to access the computer remotely, we can use a low-bandwidth communication channel. The server will receive our commands in this case.

#### Cons of the CLI <a href="#cons-of-the-cli" id="cons-of-the-cli"></a>

The command-line interface has some disadvantages.

* Learning to use the CLI effectively is difficult and time-consuming.
* The CLI has very limited features to output data. It does not allow us to draw visually appealing graphs or tables.

The first disadvantage is that we need to remember a great number of commands. Moreover, each command has several modes that change its behavior. Therefore, we must keep those in mind, too. It takes some time to remember at least a minimum set of commands for daily work.

The second disadvantage is a consequence of CLI limitations. It allows us to use only alphanumeric symbols and special characters for input and output data. It does not support any graphical objects.

## TUI and Xerox

### Text-based user interface <a href="#text-based-user-interface" id="text-based-user-interface"></a>

We can choose to make the command-line interface more user-friendly, by giving a hint to the user about available commands. This is done in the **text-based user interface (TUI)**.

The TUI uses box-drawing characters along with alphanumeric symbols and special characters. The box-drawing characters display the graphic primitives—lines, rectangles, triangles, etc.—on the screen. Primitives guide the user through the available actions they can take with the application.

The figure below shows a typical text-based user interface. There is an output of system resource usage by the htop program.

<figure><img src="../.gitbook/assets/image (15).png" alt="" width="563"><figcaption><p>Text-based user interface</p></figcaption></figure>

The additional performance gain of computers allowed OS developers to replace box-drawing characters with real graphic elements. Examples of such elements include windows, icons, buttons, and so on. It was the moment when the full-fledged graphical interface was introduced. Modern OSs provide this kind of interface.

The figure below demonstrates the Windows GUI. We can see the desktop. There are windows of three applications there. The applications are Explorer, Notepad, and Calculator. They work in parallel.

<figure><img src="../.gitbook/assets/image (17).png" alt="" width="563"><figcaption><p>windows GUI</p></figcaption></figure>

### The first GUI <a href="#the-first-gui" id="the-first-gui"></a>

The first GUI appeared in the Xerox Alto minicomputer (see the figure on the right). It was developed in the Xerox PARC research center in 1973.

However, the graphical interface did not spread widely until the 1980s. The reason is that a GUI requires a lot of memory and high computer performance. PCs with such features were too expensive for regular users at that time.Apple produced the first relatively cheap PC with a GUI in 1983, called Lisa.

<figure><img src="../.gitbook/assets/image (18).png" alt="" width="334"><figcaption><p>Minicomputer Xerox Alto</p></figcaption></figure>

\-----x-----x-----x-----x-----x-----x------x-----x-----x-----x-----x-----x-----x-----x-----x-----x-----

## OS Versions

### Families of OSes <a href="#families-of-oses" id="families-of-oses"></a>

There are three OS families that dominate the market today:

* Windows
* Linux
* macOS

The term **family** means several OS versions that follow the same architectural solutions. Therefore, most functions in these versions are implemented in the same manner.

#### Backward compatibility problem <a href="#backward-compatibility-problem" id="backward-compatibility-problem"></a>

The developers of an OS family follow the same architecture. They do not offer something fundamentally new in the latest versions of their product.

This is because changes in modern OSs happen gradually and slowly. The reason for this is a **backward compatibility problem**. This compatibility means that newer OS versions provide the features of older versions. Most existing programs require these features for their work. We can view backward compatibility as an optional requirement, but it’s a severe limitation for software development. Let’s find out why that is.

#### Limitation for software development <a href="#limitation-for-software-development" id="limitation-for-software-development"></a>

Let’s imagine that we write a program for Windows and sell it. Sometimes, users encounter errors in the program. We receive bug reports and fix the errors. Also, we add new features from time to time.

Our business goes well until the new Windows version comes. Let’s assume that Microsoft changes its architecture completely. Therefore, our program does not work on the new OS version. This leads the users of our program to the following options:

* They update Windows and wait for the new version of our program that works there.
* They do not update Windows and continue to use our program.

If users need our program for daily work, they may refuse the Windows update. This is because using the program is more important to them than getting new OS features.

Windows is a very popular and widespread OS. This means that there are many programs like ours. Their developers are likely to make the same decision as us. As a result, nobody updates to the new Windows version. This situation demonstrates the backward compatibility problem and the limitation it puts on software development. This problem forces OS developers to be careful with changing their products. The best solution for them is to make a family of similar OSs.

### Influence of user application <a href="#influence-of-user-application" id="influence-of-user-application"></a>

There is a significant influence of user applications on OS development. For example, Windows and IBM computers owe their success to a table processor called **Lotus 1-2-3**. We need both IBM PC and Windows to launch Lotus 1-2-3. For the purpose of using Lotus 1-2-3, users bought both the computer and OS. The specific combination of the hardware and software is called the **computing platform**. A popular application that brings the platform to a broad market is called a **killer application**.

<figure><img src="../.gitbook/assets/image (19).png" alt="" width="563"><figcaption></figcaption></figure>

The tabular processor **VisiCalc** was another killer application. It promoted the distribution of the Apple II computers. Free compilers for the C, Fortran and Pascal languages helped Unix OS become popular in university circles.

A killer application was behind each of the modern OS families. This application gave these OSs their initial success. Further distribution of the OS happened thanks to the **network effect**. This effect means that developers tend to choose the most widespread computing platforms for their new applications.

### Differences between the OS families <a href="#differences-between-the-os-families" id="differences-between-the-os-families"></a>

Windows and Linux are remarkable because they do not depend on the hardware. This means that we can install them on any modern PC or laptop. However, macOS runs on Apple computers only. If we want to use macOS on different hardware, we would need an unofficial modified version of the OS.

### Effect of OS design decisions <a href="#effect-of-os-design-decisions" id="effect-of-os-design-decisions"></a>

Hardware compatibility is an example of the design decisions of OS development. There are many such decisions. Together, they define the features and design of each OS family.

There is another important point for software development besides the OS design. The OS dictates the infrastructure, or development tools, for the programmer. Examples of these tools are an integrated development environment (IDE), a compiler, a build system, etc.

Tools, together with the OS API, impose some design decisions for the applications. This leads to a specific culture for program development. We must keep in mind that we should develop applications differently for each OS.

## Windows

Windows is proprietary software. This means that its source code is unavailable to users: we cannot read or modify it as we want. In other words, there is no legal way to know any more about proprietary software than its documentation tells us.

The target platforms for Windows are relatively affordable PCs and notebooks. Therefore, the market for potential Windows users is huge, and Microsoft usually maintains a competitive edge in this market.

To prevent the appearance of Windows analogs with similar features in the market, Microsoft takes care to protect its intellectual property. It does so in both technical and legal ways. For example, the Windows user agreement prohibits us from exploring the internals of the OS.

Many applications have been written for the Windows OS family. Microsoft itself developed the first applications. There is a package of office applications—Microsoft Office—and standard Windows applications. For third-party developers, they became a standard to follow.

Microsoft followed the same secrecy principle when it developed both the OS and the applications for it. Source codes are not available to users, data formats are undocumented, and third-party utilities do not have access to software features. These solutions protect Microsoft’s intellectual property.

Other software developers followed Microsoft’s example and stuck with the same secrecy principle. As a result, their applications are also self-contained and independent of each other, and their data formats are encoded and undocumented.

Typical Windows applications are easily recognizable to regular computer users due to their distinct features. For instance, they have windows with control elements—like buttons, input fields, and tabs—where users manipulate data. Text, image, or sound recordings are some examples of such data. Users can save the results of their work on the hard disk, and later open it in the same application.

If we ever write our own Windows program, it will look and work similarly. This succession of solutions is called the development culture.

## Linux

### The origins of Linux <a href="#the-origins-of-linux" id="the-origins-of-linux"></a>

Linux borrowed many ideas and solutions from Unix. Both OSs follow the set of standards called **POSIX (Portable Operating System Interface)**. POSIX defines the interfaces between applications and the operating system. The use of the same standards for Linux and Unix led to similarities in their behavior, so let’s go over the history of Unix first.

### Multics <a href="#multics" id="multics"></a>

The Unix OS appeared in the late 1960s. It was created by two engineers, Ken Thompson and Dennis Ritchie, from the Bell Labs company. Before Unix, however, they developed the **Multics** OS. This was a joint project of the Massachusetts Institute of Technology (MIT), General Electric (GE), and Bell Labs. Multics was planned as an OS for the new mainframe **GE-645**, shown in the figure below, by GE.

<figure><img src="../.gitbook/assets/image (20).png" alt="" width="563"><figcaption><p>Mainframe GE-645</p></figcaption></figure>

The developers applied several innovative solutions to Multics. One of them was time-sharing. The GE-645 mainframe was the first commercial computer where several users could work simultaneously and share their resources.

However, Multics turned out to be too complicated. The project consumed more time and money than it was expected to, so Bell Labs decided to discontinue it. However, the project was interesting from a technical point of view, and many Bell Labs engineers wanted to continue working on it. Ken Thompson was one of them.

Thompson decided to create his own operating system for the GE-645 computer. He started to write the system kernel and duplicate some Multics mechanisms. However, General Electric soon demanded the return of its GE-645. Since Bell Labs had only received the computer on loan, Thompson lost the hardware platform for his development.

#### Space Travel and PDP-7 <a href="#space-travel-and-pdp-7" id="space-travel-and-pdp-7"></a>

While he worked on a Multics analog, Thompson also had a pet project: to create a computer game called Space Travel. He launched the game on the past-generation GE-635 computer. It had the GECOS90 OS. GE-635 consisted of several modules, where each module was a cabinet with electronics. The overall computer cost was about $7500,000, and Bell Labs engineers actively used this machine. Therefore, Thompson was rarely able to use it to develop his game.

The limited access to the GE-635 machine was a problem for Thompson. So, he decided to port his game to a relatively inexpensive and rarely used PDP-791 computer (see figure below). Its cost was about $72,000. Here, Thompson met another problem. Space Travel used the features of the GECOS OS, while the PDP-7 software did not provide such features.

<figure><img src="../.gitbook/assets/image (21).png" alt="" width="375"><figcaption><p>Minicomputer PDP-7</p></figcaption></figure>

### UNIX <a href="#unix" id="unix"></a>

Thompson was soon joined by his colleague Dennis Ritchie. Together, they implemented GECOS features for the PDP-7. This included a set of libraries and subsystems. Over time, they developed these modules into the self-sufficient OS. They called it **Unix**.

Thompson and Ritchie decided they would not sell Unix, and they never intended to protect their intellectual property. They developed Unix for their own needs and distributed it for free alongside the source code. So, anyone could copy and use their OS. This seemed reasonable to the developers because the first Unix users were only Bell Labs employees.

Soon, Unix became popular among the employees. Thompson and Ritchie presented the OS at the “Symposium on Operating Systems Principles” conference. Then, they received a lot of requests for the system. However, Bell Labs belonged to AT\&T. Therefore, Bell Labs did not have the right to distribute any software on its own.

AT\&T noticed the new prospective OS and started to sell its source code to universities for $20,000. This way, university circles got a chance to further improve and develop Unix.

### Linux OS <a href="#linux-os" id="linux-os"></a>

Linus Torvalds, who would later create Linux, came across Unix while studying at the University of Helsinki. There, Torvalds came across a practical problem. He needed a Unix-compatible OS for his PC to do university tasks at home. Such an OS was not yet available. All that was currently available was Unix and the Minix OS.

#### MINIX OS <a href="#minix-os" id="minix-os"></a>

At the University of Helsinki, students performed study assignments using the MicroVAX computer, which ran Unix. However, many of them had PCs at home, and there was no Unix version for PCs. The only Unix alternative for students was the **Minix OS**.

Andrew Tanenbaum developed this OS for IBM PCs with Intel 80268 processors in 1987. He created Minix for educational purposes only. This was one reason why he refused to apply changes to his OS to support modern PCs. Tanenbaum did not want his system to become too complicated to teach students.

Meanwhile, Torvalds’s goal was to write a Unix-compatible OS for his new IBM computer with an Intel 80386 processor. He would name this OS Linux. He used Minix OS for its development but did not import any part of it to Linux. Like the creators of Unix, Torvalds had no commercial interests and did not intend to sell his software. He developed the Linux OS for his own needs and wanted to share it with everyone. This way, Linux became free. Torvalds decided to distribute it with its source code via the Internet. This decision made Linux very popular.

#### First version of Linux <a href="#first-version-of-linux" id="first-version-of-linux"></a>

Torvalds developed the kernel of the OS only. The kernel provided memory management, file system, peripherals drivers, and the processor time scheduler. However, users needed an interface to access the kernel’s features. Because of this, the Linux OS was not yet ready for use.

The solution to the problem came from a GNU software project. Richard Stallman started this project at MIT in 1983. His idea was to develop the most necessary software for computers and make them free. The major products of the GNU project were the GCC compiler, Glibc system library, system utilities, and the Bash shell. Torvalds included these products in his project and released the first Linux distribution in 1991.

The first versions of Linux did not have a graphical interface. The only way to interact with the system was through a command-line shell. Some complex applications had a text interface, but they were in the minority. Linux received a GUI in the middle of the 1990s. This interface was based on the **X Window System** free software. X Window allowed developers to create graphical applications.

#### Development similarity between Unix and Linux <a href="#development-similarity-between-unix-and-linux" id="development-similarity-between-unix-and-linux"></a>

Unix and Linux evolved in very specific conditions. Their origins differed from a typical cycle of commercial software development. These conditions created a unique development culture. Both systems developed in university circles. Computer science teachers and students used the OSs in daily work, and understood the software well. Therefore, they willingly fixed software errors and added new features to them.

Unix users usually prefer to use highly specialized command-line utilities. We can find a tool almost for each specific task. Such tools are well-written, tested many times, and work efficiently. However, all features of one utility focus on one specific task. The utility is not a universal software that can cover most of our needs.

When we face a complex task, there is no single utility to solve it. However, we can easily combine several utilities and solve our task this way. Such interaction becomes available because of a clear data format. So, we can start working with it immediately.

> Most Unix utilities use the text “data98” format. It is simple and self-explained.

Linux development culture follows Unix traditions and differs from the standards that are adopted in Windows. In the Windows world, every application is monolithic and performs all tasks by itself. Windows applications don’t rely on third-party utilities. This is because most Windows software costs money, and can thus be unavailable to users. Therefore, each developer relies on themself. They cannot force users to buy something extra to make a specific application work.

However, the situation differs with Linux. Most of the utilities are free, interchangeable, and easily accessible on the internet. Therefore, one application may require users to download and install missing system components or other applications.

#### Interaction of programs in Linux <a href="#interaction-of-programs-in-linux" id="interaction-of-programs-in-linux"></a>

The interaction of programs is crucial in Linux. Even monolithic graphical Linux applications usually provide a command-line interface. This way, they fit smoothly into the Linux ecosystem. So, we can easily integrate them with other utilities and applications.

### Bourne shell and Bash <a href="#bourne-shell-and-bash" id="bourne-shell-and-bash"></a>

When using Linux, users assemble a complex computing process from a combination of highly specialized programs. They create a general computation algorithm to get effective solutions. This is where the **shell** is useful. A shell is a special application to execute user commands. The first shell in widespread use was the **Bourne shell**. Now, it is substituted by **Bash** in most Linux distributions. We’ll cover Bash in this course.

### Linux vs Windows <a href="#linux-vs-windows" id="linux-vs-windows"></a>

Comparing Linux and Windows causes endless disputes between users on the internet. Each culture has its advantages and disadvantages.

For example, Window-style monolithic applications are better at handling tasks that require intensive calculations. However, when we combine specialized Linux utilities for the same task, there may be overhead caused by the launching and transfer of data between utilities. All this requires a lot of time. As a result, the task takes longer to complete.

Today, we observe a synthesis of Windows and Linux cultures. Microsoft started to contribute to open-source projects: the Linux kernel, the Samba networking protocol, PyTorch machine learning library, the Chromium web browser, and more. The company also released some of its projects with a free license: .NET Framework, PowerShell, VS Code IDE, and so on.

On the other hand, more commercial applications are getting ported to Linux: browsers, development tools, games, messengers, and so on. However, their developers are not ready for the changes that the Linux culture dictates. This is because such changes require a lot of time and effort, and make it more challenging to maintain the product. Instead of one application, there are two: each platform has a different version. Therefore, developers port their applications without significant changes. As a result, we now increasingly find more Windows-style applications on Linux. Users may argue the pros and cons of this process. However, the network effect ensures that the more applications run on a specific OS, the more popular it becomes.

\-----x-----x-----x-----x-----x-----x------x-----x-----x-----x-----x-----x-----x-----x-----x-----x-----

# Operating System Modeling

In this project, we designed operating system which uses design patterns according to our software architecture course. This is just an operating system modelling, not the actual one. Our operating system has many functions. Our primarily goal for the project is accomplish file input and output. Besides that, we have internal – external devices for the appropriate operating system. Furthermore, we have also proper files and directories according to the operating system type. Images from execution of the code can be viewed in sampleExecution.png.

# WHICH PATTERN DID WE USE?

A. ITERATOR PATTERN

B. COMPOSITE PATTERN

C. ABSTRACT FACTORY PATTERN

D. ADAPTER PATTERN

E. FACADE PATTERN

F. SINGLETON PATTERN

G. OBSERVER PATTERN

# A. ITERATOR PATTERN
As we know iterator pattern is essential for the traverse on the different data structure without manipulate or change corresponding interface. We used iterator pattern for our external devices. Our operating system uses iterator to navigate through devices without acknowledge of data structure which they are held. Iterator must take care of the devices to save operating system. For this operation, we also have external device collection to create its own external device iterator.

Participants

a) ITERATOR           -> Iterator

b) CONCRETE ITRATOR   -> ExternalDeviceIterator

c) AGGREGATE          -> Collection

d) CONCRETE AGGREGATE -> ExternalDeviceColection

# B. COMPOSITE PATTERN
A composite design pattern can be referred to as hierarchical structure. It provides a group of objects which are different from each other in themselves can be used as a single object. In an operating system, files and directories work within the file system. We used composite pattern for the filesystem. The operating system uses the composite design pattern for the management of the file system. Directory can have other directories or files.

Participants

a) COMPONENT  -> FileSystem

b) LEAF       -> File

c) COMPOSITE  -> Directory

# C. ABSTRACT FACTORY PATTERN
Abstract factory design pattern is to ensure that structurally related products can be managed over a common interface. Allows an object family to be created on different platforms using a single interface. In abstract factory design pattern, a class delegates the responsibility of object instantiation to another object. The purpose of using the abstract factory pattern is to be able to create new files and directories from the supported operating system using the operating system class as an interface. For example, if you are using Linux, your files and directories are LinuxFile and LinuxDir respectively.

Participants

a) ABSTRACT FACTORY -> OperatingSystem

b) CONCRETE FACTORY -> Linux, BSD, NT

c) ABSTRACT PRODUCT -> File, Directory

d) CONCRETE PRODUCT -> LinuxFile, NTFile, BSDFile, LinuxDir, NTDir, BSDDir

# D. ADAPTER PATTERN
The Adapter pattern is applied to reuse an existing class or interface class that is incompatible with each other to match a different class of interfaces. In this case, by writing an adapter, the current class can be adapted to our own system. Thus, we make the adapted object support a similar interface without code changes. As mentioned, we used the printf method as an adapter pattern method between input – output class and operating systems file classes. Whether the function names are different from each other between the operating systems, they are all use the adapter to make input operations.

Participants

a) TARGET   -> InputOutput

b) ADAPTEE  -> LinuxFile, BSDFile, NTFile

c) ADAPTER  -> NTPrintfConnector, BSDPrintfConnector, LinuxPrintfConnector

# E. FACADE PATTERN
Facade pattern preserves the details of the system and provides a single front face for the client to access the system from the outside. Subclasses in the system can be reached with this front class. The client only knows this face class in the system. In short, the frontal class is like a door to the outside of the system. Thus, facade defines higher level interface that makes the subsystem easier to use. We used facade pattern for our operating system’s subclasses. ShutDown method is façade method in Operating System. It handles all the operations for shutting down itself.

Participants

a) SUBCLASSES -> CPU, HardDisk, IO

b) FACADE     -> OperatingSystem

# F. SINGLETON PATTERN
Singleton pattern ensures that a program is just one instance of an object in the life cycle. If an object has been created, this pattern will point to the reference to that object instead of creating new one. At the same time, this pattern aims at achieving a single object created at a global level from outside the class. We provide to control this situation with GetOS method by using singleton pattern. It only creates single operating system instance for the whole program until shutting down of the OS.

Participants

a) SINGLETON  -> OperatingSystem

# G. OBSERVER PATTERN
This design pattern is used when there is a change in the circumstances of an object and when it is necessary to inform other objects that need to be aware of these changes. During this notification process, it is not desirable that the objects to be informed depend on each other. Many objects that are briefly in the listener position constantly observe the state of an object. Observers are notified during a change. The reason we use the observer pattern in our design is to make a notification of plugged in or plugged out devices by update method. When changes occur in devices, specified operating system is updated.

Participants

a) SUBJECT            -> ExternalDevice

b) OBSERVER           -> OperatingSystem

c) CONCRETE SUBJECT   -> USB, HDMI, HeadPhones

d) CONCRETE OBSERVER  -> Linux, BSD, NT



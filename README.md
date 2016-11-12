# producer-consumer-fair-solution
General information
-----------------------
This is an implementation of a fair solution to the bounded buffer producer-consumer problem with multiple producers and consumers. The solution is fair in the sense that no producer/consumer can make others starve. 

Two different versions of the solution have been implemented 
In the first one (producer_consumer.c), each consumer consumes exactly one item, and the producers only provide as many items as required by the consumers. All producers share an equal proportion of the load (number of products). 

In the second version (producer_consumer_infinite.c), the producers keep on providing and the consumers keep on consuming items (the program runs in an infinite loop) until stopped by the user. Priority based scheduling for the consumer threads has been implemented manually in this version (the program keeps track of the number of times each consumer has had a chance to buy an item and schedules the consumer threads such that each consumer consumes an item and is blocked until all other consumers have consumed an item.

Additional: makefile
The makefile is coded to compile both the programs (producer_consumer.c and producer_consumer_infinite.c). Executing the makefile compiles the programs using the GNU linux C compiler. It also creates the output files - producer_consumer, producer_consumer_infinite.

Installation
------------
$ make

Usage
------
Version 1 - producer_consumer.c:
$ ./producer_consumer N

The number of buyers 'N' must be entered to execute this program. If nothing is entered, the following prompt is displayed:"Execute program with 260 buyers?Y/n". If 'Y' is entered, the program is executed with 4 providers and 260 buyers and the result is printed on the screen. If 'n' or any other key is entered, the program terminates after displaying the message:"Program terminated".  If 0 or a negative integer is entered, the program terminates with message "Invalid number of buyers. Enter a positive value. Program terminated". If a positive integer is entered, the output is a list of items provided/bought. The thread IDs and the items provided/bought are displayed.

Version 2 - producer_consumer_infinite.c: 
$ ./producer_consumer_infinite N

The number of buyers 'N' must be entered to execute this program. If a positive integer is entered, the output is a list of items provided/bought. The thread names and the items provided/bought are displayed. The program runs until stopped by user command Ctrl+C

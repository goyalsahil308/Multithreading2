# Controlling threads using sleep 
## Libraries Used
### 1. threading:
                1.a Thread: To initialize thread 
                1.b Currentthread().setName():  To set name of current thread
                1.c Currentthread().getName()  : To get name of current thread
#### 2. time:
            We use sleep function to synchronize threads

_________________________________________________________________________________________________________

## User defined Functions:
### a1-a4 :  Adds 4 to given value and print it
### odd and even:  Print odd and even number alernatively
_________________________________________________________________________________________________________

## Target: We have to print 1-100 using multiple threads 
_________________________________________________________________________________________________________
## Working of code
First we will create 4 functions a1-a4 which are given one number each from  1 to 4 Each function will print each number and then adds 4 to it and print it.
In odd even ,there are two functions named odd and even in which odd will print 1st number and then even and so on .
Both programs  work in same way .
In a1,first a variable " a " is assigned value 1 and In a2, variable "b" =2 and so on .
We initialize thread by using below method.We can pass arguments in args.We will initialize 4 threads like this.


          t1=Thread(target=a1,args(,))
For starting execution of thread ,we use code and we will call all threads like this.

        t1.start()
After calling 1 thread ,we use sleep function to synchronize threads.The sleep function will put our program to sleep for given seconds and 
then execute next line.We are using this function to control threads otherwise we wouldnt know which thread is getting executed first.There would be 
ambiguity.

      time.sleep(5)
In functions we use while loop to print numbers upto 100.In functions , we are adding 4 to each a,b,c,d and print each in each function
After printing 1 number we will put gap of some seconds by using sleep method.This will print 4 numbers at a time means 1,2,3,4  is printed 
and it waits for seconds of gap we provided and then print 5,6,7,8 and so on.
Main thread starts all the threads when it reads .start() function and go to next statement .It will execute next lines of code without taking care
oh threads.So in that case we use .join() By executing this line main thread wont directly execute next code it will wait for thread to finish.

        Thread.join()
Similarly in odd even program ,we initialize two threads named odd and even and give a gap of some seconds.This will also work in the same way as 
other program and will hence print 1 to 100


#  Network Scanner
>Subnet scanner in C# that pings a given IP range

This project is my desire to experience developing my skills and supporting open source projects, this is the first project that I have been working on for Github!

Project fork from: https://github.com/zacharyreese/NetworkScanner


# Improvements

**Add parallel programming**
I have noticed that the original project is not fast enough to deal with a large number of servers or devices in general, as it passes successively through checks on a particular device and then the other like this.
In fact, I found it better to utilize hardware resources optimally by supporting parallel programming 🎯!

**Time ⏰**

I compared the time between the project in its original state and after my modification and added a stopwatch through programming ⏱ ; To be a fairer comparison and of course in the same field of examination.

It may be shown as in the following pictures:

In this picture, the experiment is illustrated by functional programming to the range of 15 test devices, and it took 102.2 seconds to finish

![alt text](https://github.com/MohammadYAmmar/NetworkScanner/blob/feature/parallelProgramming/Picture%20of%20functional%20programming.png "Picture of functional programming")

On the other hand in the same conditions, but this time after adding parallel programming, it took only 17.8 seconds to finish!

![alt text](https://github.com/MohammadYAmmar/NetworkScanner/blob/feature/parallelProgramming/Picture%20of%20parallel%20programming.png "Picture of parallel programming")

This table shows the time difference

| Functional | Parallel |
|--|--|
| 102.2 s | 17.8 s |

This equals a 140.667% difference!
You can verify yourself with the calculator or by using a site for the calculation such as [calculatorsoup](https://www.calculatorsoup.com/calculators/algebra/percent-difference-calculator.php)

💻 Details of the two experiments on which there is a processor: CPU Intel(R) Core(TM) i7-8550U , It contains four cores and eight threads.


To see the difference in the code, you can find me referring to it through the following comment:

    //New by: Mohammad Yaser Ammar
    
Some of the things that were in the original and amended were indicated through a comment

    //Old

# Parallel programming stability factors:
These factors are from my experiences with several projects

1 - Correct conversion for parallel programming
What I mean is not to be satisfied with converting, for example from

    for (int y = startIP[3]; y <= 255; y++) { //4th octet loop
   to 
   

    Parallel.For(startIP[3], endIP[3] +  1, (Inter, state) => 
    
You must understand how to act with it, so where are the beginning and the end with it.

2 - Overlapping incorrect values into the graphical interface

As is well known, parallel programming uses the device's resources in a distributed manner. If we assume that your device contains 8 threads, it will perform 8 operations at the same time, but let's be realistic, the device usually performs other operations in the background. On the other hand, it is efficient by the increase in the processes that occur simultaneously instead of one process, the increase in time and the optimal consumption of the device's resources.

The situation when dealing with the GUI is a little more difficult because there is **only one thread** for it. As shown in this picture: 

![alt text](https://i.stack.imgur.com/6MtB3.png
 "Picture of UI thread")

Therefore, we must solve this problem, which may appear as a cross-thread exception or overlap between values, and thus the program will become untrustworthy, or at least information without values will appear to us.

The solution I have implemented is to separate the GUI handling into a separate method, Instead of adding to listview directly via the following code:

    //listVAddr.Items.Add(new ListViewItem(new String[] { ipAddress, host.HostName, "Up" })); //Log successful pings

It will be by separating it by calling this method

    public void invoke_to_list(string ipAddress, string host, string state)

One of the important processes is to confirm a stage of invoke 

    if (listVAddr.InvokeRequired) { 
    listVAddr.Invoke(new MethodInvoker(
    delegate { listVAddr.Items.Add(item); 
    item.Checked = true; }));


The process illustration is similar to the separation that occurred in this image

![alt text](https://i.stack.imgur.com/8k5kn.png
 "Picture of UI thread with invoke")

[More details on the problem and solutions of cross-thread exception](https://stackoverflow.com/questions/142003/cross-thread-operation-not-valid-control-accessed-from-a-thread-other-than-the)

There are more additions in the comments in the codes like [here](https://github.com/MohammadYAmmar/NetworkScanner/blob/feature/parallelProgramming/NetworkScanner/Form1.cs)

Soon I will add new features and fix the stop button, so do not forget to follow the account and star to the repository  ✔🌟😁


My GitHub:  
[https://github.com/MohammadYAmmar](https://github.com/MohammadYAmmar)  
My LinkedIn:  
[https://www.linkedin.com/in/mohammad-y-ammar/](https://www.linkedin.com/in/mohammad-y-ammar/)

This site is nice for writing description [stackedit](https://stackedit.io/)
Clear steps for pull-request: [create a pull request in GitHub](https://opensource.com/article/19/7/create-pull-request-github)


Thank you for reading all of this to benefit you instead of just copying and pasting ✂!

**The part in which Mohammad Yaser Ammar wrote has ended**



## Description of the original project without modification:

# Network Scanner
>Subnet scanner in C# that pings a given IP range

This was my final project for my Computer Security Course (CSCI 5431). I developed this application using Visual Studio. This project exposed a severe security flaw in the Georgia Southern University network, where I was able to ping the IP range of the University, and access very sensitive data that was not properly secured such as University databases, donor excel files, GSU police department body cam library and arrest records, and many other critical data. I was able to gain access and create, edit, and potentially delete this data. After creating a report on what I had discovered, I went to the university to present my findings. After presenting, I worked with the top IT and CS administrators of the school's network to make sure that the exposed machines were properly secured so that this type of security vulnerability would be closed.

## Usage

To scan a range of IP addresses and request any sort of shared network folder, as well as use Windows Query Language (WQL) to gather data on the machine (Domain, Machine type, Windows version, etc.) if it was a windows machine. You can also send a force shutdown or restart command through this program.

## Installation

Add this project to Visual Studio and run

![][pic1]
![][pic2]
![][pic3]

[pic1]: https://i.gyazo.com/dd998a93ad8e46db59b84649a38d7d67.png
[pic2]: https://imgur.com/QZNfGT1.jpg
[pic3]: https://imgur.com/YwqaBvR.jpg

## Release History

* 1.0
    * Initial upload

## Meta

* Authors:
    * Zachary Reese

Zachary Reese – zactreese@gmail.com

Please do not copy or distribute my code without permission.

[https://github.com/zacharyreese](https://github.com/zacharyreese/)

## Contributing

1. Fork it (<https://github.com/zacharyreese/NetworkScanner/fork>)
2. Create your feature branch (`git checkout -b feature/fooBar`)
3. Commit your changes (`git commit -am 'Add some fooBar'`)
4. Push to the branch (`git push origin feature/fooBar`)
5. Create a new Pull Request




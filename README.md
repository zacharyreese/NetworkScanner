# Network Scanner
>Subnet scanner in C# that pings a given IP range

This was my final project for my Computer Security Course (CSCI 5431). I developed this application using Visual Studio. This project exposed a severe security flaw in my University network, where I was able to ping the IP range of the University, and access very sensitive data that was not properly secured such as University databases, donor excel files, police department body cam library and arrest records, and many other critical data. I was able to gain access and create, edit, and potentially delete this data. After creating a report on what I had discovered, I went to the university to present my findings. After presenting, I worked with the top IT and CS administrators of the school's network to make sure that the exposed machines were properly secured so that this type of security vulnerability would be closed.

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

[https://github.com/zacharyreese](https://github.com/zacharyreese/)

## Contributing

1. Fork it (<https://github.com/zacharyreese/NetworkScanner/fork>)
2. Create your feature branch (`git checkout -b feature/fooBar`)
3. Commit your changes (`git commit -am 'Add some fooBar'`)
4. Push to the branch (`git push origin feature/fooBar`)
5. Create a new Pull Request




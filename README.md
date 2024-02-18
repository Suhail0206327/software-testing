# Software-testing

## Introduction
 This is a brief introduction to software testing. The end goal for the reader is to make an overview of what is software testing to the reader. The necessity of software testing is to make our products complete and to protect them from vulnerabilities. This was not a serious issue in the early times but now, software testing is an essential part of the software cycle.  

## What is software testing?

Software testing is the process in which verification and validation of the software is done.
### Verification:
Here verification is asking "Are we building the software right?". Yes, it's more about checking if it is built correctly. Here we will be checking our code functionality and quality standards. We will be inspecting whether our software requirements are met.
### Validation:
Validation will be more focussed on the other side where how the users can use the software. Here we are asking "Are we building the right software?". Here we will be checking that is the customer able to perform the task as required. We will be validating all the functionalities and behaviors and make sure everything is working as expected.

## History of software testing

Software development started after the Second World War. A computer scientist called Tim Kilburn wrote the first piece of code for software that generated mathematical calculations in 1948 from the University of Manchester. Debugging was the main way of testing software and it remained till the 1980s, after that people started to come up with some testing plans to test the app's quality in the real world. In the 1990s the testing changed to quality assurance by iterating through all the cycles in software production using test cases. 

Do you know the story behind the first bug? In the 1940s a bug entered the computer room of the US military system and trapped in the vacuum tube. The US military team was the one whom Grace Hopper was working with. So yeah that might be the reason behind the name bug.

## Why do we need to do software testing?

The main reason for doing the software testing is to make sure our final product is ready to use without major problems. We can see even the operating system software gets some bugs and the team fixes those using a software update. Yeah so we can do minor fixes but it should not be a big one that may affect the functionality of the final products. For example, imagine that we build software for a rocket, and the rocket is launched and moved out of Earth's gravity and later we find a problem in the software that affects its functionality. So all the efforts, energy, expenses everything went awry because of not testing the functionality of the software. So it will be better to test our software properly and double-check everything is okay. It will help to save a lot of money and make our efforts count.

## Types of software testing

### 1. Integration testing:

First of all, integration means bringing the small particles together to make a joined new one. On the other hand, differentiation means breaking the bigger particles into small ones. So here in integration testing, we will be joining different parts and testing the whole. For example, in an e-commerce website, there will be individual components like authentication, product catalog, shopping cart, and payments and we combine all of these and then test if it works as expected when integrated.

### 2. Regression testing:

The term regression in mathematics refers to the unintended changes that occur on a variable while changing a dependent variable. So here we will be testing to make sure everything that was tested before is working properly when we make some changes to a particular section. For example, we have a filter function in a dress shop where we use the function to filter the products according to the size, and brand colors. And we received feedback from a user that the function was not working for the color section and then we fixed the issue and tested the fix. Now we do regression testing throughout the filtering function to make sure that other filtering things are also working as it worked before. 
### 3. Load testing:
In load testing, we will be testing our application under high usage. That is testing the behavior of our app when a lot of users are using the app at the same time and analyzing how our software is behaving. To cite an example, in a banking application, we have to test all the functionalities under high usage and make sure that everything is working properly without any lag. This load testing is a type of performance testing. That is testing the performance in different conditions and load testing is a way to test under high load. There are other performance tests as well like stress testing, endurance testing, etc.

### 4. Security testing: 
In security testing, we will be testing how secure our app is. Security testing is necessary to protect our data and resources from unknown intruders. And we will make sure that there are no loopholes left. 
#### Principle of Security Testing:
Below are the six basic principles of security testing:

* Confidentiality
* Integrity
* Authentication
* Authorization
* Availability
* Non-repudiation 
(geeksforgeeks)

There are different types of security testing Vulnerability scanning, risk assessment, security scanning, penetration testing, etc.... Let's dive more into penetration testing. 

## Penetration testing 

It is also called pen testing. In general penetration testing is a method to analyse the security of computer systems, web applications, or networks by stimulating some real-world attacks. The main objective is to find the vulnerable entry points and security weaknesses of the system. Here I wish to mention that a hacker doesn't refer to a person who has attacked the system before, it is called for someone who is good with testing knowledge and who is concerned about the security of the system. But nowadays when a person uses that to annoy to to attack a system it is also called a hacker. The ethical hackers are the hacker who works to protect the system. The hackers try to find an entry to the target software and try to load the malware into it. They also try to get an entry by making the user download something and install the malware into the system. A pen tester will be also going through these stages to protect the entry points by attacking the system with a potential threat.


## Example code snippets:
import java.net.*;

public class PortScanner {
    public static void main(String[] args) {
        String host = "example.com";
        int[] portsToScan = {80, 443, 8080};

        for (int port : portsToScan) {
            try {
                Socket socket = new Socket();
                socket.connect(new InetSocketAddress(host, port), 1000);
                System.out.println("Port " + port + " is open");
                socket.close();
            } catch (Exception e) {
                System.out.println("Port " + port + " is closed");
            }
        }
    }
}

This is pretty basic code using Java here it is checking if the ports are open or not. A class from java.net Called socket is used here and then using one of its methods "connect" it checks whether the host has a particular port that is open withing a time of 1000 milliseconds that's one second.


import java.net.*;

public class IPRangePortScanner {
    public static void main(String[] args) {
        String baseIP = "192.168.1.";
        int[] portsToScan = {80, 443, 8080};
        int timeout = 1000; // Timeout value in milliseconds

        for (int i = 1; i <= 255; i++) {
            String ipAddress = baseIP + i;

            for (int port : portsToScan) {
                try {
                    Socket socket = new Socket();
                    socket.connect(new InetSocketAddress(ipAddress, port), timeout);
                    System.out.println("Port " + port + " is open on " + ipAddress);
                    socket.close();
                } catch (SocketTimeoutException e) {
                    System.out.println("Connection to port " + port + " on " + ipAddress + " timed out");
                } catch (Exception e) {
                    System.out.println("Error connecting to port " + port + " on " + ipAddress + ": " + e.getMessage());
                }
            }
        }
    }
}

This is doing the same thing as above just printing the ip address in the messages.

## Conclusion 
So in conclusion software testing is the process that includes verification and validation of our software. There are different types of software testing. By reading these articles I hope the reader can get an idea of what software testing is. I tried to explain it as simple as possible. 

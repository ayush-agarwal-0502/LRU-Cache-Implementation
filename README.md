# LRU-Cache-Implementation
LRU (Least Recently Used ) Cache implementation using Doubly Linked List and Unordered Map 

* Project by - Ayush Agarwal 
* Fields/Subjects - Data Structures and Algorithms (DSA) , Object Oriented Programming (OOPS) 
* Tools (Programming Language) - C++ 

The code has been well explained in comments by me , refer to it for explanation . 

## Motivation 
Most of the codes available online were for storing integers in Cache , however , I felt that storing string data would be more useful since this way we could store both text and numbers in the cache . Furthermore , I have used integers as keys and string as the data . The reason for this is as follows: Suppose we have a server which has to send out data after receiving the requests . Suppose that the data is text , stored in many pages , and each page has its page number . Now , the server decided to use LRU Cache since extracting pages from the secondary memory is a time consuming affair , hence LRU Cacheing strategy has been employed . So we need the Cache to store strings , since the text on the pages will be in string format . Moreover the keys would page numbers , which would be integers , and the requester can easily request for a specific page number and get the text on that page stored in that server . 

## Usage in backend servers :
As explained in the motivation part , a Backend server of a website needs to deliver content faster to the requesting client , so the LRU Caching stratergy is used for caching data , since cache speed is much faster than the access speed of the secondary emory of the server .

## Usage of LRU in Page Replacement in Operating Systems :
* For optimising the CPU usage , we need to execute more than one process at once (since a process may request for I/O , then go into suspended state and go to the Process Control Board (PCB) leaving the CPU idle and decreasing efficiency . Hence the Degree of MultiProgramming needs to be increased .
* So Memory Management techniques are employed , they can be of 2 types , contiguous and non contiguous . 
* Contiguous Memory Allocation algorithms are First fit , Next fit , Best Fit and Worst Fit . However they suffer from External Fragmentation , meaning wasteage of memory due to holes between process causing a condition that a process will not be able to enter the main memory even if there is enough space in the memory .
* So we go for discontinuous allocation of memory . 
* We perform Paging . In this each process is divided into pages , and the main memory is divided into frames , and few pages of each process are taken to the main memory (RAM) . Each Process has its own Page Table , throught which it converts the Logical Address of the page into Physical Address , which is then used to access the page . (Paging is not the same as Segmentation and Overlay , in which we leave the work of dividing the process into (unequal) parts called segments and then sending them to the memory . Segmentation and Overlay is used mostly in Embedded Systems , where the processes are known beforehand )(This is only true for single paging , and bit different from 2 layer paging (multi layer paging) and inverted paging (global page table) respectively )
* Paging also introduces the concept of Virtual Memory , which allows us to run Processes with sizes significantly bigger than the main memory (RAM) itself .
* However , it also introduces the concept of thrashing , which means that after a certain degree of multiprogramming , Page Faults will start increasing so much that the efficiency will decrease , i.e. efficiency does not directly increase with the degree of multiprogramming always .
* Page Fault is when a particular page requested by the CPU is not found in the main memory (no reference address found in page table) , and hence has to be fetched from the secondary memory .  

# Code 

## Class Declaration 
![image](https://user-images.githubusercontent.com/86561124/172538502-211579aa-fe95-4856-9115-e00228066008.png)

## Constructor 
![image](https://user-images.githubusercontent.com/86561124/172538536-bbe251ec-8644-4ac8-a832-cb9e71422231.png)

## SIZE Method 
![image](https://user-images.githubusercontent.com/86561124/172538549-96f3d9fd-17ef-410f-92e7-a56d6fec1e55.png)

## FEEDIN Method 
![image](https://user-images.githubusercontent.com/86561124/172538565-104a36aa-e513-48da-8863-713e37c9087c.png)

![image](https://user-images.githubusercontent.com/86561124/172538574-03461f2a-ebdb-45d3-9ed2-b7f2d2b62a14.png)

## GETTIN Method 
![image](https://user-images.githubusercontent.com/86561124/172538611-e6e2969e-cf87-43f1-afbd-e231377449ac.png)

## TestBench 
![image](https://user-images.githubusercontent.com/86561124/172538631-b414bbe2-c3df-496e-a41b-c24a4f65a92c.png)

## Output of the run 
![image](https://user-images.githubusercontent.com/86561124/172538710-96ed317e-b17d-4459-8220-38cc36e2c9ba.png)

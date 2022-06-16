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
* So Memory Management techniques are employed , they can be of 2 types , contiguous and non contiguous . This work is done by Memory Management Unit (MMU) .
* Contiguous Memory Allocation algorithms are First fit , Next fit , Best Fit and Worst Fit . However they suffer from External Fragmentation , meaning wasteage of memory due to holes between process causing a condition that a process will not be able to enter the main memory even if there is enough space in the memory .
* So we go for discontinuous allocation of memory . 
* We perform Paging . In this each process is divided into pages , and the main memory is divided into frames , and few pages of each process are taken to the main memory (RAM) . Each Process has its own Page Table , throught which it converts the Logical Address of the page into Physical Address , which is then used to access the page . (Paging is not the same as Segmentation and Overlay , in which we leave the work of dividing the process into (unequal) parts called segments and then sending them to the memory . Segmentation and Overlay is used mostly in Embedded Systems , where the processes are known beforehand )(This is only true for single paging , and bit different from 2 layer paging (multi layer paging) and inverted paging (global page table) respectively )
* Paging also introduces the concept of Virtual Memory , which allows us to run Processes with sizes significantly bigger than the main memory (RAM) itself .
* However , it also introduces the concept of thrashing , which means that after a certain degree of multiprogramming , Page Faults will start increasing so much that the efficiency will decrease , i.e. efficiency does not directly increase with the degree of multiprogramming always .
* Page Fault is when a particular page requested by the CPU is not found in the main memory (no reference address found in page table) , and hence has to be fetched from the secondary memory .  This uses a lot of time called Page Fault Service Time . 
* Since Page Table is also stored in the main memory , searching for address of a page in the page table can also becomme a slow process . Hence we use Translational Lookaside Buffers (TLB) which are even faster caches , and store a part of the page table . However they are far more expensive hence limited in size . This leaves us with conclusion that we need to reduce the number of Page Faults to increase the efficiency of system , and reduce thrashing and reduce time wasted in Page Fault Service Time . 
* Hence we use Page Replacement Algorithms . 
* We have 4 types of page replacement algorithms : 
  * First In First Out (FIFO)
  * Optimal Page Replacement Algorithm 
  * Least Recently Used Algorithm 
  * Most Recently Used Algorithm 
* FIFO algorithm is fastest , but it suffers from Belady's Anommaly ( increase in number of page hits with increase in memory in FIFO page replacement case due to non stack like behaviour ) which limits its power . 
* Optimal Page Replacement Algorithm replaces the page which is going to be needed far in future compared to the other pages in memory . This is of course the most optimal thing to do , since it keeps the items for quick access . However , I feel it needs future sequence of Page requests which may or may not be known (I assumed it was not known to me while making this Project ) . 
* Least Recently Used (LRU) throws away the least recently used page from the main memory . It makes sense since the thing which has not been in demand recently may not be in demand in immidiate future also , meanwhile the recently used items may come again in use , hence should be kept . However LRU needs some memory to keep track of which pages came first etc . I feel this is not much of a problem as in a tradeoff of time vs memory , memory only gets cheaper with time whereas time only gets costlier (i.e. memories become cheaper in future , and we tend to look for time optimisation of things) . Hence I decided to make this one myself . 
* Most Recently Used (MRU) throws away the page which was most recently used among all the pages in the main memory . This at first sounded a bit ironic to me , but realised that it might be useful when it is known that something used is less likely to be used again in near future . Still I personally find LRU more intutively advantageous to me . The basic advantage might also be that we do not need to keep track of the whole past , just the most recent process , which makes its memory demand in between that of LRU and FIFO . ( Correct me if I'm wrong with the advantages and disadvantages , I did what I felt here) .
* Hence I implemented LRU Cache ( A data structure with properties suitable to implement LRU Page Replacement Algorithm ) . 

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

# LRU-Cache-Implementation
LRU (Least Recently Used ) Cache implementation using Doubly Linked List and Unordered Map 

* Project by - Ayush Agarwal 
* Fields/Subjects - Data Structures and Algorithms (DSA) , Object Oriented Programming (OOPS) 
* Tools (Programming Language) - C++ 

The code has been well explained in comments by me , refer to it for explanation . 

## Motivation 
Most of the codes availaible online were for storing integers in Cache , however , I felt that storing string data would be more useful since this way we could store both text and numbers in the cache . Furthermore , I have used integers as keys and string as the data . The reason for this is as follows: Suppose we have a server which has to send out data after receiving the requests . Suppose that the data is text , stored in many pages , and each page has its page number . Now , the server decided to use LRU Cache since extracting pages from the secondary memory is a time consuming affair , hence LRU Cacheing strategy has been employed . So we need the Cache to store strings , since the text on the pages will be in string format . Moreover the keys would page numbers , which would be integers , and the requester can easily request for a specific page number and get the text on that page stored in that server . 

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

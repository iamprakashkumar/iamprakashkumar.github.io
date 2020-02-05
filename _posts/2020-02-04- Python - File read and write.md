---
layout: post
title: Python - file read and write
date: 2020-02-05 08:24:00
desc: Handson python
---

To Read and write list to a file we can use the followin ways in pythong.  
`write()` and `read()` - deals with single line  
`writelines()` and `readlines()` - deals with multiple line  
`pickle` and `json` modules can be used to deal with serialised data  


**USING READ AND WRITE METHODS**  

```
name=['a','b','c','d','e']

with open('test.txt','w')as test:
    for listitem in name:
        test.write('%s \n' %listitem)
        
```

First we define a list using the variable name.  
test.txt file is choosen for writing operation using the `open` function. `with` keyword is used when we're using unmanaged resources.   
Next we assign all the values of name variable to listitem and using it in the for loop.  
listitem is extended by a linebreak "\n", firstly, and stored into the output file, secondly.  

> List `[]` - Can have any Datatype, Mutable  
`open()` function opens a file, and returns it as a file object.  
`with` keyword is used when working with unmanaged resources (like file streams). It allows you to ensure that a resource is "cleaned up" when the code that uses it finishes running, even if exceptions are thrown.  

![read and write op](https://user-images.githubusercontent.com/17383454/73807185-9a525980-47f1-11ea-8f7e-4dcdf4455928.png)

**Reading from a file**

```
places = []


with open('test.txt', 'r') as filehandle:
    for line in filehandle:
        
        currentPlace = line[:-1]

        
        places.append(currentPlace)
print(places)
```

The output will be as follows  

``` ['a', 'b', 'c', 'd', 'e', 'f', 'g'] ```



We read a file named `test.txt` using the `r` read mode and them alias it as filehandle. Then each line from a filehandle is read and saved into the line.  
``` currentPlace = line[:-1] ```
What is exactly happen in the above mentioned code is that we remove the linebreak from the end of the string.  

If the slicing operation is commented out ``` #currentPlace = line[:-1] ```
Then we will get the following output  

```['a\n', 'b\n', 'c\n', 'd\n', 'e\n', 'f\n', 'g\n']```



**Using writelines and readlines method**

```
check=['https://google.com','https://yahoo.com']
with open('test2.txt','w') as hand:
    hand.writelines("%s \n" %place for place in check)
```

It is also possible to write this short line of code which works on the same manner like the above mentioned code.  

```
place=[]
with open('test2.txt','r') as handle:
    place=[cur_place.rstrip() for cur_place in handle.readlines()]
print(place)    
```
   

**Pickle module**

 pickle module may become quite handy for you. Its `dump()` method stores the list efficiently as a binary data stream.  
 





### GOAL 1 : Read list of url from a file

> During HSTS check we need to enumerate a list of subdomains of our target which can be achieved using the tools like sublister.  
Then that output of suddomains will be get feed into our tool using the above mentioned codes.   
['http://google.com', 'http://yahoo.com', 'https://nokia.co']  





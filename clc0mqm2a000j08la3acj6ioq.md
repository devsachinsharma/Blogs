---
title: "What is YAML?"
seoTitle: "YAML is a human-readable data-serialization language. YAML stands for"
seoDescription: "YAML is a human-readable data-serialization language. YAML stands for "YAML ain't markup language" but was previously known as "Yet Another Markup Language"
datePublished: Fri Dec 23 2022 14:50:27 GMT+0000 (Coordinated Universal Time)
cuid: clc0mqm2a000j08la3acj6ioq
slug: what-is-yaml
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1671801486106/KZNV1GxnO.png
tags: developer, devops, beginners, yaml, wemakedevs

---

YAML is a human-readable data-serialization language. YAML stands for "YAML ain't markup language" but was previously known as "Yet Another Markup Language.

The abbreviation of YAML was changed because in markup languages you can store documents and in YAML you can store data objects.

It is basically data format which is used to exchange data quite similar to JSON and XML files. YAML mainly stores configuration files for docker, and Kubernetes and is also used to store logs, caches, etc. YAML is case sensitive eg- honda != Honda in YAML you can only store data and not commands(if or else).

# DATA SERIALIZATION:-

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1671803978428/vjEL14qQI.png align="center")

Let us consider you have an object containing details of a student and you used it in an android app now you want to use it in a web app but in doing so you might need to change the format of the object and perform different operations. Wouldn't it be easy if this object is in a particular format that can be used in both without making any changes?

This is where the process of serialization and deserialization comes into the picture.

**A process of converting the data objects that is present in a complex data structure into a stream of byte to store the object or transmit it to memory, a database, or a file.**

# DATA DESERIALIZATION :-

**Deserialization is the reverse of the serialization process, taking structured data from some format, and rebuilding it into an object.**

# Benefits of YAML:-

1. Human-readable and simple.
    
2. Strict syntax:-Indentation is important.
    
3. Easily convertible to JSON, and XML.
    
4. More powerful when representing complex data.
    
5. Parsing(reading) the data is easy.
    

# Syntax of YAML:-

```yaml
# Cars 
# Honda
```

Comments:- These are ignored by the compiler and interpreters. In YAML multi-line comments are not available. The "#" symbol represents a comment.

To separate different documents:-

```yaml
"car" : "I'm a Toyota"
1 : "This is my lucky number"
 
---

Companies:
  - Toyota
  - Honda
  - Hyundai
...
```

The "---" symbol is used to separate different documents in a single YAML file.

The "..." symbol is used to represent that a document has ended.

# Datatypes

### String Variables:-

```yaml
#String Variables
Name: Sachin Sharma
        OR
City: "New Delhi"
        OR
Country: 'India'

#Storing multiple lines in a single string.
Introduction: |
Hey my name is sachin sharma.
I am a student.

#Storing single line string but writing in multiple lines
Introduction: >
Hey my name 
is 
sachin sharma.
```

### More Datatypes:-

```yaml
#Integer 
number : 26
#Float
marks: 78.45
#Boolean
boolValue : NO
#Instead of NO n, N, false can also be written.
#Same goes for YES, you can write True, y, Y, etc.
#Exponents
exponential numbers: 6.023E56
```

YAML can automatically detect the datatype but users can also specify the datatype.

To specify a datatype:-

```yaml
randomnumber : !!int 45

marks: !!float 78.45
infinite: !!float .inf

not a number: .nan

boolValue : !!bool NO

Name: !!str Sachin Sharma

Name: !!null NULL 
~: This is a null key.

#dates and time 
date: !!timestamp 2022-12-21
india time: 2022-12-21T08:32:16.10 +5:30
no time zone: 2022-12-21T08:32:16.10
```

# Advanced Datatypes:-

### List Datatype

```yaml
Companies:
  - Toyota
  - Honda
  - Hyundai
         OR
Companies: !!seq
  - Toyota
  - Honda
  - Hyundai
         OR
Companies: [Toyota, Honda, Hyundai]
         
#Sparse sequence-Some keys are empty or null.
Companies: !!seq
  - Toyota
  - NULL
  - Honda
  -
  - Hyundai

#Nested sequence
Companies: !!seq
-
  - Toyota
  - Honda
  - Hyundai
-
  - Tata
  - Mahindra
```

### Maps Or Key Value Pairs:-

```yaml
Demo: !!map
"car" : "I'm a Toyota"
1 : "This is my lucky number" 
              OR
{car:  I'm a Toyota, 1: This is my lucky number}

#Nested map
  Student: !!map
  Name: Sachin Sharma
  role: 
    age: 82
    job: student
        OR
  Student: !!map
  Name: Sachin Sharma
  role: { age: 82, job: student}

#Pairs-Keys may have duplicate values.
demo: !!pairs
  - job: student
  - job: teacher
        OR
demo: !!pairs [job: student, job: teacher]
```

In the above code snippet "car" and "1" are both keys which point towards their values "I'm a Toyota" and "This is my lucky number" respectively.

### Set Datatype:-

In set, only unique values are allowed.

```yaml
Companies: !!set
  ? Toyota
  ? Honda
  ? Hyundai
#No repetition is allowed.
```

### Dictionary Datatype:-

```yaml
Student: !!omap
 - Sachin:
      name: Sachin Sharma
      age: 82
      job: student
        
  - Kunal:
      name: Kunal
      age: 74
      job: student
```

### Anchors:-

Anchors help us in reusing properties without having to code them again and again.

```yaml
details: &details
      age: 45
      job: student 
details: &details2
      age: 66
      job: student 

Sachin:
      name: Sachin Sharma
      <<: *details
        
 Kunal:
      name: Kunal
      <<: *details2
      job: teacher
      #This will override job.
```

### **Thank you all for giving your valuable time for reading.**

### **Resources:-**

[Kunal Kushwaha's youtube tutorials.](https://www.youtube.com/watch?v=IA90BTozdow)

[TechWorld with Nana's Youtube tutorials.](https://www.youtube.com/watch?v=1uFVr15xDGg)

### ***Any feedback or remarks will be highly appreciated.***
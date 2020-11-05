---
layout: post
title: Data Structure and Algorithms
description: Data Structure and Algorithms.
date: 2018-10-01 10:59:00 +0700
categories: algorithms
thumbnail: https://lh3.googleusercontent.com/pw/ACtC-3e-RL8q88cBXBJrfUwcZangXCm_qeBpRh50yTAdrIywl7FvKShs-YrxPZmTdTXk_t16OgXY-aGboBg_EQIBgvNBeG-YmmMctB_Q_JXcGkLG-FpcJa-6jTdQM6wQayX41axEpl1JSzFf8LQgIAK8nhJ_zw=w1361-h789-no?authuser=0
---

![](https://lh3.googleusercontent.com/pw/ACtC-3e-RL8q88cBXBJrfUwcZangXCm_qeBpRh50yTAdrIywl7FvKShs-YrxPZmTdTXk_t16OgXY-aGboBg_EQIBgvNBeG-YmmMctB_Q_JXcGkLG-FpcJa-6jTdQM6wQayX41axEpl1JSzFf8LQgIAK8nhJ_zw=w1361-h789-no?authuser=0)

Data Structure and Algorithms.

### Criteria
- Thinking about data structure and algorithms

### Concept
- Problem and solve the problem
- What is data structure?
- What is algorithms?
- Best practice and optimization
- Easiest maintain

### Source
[https://github.com/duycs/sample-algorithms){:.text-link}

### Keywords
- Algorithms
- Data structure
- Logical

### Analysis and design algorithms
### Recursive algorithm
### Array and List
### Stack and Queue
### Tree
### Graph and Nonlinear structure
### Memory management
### Sort
### Searching
### Advance data structures

### Lession
#### I. Iterations
##### 1. Binary Gap
**Find longest sequence of zeros in binary representation of an integer.
**Problems:

A binary gap within a positive integer N is any maximal sequence of consecutive zeros that is surrounded by ones at both ends in the binary representation of N.

For example, number 9 has binary representation 1001 and contains a binary gap of length 2. The number 529 has binary representation 1000010001 and contains two binary gaps: one of length 4 and one of length 3. The number 20 has binary representation 10100 and contains one binary gap of length 1. The number 15 has binary representation 1111 and has no binary gaps. The number 32 has binary representation 100000 and has no binary gaps.

Write a function:

class Solution { public int solution(int N); }

that, given a positive integer N, returns the length of its longest binary gap. The function should return 0 if N doesn't contain a binary gap.

For example, given N = 1041 the function should return 5, because N has binary representation 10000010001 and so its longest binary gap is of length 5. Given N = 32 the function should return 0, because N has binary representation '100000' and thus no binary gaps.

Write an efficient algorithm for the following assumptions:

N is an integer within the range [1..2,147,483,647].
*Copy: codility

***Program:
Java
```
class Ideone {
   static void decToBinary(int n) {
        System.out.println(Integer.toBinaryString(n));
        int[] binaryNum = new int[1000];
 
        // counter for binary array 
        int i = 0;
        while (n > 0) {
            // storing remainder in binary array 
            binaryNum[i] = n % 2;
            n = n / 2;
            i++;
        }
        ArrayList<Integer> al = new ArrayList<Integer>();
 
        // printing binary array in reverse order 
        for (int j = i - 1; j >= 0; j--) {
            if (binaryNum[j] == 0) {
                int ctr = 0;
                while (binaryNum[j] == 0) {
                    ctr++;
                    j--;
                }
                al.add(ctr);
            }
        }
 
        System.out.println(al);
    }
 
    // driver program 
    public static void main(String[] args) {
        int n = 1041;
        decToBinary(n);
    }
}
```
#### II. Arrays
##### 1. CyclicRotation
##### 2. OddOccurrencesInArray

---
### Referecnces
- Data Structure and Algorithms book
- https://www.geeksforgeeks.org/advanced-data-structures/
- https://app.codility.com/programmers/lessons/1-iterations/binary_gap/

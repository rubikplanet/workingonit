---
title: Project Euler 算法题1
date: 2018-10-06 23:58:13
categories:
- 算法
tags:
- Project Euler
- 算法
---
# Multiples of 3 and 5
## Problem 1
If we list all the natural numbers below 10 that are multiples of 3 or 5, we get 3, 5, 6 and 9. The sum of these multiples is 23.

Find the sum of all the multiples of 3 or 5 below 1000.

From: [https://projecteuler.net/problem=1](https://projecteuler.net/problem=1)

## Go实现
``` Go
package main

import (
	"fmt"
)

func main() {
	sum := 0
	for i := 0; i < 1000; i++ {
		if i%3 == 0 || i%5 == 0 {
			sum = sum + i
		}
	}
	fmt.Println(sum)
}
```

## Java实现
``` Java
public class App {

    public static void main(String[] args) {
        int sum = 0;
        for (int i = 0; i < 1000; i++) {
            if (i % 3 == 0 || i % 5 == 0) {
                sum = sum + i;
            }
        }
        System.out.println(sum);
    }

}
```

## Node.js实现
``` JavaScript
let sum = 0;
for (let i = 0; i < 1000; i++) {
  if (i%3 == 0 || i%5 == 0) {
    sum = sum + i;
  }
}
console.log(sum);
```

## Python实现
``` Python
sum = 0
for i in range(1000):
  if i%3 == 0 or i%5 == 0:
    sum = sum + i
print(sum)
```

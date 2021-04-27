---
layout: post
title:  "What are Go channels?"
author: pramod
categories: [ go-tutorial, programming ]
image: assets/images/gochannels.jpg
tags: featured
---

The channels in golang are communication lines between the Goroutines. It can be biredctional as we can send and receive with the channel operator (<-)

Channels are associated with a data type which determines what it can transport. The channel cannot transport any other type of data. 

A channel must be created before it is used

```
ch := make(chan int)
```

This channel sends and receives the block with the int data type till the other end is ready

## Sending and Receiving 

```
Write into a channel
a <- data

Read from a channel
data := <- a
```

The transmitting operations such as sending and receiving to a channel are blocking by default. This means that when the data is sent into a channel the control is blocked till a goroutine reads from the other end of the channel.
Similarly the read from the channel is blocked till the other end has a gorouting writing data into it


## Example code
Here is an example code which distributes a mathematical work between two go routines. We can see that the final result is calculated once both the goroutines have completed the calculation/computation
```
package main

import "fmt"

func add(s []int, ch chan int) {
	add := 0
	for _, v := range s {
		add += v
	}
	ch <- add // send add to c
}

func main() {
	p := []int{4,0,8,5,-1,1,7}

	d := make(chan int)
	go add(p[:len(p)/2], d)
	go add(p[len(p)/2:], d)
	x, y := <-d, <-d // receive from c

	fmt.Println(x, y, x+y)
}
```

Image courtesy - https://golangforall.com/en/tag/channels.html
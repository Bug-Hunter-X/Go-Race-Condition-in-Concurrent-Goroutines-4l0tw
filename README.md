# Go Race Condition in Concurrent Goroutines

This repository demonstrates a common race condition bug in Go when multiple goroutines access and modify a shared variable concurrently without proper synchronization.  The program intends to increment a counter 1000 times, but due to the race condition, the final counter value will likely be less than 1000.

## Bug Description
The `counter` variable is shared among multiple goroutines. Each goroutine increments the counter, but without proper synchronization mechanisms (like mutexes or atomic operations), the increments can be interleaved and lost, leading to an inaccurate final count.

## Solution
The solution utilizes a mutex to protect the `counter` variable, ensuring that only one goroutine can access and modify it at a time.
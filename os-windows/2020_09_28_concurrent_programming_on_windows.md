# Concurrent Programming on Windows

## PART I - Concepts

### Introduction

### Synchronization and Time

#### Synchronization: Kinds and Techniques

 * Data Synchronization, 共享资源，通过加锁去解决 race condition
 * Coordination and Control Synchronization, 总控与调度，不产生多线程同时访问一个内存资源的情况

**Data Synchronization**

```
The sequence of operations that must be serialized with respect to all other concurrent executions of that same sequence of operations is called a **critical region**
```

 * **critical region** implementations
 * lock, mutex, cirtical section, monitor, binary semaphore, transaction
 * 上述方法，语义上有些许区别，比如：read/write lock 允许 shared reading

A Generalization of the Idea: Semaphore

 * value > 0, threads can enter critical region
 * value == 0, threads must wait until value > 0
 * mutex is **binary semaphore** (value can only be 0 or 1)
 * Semaphores with maximum counts of more than 1 are typically called **counting semaphores**

## PART II - Mechanisms

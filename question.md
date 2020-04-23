- Different between TreeMap vs HashMap 
	- What type of tree does TreeMap use?
	- What is DB index? List some of them?
	- Why does DB index use B+Tree ? Why does not DB index  use kind of tree same like TreeMap?
	- Design a payment system? 
- How can you handle concurrently problems in payment system (2 withdraw at the same time)?

PREPARATION:
    - Database:
        - phuong phap tranh race condition
        - isolation levels
        - index methods

    - Network:
        - tcp vs udp
        - 
    - OS:
        - algorithms: banker, v.v.
        - mutex, semaphore, spin-lock

ROUND 1:
1. LRU Cache
Cache: set(key, value) get(key)
LRU: least recent u
capacity

put(key, value)
size > capacity
    remove (key, value) timestamp nho nhat
2. Simple Adder program with thread-safe and high performance
3. Thread vs Process
3.1 Port, process
3.2 TCP connections: how many TCP connections to one port? Why?

Time: 90 mins


ROUND 2:
senior
first non repeated item from data stream. 
array n items. output: 


# Database
## sql
## transations
## index
## phương pháp tránh race condition
## DB isolation level
## b tree indexing, hash methods
## when avoid indexing
## eventual consistency 
# Network
## tcp,udp
## ip, port target, source
## protocol
## DNS server
## https encrytion
## udp reliable
# OS
## process
### heap and stack
### ipc
### maximum process, thread per process. 
## memory
### user space and kernel space
## other algorithms
### banking algorithm


ROUND 3: SYSTEM DESIGN
leader:

data stream 
field:
    - user id
    - event id
    - timestamp

output: 
    number of unique user_id per event_id in last 30 minutes

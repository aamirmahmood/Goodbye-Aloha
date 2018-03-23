## Introduction

The design of medium access control (MAC) protocols has been traditionally an intense area of research due to their high impact on the overall performance of wireless communications. The majority of research activities in this field deal with different variations of protocols somehow based on ALOHA, either with or without listen before talk, i.e., carrier sensing multiple access.

### Practical problems with ALOHA :
1. These protocols operate well under low traffic loads and low number of simultaneous devices. However, they suffer from congestion as the traffic load and the number of devices increase.
2. These protocols cannot handle huge number of devices which request channel access to transmit small data packets - Eg: Event driven applications
3. Aloha and it's variations have been implemented in many types of networks like
	a. Wireless Personal Area Networks - Bluetooth Low Energy , RFID .
	b. Wireless Local Area Networks -WiFi
	c. Public cellular Networks and Cellular IoT
4. All the above types of networks are promising candidates to become backbone of IoT systems. The critical problem is that IoT systems are systems with a lot of devices , and most devices transmit data based on some trigger.So , dataframes generated by the devices are sudden , like interrupts.
Traditional ALOHA networks cannot handle this type of traffic if more number of devices simultaneously get triggered and send data.

**There is a lot of contention as to which device among the large number of devices should get the channel access if all of them transmit data simultaneously. This problem is the main motivation to think of an entirely different solution from ALOHA** .

The networks of IoT Systems poses different types of challenges such as low latency , high reliability , high availability . The network may change from an idle one to a saturated one because of the behavior of devices in the system.Most of the protocols which are based on ALOHA resolve contentions in the network using waiting backoff periods which reduces the performance of the system drastically.

The proposed solution:
Protocols based on the **Distributed Queuing**(**DQ**) technology can solve all the MAC level problems posed by IoT systems.
DQ has a lot of advantages over ALOHA based protocols. A few of them are

1. It provides near-optimum performance with respect to throughput and delay.
2. DQ behaves as a random access scheme under low traffic and automatically switches to a reservation-based scheme when the traffic increases , thus obtaining the best of the 2 methods.
3. DQ eliminates data-packet collisions and random waiting periods(backoffs).
4. DQ almost allows full channel utilization independently of the number of transmitting devices and the traffic pattern.


![Figure 1](https://i.imgur.com/evEQWzJ.png)
1) Colliding devices enter the Contention Resolution Queue (CRQ). A tree splitting algorithm is then used to resolve the contention.

![Figure 2](https://i.imgur.com/3r2igQS.png)

2) Succeeding devices enter the Data Transmission Queue (DTQ). In this case, a first-in first-out (FIFO) queue allows devices to transmit data in subsequent
frames using the data slot of the DQ frame.


This is the theoritical foundation on which the design and implementation of the MAC protocol based on DQ(Distributed Queuing) is made.
The design plan of DQ based protocol is explained in the file "Design.md" in depth.
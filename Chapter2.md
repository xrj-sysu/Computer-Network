## IEEE 802.3 Ethernet

Outline
  * Introduction
  * Ethernet Topologies
  * Ethernet Frame Format
  * Ethernet MAC Protocol -- CSMA/CD
  * 802.3 Ethernet Standards

// some words
  * CSMA/CD: Carrier Sense Multiple Access with Collision Detection
  * transceiver,adaptor,Ethernet cable, terminator, repeater.
  * 10Base5 -> 10base2 -> 10baseT

看到之前讨论区有人在纠结练习题2.10(c)"HUb" is used to connect the point-to-point segments"(b)The common network configuration is still a "bus", 我试着说一下自己的理解。
其实下面每个人无论是说到"point-to-point"和"multiple access"都没错。前者针对的是point-to-point network segment.根据维基百科,"According to the defining IEEE standards for Ethernet, 
a network segment is an electrical connection between networked devices.","on modern twisted-pair Ethernet, a network segment would correspond to the individual connection 
between end station to network equipment (i.e. repeater, hub or switch) or the connections between different pieces of network equipment."后者针对的是"multiple access interface",
各个station仍然在一个collision domain.由此也说明"it is possible to have multiple network segments within a collision domain".而判断属于"bus"还是"star"依据的是前者的意义。

Ehernet Frame Format
  * Preamble(64bits): allows the receiver to synchronize with the signal(sequence of alternating 0s and 1s) (刚好跟正在学习的数电有联系：clock, bit time, 同步和失步)
                  目的是让packet在不同终端有个统一的clock
  * Source and Destination MAC Address(48bits each).
  * Packet type(16 bits): act as demux key to identify the higher level protocol.
  * Data(up to 1500 bytes)
        * Minimally a frame must contain at least 46 bytes of data.
        * Frame must be long enough to detect collision.
  * FSC: CRS(32bits)

注意: 
  * Min 64 bytes, Max 1518 bytes针对的是length of an Ethernet frame,不包括Preamble,因为preamble是属于physical layer的信号，不是数据层的东西,
      所以frame长度是不计入preamble的。
  * 实际上，Preamble = Preamble + SFD(Start Frame Delimiter);
  * Data = LLC + PAD(padding when LLC-Frame < 46 bytes)

MAC is unique, 现在的笔电直接内置。An Ethernet adaptor receives all frames and accepts frames addressed to its own address, frames addressed to the broadcast address
and frames addressed to a multicast address if it has been instructed.

Collision Window(Slot time) = round-trip delay  10Mbps * 51.2us = 512bits，这正是min length of a frame is 64 bytes的原因。

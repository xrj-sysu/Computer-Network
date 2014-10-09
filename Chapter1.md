## Introduction to Computer Networks

Outline
* Applications
* Network Connectivity
* Network Architecture
* Network Performance

(1)The differencies between propagation time(传播时延) and transmission time(传输时延).

Firstly, switch use store-and-forward transmission...(唉，英语无力) 交换机在link的输入端使用存储转发传输机制 which means 交换机必须接受整个packet before transmiting to the link. This is why transmission time actually happens.

To caculate, propagation time = distance / speed of light(电、光啊);  transmission time = size / bandwidth

(2)封包在传输的不同阶段叫法不同，在应用层的时候叫“message”,运输层叫“segment”,网络层叫“datagram”,在链路层叫“frame”,这是因为在每一层相应加了header。

(3)                           Router(路由器)                  Switch(交换机) 
     
      packet的转送     以store and forward            强调硬件式的转换packet
                         方式处理packet               由交换机芯片完成工作

        拓扑结构       不会建立spanning tree,           建立spanning tree
                      而是用routing protocols

        网络描述     interconnected network(WAN)      switched network(LAN)
        
(4)unicast/broadcast/multicast
作用范围：switched network
Check out this neat program I wrote:

## IEEE 802.11 Wireless LAN

outline
* Introduction
* Distributed System
* IEEE 802.11 Frame format
* IEEE 802.11 MAC Architecture
* Distributed Coordination Funtion(DCF)
* Point Coodination Function(PCF)
* IEEE 802.11 Standards

基于两大问题:
1. Hidden node problem:双方虽然听不到对方的讯号，但同时传送给相同的对象会造成冲撞
2. Exposed node problem:双方虽然听得到对方的讯号，但同时可传送给不同的对象

引出:Carrier Sense Multiple Access with Collision Avoidance(CSMA/CA)

其中Key idea of CSMA/CA:
  1. exchange control frames: RTS CTS ACK
  2. for DCF
CSMA/CA(Collision Avoidance), sense the carrier
  ·Idle, wait a DIFS then transmit
  ·Busy, wait channel to idle + wait a DIFS + wait random backoff time, then transmit

802.11 does not support collision detection

一些概念:
Access Points(AP)
distribution system(DS)
active scanning
passive scanning
Distributed Coordination Function(DCF)[竞争式]     
Point Coordination Function(PCF)[非竞争式]   
point coodinator(polling master)   
IFS(Inter-Frame Space)   
contention-free   
superframe   
RTS_Threshold
Net Allocation Vector(NAV)

The technique for selecting an AP: scanning
Probe frame(node) -> Probe Response(AP) -> Association Request(node) -> Association Response(AP)

Carrier Sense shall be performed both through physical and virtual mechanisms.

The frame types should be acknowledged with an ACK frame:
  * Data
  * Poll
  * Request
  * Response

SIFS used for an ACK frame, a CTS frame, by a station responding to any polling

The length of a Superframe is a manageable parameter and that of the CF period may be variable on a per SF basis.

Three Priority levels
  SIFS < PIFS < DIFS

理解讲义的几张流程图极为关键

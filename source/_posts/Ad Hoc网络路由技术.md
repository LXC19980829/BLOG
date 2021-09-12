---
title: Ad Hoc网络路由技术
tags:
  - Ad Hoc
categories:
  - Ad Hoc
keywords: Ad Hoc
description: Ad Hoc
comments: true
toc: true
toc_number: true
auto_open: true
highlight_shrink: false
mathjax: false
katex: false
hide: false
abbrlink: 618d7205
date: 2021-03-10 20:11:40
top_img:
cover: https://cdn.jsdelivr.net/gh/LXC19980829/PicGo123@latest/img/20210417161528.png
sticky:
copyright:
copyright_author:
copyright_author_href:
copyright_url:
copyright_info:
---
> Abstract: Wireless Ad hoc network is a complicated communication system, and its routing technology is one of the most popular and active research topics. Efficient routing protocol enables wireless networks to be more flexibly organized, improving network performance and decreasing overheads. Combining novel technologies at the physical layer, such as Cognitive Radio (CR), Cooperative Communication (CC), and Multiple Input Multiple Output (MIMO), can hugely enhance the performance of Ad hoc routing protocols. 
> Key words:Ad hoc network; routing protocol; wireless communication

> 摘要：无线自组织网络(Ad hoc)是一个复杂的系统，其中路由协议是该领域中的研究热点。通过采用合理的路由技术，可使无线自组网具有更为灵活的组网方式，从而达到提升网络性能、减少网络开销等目的。通过与认知无线电(CR)技术、协同通信(CC)技术以及多输入多输出(MIMO)天线技术等物理层新技术的有效结合，可以大大改善Ad hoc路由协议的性能。

>  <code>关键词：自组织网络；路由协议；无线通信</code>

> 未来移动通信网络除了以低成本达到高数据率外，还要求网络组网灵活，具有适应性和生存能力。无线自组织网络(Ad hoc)[1-4]是一种没有预定的基础设施支撑的自组织可重构的多跳无线网络，可以作为蜂窝移动网络的有效加强。因此，移动自组织网络将因其灵活性而在未来移动通信网络中扮演重要作用。

##  Ad Hoc网络路由协议

> Ad hoc网络中，由于通信半径的限制，网络节点之间是通过多跳数据转发机制进行数据交互的，需要路由协议完成分组转发决策。与传统路由协议相比，Ad hoc路由协议的设计面临着网络拓扑动态变化、带宽受限、信道容量变化、移动终端有限的可用资源等新的问题和挑战。

> 早在1996年，因特网工程任务组(IETF)就成立了移动Ad hoc网络工作小组(MANET WG)，其核心任务就是研究无线自组织网络环境下基于IP协议的路由协议规范和接口设计。IETF RFC2501详细给出了无线Ad hoc网络的应用场合、特征和性能要求。目前，MANET WG已经公布了一系列的有关Ad hoc路由的草案，如动态源路由算法(DSR)、基于反向路径转发的拓扑分发协议(TBRPF)、优化链路状态路由算法(OLSR)、按需距离矢量路由算法(AODV)、临时按序路由算法(TORA)、区域路由算法(ZRP)；此外，研究还提出了许多Ad hoc路由协议，如目的序列距离矢量路由算法(DSDV)、无线路由协议(WRP)、陆标路由协议(LANMAR)、位置辅助路由(LAR)、鱼眼状态路由算法(FSR)。

> 这些路由协议根据所采用的基本路由机制的不同，可分为基于链路状态的路由协议、基于距离矢量的路由协议、源路由协议及反向链路协议；按照网络逻辑结构的不同，可分为平面结构的路由协议和分层结构的路由协议；按照路由发现策略的不同，可分为表驱动路由协议、按需路由协议以及混合路由协议。

##  大规模Ad Hoc网络中的路由技术

> Ad hoc网络规模性[5]的研究可以广义地定义为：研究当网络中有大量节点存在时，网络能否为分组提供可以接受的服务，它与网络大小、节点分布的密度、运行的环境(传播模型、地型环境等)及移动性相关。

> 对于中小规模(通常为几十个节点)Ad hoc网络路由协议的研究已取得了重要进展，而大规模Ad hoc网络的路由技术是Ad hoc网络研究的一个难点，它是指可以支持数百到数千个网络节点的路由算法。国际上早期的一些初步研究结果[6]，如Santivanez等人提出的基于链路状态法的模糊链路状态(FSLS)算法，研究了节点数为100～400时的部分性能；Woo和Singh提出了一个基于位置修正的SLURP算法，研究了节点数为50～1 000时的算法性能；Jinying Li等提出了基于区域的网格(Grid)系统，研究了100～600个节点时的算法性能；Rahul Jain等人提出了基于地理位置的路由算法，研究10～1000个节点的算法性能。

> 现有的路由协议或者利用全网泛洪(Global flooding)或者利用分层的方法完成路由的发现。但是，前者由于开销太大并不适合大规模的网络；后者在分层的过程中需要交互大量信息，而且可能由于节点的移动造成性能的急剧恶化。为了克服这些缺陷Nitin Nahata等人提出了一种基于连接(Contact)点的适用于大规模Ad hoc网络的高效的路由发现策略[7]。它基于“小世界(Small world)”的概念，采用了一种混合的方式：在节点的R跳(通常是3～5跳)范围内采用先验式的路由算法，如DSDV，而在R跳以外通过Contact点进行反应式的路由发现。Contact点是一些捷径点，它通过减小分割度来把网络划分成为一些“小世界”。图1所示为这个过程的示例。

> 此外，Taejoon Park等人还提出了一种基于地理位置的适用于Ad hoc网络的路由协议[8]，它在节点本地区域和分布区域中结合了位置更新机制，同时还根据位置更新门限得到一个最优的配置，以此减小总的路由开销。该协议具有可扩展性，并且路由开销较小，从而延长了节点的寿命。

## 基于新物理层技术的Ad Hoc路由

> 为了满足人们日益增长的通信需求，能够提供更大带宽的物理层传输技术层出不穷，如认知无线电技术、协同通信技术以及多输入多输出(MIMO)天线技术等。它们的出现为Ad hoc网络路由技术的进一步发展带来新的契机。

### 基于认知无线电的路由协议

> 众所周知，频谱资源十分有限，一些非授权频段占用拥挤，而那些授权频段却经常空闲，因此，可以考虑在授权用户不用自己的频率资源时，让一些非授权用户去暂时性地有效利用该空闲频谱，认知无线电[9]就是基于这种想法提出来的一种更智能的频谱共享技术，它可以感知无线通信环境，依据一定的学习和决策算法，动态地检测和有效地利用空闲频谱，大大降低了频谱和带宽对无线技术发展的束缚。它要求非授权用户和授权用户在对频谱资源利用时达到一个平衡，使得非授权用户能在不影响授权用户的前提下进行一些自己的通信。

> 认知无线电技术的特点使得节点间的链路可能经常发生变化，因此，这样的路由协议首先应该是<code>鲁棒的(Robustness)</code>，这种鲁棒性是基于多路径分析的。多一条备选的路由可以大大降低一条路径失效对网络造成的影响，使得网络具备鲁棒性。此外，这样的路由协议还应满足3点要求[10]：

- (1)路由协议应该是<code>先验式</code>的

> 如果采用了反应式的路由协议，更新路由表太浪费时间，分组若要以最小的时延传输就需要采用先验式的路由算法。但是，先验式路由协议会引入更多的控制分组数，而且路由信息的不断更新反而会缩短节点能量的持续时间。

- (2)路由协议应该是<code>基于链路状态</code>的

> 由于物理层的参数经常变化，节点的移动性及传输半径也可能改变，节点的认知能力也有所差异，因此，节点间的链路可以通过计算链路的可靠性来进行选择。

- (3)路由协议应该是分级的

> 分级的路由协议支持不同的移动组。目前认知无线电环境下，以信道的切换次数以及信道的切换频率为衡量标准，已经有基于控制信道的路由算法以及基于空时分组码的路由算法。

### 基于协同通信的路由协议

> 协同通信[11-13]利用节点间的相互协作进行数据通信。它充分利用了无线电波的全向传播特性，使无线网络中的节点相互协作形成了虚拟的天线阵列来获得传统多输入多输出天线技术的空间分集增益，当前协同通信的主要方式有：编码协同，放大中继，解码中继等方式。相对于其他协同方式，编码协同方式将协同通信技术和信道编码技术相结合，在不消耗更多系统资源(带宽等)的前提下获得完全的分集增益。图2所示为协同路由和一般多跳路由的区别。

> 当有从S节点到D节点的数据要发送时，数据依靠中间节点的中继就会到达目的节点，而对于协同路由来说，数据可以经过S→1→D完成传输，同时，位于节点S覆盖范围内的节点2、3也可以听到这样的信息，它们可以不用付出额外的能量去传输数据，这样，就可以消耗更小的能量。

> 目前，基于协同技术的路由可大致分为两类，分别是<code>基于能量的路由策略和基于带宽的路由策略</code>。基于能量的路由策略[12-13]主要针对单个源和目的节点的应用环境，在保证源节点发射信号在接收节点处能达到接收信噪比门限的基础上，通过为协同节点最优化地分配功率，从而达到降低网络总能量开销的目的。基于带宽[11]的路由策略主要是通过引入协同通信技术，以最大化源节点到目的节点间路径的带宽为目标完成路由决策。协同技术在该种路由机制中主要有两种应用方式[11]。一种是在选择好一条源到目的节点路由的基础上，通过在每一跳节点间根据对带宽的改善程度有选择地进行协同，达到提升路由传输能力的目的。这种方式可称为基于协同的路由。另一种方式是在路由选择的同时就考虑到协同技术对每跳传输带宽的影响，从而决定每跳传输是否采用协同通信技术，并选择该情况下带宽最大的路由进行数据传输。该方式称为<code>动态协同路由</code>。

### 基于MIMO的路由协议

> <code>MIMO系统</code>利用空分复用和分集，在不增加额外功率和带宽的前提下提供高的频谱利用率，作为智能天线技术中一个最复杂的技术，MIMO链路现在被普遍应用，并且已经进入了无线局域网(WLAN)、WiMAX及Ad hoc领域，与其相关的路由技术也是现在研究的一个热点问题。

> 目前基于MIMO的适应于无线自组织网络的路由协议并不多见。K.Sundaresan等人在2005年的IEEE 的国际会议(ICNP)上，发表了论文《Routing in Ad-Hoc Networks with MIMO Links》[14]。该文给出了一种适应于MIMO信道条件的自适应路由协议。该协议通过利用MIMO系统两种不同的工作模式：空间复用和空间分集来实现路由的自适应选择。在空间复用模式中，节点通过每个天线发射不同的数据流，能够获得复用增益，提高链路以及整个路由的传输容量。在空间分集模式中，节点在每根天线上发送相同的数据流，以获得分集增益。这种分集技术能够有效地提高通信系统的抗干扰能力，降低系统传输的误比特率，提高链路及路由传输的可靠性，能够满足无线信道条件较差环境的应用要求。

## 结束语

> 本文综述了无线Ad hoc网络中的主要路由协议，着重介绍了<code>能够适应大规模网络环境的Ad hoc网络路由协议及基于新物理层技术的Ad hoc网络路由协议</code>。这些方法在一定程度上可在不同层面满足Ad hoc网络的路由需求。随着人们需求的不断提高，网络的规模化发展是一个必然趋势。如何在大规模的网络中提出更能符合实际应用的路由协议，并结合新的物理层技术实现网络中多种路由协议的平滑过渡是今后Ad hoc网络路由技术研究的重要方向。

>  引用：盛敏,田野,李建东,SHENGMin,TIANYe,LIJian-dong. AdHoc网络路由技术[J]. 中兴通讯技术, 2007, 13(4):8-10.

##  参考文献
[1] Hass Z J, Deng J, Liang B, et al. Wireless Ad hoc networks [M]//Encyclopedia of Telecommunications. New York NY, USA: John Wiley & Sons, 2002.
[2] 苏静, 郭伟. 无线移动自组织网路由协议综述 [J]. 中国测试技术, 2005,31(2):91-93. 
[3] 高云全, 孔婷, 邬家炜. 移动Ad hoc网路由协议综述 [J]. 科技广场, 2005(5):40-43. 
[4] 史美林, 英春. 自组网路由协议综述 [J]. 通信学报, 2001,22(11):93-103. 
[5] 李建东. 大规模无线移动Ad hoc网络 [J]. 深圳大学学报: 理工版, 2004,21(4):283-286. 
[6] LI J. Overview on scalability of routing protocols for mobile Ad hoc networks [D]. New York, NY, USA: Cornell University, 2003.
[7] Nahata N, Pamu P, et al. Efficient resource discovery for large scale Ad hoc networks using contacts [EB/OL]. http://nile.usc.edu/ee499/contacts.
[8] Park T, Shin K G. Optimal tradeoffs for location-based routing in large-scale Ad hoc networks [J]. IEEE/ACM Transmissions on Networking, 2005,13(2):398-410.
[9] 郭彩丽, 张天魁. 认知无线电关键技术及应用的研究现状 [J]. 现代电信科技, 2006(6):29-34.
[10] Pawecza P. Protocol requirements for cognitive radio networks [EB/OL]. 2005-07-20. https://doc.freeband.nl/dscgi/ds.py/Get/File-60831.
[11] Beres E, Adve R S. Cooperation and routing in multi-hop networks [C]// Proceedings IEEE International Conference on Communications, Jun 24-27, 2007, Scotland, UK. 
[12] Xie Fang, Tian Hui, Zhang Ping, et al. Cooperative routing strategies in Ad hoc networks [C]// Proceedings of 61st Vehicular Technology Conference: Vol 4, May 30-Jun 1,2005, Stockholm, Sweden. Piscataway, NJ, USA: IEEE,2005:2509-2512.
[13] Khandani A, Abounadi J, Modiano e, et al. Cooperative routing in wireless networks [C]// Proceedings of Allerton Conference on Communications, Control and Computing, Oct 1-3,2003, Monticello, IL,USA. Boston, MA,USA: Kluwer Academic Publisher, 2003:1270-1279.
[14] Sundaresan K, Sivakumar R. Routing in ad-hoc networks with MIMO links [C]// Proceedings of 13th IEEE International Conference on Network Protocol, Nov 6-9,Boston,MA, USA. Los Alamitos: IEEE Computer Society,2005:85-95.
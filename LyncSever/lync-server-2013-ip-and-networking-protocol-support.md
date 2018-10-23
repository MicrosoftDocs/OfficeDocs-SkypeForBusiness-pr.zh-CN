---
title: Lync Server 2013：IP 和网络协议支持
TOCTitle: IP 和网络协议支持
ms:assetid: b0cffb10-3478-445c-89c7-8cb8b5027424
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg412848(v=OCS.15)
ms:contentKeyID: 49313946
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 中的 IP 和网络协议支持

 

_**上一次修改主题：** 2016-12-08_

Lync Server 2013 支持下列 IP 和网络协议：

  - **IP 协议。**    Lync Server 2013 对服务器网络支持 IP 版本 4 (IPv4) 或 IP 版本 6 (IPv6)。
    
    > [!NOTE]  
    > Lync Server 2013 可以在启用双 IP 堆栈的网络上运行。
    


  - **SIP 传输协议。**   一般情况下，SIP 至少可以使用 3 种传输类型：用户数据报协议 (UDP)、传输控制协议 (TCP) 和传输层安全性 (TLS)。在默认 SIP 传输配置中，TLS 将取代 TCP。在 Lync Server 2013 网络中使用 TLS。在网络边缘， Lync Server 2013 可以通过 TCP 进行交互操作。Lync Server 2013 不支持使用 UDP 进行 SIP 传输，因为 UDP 未达到企业通信安全性、可靠性和可伸缩性的最低标准。有关详细信息，请参阅 NextHop 博客文章“使用 UDP 还是不使用 UDP，这是一个问题”，网址为 [http://go.microsoft.com/fwlink/p/?linkId=185369](http://go.microsoft.com/fwlink/p/?linkid=185369)。
    
    > [!NOTE]  
    > 每个博客的内容及其 URL 如有更改，恕不另行通知。
    


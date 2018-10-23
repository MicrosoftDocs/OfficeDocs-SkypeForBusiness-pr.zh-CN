---
title: Lync Server 2013：企业语音的软件先决条件
TOCTitle: 企业语音的软件先决条件
ms:assetid: 41172119-9631-46c7-9d9f-386d951c650b
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg425916(v=OCS.15)
ms:contentKeyID: 49312628
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 中企业语音的软件先决条件

 

_**上一次修改主题：** 2012-10-03_

验证要在其中部署企业语音的基础结构是否满足以下软件先决条件：

  - 已在网络上安装 Lync Server 2013 Standard Edition 或 Enterprise Edition，并且运行正常。

  - 已在外围网络中部署所有边缘服务器（包括运行 访问边缘服务、 A/V 边缘服务、 Web 会议边缘服务和反向代理的 边缘服务器），并且运行正常。

  - 要将 Exchange 统一消息与 Lync Server 集成，并向 Lync 终结点提供丰富的通知和呼叫日志信息，需要安装 Microsoft Exchange Server 2007 Service Pack 3 (SP3)、Microsoft Exchange Server 2010 或 Microsoft Exchange Server 2013。

  - 已创建一个或多个用户，并对这些用户启用了 Lync Server。

  - 已成功部署 Lync 客户端和设备。

  - 已在网络中的某台服务器上安装 拓扑生成器。

## 后续步骤：验证安全性和配置先决条件

验证企业语音的软件先决条件后，可以使用文档继续准备部署企业语音：

1.  验证安全性、用户配置和硬件先决条件，如 [Lync Server 2013 中企业语音的安全性和配置先决条件](lync-server-2013-security-and-configuration-prerequisites-for-enterprise-voice.md)中所述。

2.  安装中介服务器（如 [在 Lync Server 2013 中安装中介服务器的文件](lync-server-2013-install-the-files-for-mediation-server.md)中所述），但仅 当要部署独立的中介服务器或池时才执行此操作，因为如果进行并置，会在前端池或 Standard Edition Server 部署过程中安装中介服务器。

3.  配置中继连接以为用户提供 PSTN 连接，如 [在 Lync Server 2013 中配置中继](lync-server-2013-configuring-trunks.md)中所述。


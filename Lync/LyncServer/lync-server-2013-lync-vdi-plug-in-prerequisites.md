---
title: Lync Server 2013： Lync VDI 插件先决条件
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Lync VDI plug-in prerequisites
ms:assetid: da25a976-7624-4dfc-b332-9c4db4ee78da
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205304(v=OCS.15)
ms:contentKeyID: 48185552
ms.date: 03/07/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7be6cd7dcf58cae1cfe794c6a27d27fc5aaa5193
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42186105"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="lync-vdi-plug-in-prerequisites-in-lync-server-2013"></a>Lync Server 2013 中的 lync VDI 插件先决条件

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2017-03-07_

在虚拟桌面基础结构（VDI）环境中，虚拟机和用户的本地计算机必须满足本节中概述的要求。

<div>


> [!NOTE]  
> 有关如何安装和部署虚拟化环境的详细信息，请参阅您的虚拟化解决方案提供商。 有关基于 Hyper-v 和远程桌面服务部署虚拟化环境的信息，请参阅 Microsoft TechNet 库中的以下文章： 
> <UL>
> <LI>
> <P>Hyper-v 位置<A class=uri href="https://go.microsoft.com/fwlink/p/?linkid=247514">https://go.microsoft.com/fwlink/p/?linkid=247514</A></P>
> <LI>
> <P>Windows Server&nbsp;2008&nbsp;R2 中的远程桌面服务<A class=uri href="https://go.microsoft.com/fwlink/p/?linkid=247513">https://go.microsoft.com/fwlink/p/?linkid=247513</A></P></LI></UL>



</div>

以下是在数据中心计算机上运行的虚拟机的要求：

  - 虚拟机必须使用 Windows 10、windows 8.1、windows 8、Windows 7 或 Windows Server 2008 R2 以及最新的 service pack 进行配置。

以下是用户和用户的本地计算机的要求：

  - 用户必须驻留在 Lync Server 2013 上。

  - 本地计算机必须运行 Windows Embedded Standard 7 with SP1、Windows 7 SP1、windows 8、Windows 8.1 Embedded 或 Windows 8.1 （未嵌入）。

  - 如果使用远程桌面服务，则 Lync VDI 插件位数（即应用程序是否为32位或64位）必须与本地计算机的操作系统位数匹配。 本地计算机上的操作系统和虚拟机上的操作系统的位数不需要匹配。 如果使用的是其他虚拟化解决方案或平台，请参阅虚拟化解决方案提供商关于位数要求的指南。

  - 本地计算机必须运行最新版本的远程桌面客户端。 从虚拟化解决方案提供商处安装来自 Microsoft 或最新远程桌面客户端软件的远程桌面服务客户端的最新更新。 有关最新的远程桌面服务更新， [https://go.microsoft.com/fwlink/p/?LinkId=268032](https://go.microsoft.com/fwlink/p/?linkid=268032)请参阅。

  - 在本地计算机上，必须配置远程桌面客户端设置，以便在本地计算机上播放音频，并禁用远程录制。 若要在 Windows 中为远程桌面连接配置这些设置，请参阅下一节 "配置远程桌面连接设置"。

<div>

## <a name="to-configure-remote-desktop-connection-settings"></a>配置远程桌面连接设置

若要为 Lync VDI 插件准备 Windows 中的远程桌面连接，请执行以下步骤。

1.  如果本地计算机运行的是 Windows 8，请跳过此步骤。 如果本地计算机运行的是 Windows 7 SP1，请安装最新的 Windows 8 版本的远程桌面服务客户端，网址[https://go.microsoft.com/fwlink/p/?LinkId=268032](https://go.microsoft.com/fwlink/p/?linkid=268032)为。

2.  通过单击 "**开始**"，然后单击 "**远程桌面连接**" 来启动远程桌面服务客户端。

3.  单击 **"选项"**。

4.  单击 "**本地资源**" 选项卡。在 "**远程音频**" 下，单击 "**设置**"，然后执行以下操作：
    
      - 在 "**远程音频播放**" 下，选择 "**在此计算机上播放**"。
    
      - 在 "**远程音频录制**" 下，选择 "**不录制**"。
    
      - 单击“确定”。

5.  单击 "**体验**" 选项卡。在 "**性能**" 下，清除 "**永久位图缓存**" 复选框。

6.  单击 "**常规**" 选项卡。在 "**计算机**" 中，键入虚拟机的名称，然后单击 "**连接**"。

</div>

</div>

<span> </span>

</div>

</div>

</div>


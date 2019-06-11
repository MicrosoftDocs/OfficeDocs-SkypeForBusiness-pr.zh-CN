---
title: Lync Server 2013：移动的拓扑和组件
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Topologies and components for mobility
ms:assetid: be3cae7a-095d-4785-91ba-6fac99eba92a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690037(v=OCS.15)
ms:contentKeyID: 48185282
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 537eda14f2587e06bd8a1112f2a6a44299b0b78e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34845545"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="topologies-and-components-for-mobility-in-lync-server-2013"></a>Lync Server 2013 中移动的拓扑和组件

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2013-02-17_

    The information in this topic pertains to Cumulative Updates for Lync Server 2013: February 2013.

为了在移动设备上支持 Lync 移动应用程序, Lync Server 2013 提供了三种服务: Lync Server 2013 Mcx 移动服务、Lync Server 2013 自动发现服务和 Lync Server 2013 推送通知服务。 Lync Server 2013 的累积更新: 2 月2013为 Lync 2013 移动客户端添加了一项免费的、高级的服务, 其中包括通过使用统一通信 Web API 或 UCWA 的移动支持。 本部分简要介绍这些组件并确定支持移动性的 Lync Server 2013 拓扑。

<div>


> [!NOTE]  
> 移动服务也可在混合部署中使用。 如果用户处于联机状态, 则无需为支持移动性部署服务。 您需要定义自动发现服务的设置以使移动用户能够找到其在线标识。



</div>

<div>


> [!IMPORTANT]  
> 如果你计划任何外部用户连接 (例如, 联盟、外部用户访问或移动功能), 则必须将 Edge 服务器与标准版 server 和前端服务器或前端池配合使用。 标准版服务器和前端服务器或前端池没有必要的组件来允许外部用户访问内部部署, 或用于内部部署与外部用户进行通信。 对于包括与内部用户进行协作或通信的所有方案 (包括移动性), 必须至少部署一个 Edge 服务器和一个反向代理。<BR><EM>推送通知</EM>使用 Lync Online services 的联合身份验证类型, 它托管推式通知交换所 (PNCH)。 推送通知是指在移动设备处于非活动状态时, 由应用程序推送到 Apple iPhone、iPad 和 Windows Phone 的声音通知、屏幕通知 (文本) 和锁屏提醒。 PNCH 从 Lync Server 接收推送通知。 当 PNCH 收到邮件的通知时, PNCH 将通过 Apple 推送通知服务或 Lync Server 2013 推送通知服务将通知转发给移动客户, 具体取决于该消息的目标移动客户端。 PNCH 是这些移动客户端所需的服务。 若要与 Lync Online 联盟, PNCH 使用 Edge 服务器和证书以确保机密性和身份验证、策略以及正确配置的域名系统 (DNS) 记录。 Nokia Symbian 和基于 Android 的 Lync 移动客户端不使用 PNCH。 有关规划和部署 Edge 服务器的详细信息, 请参阅在 lync server <A href="lync-server-2013-planning-for-external-user-access.md">2013 中规划外部用户访问</A>和<A href="lync-server-2013-deploying-external-user-access.md">在 lync Server 2013 中部署外部用户访问</A>。<BR>Lync 2013 移动客户端适用于 Lync Server 2013 的累积更新引入的 Apple 设备的客户端: 2 月2013不再使用推送通知或推送通知交换所 (PNCH)。 Windows Phone 上的 Lync 2013 移动客户端仍然使用推送通知和 (PNCH)。



</div>

<div>

## <a name="mobility-components"></a>移动组件

支持移动性的服务如下所示:

  - **Lync server 2013 统一通信 Web API (UCWA)**   提供与 Lync server 2013 中的移动和 Web 客户端进行实时通信的服务。 当你部署 Lync Server 2013 的累积更新时: 2 月2013至前端服务器和控制器, 安装将在内部和外部 web 服务 (Ucwa) 中创建一个虚拟目录。 属于 Ucwa 虚拟目录的 web 组件接受来自启用 UCWA 的客户端的调用。 客户端应用通过 REST 界面与状态、联系人、即时消息、VoIP、视频会议和协作进行通信。 UCWA 使用基于 P 获取的通道向客户端应用发送事件, 例如传入呼叫、传入即时消息或消息。
    
    <div>
    

    > [!NOTE]  
    > <EM>REST</EM>或 representational 状态传送是一种软件体系结构样式, 适用于广泛采用多种形式的分布式系统, 并且非常适合于一般的 Web 服务要求。

    
    </div>

  - **Lync Server 2013 移动服务 (Mcx)**   此服务在移动设备上支持 Lync 功能, 例如即时消息 (IM)、状态和联系人。 移动服务在每个池中的每个前端服务器上安装, 用于在移动设备上支持 Lync 功能。 安装 Lync Server 2013 时, 将在内部网站和前端服务器上的外部网站下创建新的虚拟目录 (Mcx)。
    
    <div>
    

    > [!IMPORTANT]  
    > Lync server 2013 与 Lync Server 2013 的累积更新: 2 月2013支持 Lync Server 2010 的累积更新中引入的移动服务: 2011 年11月 (通常称为 Mcx) 和 UCWA web 组件。 这两个移动服务的组合可提供与 lync Server 2013 上的 Lync 2010 移动版和 Lync 2013 移动客户端用户的互操作性和使用。

    
    </div>

  - **Lync server 2013 自动发现服务**   此服务标识用户的位置, 并允许移动设备和其他 Lync 客户端查找资源 (如 Lync Server 2013 Web 服务的内部和外部 url) 和 URLMcx 或 UCWA —无论网络位置如何。 自动发现使用硬编码的主机名称 (lyncdiscoverinternal 在网络内部使用的用户; lyncdiscover 用于网络外部用户) 和用户的 SIP 域。 它支持使用 HTTP 或 HTTPS 的客户端连接。
    
    自动发现服务在每个前端服务器和每个池中的每个控制器上安装, 用于在移动设备上支持 Lync 功能。 安装自动发现服务时, 将在内部网站和外部网站 (前端服务器和控制器) 下创建新的虚拟目录 (自动发现)。
    
    <div>
    

    > [!NOTE]  
    > 自动发现服务将在此处列出, 因为它在提供移动客户端服务时仍然是关键组件。 Lync Server 2013 中自动发现的角色已被扩展, 以便为所有客户端提供服务。 有关规划自动发现服务的详细信息, 请参阅<A href="lync-server-2013-planning-for-autodiscover.md">在 Lync Server 2013 中规划自动发现</A>。

    
    </div>

  - **推送通知服务**   此服务是位于 Lync Online 数据中心的基于云的服务。 当受支持的 Apple iOS 设备或 Windows Phone 上的 Lync mobile 应用程序处于非活动状态时, 它无法响应新事件, 例如新的即时消息 (IM) 邀请、错过的即时消息、错过的呼叫或语音邮件, 因为这些设备不支持在后台运行的移动应用程序。 在这些情况下, 将向移动设备发送新事件 (称为*推送通知*) 的通知。 移动服务将通知发送到基于云的推送通知服务, 然后将通知发送到 Apple 推送通知服务 (APN) (适用于受支持的 Apple iOS 设备) 或 Microsoft 推送通知服务 (MPNS) (适用于 Windows Phone), 然后将其发送到移动设备。 然后, 用户可以在移动设备上响应通知以激活应用程序。
    
    Apple 和 Windows Phone 设备上的 Lync 2010 Mobile 使用推送通知。 Lync 2013 移动客户端适用于 Lync Server 2013 的累积更新引入的 Apple 设备: 2 月2013不再使用推送通知或推送通知交换所 (PNCH)。

下图说明了推送通知服务如何在使用 UCWA 和 Lync 2013 移动客户端的 Lync Server 2013 拓扑中使用。

![166d60fd-ff71-4ffe-9f66-3c8bbde0b5ae](images/Hh690037.166d60fd-ff71-4ffe-9f66-3c8bbde0b5ae(OCS.15).jpg "166d60fd-ff71-4ffe-9f66-3c8bbde0b5ae")

在 Lync Server 2010 的累积更新中引入:11 月 2011, Mcx 服务向 Lync 2010 移动客户端提供服务。 下图显示了使用 Mcx 和 Lync 2010 移动客户端对拓扑应用的推送通知服务。

![3081634e-60e7-4348-b24e-bbbf05a90f5f](images/Hh690037.3081634e-60e7-4348-b24e-bbbf05a90f5f(OCS.15).jpg "3081634e-60e7-4348-b24e-bbbf05a90f5f")

</div>

<div>

## <a name="supported-topologies"></a>支持的拓扑

应用 Lync Server 2013 的累积更新: 2 月2013将添加 UCWA web 组件以支持 Lync 2013 移动客户端功能在下列拓扑中的移动:

  - Lync Server 2013 标准版

  - Lync Server 2013 企业版

边缘服务器可以是 Lync Server 2010 Edge 服务器。

没有 Lync Server 2013 的累积更新的 Lync Server 2013 部署: 2 月2013将使用 Mcx 移动服务, 并且只能为 Lync 2010 手机提供服务。

<div>


> [!IMPORTANT]  
> 移动服务在与具有两个网络接口的中介服务器角色 collocated 的前端服务器上受支持, 但你必须采取相应的步骤来配置这些接口。 必须将 IP 地址分配给将作为中介服务器进行通信的特定接口, 以及将作为前端服务器通信的网络接口 IP。 你可以在拓扑生成器中执行此操作, 方法是为每个服务选择正确的 IP 地址, 而不是使用默认<STRONG>使用所有配置的 IP 地址</STRONG>。



</div>

</div>

<div>

## <a name="see-also"></a>另请参阅


[在 Lync Server 2013 中规划外部用户访问](lync-server-2013-planning-for-external-user-access.md)  
[在 Lync Server 2013 中部署外部用户访问](lync-server-2013-deploying-external-user-access.md)  
[在 Lync Server 2013 中规划自动发现](lync-server-2013-planning-for-autodiscover.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


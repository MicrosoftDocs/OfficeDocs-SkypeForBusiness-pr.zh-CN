---
title: Lync Server 2013：移动性的拓扑和组件
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Topologies and components for mobility
ms:assetid: be3cae7a-095d-4785-91ba-6fac99eba92a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690037(v=OCS.15)
ms:contentKeyID: 48185282
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4b27472526f98bc0f867b027fe111aac9c4f9aab
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48535969"
---
# <a name="topologies-and-components-for-mobility-in-lync-server-2013"></a>Lync Server 2013 中的移动性拓扑和组件

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2013-02-17_

    The information in this topic pertains to Cumulative Updates for Lync Server 2013: February 2013.

为了在移动设备上支持 Lync 移动应用程序，Lync Server 2013 提供了三种服务： Lync Server 2013 Mcx 移动服务、Lync Server 2013 自动发现服务和 Lync Server 2013 推送通知服务。 Lync Server 2013 的累积更新：二月份2013为 Lync 2013 移动客户端添加了免费的、高级的服务，并通过使用统一通信 Web API 或 UCWA 实现了移动性支持。 本节简要介绍了这些组件，并标识了支持移动性的 Lync Server 2013 拓扑。

<div>


> [!NOTE]  
> 混合部署中也提供了移动服务。 如果您的用户驻留在联机部署中，则不要求您部署用于支持移动的服务。 您需要为自动发现服务定义一个设置，以使移动用户能够查找其联机标识。



</div>

<div>


> [!IMPORTANT]  
> 如果您正在规划任何外部用户连接 (例如，联盟、外部用户访问或移动功能) ，则必须将边缘服务器与 Standard Edition server 和前端服务器或前端池结合使用。 Standard Edition server 和前端服务器或前端池不具有使外部用户能够访问内部部署的必要组件，或用于与外部用户进行通信的内部部署。 对于包括外部用户协作或与内部用户通信的所有方案，包括移动性，必须至少部署一个边缘服务器和一个反向代理。<BR><EM>推送通知</EM> 使用与 Lync Online services （承载推送通知交换所 (PNCH）) 的联合身份验证类型。 推送通知是指在移动设备处于非活动状态时，由应用程序推送到 Apple iPhone、iPad 和 Windows Phone 的声音警报、屏幕警报 (文本) 和徽章。 PNCH 从 Lync Server 接收推送通知。 当 PNCH 收到邮件通知时，PNCH 基于邮件所面向的移动客户端，通过 Apple 推送通知服务或 Lync Server 2013 推送通知服务，将通知转发给移动客户端。 PNCH 对于这些移动客户端而言是一项必需服务。 若要联合使用 Lync Online，PNCH 使用边缘服务器和证书来确保机密性和身份验证、策略以及正确配置的域名系统 (DNS) 记录。 Nokia Symbian 和基于 Android 的 Lync 移动客户端不使用 PNCH。 有关规划和部署边缘服务器的详细信息，请参阅在 lync server <A href="lync-server-2013-planning-for-external-user-access.md">2013 中规划外部用户访问</A> 和 <A href="lync-server-2013-deploying-external-user-access.md">在 lync Server 2013 中部署外部用户访问</A>。<BR>Lync 2013 Mobile 客户端（适用于使用 Lync Server 2013 的累积更新引入的 Apple 设备）：二月份2013不再使用推送通知或推送通知交换所 (PNCH) 。 Windows Phone 上的 Lync 2013 移动客户端仍使用推送通知和 (PNCH) 。



</div>

<div>

## <a name="mobility-components"></a>移动组件

以下是支持移动的服务：

  - **Lync Server 2013 统一通信 WEB API (UCWA) **    提供用于在 Lync Server 2013 中与移动和 web 客户端进行实时通信的服务。 当您将 Lync Server 2013 2013 的累积更新部署到前端服务器和控制器时，安装程序会在内部和外部 web 服务 (Ucwa) 中创建一个虚拟目录。 作为 Ucwa 虚拟目录一部分的 web 组件接受来自启用 UCWA 的客户端的调用。 客户端应用通过 REST 界面与状态、联系人、即时消息、VoIP、视频会议和协作进行通信。 UCWA 使用基于 P GET 的通道向客户端应用发送事件，例如传入呼叫、传入即时消息或邮件。
    
    <div>
    

    > [!NOTE]  
    > <EM>REST</EM> 或代表性状态传输是一种软件体系结构样式，适用于广泛采用多种形式的分布式系统，非常适合一般情况下的 Web 服务要求。

    
    </div>

  - **Lync Server 2013 移动服务 (Mcx) **    此服务支持移动设备上的 Lync 功能，如即时消息 (IM) 、状态和联系人。 移动服务安装在每个池中的每个前端服务器上，以支持移动设备上的 Lync 功能。 安装 Lync Server 2013 时，会在内部网站和前端服务器上的外部网站下创建一个新的虚拟目录 (Mcx) 。
    
    <div>
    

    > [!IMPORTANT]  
    > Lync Server 2013 with the lync Server 2013 的累积更新：2月2013支持 Lync Server 2011 2010 的累积更新中引入的移动服务（通常称为 Mcx）和 UCWA web 组件。 在 Lync Server 2013 上，这两种移动服务的组合提供了互操作性并供用户使用 Lync 2010 移动和 Lync 2013 移动客户端。

    
    </div>

  - **Lync Server 2013 自动发现服务**    此服务标识用户的位置，并使移动设备和其他 Lync 客户端能够查找资源（例如 Lync Server 2013 Web 服务的内部和外部 Url）以及 Mcx 或 UCWA 的 URL —而不考虑网络位置。 自动发现对网络内的用户 (lyncdiscoverinternal. 使用硬编码的主机名。lyncdiscover. 在网络外部的用户) 和用户的 SIP 域。 它支持使用 HTTP 或 HTTPS 的客户端连接。
    
    自动发现服务安装在每个前端服务器上和每个池中的每个控制器上，以支持移动设备上的 Lync 功能。 在安装自动发现服务时，会在内部网站和外部网站（前端服务器和控制器）下创建一个新的虚拟目录 (自动发现) 。
    
    <div>
    

    > [!NOTE]  
    > 自动发现服务在此处列出，因为它在提供移动客户端服务时仍是一个关键组件。 Lync Server 2013 中的自动发现角色已扩展为为所有客户端提供服务。 有关对自动发现服务进行规划的详细信息，请参阅 <A href="lync-server-2013-planning-for-autodiscover.md">在 Lync Server 2013 中规划自动发现</A>。

    
    </div>

  - **推送通知服务**    此服务是一个基于云的服务，位于 Lync Online 数据中心中。 当受支持的 Apple iOS 设备或 Windows Phone 上的 Lync 移动应用程序处于非活动状态时，它无法响应新事件，例如新的即时消息 (IM) 邀请、错过的即时消息、未接来电或语音邮件，因为这些设备不支持在后台运行的移动应用程序。 在这些情况下，会将新事件通知（称为 *推送通知*）发送到移动设备。 移动服务将通知发送到基于云的推送通知服务，该服务随后会将通知发送到 Apple 推送通知服务 (APNS)  (以获取受支持的 Apple iOS 设备) 或 Microsoft 推送通知服务 (MPNS)  (，然后将其发送到移动设备。 然后，用户可以在移动设备上响应通知以激活应用程序。
    
    Apple 和 Windows Phone 设备上的 Lync 2010 Mobile 使用推送通知。 Lync 2013 移动客户端（适用于使用 Lync Server 2013 的累积更新引入的 Apple 设备）：二月2013不再使用推送通知或推送通知交换所 (PNCH) 。

下图说明了推送通知服务在使用 UCWA 和 Lync 2013 移动客户端的 Lync Server 2013 拓扑中的适合程度。

![166d60fd-ff71-4ffe-9f66-3c8bbde0b5ae](images/Hh690037.166d60fd-ff71-4ffe-9f66-3c8bbde0b5ae(OCS.15).jpg "166d60fd-ff71-4ffe-9f66-3c8bbde0b5ae")

在 Lync Server 2010 的累积更新中引入：11月2011，Mcx 服务为 Lync 2010 移动客户端提供服务。 下图演示了推送通知服务，因为它适用于使用 Mcx 和 Lync 2010 移动客户端的拓扑。

![3081634e-60e7-4348-b24e-bbbf05a90f5f](images/Hh690037.3081634e-60e7-4348-b24e-bbbf05a90f5f(OCS.15).jpg "3081634e-60e7-4348-b24e-bbbf05a90f5f")

</div>

<div>

## <a name="supported-topologies"></a>支持的拓扑

对 Lync Server 2013 应用累积更新：二月份2013添加 UCWA web 组件以支持以下拓扑中的 Lync 2013 移动客户端功能的移动性：

  - Lync Server 2013 Standard Edition

  - Lync Server 2013 企业版

边缘服务器可以是 Lync Server 2010 边缘服务器。

没有 Lync Server 2013 累积更新的 Lync Server 2013 部署：2月2013将使用 Mcx 移动服务，并且只能为 Lync 2010 Mobile 提供服务。

<div>


> [!IMPORTANT]  
> 移动服务在并置的前端服务器上受支持，后者与具有两个网络接口的中介服务器角色一起使用，但您必须采取相应的步骤来配置这些接口。 您必须将 IP 地址分配给将作为中介服务器进行通信的特定接口，以及将作为前端服务器进行通信的网络接口 IP。 您可以在拓扑生成器中执行此操作，方法是为每个服务选择正确的 IP 地址，而不是使用默认值 " <STRONG>使用所有已配置的 ip 地址</STRONG>"。



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


---
title: Lync Server 2013：移动的拓扑和组件
TOCTitle: 移动的拓扑和组件
ms:assetid: be3cae7a-095d-4785-91ba-6fac99eba92a
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Hh690037(v=OCS.15)
ms:contentKeyID: 49314096
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 中移动的拓扑和组件

 

_**上一次修改主题：** 2013-02-17_

    The information in this topic pertains to Cumulative Updates for Lync Server 2013: February 2013.

为支持移动设备上的 Lync 移动应用程序，Lync Server 2013 提供了三项服务： Lync Server 2013 Mcx Mobility Service、 Lync Server 2013 自动发现服务以及 Lync Server 2013 推送通知服务。2013 年 2 月版 Lync Server 2013 累积更新增加了一项免费的高级服务 Lync 2013 Mobile 客户端，该服务通过统一通信 Web API 或 UCWA 提供移动支持。本节简要介绍这些组件并确定支持移动性的 Lync Server 2013 拓扑。

> [!NOTE]  
> 混合部署中也提供了移动服务。如果您的用户驻留在联机部署中，则无需部署用于支持移动性的服务。您无需为自动发现服务定义设置，即可允许移动用户查找他们的联机标识。


> [!IMPORTANT]  
> 如果您正在规划任何外部用户连接（例如，联盟、外部用户访问或移动功能），则必须将 边缘服务器与 Standard Edition Server以及 前端服务器或 前端池结合使用。 Standard Edition Server 和 前端服务器或 前端池不需要任何必需组件，即可允许外部用户访问您的内部部署，或者允许内部部署与您的外部用户进行通信。对于包括与内部用户进行协作或通信的外部用户的所有方案（包括移动性），您必须至少部署一个 边缘服务器和一个反向代理。<br />
> <em>推送通知</em> 使用一种与 Lync Online 服务的联盟，以承载推送通知交换所 (PNCH)。当移动设备处于非活动状态时，推送通知是指声音提醒、屏幕上的通知（文本），以及由应用程序推送到 Apple iPhone、iPad 和 Windows Phone 的徽章。PNCH 会接收来自 Lync Server 的推送通知。当 PNCH 收到消息通知时，它将根据消息所针对的移动客户端，通过 Apple 推送通知服务或 Lync Server 2013 推送通知服务将通知转发到移动客户端。PNCH 对于这些移动客户端而言是一项必需服务。为了与 Lync Online 联盟，PNCH 会使用 边缘服务器和证书，以确保保密性和身份验证、策略，以及正确配置的域名系统 (DNS) 记录。基于 Nokia Symbian 和 Android 的 Lync Mobile 客户端不使用 PNCH。有关规划和部署 边缘服务器的详细信息，请参阅 <a href="lync-server-2013-planning-for-external-user-access.md">在 Lync Server 2013 中规划外部用户访问</a>和 <a href="lync-server-2013-deploying-external-user-access.md">在 Lync Server 2013 中部署外部用户访问</a>。<br />
> 随 2013 年 2 月版 Lync Server 2013 累积更新引入的、适用于 Apple 设备的 Lync 2013 Mobile 客户端不再使用推送通知或推送通知交换所 (PNCH)。但 Windows Phone 上的 Lync 2013 Mobile 客户端仍使用推送通知和 PNCH。



## 移动组件

以下是支持移动的服务：

  - **Lync Server 2013 统一通信 Web API (UCWA)**   提供与 Lync Server 2013 中的移动客户端和 Web 客户端进行实时通信的服务。在将 2013 年 2 月版 Lync Server 2013 累积更新部署到 前端服务器和 控制器中时，安装过程会在内部和外部 Web 服务中创建一个虚拟目录 (Ucwa)。包含在该 Ucwa 虚拟目录中的 Web 组件将接受来自支持 UCWA 的客户端的呼叫。客户端应用程序通过 REST 接口实现状态、联系人、即时消息、VoIP、视频会议和协作通信。UCWA 使用基于 P-GET 的通道发送事件，例如来电、传入的即时消息或者发送到客户端应用程序的消息。
    
    > [!NOTE]
    > <em>REST</em> （也称为“代表性状态传输”）是一种以多种形式得到广泛应用的、针对分布式系统的软件体系结构样式。它通常能够较好地符合 Web 服务的各项要求。


  - **Lync Server 2013 Mobility Service (Mcx)** 该服务支持移动设备上的 Lync 功能，例如即时消息 (IM)、状态和联系人。Mobility Service 安装在每个池中的每台 前端服务器上，旨在支持移动设备上的 Lync 功能。在安装 Lync Server 2013 时，会在 前端服务器上的内部和外部网站下同时创建一个新的虚拟目录 (Mcx)。
    
    > [!IMPORTANT]
    > 包含 2013 年 2 月版 Lync Server 2013 累积更新的 Lync Server 2013 支持 2011 年 11 月版 Lync Server 2010 累积更新中引入的 Mobility Service（通常称为 Mcx）和 UCWA Web 组件。这两种移动服务的组合可提供互操作性，并且使用户能够在 Lync Server 2013 上结合使用 Lync 2010 Mobile 和 Lync 2013 Mobile 客户端。


  - **Lync Server 2013 自动发现服务**   此服务确定用户的位置，并使移动设备和其他 Lync 客户端能够定位资源（例如，Lync Server 2013 Web 服务的内部和外部 URL 以及 Mcx 或 UCWA 的 URL），与网络位置无关。自动发现功能使用硬编码的主机名（对于网络内部用户，为 lyncdiscoverinternal；对于网络外部用户，为 lyncdiscover）和用户的 SIP 域。它支持使用 HTTP 或 HTTPS 的客户端连接。
    
    自动发现服务安装在每个池中的每台 前端服务器上和每个 控制器上，旨在支持移动设备上的 Lync 功能。在安装自动发现服务时，会在 前端服务器和 控制器上的内部和外部网站下同时创建一个新的虚拟目录 (Autodiscover)。
    
    > [!NOTE]
    > 在此处列出自动发现服务是因为它在提供移动客户端服务时保留了关键组件。 Lync Server 2013 中自动发现的角色已扩展为可为所有客户端提供服务。有关规划自动发现服务的详细信息，请参阅 <a href="lync-server-2013-planning-for-autodiscover.md">规划自动发现</a>。


  - **推送通知服务**   此服务是一项位于 Lync Online 数据中心内的基于云的服务。当受支持的 Apple iOS 设备或 Windows Phone 上的 Lync 移动应用程序处于非活动状态时，它无法响应新的事件（例如，新的即时消息 (IM) 邀请、错过的即时消息、错过的呼叫或语音邮件），因为这些设备不支持在后台运行的移动应用程序。在此情况下，会向移动设备发送新事件的通知（称作*推送通知*）。Mobility Service 会将该通知发送到基于云的推送通知服务，然后该服务会将通知发送到 Apple 推送通知服务 (APNS)（对于受支持的 Apple iOS 设备）或 Microsoft 推送通知服务 (MPNS)（对于 Windows Phone），这两种服务稍后会将通知发送到移动设备。然后，用户可在移动设备上响应该通知以激活应用程序。
    
    Apple 和 Windows Phone 设备上的 Lync 2010 Mobile 使用推送通知。而随 2013 年 2 月版 Lync Server 2013 累积更新引入的、适用于 Apple 设备的 Lync 2013 Mobile 客户端不再使用推送通知或推送通知交换所 (PNCH)。

下图说明了推送通知服务如何符合使用 UCWA 和 Lync 2013 Mobile 客户端的 Lync Server 2013 拓扑。

![推送通知服务 UCWA](images/Hh690037.166d60fd-ff71-4ffe-9f66-3c8bbde0b5ae(OCS.15).jpg "推送通知服务 UCWA")

在 2011 年 11 月版 Lync Server 2010 累积更新中引入的 Mcx 服务可为 Lync 2010 Mobile 客户端提供服务。下图说明了推送通知服务，因为它适用于使用 Mcx 和 Lync 2010 Mobile 客户端的拓扑。

![推送通知服务 MCX](images/Hh690037.3081634e-60e7-4348-b24e-bbbf05a90f5f(OCS.15).jpg "推送通知服务 MCX")

## 支持的拓扑

应用 2013 年 2 月版 Lync Server 2013 累积更新时会添加 UCWA Web 组件，以便在下列拓扑中为 Lync 2013 Mobile 客户端功能提供移动支持：

  - Lync Server 2013 标准版

  - Lync Server 2013 企业版

边缘服务器可以是 Lync Server 2010  边缘服务器。

不包含 2013 年 2 月版 Lync Server 2013 累积更新的 Lync Server 2013 部署将使用 Mcx Mobility Service，并且只能为 Lync 2010 Mobile 提供服务。

> [!IMPORTANT]
> Mobility Service 在通过两个网络接口与 中介服务器角色并置的 前端服务器上受支持，但您必须执行适当的步骤来配置这些接口。您必须为将作为 中介服务器通信的特定接口，以及将作为 前端服务器通信的网络接口 IP 分配 IP 地址。通过在 拓扑生成器中为每项服务选择正确的 IP 地址，而不是使用默认的“使用所有已配置的 IP 地址”，您可以实现此目的。


## 另请参阅

#### 其他资源

[在 Lync Server 2013 中规划外部用户访问](lync-server-2013-planning-for-external-user-access.md)  
[在 Lync Server 2013 中部署外部用户访问](lync-server-2013-deploying-external-user-access.md)  
[规划自动发现](lync-server-2013-planning-for-autodiscover.md)


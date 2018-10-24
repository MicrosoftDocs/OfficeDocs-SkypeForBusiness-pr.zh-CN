---
title: Lync Server 2013：定义会议要求
TOCTitle: 定义会议要求
ms:assetid: 5c83e268-22bf-42b2-bac3-3237b5e02e03
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ204935(v=OCS.15)
ms:contentKeyID: 49312976
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 在 Lync Server 2013 中定义会议要求

 

_**上一次修改主题：** 2012-09-30_

在确定要部署的会议功能时，需要考虑您希望向用户提供的功能和网络带宽功能。以下问题列表将指导您完成会议规划过程，以便根据您的组织的要求确定应部署哪些会议功能。

  - **是否要启用包括文档协作和应用程序共享的 Web 会议？**
    
    如果是，则必须在 Microsoft Lync Server 2013 规划工具或拓扑生成器 中对前端池启用会议。启用会议时会同时启用 Web 会议和 A/V 会议。
    
    与文档协作相比，应用程序共享要求使用更多的网络带宽。 Lync Server 2013 提供了限制机制来控制每个应用程序共享会话。默认情况下，每个会话设置为 1.5 KB/秒。
    
    如果您不希望启用应用程序共享，但希望启用文档协作，则可以启用会议并使用会议策略来禁用应用程序共享。有关配置会议策略的详细信息，请参阅 [会议策略](lync-server-2013-conferencing-policies.md)。
    
    若要支持用户共享 PowerPoint 演示文稿，则需要配置 Office Web Apps Server。有关配置 Office Web Apps Server 的详细信息，请参阅 [配置与 Office Web Apps Server 和 Lync Server 2013 的集成](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md)。

  - **是否要启用 A/V 会议？**
    
    如果是，则必须在 Lync Server 2013 规划工具或 拓扑生成器中对 前端池启用会议。启用会议时会同时启用 Web 会议和 A/V 会议。
    
    与 Web 会议（包括文档协作和应用程序共享）相比，A/V 会议要求并使用更多的网络带宽。如果您不希望启用 A/V 会议，但希望启用 Web 会议，则可以启用会议并使用会议策略来禁用 A/V 会议。
    
    如果希望启用音频会议但不启用视频会议，则可以启用 A/V 会议并使用会议策略来阻止视频会议。或者，可以启用 A/V 会议并且只允许某些用户来启动或参加 A/V 会议。
    
    > [!NOTE]  
    > 企业语音对于 A/V 会议不是必需的。如果您启用 A/V 会议，并且您的用户有音频设备，则他们可以将音频添加到其会议，即使您使用 PBX 作为电话解决方案也是如此。
    


  - **使用 PSTN 电话时，是否要允许用户加入会议的音频部分？**
    
    如果是，则部署并启用电话拨入式会议。然后，组织内部和外部的受邀用户可以使用 PSTN 电话加入会议的音频部分。

  - **是否希望允许使用 Lync Server 2013 客户端的外部用户参入您已启用的会议类型？**
    
    如果是，则应部署边缘服务器。允许外部参加会议可以最大限度地提高您在 Lync Server 2013 方面的投资回报。例如，拥有便携式计算机的用户可通过 Lync Server 2013 从任何地方（家中、机场或客户现场）加入会议。
    
    此外，在部署 边缘服务器后，可以与其他组织（如您的客户或供应商）建立联盟关系，这样，来自这些组织的用户便可以更轻松地与您的用户协作。
    
    有关部署 边缘服务器的详细信息，请参阅 [在 Lync Server 2013 中规划外部用户访问](lync-server-2013-planning-for-external-user-access.md)和 [在 Lync Server 2013 中部署外部用户访问](lync-server-2013-deploying-external-user-access.md)。有关为 Office Web Apps Server 启用外部访问的详细信息，请参阅 [在 Lync Server 2013 中使用反向代理服务器发布 Office Web Apps Server](lync-server-2013-publishing-office-web-apps-server-using-a-reverse-proxy-server.md)。

  - **是否要控制可加入 Lync Server 2013 会议的客户端？**
    
    如果是，则应配置与会页面，以便只有要支持的客户端选项可用。用户每次单击链接加入预定的会议时， Lync Server 2013 都会检测计算机上是否已安装客户端。然后，启动默认客户端，并打开包含备用客户端的链接的与会页面。与会页面始终包含使用 Microsoft Lync Web App 的选项。除了此选项之外，还可以决定是否包含 与会者 和早期版本的 Communicator 的链接。有关详细信息，请参阅 [在 Lync Server 2013 中配置与会页面](lync-server-2013-configuring-the-meeting-join-page.md)。

## 本部分内容

  - [Web 会议要求](lync-server-2013-web-conferencing-requirements.md)

  - [A/V 会议要求](lync-server-2013-a-v-conferencing-requirements.md)

  - [电话拨入式会议要求](lync-server-2013-dial-in-conferencing-requirements.md)

## 另请参阅

#### 其他资源

[在 Lync Server 2013 中规划会议](lync-server-2013-planning-for-conferencing.md)  
[Lync Server 2013 中会议的部署清单](lync-server-2013-deployment-checklist-for-conferencing.md)


---
title: Lync Server 2013：定义会议要求
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Defining your requirements for conferencing
ms:assetid: 5c83e268-22bf-42b2-bac3-3237b5e02e03
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204935(v=OCS.15)
ms:contentKeyID: 48184255
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 60193673efff29ec877626a9c5c18be23507e6fa
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34830702"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="defining-your-requirements-for-conferencing-in-lync-server-2013"></a>在 Lync Server 2013 中定义会议要求

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2012-09-30_

在确定要部署的会议功能时，需要考虑您希望向用户提供的功能和网络带宽功能。 下面的问题列表将指导你完成会议规划过程, 以根据组织的要求确定应部署的会议功能。

  - **是否要启用包括文档协作和应用程序共享的 Web 会议？**
    
    如果是这样, 您必须在 Microsoft Lync Server 2013、计划工具或拓扑生成器中启用您的前端池的会议。 启用会议时, 同时启用 web 会议和 A/V 会议。
    
    与文档协作相比，应用程序共享要求使用更多的网络带宽。 Lync Server 2013 提供控制每个应用程序共享会话的节流机制。 默认情况下，每个会话设置为 1.5 KB/秒。
    
    如果您不想启用应用程序共享, 但需要文档协作, 则可以启用会议并使用会议策略来禁用应用程序共享。 有关配置会议策略的详细信息, 请参阅[Lync Server 2013 中的会议策略](lync-server-2013-conferencing-policies.md)。
    
    若要支持用户共享 PowerPoint 演示文稿，则需要配置 Office Web Apps Server。 有关配置 Office Web Apps 服务器的详细信息, 请参阅[配置与 Office Web Apps server 和 Lync server 2013 的集成](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md)。

  - **是否要启用 A/V 会议？**
    
    如果是这样, 您必须在 Lync Server 2013、计划工具或拓扑结构生成器中启用您的前端池的会议。 启用会议时, 同时启用 web 会议和 A/V 会议。
    
    A/V 会议要求和使用比 web 会议更多的网络带宽 (包括文档协作和应用程序共享)。 如果您不想启用 A/V 会议, 但想要启用 web 会议, 则可以启用会议并使用会议策略来禁用 A/V 会议。
    
    如果想要启用音频会议, 而不是视频会议, 可以启用 A/V 式会议并使用会议策略来阻止视频会议。 或者，可以启用 A/V 会议并且只允许某些用户来启动或参加 A/V 会议。
    
    <div>
    

    > [!NOTE]  
    > 企业语音对于 A/V 会议不是必需的。如果您启用 A/V 会议，并且您的用户有音频设备，则他们可以将音频添加到其会议，即使您使用 PBX 作为电话解决方案也是如此。

    
    </div>

  - **您是否希望让用户在使用 PSTN 手机时加入会议的音频部分？**
    
    如果是，则部署并启用电话拨入式会议。然后，组织内部和外部的受邀用户可以使用 PSTN 电话加入会议的音频部分。

  - **是否要为使用 Lync Server 2013 客户端的外部用户加入已启用的会议类型？**
    
    如果是这样, 你应该部署边缘服务器。 通过允许外部参与会议, 您可以在 Lync Server 2013 中获得最大投资。 例如, 具有 Lync Server 2013 的便携式计算机的用户可以从他们的任何位置 (在家中、在机场或在客户的场所) 加入会议。
    
    此外, 部署了 Edge 服务器后, 您可以创建与其他组织 (如客户或供应商) 的联盟关系, 并且这些组织中的用户可以更轻松地与您的用户进行协作。
    
    有关部署边缘服务器的详细信息, 请参阅[在 Lync server 2013 中规划外部用户访问](lync-server-2013-planning-for-external-user-access.md)和[在 lync Server 2013 中部署外部用户访问](lync-server-2013-deploying-external-user-access.md)。 有关启用 Office Web Apps 服务器的外部 access 的详细信息, 请参阅[使用反向代理服务器在 Lync Server 2013 中发布 Office Web Apps 服务器](lync-server-2013-publishing-office-web-apps-server-using-a-reverse-proxy-server.md)。

  - **是否要控制可加入 Lync Server 2013 会议的客户端？**
    
    如果是，则应配置与会页面，以便只有要支持的客户端选项可用。 每当用户单击链接加入计划的会议时, Lync Server 2013 将检测是否已在计算机上安装了客户端。 然后，启动默认客户端，并打开包含备用客户端的链接的与会页面。 会议加入页面始终包含使用 Microsoft Lync Web App 的选项。 除了此选项之外，还可以决定是否包含 Attendee 和早期版本 Communicator 的链接。 有关详细信息, 请参阅[在 Lync Server 2013 中配置会议加入页面](lync-server-2013-configuring-the-meeting-join-page.md)。

<div>

## <a name="in-this-section"></a>本节内容

  - [Lync Server 2013 中的网络会议要求](lync-server-2013-web-conferencing-requirements.md)

  - [Lync Server 2013 中的 A/V 会议要求](lync-server-2013-a-v-conferencing-requirements.md)

  - [Lync Server 2013 中的电话拨入式会议要求](lync-server-2013-dial-in-conferencing-requirements.md)

</div>

<div>

## <a name="see-also"></a>另请参阅


[在 Lync Server 2013 中规划会议](lync-server-2013-planning-for-conferencing.md)  
[Lync Server 2013 中会议的部署清单](lync-server-2013-deployment-checklist-for-conferencing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


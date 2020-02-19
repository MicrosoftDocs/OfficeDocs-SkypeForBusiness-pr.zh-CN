---
title: Lync Server 2013：定义会议要求
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Defining your requirements for conferencing
ms:assetid: 5c83e268-22bf-42b2-bac3-3237b5e02e03
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204935(v=OCS.15)
ms:contentKeyID: 48184255
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ee3b7631a3c05fb497ee7fcdf37b6db984361845
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42137813"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="defining-your-requirements-for-conferencing-in-lync-server-2013"></a>在 Lync Server 2013 中定义会议要求

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-09-30_

在确定要部署的会议功能时，需要考虑您希望向用户提供的功能和网络带宽功能。以下问题列表将指导您完成会议规划过程，以便根据您的组织的要求确定应部署哪些会议功能。

  - **是否要启用包括文档协作和应用程序共享的 Web 会议？**
    
    如果是这样，则必须在 Microsoft Lync Server 2013、规划工具或拓扑生成器中为前端池启用会议。 启用会议时会同时启用 Web 会议和 A/V 会议。
    
    与文档协作相比，应用程序共享要求使用更多的网络带宽。 Lync Server 2013 提供了用于控制每个应用程序共享会话的限制机制。 默认情况下，每个会话设置为 1.5 KB/秒。
    
    如果您不希望启用应用程序共享，但希望启用文档协作，则可以启用会议并使用会议策略来禁用应用程序共享。 有关配置会议策略的详细信息，请参阅[Lync Server 2013 中的会议策略](lync-server-2013-conferencing-policies.md)。
    
    若要使用户能够共享 PowerPoint 演示文稿，您需要配置 Office Web Apps Server。 有关配置 Office Web Apps Server 的详细信息，请参阅[配置与 Office Web Apps server 和 Lync Server 2013 的集成](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md)。

  - **是否要启用 A/V 会议？**
    
    如果是这样，则必须在 Lync Server 2013、规划工具或拓扑生成器中为前端池启用会议。 启用会议时会同时启用 Web 会议和 A/V 会议。
    
    与 Web 会议（包括文档协作和应用程序共享）相比，A/V 会议要求并使用更多的网络带宽。如果您不希望启用 A/V 会议，但希望启用 Web 会议，则可以启用会议并使用会议策略来禁用 A/V 会议。
    
    如果希望启用音频会议但不启用视频会议，则可以启用 A/V 会议并使用会议策略来阻止视频会议。或者，可以启用 A/V 会议并且只允许某些用户来启动或参加 A/V 会议。
    
    <div>
    

    > [!NOTE]  
    > 您无需使用企业语音即可使用 A/V 会议。 如果您启用 A/V 会议，并且您的用户有音频设备，则他们可以将音频添加到其会议，即使您使用 PBX 作为电话解决方案也是如此。

    
    </div>

  - **使用 PSTN 电话时，是否要允许用户加入会议的音频部分？**
    
    如果是，则部署并启用电话拨入式会议。然后，组织内部和外部的受邀用户可以使用 PSTN 电话加入会议的音频部分。

  - **是否要使用 Lync Server 2013 客户端启用外部用户以加入已启用的会议类型？**
    
    如果是，则应部署边缘服务器。 通过允许外部参与会议，你可以最大限度地提高 Lync Server 2013 的投资。 例如，具有 Lync Server 2013 的便携式计算机的用户可以在在家、在机场或在客户网站中的任何地方加入会议。
    
    此外，通过部署边缘服务器，可以与其他组织（如您的客户或供应商）建立联盟关系，这样，来自这些组织的用户便可以更轻松地与您的用户协作。
    
    有关部署边缘服务器的详细信息，请参阅在 lync server [2013 中规划外部用户访问](lync-server-2013-planning-for-external-user-access.md)和[在 lync Server 2013 中部署外部用户访问](lync-server-2013-deploying-external-user-access.md)。 有关启用 Office Web Apps Server 外部访问的详细信息，请参阅[使用反向代理服务器在 Lync Server 2013 中发布 Office Web Apps server](lync-server-2013-publishing-office-web-apps-server-using-a-reverse-proxy-server.md)。

  - **是否要控制可加入 Lync Server 2013 会议的客户端？**
    
    如果是，则应配置与会页面，以便只有要支持的客户端选项可用。 用户每次单击链接加入计划的会议时，Lync Server 2013 将检测是否已在计算机上安装了客户端。 然后，启动默认客户端，并打开包含备用客户端的链接的与会页面。 与会页面始终包含使用 Microsoft Lync Web App 的选项。 除了此选项之外，您还可以决定是否包括与会者的链接和以前版本的 Communicator。 有关详细信息，请参阅[在 Lync Server 2013 中配置会议加入页面](lync-server-2013-configuring-the-meeting-join-page.md)。

<div>

## <a name="in-this-section"></a>本部分内容

  - [Lync Server 2013 中的 Web 会议要求](lync-server-2013-web-conferencing-requirements.md)

  - [Lync Server 2013 中的 A/V 会议要求](lync-server-2013-a-v-conferencing-requirements.md)

  - [Lync Server 2013 中的电话拨入式会议要求](lync-server-2013-dial-in-conferencing-requirements.md)

</div>

<div>

## <a name="see-also"></a>另请参阅


[在 Lync Server 2013 中规划会议](lync-server-2013-planning-for-conferencing.md)  
[Lync Server 2013 中的会议的部署清单](lync-server-2013-deployment-checklist-for-conferencing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


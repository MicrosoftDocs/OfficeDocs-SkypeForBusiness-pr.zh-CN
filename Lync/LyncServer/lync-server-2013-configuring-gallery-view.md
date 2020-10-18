---
title: Lync Server 2013：配置库视图
description: Lync Server 2013：配置库视图。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Gallery View
ms:assetid: 4a609178-47d8-4682-ac8d-29f882801924
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204871(v=OCS.15)
ms:contentKeyID: 48184069
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2aec2f1e3c7bff9a3736f40584a29880978b9daa
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48575918"
---
# <a name="configuring-gallery-view-in-lync-server-2013"></a>在 Lync Server 2013 中配置库视图

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-10-30_

在 Lync Server 2013 中，配置库在会议策略中查看视频会议。 默认情况下，库视图处于打开状态。 如果您不希望允许使用库视图，或希望仅允许部分用户使用，则需要使用会议策略关闭此功能。

当会议参与者的视频不可用时，如果部署高分辨率照片（Lync Server 2013 中的一项新功能），则用户的库视图体验会得到增强。 高分辨率照片为存储在 Active Directory 域服务中的较小、有限的分辨率联系人照片提供了另一种替代方案。 高分辨率照片存储在用户的 Exchange 2013 邮箱中，因此，需要将 Lync Server 2013 与 Exchange 2013 集成。 有关详细信息，请参阅 NextHop 博客文章 "集成 Exchange 2013 和 Lync Server 2013" [https://go.microsoft.com/fwlink/p/?LinkId=260987](https://go.microsoft.com/fwlink/p/?linkid=260987) 。

<div>


> [!NOTE]  
> 每个博客的内容及其 URL 如有更改，恕不另行通知。



</div>

您可以通过使用 Lync Server 2013 控制面板或使用以下 cmdlet 之一来查看或修改库视图参数：

  - **Set-csconferencingpolicy**

  - **Set-csconferencingpolicy**

  - **新 Set-csconferencingpolicy**

使用下列会议策略设置配置库视图：

  - **AllowMultiview**    此参数控制是否允许用户组织库观看视频会议。 此参数适用于用户创建的已安排的会议和临时会议。
    
    示例：
    
      - 对于在 Lync Server 2013 池上托管的用户 A，此参数设置为 True。 用户 A 组织的会议允许用户加入和接收多个视频流。
    
      - 如果用户 B 驻留在 Lync Server 2013 池上，则此参数设置为 False。 用户 B 组织的会议具有一个视频流，这与 Lync Server 2010 提供的视频会议体验类似。
    
    此参数确定可组织允许多个视频流的会议的用户。允许多个视频流的会议中的参与者可能会也可能不会被允许接收多个视频流，这取决于他们各自的权限（请参阅 EnableMultiviewJoin 参数的描述）。

  - **EnableMultiviewJoin**    此参数控制会议中的参与者是否在允许会议的会议中接收库观看视频体验。 此参数控制用户参与的所有会议中的用户体验。
    
    示例：
    
      - 对于用户 C，此参数设置为 True。用户 C 在参与组织或由用户 A 启动的会议时，可以收到多个视频流。用户 C 接收与 Lync Server 2010 提供的视频会议体验类似的单一视频流，当用户参与组织或由用户 B 启动的会议时。
    
      - 对于用户 D，此参数设置为 False。用户 D 接收单个视频流，与 Lync Server 2010 在参与按用户 A 或用户 B 组织的任何会议时所提供的视频会议体验类似。

下面的过程是使用 Lync Server 命令行管理程序启用库观看视频会议的示例。

<div>

## <a name="to-modify-conferencing-policy-for-gallery-view-video-conferencing"></a>修改库视图视频会议的会议策略

1.  启动 Lync Server 命令行管理程序：依次单击“开始”****、“所有程序”****、“Microsoft Lync Server 2013”**** 和“Lync Server 命令行管理程序”****。

2.  在命令行处，运行以下 cmdlet 以编辑会议策略：
    
        Set-CsConferencingPolicy -Identity Pool01ConferencingPolicy -AllowMultiview $true -EnableMultiviewJoin $true 

</div>

</div>

<span> </span>

</div>

</div>

</div>


---
title: 'Lync Server 2013: 配置库视图'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring Gallery View
ms:assetid: 4a609178-47d8-4682-ac8d-29f882801924
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204871(v=OCS.15)
ms:contentKeyID: 48184069
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7333c1928bd92dbe6145f238d828e81bbeb3d868
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34837245"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-gallery-view-in-lync-server-2013"></a>在 Lync Server 2013 中配置库视图

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2012-10-30_

在 Lync Server 2013 中, 你可以在会议策略中配置库查看视频会议。 默认情况下, 库视图处于打开状态。 如果你不想允许库视图, 或者希望仅对某些用户允许它, 你需要关闭会议策略中的功能。

当会议参与者的视频不可用时, 如果在 Lync Server 2013 中部署高分辨率的照片, 则用户的库视图体验将会增强。 高分辨率照片为存储在 Active Directory 域服务中的较小的、有限的分辨率联系人照片提供备用方案。 高分辨率的照片存储在用户的 Exchange 2013 邮箱中, 因此需要您将 Lync Server 2013 与 Exchange 2013 集成。 有关详细信息, 请参阅 NextHop 博客文章 "集成 Exchange 2013 和 Lync Server 2013" [http://go.microsoft.com/fwlink/p/?LinkId=260987](http://go.microsoft.com/fwlink/p/?linkid=260987)。

<div>


> [!NOTE]  
> 每个博客的内容及其 URL 如有更改，恕不另行通知。



</div>

你可以使用 Lync Server 2013 控制面板或使用以下 cmdlet 之一查看或修改库视图参数:

  - **Get-CsConferencingPolicy**

  - **Set-CsConferencingPolicy**

  - **New-CsConferencingPolicy**

通过下列会议策略设置配置库视图:

  - **AllowMultiview**   此参数控制是否允许用户组织库观看视频会议。 此参数适用于用户创建的计划和临时会议。
    
    说明
    
      - 对于用户 A, 此参数设置为 True, 其托管在 Lync Server 2013 池中。 通过用户 A 组织的会议允许用户加入和接收多个视频流。
    
      - 对于在 Lync Server 2013 池中托管的用户 B, 此参数设置为 "False"。 按用户 B 组织的会议的单个视频流与 Lync Server 2010 提供的视频会议体验类似。
    
    此参数确定哪些人可以组织允许多个视频流的会议。 允许多个视频流的参与者可能或不允许多个视频流接收多个视频流, 具体取决于其各个权限 (请参阅 EnableMultiviewJoin 参数的说明)。

  - **EnableMultiviewJoin**   此参数控制会议中的参与者是否在允许会议的会议中接收库查看视频体验。 此参数控制用户在其参与的任何会议中的体验。
    
    说明
    
      - 对于用户 C, 此参数设置为 True。当参与由用户 A 组织或启动的会议时, 用户 C 可以接收多个视频流。用户 C 接收与 Lync Server 2010 提供的视频会议体验类似的单个视频流参与由用户 B 组织或启动的会议。
    
      - 对于用户 D, 此参数设置为 False。用户 D 接收单个视频流, 该视频流与 Lync Server 2010 在参与由用户 A 或用户 B 组织的任何会议时所提供的视频会议体验类似。

以下过程是使用 Lync Server 命令行管理程序启用库观看视频会议的示例。

<div>

## <a name="to-modify-conferencing-policy-for-gallery-view-video-conferencing"></a>修改库的会议策略查看视频会议

1.  启动 Lync Server 命令行管理程序: 依次单击 "**开始**"、"**所有程序**"、" **Microsoft Lync server 2013**", 然后单击 " **Lync server Management shell**"。

2.  在命令行中, 运行以下 cmdlet 以编辑会议策略:
    
        Set-CsConferencingPolicy -Identity Pool01ConferencingPolicy -AllowMultiview $true -EnableMultiviewJoin $true 

</div>

</div>

<span> </span>

</div>

</div>

</div>


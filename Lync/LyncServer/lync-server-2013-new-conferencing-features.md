---
title: Lync Server 2013：新的会议功能
TOCTitle: 新的会议功能
ms:assetid: feeb81e8-1424-408c-a440-886aa0fb133c
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg413085(v=OCS.15)
ms:contentKeyID: 49314861
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 中新的会议功能

 

_**上一次修改主题：** 2012-11-08_

Lync Server 2013 引入了多个可增强会议功能的新功能，如下面列表所述。

  - **加入启动器**
    
    Lync Server 2013 可更新加入启动器以在启动客户端前验证每次会议，并对下列客户端中打开会议提供支持：
    
      - Windows Phone 7
    
      - Android 设备
    
      - Apple iOS 设备
    
      - Windows 8
    
      - Internet Explorer 10

  - **已更新的 PowerPoint 共享**
    
    Lync Server 2013 现在使用 Office Web Apps 和 Office Web Apps Server（以前称为 WAC Server）处理 PowerPoint 演示文稿。使用 Office Web Apps Server 可允许更高的分辨率显示和更好地支持 PowerPoint 功能，访问更多类型的移动设备（ Lync Server 2013 使用标准 DHTML 和 JavaScript 广播 PowerPoint 演示文稿），并使具有相应权限的用户能够浏览独立于演示本身的 PowerPoint 演示文稿。

  - **图库视图和 HD 视频会议**
    
    在视频会议中，用户可以同时看到多达 5 个会议参与者的视频。
    
    > [!NOTE]  
    > 图库视图经历过有高达 75 个参与者的会议。当会议增加到超过 75 个参与者时，会经历回复到单个视图。
    


  - **HD 视频**
    
    用户在双方呼叫和多方会议中可遇到分辨率高达 HD 1080P 的情况。

  - **演示者仅视频模式**
    
    演示者可配置会议，以便仅显示演示者的视频。当多个视频流可用并锁定到不同源时此模式在大型会议中可起到防止干扰的作用。此模式还应用于由会议设备捕获和提供的视频。

  - **视频聚焦**
    
    演示者可配置会议，以便会议中的每个人仅能看到来自其为视频源的选定参与者的视频。此模式还应用于由会议设备为全景视频捕获和提供的视频。

  - **用于非企业语音用户的拨出式会议**
    
    Lync Server 2013 现在允许未启用企业语音的参与者从会议启动拨出呼叫。此功能由管理员配置。

  - **存档**
    
    如果 Exchange Server 集成启用了存档功能，则可将会议期间共享的任何文档存档到 Exchange 2013 数据存储中。这包括 PowerPoint 演示文稿、附件、白板和投票。

  - **会议邀请自定义**
    
    管理员可以使用 Lync Server 控制面板或 Lync Server 命令行管理程序为在线会议自定义电子邮件邀请。自定义项可包括用于徽标的 URL、帮助文本、合法文本和脚本文本。所有后续邀请都将包括自定义项。

## 另请参阅

#### 其他资源

[在 Lync Server 2013 中规划会议](lync-server-2013-planning-for-conferencing.md)


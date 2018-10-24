---
title: 配置图库视图
TOCTitle: 配置图库视图
ms:assetid: 4a609178-47d8-4682-ac8d-29f882801924
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ204871(v=OCS.15)
ms:contentKeyID: 49312757
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 配置图库视图

 

_**上一次修改主题：** 2016-12-08_

在 Lync Server 2013 中，按会议策略配置库视图视频会议。默认情况下，库视图处于打开状态。如果您不希望允许使用库视图，或希望仅允许部分用户使用，则需要使用会议策略关闭此功能。

当会议参与者的视频不可用时，如果您部署了高分辨率照片（Lync Server 2013 中的新功能），则可增强用户的库视图体验。高分辨率照片提供了对存储在 Active Directory 域服务 中的较小、分辨率有限的联系人照片的替换。高分辨率照片存储在用户的 Exchange 2013 邮箱中，因此需要您将 Lync Server 2013 与 Exchange 2013 集成。有关详细信息，请参阅 NextHop 博客文章“集成 Exchange 2013 和 Lync Server 2013”，网址为 [http://go.microsoft.com/fwlink/?linkid=260987\&clcid=0x804](http://go.microsoft.com/fwlink/?linkid=260987%26clcid=0x804)。

> [!NOTE]  
> 每个博客的内容及其 URL 如有更改，恕不另行通知。



您可使用 Lync Server 2013 控制面板或下列 cmdlet 之一查看或修改库视图参数：

  - **Get-CsConferencingPolicy**

  - **Set-CsConferencingPolicy**

  - **New-CsConferencingPolicy**

使用下列会议策略设置配置库视图：

  - **AllowMultiview**   此参数控制是否允许用户组织库视图视频会议。此参数适用于用户创建的已安排的会议和临时会议。
    
    示例：
    
      - 用户 A 的此参数设置为 True，该用户位于 Lync Server 2013 池。用户 A 组织的会议允许用户加入和接收多个视频流。
    
      - 用户 B 的此参数设置为 False，该用户位于 Lync Server 2013 池。用户 B 组织的会议具有一个与 Lync Server 2010 提供的视频会议体验类似的视频流。
    
    此参数确定可组织允许多个视频流的会议的用户。允许多个视频流的会议中的参与者可能会也可能不会被允许接收多个视频流，这取决于他们各自的权限（请参阅 EnableMultiviewJoin 参数的描述）。

  - **EnableMultiviewJoin**   此参数控制会议的参与者在允许库视图视频体验的会议中是否接此体验。此参数控制用户参与的所有会议中的用户体验。
    
    示例：
    
      - 用户 C 的此参数设置为 True。用户 C 在参与用户 A 组织或发起的会议时可接收多个视频流。用户 C 在参与用户 B 组织或发起的会议时接收一个与 Lync Server 2010 提供的视频会议体验类似的视频流。
    
      - 用户 D 的此参数设置为 False。用户 D 在参与用户 A 或用户 B 组织的任何会议时接收一个与 Lync Server 2010 提供的视频会议体验类似的视频流。

以下过程是使用 Lync Server 命令行管理程序 启用库视图视频会议的示例。

## 修改库视图视频会议的会议策略

1.  启动 Lync Server 命令行管理程序：依次单击“开始”、“所有程序”和“Microsoft Lync Server 2013”，然后单击“Lync Server 命令行管理程序”。

2.  在命令行处，运行以下 cmdlet 以编辑会议策略：
    
        Set-CsConferencingPolicy -Identity Pool01ConferencingPolicy -AllowMultiview $true -EnableMultiviewJoin $true


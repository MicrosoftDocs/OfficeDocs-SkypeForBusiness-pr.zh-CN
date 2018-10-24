---
title: 将会议设备移至新注册器池
TOCTitle: 将会议设备移至新注册器池
ms:assetid: 26e02ca3-e881-4f90-8bf0-b13649108100
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ994025(v=OCS.15)
ms:contentKeyID: 52060980
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 将会议设备移至新注册器池

 

_**上一次修改主题：** 2013-02-20_

使用 **Move-CsMeetingRoom** cmdlet 将会议设备从一个注册器池移至另一个注册器池。此 cmdlet 既可从 Lync Server 2013 命令行管理程序中运行，也可从 Windows PowerShell 的远程会话中运行。

> [!NOTE]  
> 有关使用远程 Windows PowerShell 连接到 Lync Server 的详细信息，请参阅 Lync Server Windows PowerShell 博客文章“快速入门：使用远程 PowerShell 管理 Microsoft Lync Server 2010”，网址为 <a href="http://go.microsoft.com/fwlink/p/?linkid=255876">http://go.microsoft.com/fwlink/p/?linkId=255876</a>。




## 将会议设备移至新注册器池

  - 若要移动会议设备，您必须指定要移动的会议室的标识，然后将 Target 参数设置为该设备将移到的注册器池的完全限定域名 (FQDN)。例如：
    
        Move-CsMeetingRoom -Target "atl-cs-001.litwareinc.com" -Identity "Room 14"

有关详细信息，请参阅 [Move-CsMeetingRoom](https://docs.microsoft.com/en-us/powershell/module/skype/Move-CsMeetingRoom) cmdlet 的帮助主题。


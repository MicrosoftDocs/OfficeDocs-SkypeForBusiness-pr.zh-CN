---
title: 创建或修改会议设备联系对象
TOCTitle: 创建或修改会议设备联系对象
ms:assetid: 62ed64be-379c-417d-9453-511881cf5604
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ994035(v=OCS.15)
ms:contentKeyID: 52061032
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 创建或修改会议设备联系对象

 

_**上一次修改主题：** 2013-10-02_

若要创建会议室对象，请首先创建 Active Directory 用户帐户来表示设备。然后，使用 **Enable-CsMeetingRoom** cmdlet 来使该帐户能够作为会议设备运行。如果您需要更改现有会议设备的属性，请使用 **Set-CsMeetingRoom** cmdlet。

可以从 Lync Server 2013 命令行管理程序或从 Windows PowerShell 的远程会话中运行这些 cmdlet。

> [!NOTE]  
> 有关使用远程 Windows PowerShell 连接到 Lync Server 的详细信息，请参阅 Lync Server Windows PowerShell 博客文章“快速入门：使用远程 PowerShell 管理 Microsoft Lync Server 2010”，网址为 <a href="http://go.microsoft.com/fwlink/p/?linkid=255876">http://go.microsoft.com/fwlink/p/?linkId=255876</a>。




## 创建会议设备

  - 在您创建了表示新会议设备的 Active Directory 用户帐户之后，使用 **Enable-CsMeetingRoom** cmdlet 启用它。确保包括 a) 会议设备标识、b) 会议室帐户将驻留在的注册器池和 c) 要分配给该帐户的 SIP 地址。例如：
    
        Enable-CsMeetingRoom -Identity "Redmond Conferencing device" -RegistrarPool "atl-cs-001.litwareinc.com" -SipAddress "sip:RedmondMeetingRoom@litwareinc.com"

## 修改会议设备

  - 若要修改现有会议设备的属性值，请使用 **Set-CsMeetingRoom** cmdlet。例如，以下命令更新与会议设备关联的电话号码 (LineUri)：
    
        Set-CsMeetingRoom -Identity "Redmond Conferencing device" -LineUri "tel:+12065551219"

有关详细信息，请参阅 [Set-CsMeetingRoom](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsMeetingRoom) cmdlet 和 [Enable-CsMeetingRoom](https://docs.microsoft.com/en-us/powershell/module/skype/Enable-CsMeetingRoom) cmdlet 的帮助主题。


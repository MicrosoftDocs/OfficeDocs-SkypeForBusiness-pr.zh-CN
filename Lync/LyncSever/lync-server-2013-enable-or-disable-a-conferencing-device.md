---
title: 启用或禁用会议设备
TOCTitle: 启用或禁用会议设备
ms:assetid: d5140e38-d015-4706-9bde-cf2fa748c36b
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ994070(v=OCS.15)
ms:contentKeyID: 52061137
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 启用或禁用会议设备

 

_**上一次修改主题：** 2013-02-20_

使用 **Enable-CsMeetingRoom** cmdlet 和 **Disable-CsMeetingRoom** cmdlet 可启用和禁用会议设备。可从 Lync Server 2013 命令行管理程序或从 Windows PowerShell 的远程会话中运行这些 cmdlet。

> [!NOTE]  
> 有关使用远程 Windows PowerShell 连接到 Lync Server 的详细信息，请参阅 Lync Server Windows PowerShell 博客文章“快速入门：使用远程 PowerShell 管理 Microsoft Lync Server 2010”，网址为 <a href="http://go.microsoft.com/fwlink/p/?linkid=255876">http://go.microsoft.com/fwlink/p/?linkId=255876</a>。




## 启用会议设备

  - 要启用会议设备，请使用 **Enable-CsMeetingRoom** cmdlet。在启用会议设备时，您必须包括 a) 会议设备标识，b) 将承载会议室帐户的注册器池，以及 c) 要分配给该帐户的 SIP 地址。
    
        Enable-CsMeetingRoom -Identity "Redmond Conferencing device" -RegistrarPool "atl-cs-001.litwareinc.com" -SipAddress "sip:RedmondMeetingRoom@litwareinc.com"

## 禁用会议设备

  - 要禁用会议设备，请使用 **Disable-CsMeetingRoom** cmdlet。请确保指定要禁用的会议设备的标识：
    
        Disable-CsMeetingRoom -Identity "sip:RedmondMeetingRoom@litwareinc.com"

有关详细信息，请参阅 [Enable-CsMeetingRoom](https://docs.microsoft.com/en-us/powershell/module/skype/Enable-CsMeetingRoom) cmdlet 和 [Disable-CsMeetingRoom](https://docs.microsoft.com/en-us/powershell/module/skype/Disable-CsMeetingRoom) cmdlet 的帮助主题。


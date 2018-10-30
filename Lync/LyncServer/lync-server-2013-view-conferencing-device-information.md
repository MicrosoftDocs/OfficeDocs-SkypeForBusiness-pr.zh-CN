---
title: 查看会议设备信息
TOCTitle: 查看会议设备信息
ms:assetid: 838bdbf8-8b68-4eb6-8fa3-45bfd5b0b1cd
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ994043(v=OCS.15)
ms:contentKeyID: 52061062
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 查看会议设备信息

 

_**上一次修改主题：** 2013-02-20_

您可以使用 Windows PowerShell 和 **Get-CsMeetingRoom** cmdlet 查看有关配置用于供贵组织使用的会议设备的信息。从 Lync Server 2013 命令行管理程序或从 Windows PowerShell 的远程会话运行 **Get-CsMeetingRoom** cmdlet。

> [!NOTE]  
> 有关使用远程 Windows PowerShell 连接到 Lync Server 的详细信息，请参阅 Lync Server Windows PowerShell 博客文章“快速入门：使用远程 PowerShell 管理 Microsoft Lync Server 2010”，网址为 <a href="http://go.microsoft.com/fwlink/p/?linkid=255876">http://go.microsoft.com/fwlink/p/?linkId=255876</a>。


如果使用不带任何参数的 **Get-CsMeetingRoom** cmdlet，则它返回有关所有会议设备的信息。可选参数提供筛选信息的不同方式。有关详细信息，请参阅 [Get-CsMeetingRoom](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsMeetingRoom) 的“参数”部分。


## 查看有关所有会议设备的信息

  - 若要查看有关您的所有会议设备的详细信息，请在 Lync Server 命令行管理程序中键入以下命令，然后按 Enter：
    
        Get-CsMeetingRoom
    
    此 cmdlet 为每个会议设备返回类似如下的信息。请注意，此示例只显示您在运行此 cmdlet 后将看到的部分信息：
    
        ContactOptionFlags                : 64
        OwnerUrn                          : urn:device:roomsystem
        OriginatorSid                     :
        SamAccountName                    : room12129
        UserPrincipalName                 : room1219@litwareinc.com
        FirstName                         : 
        LastName                          :
        WindowsEmailAddress               :
        Sid                               : S-1-5-21-2831376166-2963252556-2165051629-1257
        LineServerURI                     :
        AudioVideoDisabled                : False
        IPPBXSoftPhoneRoutingEnabled      : False
        RemoteCallControlTelephonyEnabled : False
        PrivateLine                       :
        AcpInfo                           : {}
        HostedVoiceMail                   :
        DisplayName                       : Room 1219

## 查看有关特定会议设备的信息

  - 若要查看特定会议设备的信息，请包括 Identity 参数后跟会议设备标识（通常为 Active Directory 显示名称）。例如：
    
        Get-CsMeetingRoom -Identity "Room 1219"

有关详细信息，请参阅 [Get-CsMeetingRoom](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsMeetingRoom) cmdlet 的帮助主题。


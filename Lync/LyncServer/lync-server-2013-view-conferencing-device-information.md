---
title: 'Lync Server 2013: 查看会议设备信息'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: View conferencing device information
ms:assetid: 838bdbf8-8b68-4eb6-8fa3-45bfd5b0b1cd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994043(v=OCS.15)
ms:contentKeyID: 51803954
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b4b40e0ee28f13aa6be52009b750258c5cdadffe
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34845357"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="view-conferencing-device-information-in-lync-server-2013"></a>在 Lync Server 2013 中查看会议设备信息

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2013-02-20_

你可以使用 Windows PowerShell 和**CsMeetingRoom** cmdlet 查看配置为在你的组织中使用的会议设备的相关信息。 从 Lync Server 2013 命令行管理程序或 Windows PowerShell 的远程会话运行**CsMeetingRoom** cmdlet。

<div>


> [!NOTE]  
> 有关使用远程 Windows PowerShell 连接到 Lync Server 的详细信息, 请参阅 Lync Server Windows PowerShell 博客文章 "快速入门: 使用远程 PowerShell 管理 Microsoft Lync Server 2010" <A href="http://go.microsoft.com/fwlink/p/?linkid=255876">http://go.microsoft.com/fwlink/p/?linkId=255876</A>。



</div>

如果您使用不带任何参数的**CsMeetingRoom** cmdlet, 它将返回有关所有会议设备的信息。 可选参数提供不同的筛选信息的方式。 有关详细信息, 请参阅[CsMeetingRoom](https://docs.microsoft.com/powershell/module/skype/Get-CsMeetingRoom)的 "参数" 部分。

<div>


<div>

## <a name="viewing-information-about-all-your-conferencing-devices"></a>查看有关所有会议设备的信息

  - 若要查看有关所有会议设备的详细信息, 请在 Lync Server 命令行管理程序中键入以下命令, 然后按 Enter:
    
        Get-CsMeetingRoom
    
    此 cmdlet 将为每个会议设备返回类似于以下内容的信息。 请注意, 此示例仅显示运行此 cmdlet 时你将看到的一些信息:
    
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

</div>

<div>

## <a name="viewing-information-about-a-specific-conferencing-device"></a>查看有关特定会议设备的信息

  - 若要查看特定会议设备的信息, 请在标识参数后添加会议设备标识 (通常是 Active Directory 显示名称)。 例如：
    
        Get-CsMeetingRoom -Identity "Room 1219"

</div>

有关详细信息, 请参阅[CsMeetingRoom](https://docs.microsoft.com/powershell/module/skype/Get-CsMeetingRoom) Cmdlet 的帮助主题。

</div>

</div>

<span> </span>

</div>

</div>

</div>


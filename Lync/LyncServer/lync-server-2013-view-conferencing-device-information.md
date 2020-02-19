---
title: Lync Server 2013：查看会议设备信息
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: View conferencing device information
ms:assetid: 838bdbf8-8b68-4eb6-8fa3-45bfd5b0b1cd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994043(v=OCS.15)
ms:contentKeyID: 51803954
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4fd7b840e03410069c59c30e46ec22902f96ce3a
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42136800"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="view-conferencing-device-information-in-lync-server-2013"></a>在 Lync Server 2013 中查看会议设备信息

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2013-02-20_

您可以使用 Windows PowerShell 和**disable-csmeetingroom** cmdlet 查看有关配置为在组织中使用的会议设备的信息。 从 Lync Server 2013 命令行管理程序或从 Windows PowerShell 的远程会话运行**disable-csmeetingroom** cmdlet。

<div>


> [!NOTE]  
> 有关使用远程 Windows PowerShell 连接到 Lync Server 的详细信息，请参阅在上<A href="https://go.microsoft.com/fwlink/p/?linkid=255876">https://go.microsoft.com/fwlink/p/?linkId=255876</A>的 Lync Server Windows powershell 博客文章 "快速入门：使用远程 PowerShell 管理 Microsoft Lync Server 2010"。



</div>

如果使用不带任何参数的**disable-csmeetingroom** cmdlet，则它将返回有关所有会议设备的信息。 可选参数提供了不同的筛选信息的方法。 有关详细信息，请参阅[disable-csmeetingroom](https://docs.microsoft.com/powershell/module/skype/Get-CsMeetingRoom)的 "参数" 部分。

<div>


<div>

## <a name="viewing-information-about-all-your-conferencing-devices"></a>查看有关所有会议设备的信息

  - 若要查看有关所有会议设备的详细信息，请在 Lync Server 命令行管理程序中键入以下命令，然后按 Enter：
    
        Get-CsMeetingRoom
    
    此 cmdlet 为每个会议设备返回类似于以下内容的信息。 请注意，此示例仅显示运行此 cmdlet 时将看到的一些信息：
    
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

  - 若要查看特定会议设备的信息，请在 Identity 参数后面加上会议设备标识（通常是 Active Directory 显示名称）。 例如：
    
        Get-CsMeetingRoom -Identity "Room 1219"

</div>

有关详细信息，请参阅[disable-csmeetingroom](https://docs.microsoft.com/powershell/module/skype/Get-CsMeetingRoom) Cmdlet 的帮助主题。

</div>

</div>

<span> </span>

</div>

</div>

</div>


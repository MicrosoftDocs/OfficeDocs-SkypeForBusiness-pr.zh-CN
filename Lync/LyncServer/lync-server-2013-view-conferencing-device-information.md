---
title: Lync Server 2013：查看会议设备信息
description: Lync Server 2013：查看会议设备信息。
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
ms.openlocfilehash: 9bbbdcecbc15ef59b2b9e22ffd2b28ff745d67a2
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48574768"
---
# <a name="view-conferencing-device-information-in-lync-server-2013"></a><span data-ttu-id="bfa03-103">在 Lync Server 2013 中查看会议设备信息</span><span class="sxs-lookup"><span data-stu-id="bfa03-103">View conferencing device information in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bfa03-104">_**上次修改的主题：** 2013-02-20_</span><span class="sxs-lookup"><span data-stu-id="bfa03-104">_**Topic Last Modified:** 2013-02-20_</span></span>

<span data-ttu-id="bfa03-105">您可以使用 Windows PowerShell 和 **disable-csmeetingroom** cmdlet 查看有关配置为在组织中使用的会议设备的信息。</span><span class="sxs-lookup"><span data-stu-id="bfa03-105">You can view information about the conferencing devices configured for use in your organization by using Windows PowerShell and the **Get-CsMeetingRoom** cmdlet.</span></span> <span data-ttu-id="bfa03-106">从 Lync Server 2013 命令行管理程序或从 Windows PowerShell 的远程会话运行 **disable-csmeetingroom** cmdlet。</span><span class="sxs-lookup"><span data-stu-id="bfa03-106">Run the **Get-CsMeetingRoom** cmdlet from either the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="bfa03-107">有关使用远程 Windows PowerShell 连接到 Lync Server 的详细信息，请参阅在上的 Lync Server Windows PowerShell 博客文章 "快速入门：使用远程 PowerShell 管理 Microsoft Lync Server 2010" <A href="https://go.microsoft.com/fwlink/p/?linkid=255876">https://go.microsoft.com/fwlink/p/?linkId=255876</A> 。</span><span class="sxs-lookup"><span data-stu-id="bfa03-107">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at <A href="https://go.microsoft.com/fwlink/p/?linkid=255876">https://go.microsoft.com/fwlink/p/?linkId=255876</A>.</span></span>



</div>

<span data-ttu-id="bfa03-108">如果使用不带任何参数的 **disable-csmeetingroom** cmdlet，则它将返回有关所有会议设备的信息。</span><span class="sxs-lookup"><span data-stu-id="bfa03-108">If you use the **Get-CsMeetingRoom** cmdlet without any parameters, it returns information about all your conferencing devices.</span></span> <span data-ttu-id="bfa03-109">可选参数提供了不同的筛选信息的方法。</span><span class="sxs-lookup"><span data-stu-id="bfa03-109">Optional parameters provide different ways for you to filter information.</span></span> <span data-ttu-id="bfa03-110">有关详细信息，请参阅 [disable-csmeetingroom](https://docs.microsoft.com/powershell/module/skype/Get-CsMeetingRoom)的 "参数" 部分。</span><span class="sxs-lookup"><span data-stu-id="bfa03-110">For details, see the Parameters section of [Get-CsMeetingRoom](https://docs.microsoft.com/powershell/module/skype/Get-CsMeetingRoom).</span></span>

<div>


<div>

## <a name="viewing-information-about-all-your-conferencing-devices"></a><span data-ttu-id="bfa03-111">查看有关所有会议设备的信息</span><span class="sxs-lookup"><span data-stu-id="bfa03-111">Viewing Information about All Your Conferencing Devices</span></span>

  - <span data-ttu-id="bfa03-112">若要查看有关所有会议设备的详细信息，请在 Lync Server 命令行管理程序中键入以下命令，然后按 Enter：</span><span class="sxs-lookup"><span data-stu-id="bfa03-112">To view details about all your conferencing devices, type the following command in the Lync Server Management Shell, and then press Enter:</span></span>
    
        Get-CsMeetingRoom
    
    <span data-ttu-id="bfa03-113">此 cmdlet 为每个会议设备返回类似于以下内容的信息。</span><span class="sxs-lookup"><span data-stu-id="bfa03-113">This cmdlet returns information similar to the following for each conferencing device.</span></span> <span data-ttu-id="bfa03-114">请注意，此示例仅显示运行此 cmdlet 时将看到的一些信息：</span><span class="sxs-lookup"><span data-stu-id="bfa03-114">Note that this example shows only some of the information that you’ll see when you run this cmdlet:</span></span>
    
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

## <a name="viewing-information-about-a-specific-conferencing-device"></a><span data-ttu-id="bfa03-115">查看有关特定会议设备的信息</span><span class="sxs-lookup"><span data-stu-id="bfa03-115">Viewing Information about a Specific Conferencing Device</span></span>

  - <span data-ttu-id="bfa03-116">若要查看特定会议设备的信息，请在 Identity 参数后面加上会议设备标识 (通常是 Active Directory 显示名称) 。</span><span class="sxs-lookup"><span data-stu-id="bfa03-116">To view information for a specific conferencing device, include the Identity parameter followed by the conferencing device identity (typically, the Active Directory display name).</span></span> <span data-ttu-id="bfa03-117">例如：</span><span class="sxs-lookup"><span data-stu-id="bfa03-117">For example:</span></span>
    
        Get-CsMeetingRoom -Identity "Room 1219"

</div>

<span data-ttu-id="bfa03-118">有关详细信息，请参阅 [disable-csmeetingroom](https://docs.microsoft.com/powershell/module/skype/Get-CsMeetingRoom) Cmdlet 的帮助主题。</span><span class="sxs-lookup"><span data-stu-id="bfa03-118">For details, see the Help topic for the [Get-CsMeetingRoom](https://docs.microsoft.com/powershell/module/skype/Get-CsMeetingRoom) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>


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

# <a name="view-conferencing-device-information-in-lync-server-2013"></a><span data-ttu-id="aa93a-102">在 Lync Server 2013 中查看会议设备信息</span><span class="sxs-lookup"><span data-stu-id="aa93a-102">View conferencing device information in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="aa93a-103">_**主题上次修改时间:** 2013-02-20_</span><span class="sxs-lookup"><span data-stu-id="aa93a-103">_**Topic Last Modified:** 2013-02-20_</span></span>

<span data-ttu-id="aa93a-104">你可以使用 Windows PowerShell 和**CsMeetingRoom** cmdlet 查看配置为在你的组织中使用的会议设备的相关信息。</span><span class="sxs-lookup"><span data-stu-id="aa93a-104">You can view information about the conferencing devices configured for use in your organization by using Windows PowerShell and the **Get-CsMeetingRoom** cmdlet.</span></span> <span data-ttu-id="aa93a-105">从 Lync Server 2013 命令行管理程序或 Windows PowerShell 的远程会话运行**CsMeetingRoom** cmdlet。</span><span class="sxs-lookup"><span data-stu-id="aa93a-105">Run the **Get-CsMeetingRoom** cmdlet from either the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="aa93a-106">有关使用远程 Windows PowerShell 连接到 Lync Server 的详细信息, 请参阅 Lync Server Windows PowerShell 博客文章 "快速入门: 使用远程 PowerShell 管理 Microsoft Lync Server 2010" <A href="http://go.microsoft.com/fwlink/p/?linkid=255876">http://go.microsoft.com/fwlink/p/?linkId=255876</A>。</span><span class="sxs-lookup"><span data-stu-id="aa93a-106">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at <A href="http://go.microsoft.com/fwlink/p/?linkid=255876">http://go.microsoft.com/fwlink/p/?linkId=255876</A>.</span></span>



</div>

<span data-ttu-id="aa93a-107">如果您使用不带任何参数的**CsMeetingRoom** cmdlet, 它将返回有关所有会议设备的信息。</span><span class="sxs-lookup"><span data-stu-id="aa93a-107">If you use the **Get-CsMeetingRoom** cmdlet without any parameters, it returns information about all your conferencing devices.</span></span> <span data-ttu-id="aa93a-108">可选参数提供不同的筛选信息的方式。</span><span class="sxs-lookup"><span data-stu-id="aa93a-108">Optional parameters provide different ways for you to filter information.</span></span> <span data-ttu-id="aa93a-109">有关详细信息, 请参阅[CsMeetingRoom](https://docs.microsoft.com/powershell/module/skype/Get-CsMeetingRoom)的 "参数" 部分。</span><span class="sxs-lookup"><span data-stu-id="aa93a-109">For details, see the Parameters section of [Get-CsMeetingRoom](https://docs.microsoft.com/powershell/module/skype/Get-CsMeetingRoom).</span></span>

<div>


<div>

## <a name="viewing-information-about-all-your-conferencing-devices"></a><span data-ttu-id="aa93a-110">查看有关所有会议设备的信息</span><span class="sxs-lookup"><span data-stu-id="aa93a-110">Viewing Information about All Your Conferencing Devices</span></span>

  - <span data-ttu-id="aa93a-111">若要查看有关所有会议设备的详细信息, 请在 Lync Server 命令行管理程序中键入以下命令, 然后按 Enter:</span><span class="sxs-lookup"><span data-stu-id="aa93a-111">To view details about all your conferencing devices, type the following command in the Lync Server Management Shell, and then press Enter:</span></span>
    
        Get-CsMeetingRoom
    
    <span data-ttu-id="aa93a-112">此 cmdlet 将为每个会议设备返回类似于以下内容的信息。</span><span class="sxs-lookup"><span data-stu-id="aa93a-112">This cmdlet returns information similar to the following for each conferencing device.</span></span> <span data-ttu-id="aa93a-113">请注意, 此示例仅显示运行此 cmdlet 时你将看到的一些信息:</span><span class="sxs-lookup"><span data-stu-id="aa93a-113">Note that this example shows only some of the information that you’ll see when you run this cmdlet:</span></span>
    
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

## <a name="viewing-information-about-a-specific-conferencing-device"></a><span data-ttu-id="aa93a-114">查看有关特定会议设备的信息</span><span class="sxs-lookup"><span data-stu-id="aa93a-114">Viewing Information about a Specific Conferencing Device</span></span>

  - <span data-ttu-id="aa93a-115">若要查看特定会议设备的信息, 请在标识参数后添加会议设备标识 (通常是 Active Directory 显示名称)。</span><span class="sxs-lookup"><span data-stu-id="aa93a-115">To view information for a specific conferencing device, include the Identity parameter followed by the conferencing device identity (typically, the Active Directory display name).</span></span> <span data-ttu-id="aa93a-116">例如：</span><span class="sxs-lookup"><span data-stu-id="aa93a-116">For example:</span></span>
    
        Get-CsMeetingRoom -Identity "Room 1219"

</div>

<span data-ttu-id="aa93a-117">有关详细信息, 请参阅[CsMeetingRoom](https://docs.microsoft.com/powershell/module/skype/Get-CsMeetingRoom) Cmdlet 的帮助主题。</span><span class="sxs-lookup"><span data-stu-id="aa93a-117">For details, see the Help topic for the [Get-CsMeetingRoom](https://docs.microsoft.com/powershell/module/skype/Get-CsMeetingRoom) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>


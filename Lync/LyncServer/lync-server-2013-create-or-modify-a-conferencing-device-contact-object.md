---
title: Lync Server 2013：创建或修改会议设备联系人对象
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a conferencing device Contact object
ms:assetid: 62ed64be-379c-417d-9453-511881cf5604
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994035(v=OCS.15)
ms:contentKeyID: 51803945
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 56d594f0bf6e393545f4a7c29785b5f66b328bdc
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41758096"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-conferencing-device-contact-object-in-lync-server-2013"></a><span data-ttu-id="cf981-102">在 Lync Server 2013 中创建或修改会议设备联系人对象</span><span class="sxs-lookup"><span data-stu-id="cf981-102">Create or modify a conferencing device Contact object in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cf981-103">_**主题上次修改时间：** 2013-10-02_</span><span class="sxs-lookup"><span data-stu-id="cf981-103">_**Topic Last Modified:** 2013-10-02_</span></span>

<span data-ttu-id="cf981-104">若要创建会议会议室对象，请首先创建一个 Active Directory 用户帐户来表示该设备。</span><span class="sxs-lookup"><span data-stu-id="cf981-104">To create a conferencing room object, first create an Active Directory user account to represent the device.</span></span> <span data-ttu-id="cf981-105">然后，使用**CsMeetingRoom** cmdlet 使该帐户能够充当会议设备。</span><span class="sxs-lookup"><span data-stu-id="cf981-105">Then, use the **Enable-CsMeetingRoom** cmdlet to enable that account to function as a conferencing device.</span></span> <span data-ttu-id="cf981-106">如果需要更改现有会议设备的属性，请使用**CsMeetingRoom** cmdlet。</span><span class="sxs-lookup"><span data-stu-id="cf981-106">If you need to change the properties of an existing conferencing device, use the **Set-CsMeetingRoom** cmdlet.</span></span>

<span data-ttu-id="cf981-107">这些 cmdlet 既可以从 Lync Server 2013 管理外壳运行，也可以从 Windows PowerShell 的远程会话运行。</span><span class="sxs-lookup"><span data-stu-id="cf981-107">These cmdlets can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="cf981-108">有关使用远程 Windows PowerShell 连接到 Lync Server 的详细信息，请参阅 Lync Server Windows PowerShell 博客文章 "快速入门：使用远程 PowerShell 管理 Microsoft Lync Server 2010" <A href="http://go.microsoft.com/fwlink/p/?linkid=255876">http://go.microsoft.com/fwlink/p/?linkId=255876</A>。</span><span class="sxs-lookup"><span data-stu-id="cf981-108">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at <A href="http://go.microsoft.com/fwlink/p/?linkid=255876">http://go.microsoft.com/fwlink/p/?linkId=255876</A>.</span></span>



</div>

<div>


<div>

## <a name="creating-a-conferencing-device"></a><span data-ttu-id="cf981-109">创建会议设备</span><span class="sxs-lookup"><span data-stu-id="cf981-109">Creating a Conferencing Device</span></span>

  - <span data-ttu-id="cf981-110">在创建表示新会议设备的 Active Directory 用户帐户后，通过使用**enable-CsMeetingRoom** cmdlet 启用它。</span><span class="sxs-lookup"><span data-stu-id="cf981-110">After you create the Active Directory user account that represents the new conferencing device, enable it by using the **Enable-CsMeetingRoom** cmdlet.</span></span> <span data-ttu-id="cf981-111">请确保包含 a）会议设备标识，b）房间帐户将托管的注册机构池，c）要分配给该帐户的 SIP 地址。</span><span class="sxs-lookup"><span data-stu-id="cf981-111">Be sure to include a) the conferencing device identity, b) the registrar pool where the room account will be homed, and c) the SIP address to be assigned to that account.</span></span> <span data-ttu-id="cf981-112">例如：</span><span class="sxs-lookup"><span data-stu-id="cf981-112">For example:</span></span>
    
        Enable-CsMeetingRoom -Identity "Redmond Conferencing device" -RegistrarPool "atl-cs-001.litwareinc.com" -SipAddress "sip:RedmondMeetingRoom@litwareinc.com"

</div>

<div>

## <a name="modifying-a-conferencing-device"></a><span data-ttu-id="cf981-113">修改会议设备</span><span class="sxs-lookup"><span data-stu-id="cf981-113">Modifying a Conferencing Device</span></span>

  - <span data-ttu-id="cf981-114">若要修改现有会议设备的属性值，请使用**CsMeetingRoom** cmdlet。</span><span class="sxs-lookup"><span data-stu-id="cf981-114">To modify the property values of an existing conferencing device, use the **Set-CsMeetingRoom** cmdlet.</span></span> <span data-ttu-id="cf981-115">例如，以下命令将更新与会议设备相关联的电话号码（LineUri）：</span><span class="sxs-lookup"><span data-stu-id="cf981-115">For example, the following command updates the phone number (LineUri) associated with a conferencing device:</span></span>
    
        Set-CsMeetingRoom -Identity "Redmond Conferencing device" -LineUri "tel:+12065551219"

</div>

<span data-ttu-id="cf981-116">有关详细信息，请参阅[Enable-CsMeetingRoom](https://docs.microsoft.com/powershell/module/skype/Enable-CsMeetingRoom) Cmdlet 和[CsMeetingRoom](https://docs.microsoft.com/powershell/module/skype/Set-CsMeetingRoom) cmdlet 的帮助主题。</span><span class="sxs-lookup"><span data-stu-id="cf981-116">For details, see the Help topics for the [Enable-CsMeetingRoom](https://docs.microsoft.com/powershell/module/skype/Enable-CsMeetingRoom) cmdlet and the [Set-CsMeetingRoom](https://docs.microsoft.com/powershell/module/skype/Set-CsMeetingRoom) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>


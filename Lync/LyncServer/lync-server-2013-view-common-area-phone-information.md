---
title: Lync Server 2013：查看公用区域电话信息
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: View common area phone information
ms:assetid: e652240c-6a3f-4be7-a083-32f24c08e655
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994081(v=OCS.15)
ms:contentKeyID: 51803992
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7e045cb13d0e0d0c085d9d45e23b1510d61c93a3
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/14/2020
ms.locfileid: "42007161"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="view-common-area-phone-information-in-lync-server-2013"></a><span data-ttu-id="2a630-102">在 Lync Server 2013 中查看常见区域电话信息</span><span class="sxs-lookup"><span data-stu-id="2a630-102">View common area phone information in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2a630-103">_**上次修改的主题：** 2013-02-20_</span><span class="sxs-lookup"><span data-stu-id="2a630-103">_**Topic Last Modified:** 2013-02-20_</span></span>

<span data-ttu-id="2a630-104">您可以使用**CsCommonAreaPhone** cmdlet 查看配置为在组织中使用的公共区域电话的相关信息。</span><span class="sxs-lookup"><span data-stu-id="2a630-104">You can view information about the common area phones configured for use in your organization by using the **Get-CsCommonAreaPhone** cmdlet.</span></span> <span data-ttu-id="2a630-105">不使用任何参数的情况下，此 cmdlet 将返回有关所有公用区域电话的信息。</span><span class="sxs-lookup"><span data-stu-id="2a630-105">Used without any parameters, this cmdlet returns information about all your common area phones.</span></span> <span data-ttu-id="2a630-106">可选参数提供了不同的筛选信息的方法。</span><span class="sxs-lookup"><span data-stu-id="2a630-106">Optional parameters provide different ways for you to filter information.</span></span> <span data-ttu-id="2a630-107">例如，您可以返回在指定的组织单位（OU）中有联系人对象的所有公用区域电话，或在指定建筑物中的所有联系人对象。</span><span class="sxs-lookup"><span data-stu-id="2a630-107">For example, you can return all the common area phones that have contact objects in a specified organizational unit (OU) or all the contacts objects located in a specified building.</span></span> <span data-ttu-id="2a630-108">有关**CsCommonAreaPhone**参数的详细信息，请参阅[CsCommonAreaPhone](https://docs.microsoft.com/powershell/module/skype/Get-CsCommonAreaPhone)。</span><span class="sxs-lookup"><span data-stu-id="2a630-108">For details about **Get-CsCommonAreaPhone** parameters, see [Get-CsCommonAreaPhone](https://docs.microsoft.com/powershell/module/skype/Get-CsCommonAreaPhone).</span></span>

<span data-ttu-id="2a630-109">从 Lync Server 2013 命令行管理程序或从 Windows PowerShell 的远程会话中运行**CsCommonAreaPhone** 。</span><span class="sxs-lookup"><span data-stu-id="2a630-109">Run **Get-CsCommonAreaPhone** either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span>

<div>


<div>

## <a name="viewing-information-about-all-your-common-area-phones"></a><span data-ttu-id="2a630-110">查看有关所有公用区域电话的信息</span><span class="sxs-lookup"><span data-stu-id="2a630-110">Viewing Information about All Your Common Area Phones</span></span>

  - <span data-ttu-id="2a630-111">若要查看有关所有公用区域电话的信息，请在 Lync Server 命令行管理程序中键入以下命令，然后按 Enter：</span><span class="sxs-lookup"><span data-stu-id="2a630-111">To view information about all your common area phones, type the following command in the Lync Server Management Shell, and then press Enter:</span></span>
    
        Get-CsCommonAreaPhone
    
    <span data-ttu-id="2a630-112">您将获得与以下内容类似的信息：</span><span class="sxs-lookup"><span data-stu-id="2a630-112">You’ll get information similar to this:</span></span>
    
        Identity           : CN=Building 14 Lobby,OU=Redmond,
                             DC=litwareinc,DC=com
        RegistrarPool      : atl-cs-001.litwareinc.com
        Enabled            : True
        SipAddress         : sip:4714e34b-9781-421d-b07a-
                             52056b5b4a56@litwareinc.com
        ClientPolicy       :
        PinPolicy          :
        VoicePolicy        :
        MobilityPolicy     :
        GroupChatPolicy    :
        ConferencingPolicy :
        LineURI            : tel:+14255550712
        DisplayNumber      : 1-425-555-0712
        DisplayName        : Building 14 Lobby
        Description        :
        ExUmEnabled        : False

</div>

<span data-ttu-id="2a630-113">有关详细信息，请参阅[CsCommonAreaPhone](https://docs.microsoft.com/powershell/module/skype/Get-CsCommonAreaPhone) Cmdlet 的帮助主题。</span><span class="sxs-lookup"><span data-stu-id="2a630-113">For details, see the Help topic for the [Get-CsCommonAreaPhone](https://docs.microsoft.com/powershell/module/skype/Get-CsCommonAreaPhone) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>


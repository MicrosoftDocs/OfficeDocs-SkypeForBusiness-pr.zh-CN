---
title: Lync Server 2013：查看受信任的应用程序信息
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: View trusted application information
ms:assetid: 7b916323-96fb-4308-bc95-c178de41a3d3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688103(v=OCS.15)
ms:contentKeyID: 49733702
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bf8a95fa58ea1398c281fc5cba2f8b08a5ec902e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757386"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="view-trusted-application-information-in-lync-server-2013"></a><span data-ttu-id="f4eae-102">在 Lync Server 2013 中查看受信任的应用程序信息</span><span class="sxs-lookup"><span data-stu-id="f4eae-102">View trusted application information in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f4eae-103">_**主题上次修改时间：** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="f4eae-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="f4eae-104">你可以使用 Windows PowerShell 和**CsTrustedApplication** cmdlet 查看有关你的受信任的应用程序的信息。</span><span class="sxs-lookup"><span data-stu-id="f4eae-104">You can view information about your trusted applications by using Windows PowerShell and the **Get-CsTrustedApplication** cmdlet.</span></span> <span data-ttu-id="f4eae-105">此 cmdlet 既可以从 Lync Server 2013 管理外壳运行，也可以从 Windows PowerShell 的远程会话运行。</span><span class="sxs-lookup"><span data-stu-id="f4eae-105">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="f4eae-106">有关使用远程 Windows PowerShell 连接到 Lync Server 的详细信息，请参阅 Lync Server Windows PowerShell 博客文章 "快速入门：使用远程 PowerShell 管理 Microsoft Lync Server 2010" [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)。</span><span class="sxs-lookup"><span data-stu-id="f4eae-106">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-view-trusted-applications"></a><span data-ttu-id="f4eae-107">查看受信任的应用程序</span><span class="sxs-lookup"><span data-stu-id="f4eae-107">To view trusted applications</span></span>

  - <span data-ttu-id="f4eae-108">若要查看所有受信任的应用程序，请在 Lync Server 命令行管理程序中键入以下命令，然后按 ENTER：</span><span class="sxs-lookup"><span data-stu-id="f4eae-108">To view all of your trusted applications, type the following command in the Lync Server Management Shell and then press ENTER:</span></span>
    
        Get-CsConferenceDisclaimer
    
    <span data-ttu-id="f4eae-109">此命令针对每个受信任的应用程序返回类似于以下内容的信息：</span><span class="sxs-lookup"><span data-stu-id="f4eae-109">This command returns information similar to the following for each trusted application:</span></span>
    
        Identity               : CN={5dedf4b0-a590-49b3-80cf-f16f914bbef9},CN=Application Contacts,CN=RTC
                                 Service,CN=Services,CN=Configuration,DC=litware,DC=com
        RegistrarPool          : 487279971
        HomeServer             : CN=Lc Services,CN=Microsoft,CN=co1:2,CN=Pools,CN=RTC
                                 Service,CN=Services,CN=Configuration,DC=litware,DC=com
        OwnerUrn               : urn:application:helpdesk
        SipAddress             : sip:RtcApplication-dbf5142f-2bb2-4c4f-9531-b7fea45c5000@litware.com
        DisplayName            :
        DisplayNumber          :
        LineURI                :
        PrimaryLanguage        : 0
        SecondaryLanguages     : {}
        EnterpriseVoiceEnabled : True
        ExUmEnabled            : False
        Enabled                : True
    
    <span data-ttu-id="f4eae-110">有关详细信息，请参阅[CsTrustedApplication](https://docs.microsoft.com/powershell/module/skype/Get-CsTrustedApplication)。</span><span class="sxs-lookup"><span data-stu-id="f4eae-110">For details, see [Get-CsTrustedApplication](https://docs.microsoft.com/powershell/module/skype/Get-CsTrustedApplication).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>


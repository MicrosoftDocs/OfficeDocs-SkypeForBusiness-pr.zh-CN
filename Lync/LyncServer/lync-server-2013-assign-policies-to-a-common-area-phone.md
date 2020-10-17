---
title: Lync Server 2013：将策略分配给公用区域电话
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Assign policies to a common area phone
ms:assetid: f0554fd1-b237-49b3-9eb4-26f4b91f5604
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994082(v=OCS.15)
ms:contentKeyID: 51803993
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7a6403092daa1a8cd84d246f2bd3bdece7661fef
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48499459"
---
# <a name="assign-policies-in-lync-server-2013-to-a-common-area-phone"></a><span data-ttu-id="5155a-102">在 Lync Server 2013 中将策略分配给公用区域电话</span><span class="sxs-lookup"><span data-stu-id="5155a-102">Assign policies in Lync Server 2013 to a common area phone</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5155a-103">_**上次修改的主题：** 2013-02-20_</span><span class="sxs-lookup"><span data-stu-id="5155a-103">_**Topic Last Modified:** 2013-02-20_</span></span>

<span data-ttu-id="5155a-104">为公用区域电话创建策略后 (有关详细信息，请参阅 [create a voice policy and CONFIGURE PSTN usage 记录 In Lync Server 2013](lync-server-2013-create-a-voice-policy-and-configure-pstn-usage-records.md)) 中，可以使用 Windows PowerShell 和相应的 **Grant-Cs** cmdlet 将策略分配给公用区域电话。</span><span class="sxs-lookup"><span data-stu-id="5155a-104">After you create your policy for common area phones (for details, see [Create a voice policy and configure PSTN usage records in Lync Server 2013](lync-server-2013-create-a-voice-policy-and-configure-pstn-usage-records.md)), you can assign the policy to a common area phone by using Windows PowerShell and the appropriate **Grant-Cs** cmdlet.</span></span> <span data-ttu-id="5155a-105">这些 cmdlet 可从 Lync Server 2013 命令行管理程序或 Windows PowerShell 的远程会话中运行。</span><span class="sxs-lookup"><span data-stu-id="5155a-105">These cmdlets can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="5155a-106">有关使用远程 Windows PowerShell 连接到 Lync Server 的详细信息，请参阅在上的 Lync Server Windows PowerShell 博客文章 "快速入门：使用远程 PowerShell 管理 Microsoft Lync Server 2010" [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) 。</span><span class="sxs-lookup"><span data-stu-id="5155a-106">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>


<div>

## <a name="assigning-a-policy-to-a-single-common-area-phone"></a><span data-ttu-id="5155a-107">将策略分配给单个公共区域电话</span><span class="sxs-lookup"><span data-stu-id="5155a-107">Assigning a Policy to a Single Common Area Phone</span></span>

  - <span data-ttu-id="5155a-108">以下命令将每用户语音策略 RedmondVoice 分配给具有标识生成14前厅浏览的公共区域电话。</span><span class="sxs-lookup"><span data-stu-id="5155a-108">The following command assigns the per-user voice policy RedmondVoice to the common area phone that has the Identity Building 14 Lobby.</span></span>
    
        Grant-CsVoicePolicy -Identity "Building 14 Lobby" -PolicyName "RedmondVoicePolicy"

</div>

<div>

## <a name="assigning-a-policy-to-multiple-common-area-phones"></a><span data-ttu-id="5155a-109">将策略分配给多个公用区域电话</span><span class="sxs-lookup"><span data-stu-id="5155a-109">Assigning a Policy to Multiple Common Area Phones</span></span>

  - <span data-ttu-id="5155a-110">在此示例中，将每用户语音策略 RedmondVoice 分配给配置为在组织中使用的所有公用区域电话。</span><span class="sxs-lookup"><span data-stu-id="5155a-110">In this example, the per-user voice policy RedmondVoice is assigned to all the common area phones configured for use in the organization.</span></span>
    
        Get-CsCommonAreaPhone | Grant-CsVoicePolicy  -PolicyName "RedmondVoicePolicy"

</div>

<span data-ttu-id="5155a-111">有关详细信息，请参阅 [set-csvoicepolicy](https://docs.microsoft.com/powershell/module/skype/Grant-CsVoicePolicy)的帮助主题。</span><span class="sxs-lookup"><span data-stu-id="5155a-111">For details, see the Help topics for the [Grant-CsVoicePolicy](https://docs.microsoft.com/powershell/module/skype/Grant-CsVoicePolicy).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="5155a-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5155a-112">See Also</span></span>


[<span data-ttu-id="5155a-113">CsCommonAreaPhone</span><span class="sxs-lookup"><span data-stu-id="5155a-113">Get-CsCommonAreaPhone</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsCommonAreaPhone)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


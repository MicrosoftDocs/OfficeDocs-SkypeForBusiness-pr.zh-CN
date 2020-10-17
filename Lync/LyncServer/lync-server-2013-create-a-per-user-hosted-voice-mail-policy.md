---
title: Lync Server 2013：创建每用户托管的语音邮件策略
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create a per-user hosted voice mail policy
ms:assetid: 39018a7c-e0c3-46a2-be4e-05604ec67a50
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425867(v=OCS.15)
ms:contentKeyID: 48183902
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 04dc942c0cd44c6390c8a7d6627c5da4b551b94c
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48501889"
---
# <a name="create-a-per-user-hosted-voice-mail-policy-in-lync-server-2013"></a><span data-ttu-id="f8f79-102">在 Lync Server 2013 中创建每用户托管的语音邮件策略</span><span class="sxs-lookup"><span data-stu-id="f8f79-102">Create a per-user hosted voice mail policy in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f8f79-103">_**上次修改的主题：** 2012-09-24_</span><span class="sxs-lookup"><span data-stu-id="f8f79-103">_**Topic Last Modified:** 2012-09-24_</span></span>

<span data-ttu-id="f8f79-104">\*\* 每用户策略只能影响单个用户、组和联系对象。</span><span class="sxs-lookup"><span data-stu-id="f8f79-104">A *per-user* policy can only impact individual users, groups, and contact objects.</span></span> <span data-ttu-id="f8f79-105">要部署每用户策略，必须将策略显式分配给一个或多个用户、组或联系对象。</span><span class="sxs-lookup"><span data-stu-id="f8f79-105">To deploy a per-user policy, you must explicitly assign the policy to one or more users, groups, or contact objects.</span></span> <span data-ttu-id="f8f79-106">有关详细信息，请参阅 [在 Lync Server 2013 中分配每用户托管语音邮件策略](lync-server-2013-assign-a-per-user-hosted-voice-mail-policy.md)。</span><span class="sxs-lookup"><span data-stu-id="f8f79-106">For details, see [Assign a per-user hosted voice mail policy in Lync Server 2013](lync-server-2013-assign-a-per-user-hosted-voice-mail-policy.md).</span></span>

<span data-ttu-id="f8f79-107">有关使用每用户托管语音邮件策略的详细信息，请参阅 Lync Server 命令行管理程序文档中的以下 cmdlet：</span><span class="sxs-lookup"><span data-stu-id="f8f79-107">For details about working with per-user hosted voice mail policies, see the Lync Server Management Shell documentation for the following cmdlets:</span></span>

  - [<span data-ttu-id="f8f79-108">新 CsHostedVoicemailPolicy</span><span class="sxs-lookup"><span data-stu-id="f8f79-108">New-CsHostedVoicemailPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsHostedVoicemailPolicy)

  - [<span data-ttu-id="f8f79-109">CsHostedVoicemailPolicy</span><span class="sxs-lookup"><span data-stu-id="f8f79-109">Set-CsHostedVoicemailPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsHostedVoicemailPolicy)

  - [<span data-ttu-id="f8f79-110">CsHostedVoicemailPolicy</span><span class="sxs-lookup"><span data-stu-id="f8f79-110">Get-CsHostedVoicemailPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsHostedVoicemailPolicy)

<div>

## <a name="to-create-a-per-user-hosted-voice-mail-policy"></a><span data-ttu-id="f8f79-111">创建每用户托管语音邮件策略</span><span class="sxs-lookup"><span data-stu-id="f8f79-111">To create a per-user hosted voice mail policy</span></span>

1.  <span data-ttu-id="f8f79-112">启动 Lync Server 命令行管理程序：依次单击“开始”\*\*\*\*、“所有程序”\*\*\*\*、“Microsoft Lync Server 2013”\*\*\*\* 和“Lync Server 命令行管理程序”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="f8f79-112">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="f8f79-p102">运行 New-CsHostedVoicemailPolicy cmdlet 创建策略。例如，运行：</span><span class="sxs-lookup"><span data-stu-id="f8f79-p102">Run the New-CsHostedVoicemailPolicy cmdlet to create the policy. For example, run:</span></span>
    
        New-CsHostedVoicemailPolicy -Identity ExRedmond -Destination ExUM.fabrikam.com -Description "Hosted voice mail policy for Redmond users." -Organization "corp1.litwareinc.com, corp2.litwareinc.com"
    
    <span data-ttu-id="f8f79-115">以上示例创建了一个具有每用户作用域的托管语音邮件策略，并设置了以下参数：</span><span class="sxs-lookup"><span data-stu-id="f8f79-115">The previous example creates a hosted voice mail policy with per-user scope, and sets the following parameters:</span></span>
    
      - <span data-ttu-id="f8f79-p103">**Identity** 为策略指定唯一标识符，其中包含作用域。对于具有每用户作用域的策略，此参数值会指定为简单字符串，如 ExRedmond。</span><span class="sxs-lookup"><span data-stu-id="f8f79-p103">**Identity** specifies a unique identifier for the policy, which includes the scope. For a policy with per-user scope, this parameter value is specified as a simple string, for example, ExRedmond.</span></span>
    
      - <span data-ttu-id="f8f79-p104">**Destination** 指定托管 Exchange UM 服务的完全限定域名 (FQDN)。此参数为可选参数，但如果尝试为用户启用托管语音邮件，而用户的已分配策略没有 Destination 值，则无法启用。</span><span class="sxs-lookup"><span data-stu-id="f8f79-p104">**Destination** specifies the fully qualified domain name (FQDN) of the hosted Exchange UM service. This parameter is optional, but if you attempt to enable a user for hosted voice mail and the user’s assigned policy does not have a Destination value, the enable will fail.</span></span>
    
      - <span data-ttu-id="f8f79-120">**Description** 提供有关策略的可选描述性信息。</span><span class="sxs-lookup"><span data-stu-id="f8f79-120">**Description** provides optional descriptive information about the policy.</span></span>
    
      - <span data-ttu-id="f8f79-121">**组织** 指定 Home Lync Server 2013 用户的 Exchange 租户的逗号分隔列表。</span><span class="sxs-lookup"><span data-stu-id="f8f79-121">**Organization** specifies a comma-separated list of the Exchange tenants that home Lync Server 2013 users.</span></span> <span data-ttu-id="f8f79-122">必须将每个租户指定为托管 Exchange UM 服务上租户的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="f8f79-122">Each tenant must be specified as the FQDN of that tenant on the hosted Exchange UM service.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="f8f79-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f8f79-123">See Also</span></span>


[<span data-ttu-id="f8f79-124">在 Lync Server 2013 中分配每用户托管的语音邮件策略</span><span class="sxs-lookup"><span data-stu-id="f8f79-124">Assign a per-user hosted voice mail policy in Lync Server 2013</span></span>](lync-server-2013-assign-a-per-user-hosted-voice-mail-policy.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


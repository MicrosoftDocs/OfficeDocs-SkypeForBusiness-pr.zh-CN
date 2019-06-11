---
title: 'Lync Server 2013: 创建每用户托管的语音邮件策略'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create a per-user hosted voice mail policy
ms:assetid: 39018a7c-e0c3-46a2-be4e-05604ec67a50
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425867(v=OCS.15)
ms:contentKeyID: 48183902
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d09638c28c1cbd2b068972aff169376508325885
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34837077"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-a-per-user-hosted-voice-mail-policy-in-lync-server-2013"></a><span data-ttu-id="ed503-102">在 Lync Server 2013 中创建每用户托管语音邮件策略</span><span class="sxs-lookup"><span data-stu-id="ed503-102">Create a per-user hosted voice mail policy in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ed503-103">_**主题上次修改时间:** 2012-09-24_</span><span class="sxs-lookup"><span data-stu-id="ed503-103">_**Topic Last Modified:** 2012-09-24_</span></span>

<span data-ttu-id="ed503-104">*每用户*策略只能影响单个用户、组和联系人对象。</span><span class="sxs-lookup"><span data-stu-id="ed503-104">A *per-user* policy can only impact individual users, groups, and contact objects.</span></span> <span data-ttu-id="ed503-105">若要部署每用户策略, 必须将策略显式分配给一个或多个用户、组或联系人对象。</span><span class="sxs-lookup"><span data-stu-id="ed503-105">To deploy a per-user policy, you must explicitly assign the policy to one or more users, groups, or contact objects.</span></span> <span data-ttu-id="ed503-106">有关详细信息, 请参阅[在 Lync Server 2013 中分配每用户托管语音邮件策略](lync-server-2013-assign-a-per-user-hosted-voice-mail-policy.md)。</span><span class="sxs-lookup"><span data-stu-id="ed503-106">For details, see [Assign a per-user hosted voice mail policy in Lync Server 2013](lync-server-2013-assign-a-per-user-hosted-voice-mail-policy.md).</span></span>

<span data-ttu-id="ed503-107">有关使用每用户托管语音邮件策略的详细信息, 请参阅以下 cmdlet 的 Lync Server Management Shell 文档:</span><span class="sxs-lookup"><span data-stu-id="ed503-107">For details about working with per-user hosted voice mail policies, see the Lync Server Management Shell documentation for the following cmdlets:</span></span>

  - [<span data-ttu-id="ed503-108">新-CsHostedVoicemailPolicy</span><span class="sxs-lookup"><span data-stu-id="ed503-108">New-CsHostedVoicemailPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsHostedVoicemailPolicy)

  - [<span data-ttu-id="ed503-109">Set-CsHostedVoicemailPolicy</span><span class="sxs-lookup"><span data-stu-id="ed503-109">Set-CsHostedVoicemailPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsHostedVoicemailPolicy)

  - [<span data-ttu-id="ed503-110">CsHostedVoicemailPolicy</span><span class="sxs-lookup"><span data-stu-id="ed503-110">Get-CsHostedVoicemailPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsHostedVoicemailPolicy)

<div>

## <a name="to-create-a-per-user-hosted-voice-mail-policy"></a><span data-ttu-id="ed503-111">创建每用户托管的语音邮件策略</span><span class="sxs-lookup"><span data-stu-id="ed503-111">To create a per-user hosted voice mail policy</span></span>

1.  <span data-ttu-id="ed503-112">启动 Lync Server 命令行管理程序: 依次单击 "**开始**"、"**所有程序**"、" **Microsoft Lync server 2013**", 然后单击 " **Lync server Management shell**"。</span><span class="sxs-lookup"><span data-stu-id="ed503-112">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="ed503-113">运行 CsHostedVoicemailPolicy cmdlet 以创建策略。</span><span class="sxs-lookup"><span data-stu-id="ed503-113">Run the New-CsHostedVoicemailPolicy cmdlet to create the policy.</span></span> <span data-ttu-id="ed503-114">例如，运行：</span><span class="sxs-lookup"><span data-stu-id="ed503-114">For example, run:</span></span>
    
        New-CsHostedVoicemailPolicy -Identity ExRedmond -Destination ExUM.fabrikam.com -Description "Hosted voice mail policy for Redmond users." -Organization "corp1.litwareinc.com, corp2.litwareinc.com"
    
    <span data-ttu-id="ed503-115">前面的示例将创建具有每用户作用域的托管语音邮件策略, 并设置以下参数:</span><span class="sxs-lookup"><span data-stu-id="ed503-115">The previous example creates a hosted voice mail policy with per-user scope, and sets the following parameters:</span></span>
    
      - <span data-ttu-id="ed503-116">**标识**指定策略的唯一标识符, 其中包括范围。</span><span class="sxs-lookup"><span data-stu-id="ed503-116">**Identity** specifies a unique identifier for the policy, which includes the scope.</span></span> <span data-ttu-id="ed503-117">对于具有每用户范围的策略, 此参数值指定为一个简单的字符串, 例如 ExRedmond。</span><span class="sxs-lookup"><span data-stu-id="ed503-117">For a policy with per-user scope, this parameter value is specified as a simple string, for example, ExRedmond.</span></span>
    
      - <span data-ttu-id="ed503-118">**Destination**指定托管 Exchange UM 服务的完全限定的域名 (FQDN)。</span><span class="sxs-lookup"><span data-stu-id="ed503-118">**Destination** specifies the fully qualified domain name (FQDN) of the hosted Exchange UM service.</span></span> <span data-ttu-id="ed503-119">此参数是可选的, 但如果你尝试为托管语音邮件启用用户, 并且用户分配的策略没有目标值, 则 enable 将失败。</span><span class="sxs-lookup"><span data-stu-id="ed503-119">This parameter is optional, but if you attempt to enable a user for hosted voice mail and the user’s assigned policy does not have a Destination value, the enable will fail.</span></span>
    
      - <span data-ttu-id="ed503-120">**说明**提供有关策略的可选描述性信息。</span><span class="sxs-lookup"><span data-stu-id="ed503-120">**Description** provides optional descriptive information about the policy.</span></span>
    
      - <span data-ttu-id="ed503-121">**组织**指定用于家庭 Lync Server 2013 用户的 Exchange 租户的逗号分隔列表。</span><span class="sxs-lookup"><span data-stu-id="ed503-121">**Organization** specifies a comma-separated list of the Exchange tenants that home Lync Server 2013 users.</span></span> <span data-ttu-id="ed503-122">必须在托管 Exchange UM 服务上将每个租户指定为该租户的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="ed503-122">Each tenant must be specified as the FQDN of that tenant on the hosted Exchange UM service.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="ed503-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ed503-123">See Also</span></span>


[<span data-ttu-id="ed503-124">在 Lync Server 2013 中分配每用户托管语音邮件策略</span><span class="sxs-lookup"><span data-stu-id="ed503-124">Assign a per-user hosted voice mail policy in Lync Server 2013</span></span>](lync-server-2013-assign-a-per-user-hosted-voice-mail-policy.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


---
title: 'Lync Server 2013: 创建网站级托管语音邮件策略'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create a site-level hosted voice mail policy
ms:assetid: 145892c8-a6ca-45fb-9e83-786f709dd775
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398216(v=OCS.15)
ms:contentKeyID: 48183481
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d9df91e28eeba8bc9769e4fcbeff6ebba2b3746d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34837076"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-a-site-level-hosted-voice-mail-policy-in-lync-server-2013"></a><span data-ttu-id="72f09-102">在 Lync Server 2013 中创建网站级托管语音邮件策略</span><span class="sxs-lookup"><span data-stu-id="72f09-102">Create a site-level hosted voice mail policy in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="72f09-103">_**主题上次修改时间:** 2012-09-24_</span><span class="sxs-lookup"><span data-stu-id="72f09-103">_**Topic Last Modified:** 2012-09-24_</span></span>

<span data-ttu-id="72f09-104">*网站*策略可能会影响托管在定义了该策略的网站上的所有用户。</span><span class="sxs-lookup"><span data-stu-id="72f09-104">A *site* policy can impact all users that are homed on the site for which the policy is defined.</span></span> <span data-ttu-id="72f09-105">如果用户已配置为托管 Exchange UM 访问, 并且尚未分配每用户策略, 则应用网站策略。</span><span class="sxs-lookup"><span data-stu-id="72f09-105">If a user is configured for hosted Exchange UM access and has not been assigned a Per-user policy, the site policy applies.</span></span> <span data-ttu-id="72f09-106">如果尚未部署网站策略, 则应用全局策略。</span><span class="sxs-lookup"><span data-stu-id="72f09-106">If you have not deployed a site policy, the global policy applies.</span></span>

<span data-ttu-id="72f09-107">有关配置网站策略的详细信息, 请参阅以下 cmdlet 的 Lync Server Management Shell 文档:</span><span class="sxs-lookup"><span data-stu-id="72f09-107">For details about configuring site policies, see the Lync Server Management Shell documentation for the following cmdlets:</span></span>

  - [<span data-ttu-id="72f09-108">新-CsHostedVoicemailPolicy</span><span class="sxs-lookup"><span data-stu-id="72f09-108">New-CsHostedVoicemailPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsHostedVoicemailPolicy)

  - [<span data-ttu-id="72f09-109">Set-CsHostedVoicemailPolicy</span><span class="sxs-lookup"><span data-stu-id="72f09-109">Set-CsHostedVoicemailPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsHostedVoicemailPolicy)

  - [<span data-ttu-id="72f09-110">CsHostedVoicemailPolicy</span><span class="sxs-lookup"><span data-stu-id="72f09-110">Get-CsHostedVoicemailPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsHostedVoicemailPolicy)

<div>

## <a name="to-create-a-site-hosted-voice-mail-policy"></a><span data-ttu-id="72f09-111">创建网站托管语音邮件策略</span><span class="sxs-lookup"><span data-stu-id="72f09-111">To create a site hosted voice mail policy</span></span>

1.  <span data-ttu-id="72f09-112">启动 Lync Server 命令行管理程序: 依次单击 "**开始**"、"**所有程序**"、" **Microsoft Lync server 2013**", 然后单击 " **Lync server Management shell**"。</span><span class="sxs-lookup"><span data-stu-id="72f09-112">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="72f09-113">运行 CsHostedVoicemailPolicy cmdlet 以创建策略。</span><span class="sxs-lookup"><span data-stu-id="72f09-113">Run the New-CsHostedVoicemailPolicy cmdlet to create the policy.</span></span> <span data-ttu-id="72f09-114">例如，运行：</span><span class="sxs-lookup"><span data-stu-id="72f09-114">For example, run:</span></span>
    
        New-CsHostedVoicemailPolicy -Identity site:Redmond -Destination ExUM.fabrikam.com -Description "Hosted voice mail policy for the Redmond site." -Organization "corp1.litwareinc.com, corp2.litwareinc.com"
    
    <span data-ttu-id="72f09-115">此示例创建一个具有网站范围的托管语音邮件策略, 并设置以下参数:</span><span class="sxs-lookup"><span data-stu-id="72f09-115">This example creates a hosted voice mail policy with site scope, and sets the following parameters:</span></span>
    
      - <span data-ttu-id="72f09-116">**标识**指定策略的唯一标识符, 其中包括范围。</span><span class="sxs-lookup"><span data-stu-id="72f09-116">**Identity** specifies a unique identifier for the policy, which includes the scope.</span></span> <span data-ttu-id="72f09-117">对于具有网站范围的策略, 必须在格式`site:` \* \<名称\>\* 中指定 Identity 参数值, 例如。 `site:Redmond`</span><span class="sxs-lookup"><span data-stu-id="72f09-117">For a policy with site scope, the Identity parameter value must be specified in the format `site:`*\<name\>*, for example, `site:Redmond`.</span></span>
    
      - <span data-ttu-id="72f09-118">**Destination**指定托管 Exchange UM 服务的完全限定的域名 (FQDN)。</span><span class="sxs-lookup"><span data-stu-id="72f09-118">**Destination** specifies the fully qualified domain name (FQDN) of the hosted Exchange UM service.</span></span> <span data-ttu-id="72f09-119">此参数是可选的, 但如果你尝试为托管语音邮件启用用户, 并且用户分配的策略没有目标值, 则 enable 将失败。</span><span class="sxs-lookup"><span data-stu-id="72f09-119">This parameter is optional, but if you attempt to enable a user for hosted voice mail and the user’s assigned policy does not have a Destination value, the enable will fail.</span></span>
    
      - <span data-ttu-id="72f09-120">**说明**提供有关策略的可选描述性信息。</span><span class="sxs-lookup"><span data-stu-id="72f09-120">**Description** provides optional descriptive information about the policy.</span></span>
    
      - <span data-ttu-id="72f09-121">**组织**指定用于家庭 Lync Server 2013 用户的 Exchange 租户的逗号分隔列表。</span><span class="sxs-lookup"><span data-stu-id="72f09-121">**Organization** specifies a comma-separated list of the Exchange tenants that home Lync Server 2013 users.</span></span> <span data-ttu-id="72f09-122">必须在托管 Exchange UM 服务上将每个租户指定为该租户的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="72f09-122">Each tenant must be specified as the FQDN of that tenant on the hosted Exchange UM service.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>


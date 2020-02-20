---
title: Lync Server 2013：创建网站级别托管的语音邮件策略
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create a site-level hosted voice mail policy
ms:assetid: 145892c8-a6ca-45fb-9e83-786f709dd775
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398216(v=OCS.15)
ms:contentKeyID: 48183481
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dd227787ae790b280c98c73e9ca0bb516d7dc092
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42145561"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="create-a-site-level-hosted-voice-mail-policy-in-lync-server-2013"></a><span data-ttu-id="21667-102">在 Lync Server 2013 中创建网站级别托管的语音邮件策略</span><span class="sxs-lookup"><span data-stu-id="21667-102">Create a site-level hosted voice mail policy in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="21667-103">_**上次修改的主题：** 2012-09-24_</span><span class="sxs-lookup"><span data-stu-id="21667-103">_**Topic Last Modified:** 2012-09-24_</span></span>

<span data-ttu-id="21667-p101">*站点* 策略可以影响在为其定义策略的站点上承载的所有用户。如果已为用户配置托管 Exchange UM 访问且未向用户分配每用户策略，则将应用站点策略。如果尚未部署站点策略，则将应用全局策略。</span><span class="sxs-lookup"><span data-stu-id="21667-p101">A *site* policy can impact all users that are homed on the site for which the policy is defined. If a user is configured for hosted Exchange UM access and has not been assigned a Per-user policy, the site policy applies. If you have not deployed a site policy, the global policy applies.</span></span>

<span data-ttu-id="21667-107">有关配置网站策略的详细信息，请参阅 Lync Server 命令行管理程序文档中的以下 cmdlet：</span><span class="sxs-lookup"><span data-stu-id="21667-107">For details about configuring site policies, see the Lync Server Management Shell documentation for the following cmdlets:</span></span>

  - [<span data-ttu-id="21667-108">新 CsHostedVoicemailPolicy</span><span class="sxs-lookup"><span data-stu-id="21667-108">New-CsHostedVoicemailPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsHostedVoicemailPolicy)

  - [<span data-ttu-id="21667-109">CsHostedVoicemailPolicy</span><span class="sxs-lookup"><span data-stu-id="21667-109">Set-CsHostedVoicemailPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsHostedVoicemailPolicy)

  - [<span data-ttu-id="21667-110">CsHostedVoicemailPolicy</span><span class="sxs-lookup"><span data-stu-id="21667-110">Get-CsHostedVoicemailPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsHostedVoicemailPolicy)

<div>

## <a name="to-create-a-site-hosted-voice-mail-policy"></a><span data-ttu-id="21667-111">创建站点托管语音邮件策略</span><span class="sxs-lookup"><span data-stu-id="21667-111">To create a site hosted voice mail policy</span></span>

1.  <span data-ttu-id="21667-112">启动 Lync Server 命令行管理程序：依次单击“开始”\*\*\*\*、“所有程序”\*\*\*\*、“Microsoft Lync Server 2013”\*\*\*\* 和“Lync Server 命令行管理程序”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="21667-112">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="21667-p102">运行 New-CsHostedVoicemailPolicy cmdlet 创建策略。例如，运行：</span><span class="sxs-lookup"><span data-stu-id="21667-p102">Run the New-CsHostedVoicemailPolicy cmdlet to create the policy. For example, run:</span></span>
    
        New-CsHostedVoicemailPolicy -Identity site:Redmond -Destination ExUM.fabrikam.com -Description "Hosted voice mail policy for the Redmond site." -Organization "corp1.litwareinc.com, corp2.litwareinc.com"
    
    <span data-ttu-id="21667-115">本示例创建 site 作用域的托管语音邮件策略，并设置以下参数：</span><span class="sxs-lookup"><span data-stu-id="21667-115">This example creates a hosted voice mail policy with site scope, and sets the following parameters:</span></span>
    
      - <span data-ttu-id="21667-116">**Identity** 为策略指定唯一标识符，其中包含作用域。</span><span class="sxs-lookup"><span data-stu-id="21667-116">**Identity** specifies a unique identifier for the policy, which includes the scope.</span></span> <span data-ttu-id="21667-117">对于具有站点范围的策略，必须在格式`site:` \* \<名称\>\* 中指定 Identity 参数值，例如。 `site:Redmond`</span><span class="sxs-lookup"><span data-stu-id="21667-117">For a policy with site scope, the Identity parameter value must be specified in the format `site:`*\<name\>*, for example, `site:Redmond`.</span></span>
    
      - <span data-ttu-id="21667-p104">**Destination** 指定托管 Exchange UM 服务的完全限定域名 (FQDN)。此参数为可选参数，但如果尝试为用户启用托管语音邮件，而用户的已分配策略没有 Destination 值，则无法启用。</span><span class="sxs-lookup"><span data-stu-id="21667-p104">**Destination** specifies the fully qualified domain name (FQDN) of the hosted Exchange UM service. This parameter is optional, but if you attempt to enable a user for hosted voice mail and the user’s assigned policy does not have a Destination value, the enable will fail.</span></span>
    
      - <span data-ttu-id="21667-120">**Description** 提供有关策略的可选描述性信息。</span><span class="sxs-lookup"><span data-stu-id="21667-120">**Description** provides optional descriptive information about the policy.</span></span>
    
      - <span data-ttu-id="21667-121">**组织**指定 Home Lync Server 2013 用户的 Exchange 租户的逗号分隔列表。</span><span class="sxs-lookup"><span data-stu-id="21667-121">**Organization** specifies a comma-separated list of the Exchange tenants that home Lync Server 2013 users.</span></span> <span data-ttu-id="21667-122">必须将每个租户指定为托管 Exchange UM 服务上租户的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="21667-122">Each tenant must be specified as the FQDN of that tenant on the hosted Exchange UM service.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>


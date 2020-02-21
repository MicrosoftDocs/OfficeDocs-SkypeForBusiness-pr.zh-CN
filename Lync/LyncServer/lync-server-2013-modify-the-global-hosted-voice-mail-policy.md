---
title: Lync Server 2013：修改全局托管的语音邮件策略
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Modify the global hosted voice mail policy
ms:assetid: f059b3ce-a7d8-4ea9-b10b-0052222ec2ce
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412994(v=OCS.15)
ms:contentKeyID: 48185757
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 88d0e29981df18ed883d6c33fb810d86da09d255
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42184795"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="modify-the-global-hosted-voice-mail-policy-in-lync-server-2013"></a><span data-ttu-id="a44a6-102">在 Lync Server 2013 中修改全局托管语音邮件策略</span><span class="sxs-lookup"><span data-stu-id="a44a6-102">Modify the global hosted voice mail policy in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a44a6-103">_**上次修改的主题：** 2012-09-24_</span><span class="sxs-lookup"><span data-stu-id="a44a6-103">_**Topic Last Modified:** 2012-09-24_</span></span>

<span data-ttu-id="a44a6-104">*全局*托管的语音邮件策略随 Lync Server 2013 一起安装。</span><span class="sxs-lookup"><span data-stu-id="a44a6-104">The *global* hosted voice mail policy is installed with Lync Server 2013.</span></span> <span data-ttu-id="a44a6-105">可以根据需要修改该策略，但不能重命名或删除它。</span><span class="sxs-lookup"><span data-stu-id="a44a6-105">You can modify it to meet your needs, but you cannot rename or delete it.</span></span> <span data-ttu-id="a44a6-106">若要修改全局策略，您可以针对特定的部署使用 Set-CsHostedVoicemailPolicy cmdlet 将参数设置为相应的值。</span><span class="sxs-lookup"><span data-stu-id="a44a6-106">To modify the global policy, you use the Set-CsHostedVoicemailPolicy cmdlet to set the parameters to appropriate values for your specific deployment.</span></span>

<span data-ttu-id="a44a6-107">有关[CsHostedVoicemailPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsHostedVoicemailPolicy) cmdlet 的详细信息，请参阅 Lync Server 命令行管理程序文档。</span><span class="sxs-lookup"><span data-stu-id="a44a6-107">For details about the [Set-CsHostedVoicemailPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsHostedVoicemailPolicy) cmdlet, see the Lync Server Management Shell documentation.</span></span>

<div>

## <a name="to-modify-the-global-hosted-voice-mail-policy"></a><span data-ttu-id="a44a6-108">修改全局托管语音邮件策略</span><span class="sxs-lookup"><span data-stu-id="a44a6-108">To modify the global hosted voice mail policy</span></span>

1.  <span data-ttu-id="a44a6-109">启动 Lync Server 命令行管理程序：依次单击“开始”\*\*\*\*、“所有程序”\*\*\*\*、“Microsoft Lync Server 2013”\*\*\*\* 和“Lync Server 命令行管理程序”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="a44a6-109">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="a44a6-110">运行 Set-CsHostedVoicemailPolicy cmdlet，为您的环境设置全局策略参数。</span><span class="sxs-lookup"><span data-stu-id="a44a6-110">Run the Set-CsHostedVoicemailPolicy cmdlet to set the global policy parameters for your environment.</span></span> <span data-ttu-id="a44a6-111">例如，运行：</span><span class="sxs-lookup"><span data-stu-id="a44a6-111">For example, run:</span></span>
    
        Set-CsHostedVoicemailPolicy -Destination ExUM.fabrikam.com -Organization "corp1.litwareinc.com"
    
    <span data-ttu-id="a44a6-112">由于此命令不指定策略的 Identity 参数，因此 Windows PowerShell 命令行界面将在全局托管的语音邮件策略上设置以下值：</span><span class="sxs-lookup"><span data-stu-id="a44a6-112">Because this command does not specify the policy’s Identity parameter, Windows PowerShell command-line interface sets the following values on the global hosted voice mail policy:</span></span>
    
      - <span data-ttu-id="a44a6-p103">**Destination** 指定托管 Exchange UM 服务的完全限定域名 (FQDN)。此参数为可选参数，但如果尝试为用户启用托管语音邮件，而用户的已分配策略没有 Destination 值，则无法启用。</span><span class="sxs-lookup"><span data-stu-id="a44a6-p103">**Destination** specifies the fully qualified domain name (FQDN) of the hosted Exchange UM service. This parameter is optional, but if you attempt to enable a user for hosted voice mail and the user’s assigned policy does not have a Destination value, the enable will fail.</span></span>
    
      - <span data-ttu-id="a44a6-115">**组织**指定家庭 Lync Server 用户的 Exchange 租户的逗号分隔列表。</span><span class="sxs-lookup"><span data-stu-id="a44a6-115">**Organization** specifies a comma-separated list of the Exchange tenants that home Lync Server users.</span></span> <span data-ttu-id="a44a6-116">必须将每个租户指定为托管 Exchange UM 服务上租户的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="a44a6-116">Each tenant must be specified as the FQDN of that tenant on the hosted Exchange UM service.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="a44a6-p105">在前面的示例 cmdlet 中，“corp1.litwareinc.com”值替代可能已经显示在 Organization 参数中的任何值。例如，如果策略已包含以逗号分隔的组织列表，则会替换整个列表。如果要向列表中添加组织，而不是替换整个列表，可运行类似如下的命令。</span><span class="sxs-lookup"><span data-stu-id="a44a6-p105">In the previous example cmdlet, the value “corp1.litwareinc.com” replaces any value that might already be present in the Organization parameter. For example, if the policy already contains a comma-separated list of organizations, the full list would be replaced. If you want to add an organization to the list rather than replace the entire list, run a command similar to the following.</span></span>

    
    </div>
    
        $a = Get-CsHostedVoicemailPolicy
        $a.Organization += ",corp3.litwareinc.com"
        Set-CsHostedVoicemailPolicy -Organization $a.Organization

</div>

</div>

<span> </span>

</div>

</div>

</div>


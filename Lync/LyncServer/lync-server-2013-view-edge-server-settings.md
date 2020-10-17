---
title: Lync Server 2013：查看边缘服务器设置
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: View Edge Server settings
ms:assetid: 684154cc-cffc-4d2e-8baa-be52c625e5d7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn747890(v=OCS.15)
ms:contentKeyID: 63969612
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ceb3f536a0aadb181b1b740d74c8f61715efed21
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48506389"
---
# <a name="view-edge-server-settings-in-lync-server-2013"></a><span data-ttu-id="0cac6-102">在 Lync Server 2013 中查看边缘服务器设置</span><span class="sxs-lookup"><span data-stu-id="0cac6-102">View Edge Server settings in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0cac6-103">_**上次修改的主题：** 2014-05-20_</span><span class="sxs-lookup"><span data-stu-id="0cac6-103">_**Topic Last Modified:** 2014-05-20_</span></span>

<span data-ttu-id="0cac6-104">应对照配置管理数据库中的数据检查常规边缘服务器配置，以帮助确保根据定义的更改控制过程记录所有更改。</span><span class="sxs-lookup"><span data-stu-id="0cac6-104">General Edge Server configurations should be reviewed against the data in the configuration management database—to help guarantee that all changes were documented as per the defined change control procedures.</span></span>

<span data-ttu-id="0cac6-105">其他检查可能包含以下各节所述的内容：</span><span class="sxs-lookup"><span data-stu-id="0cac6-105">Additional checks could include those that are described in the following sections:</span></span>

<div>

## <a name="verify-the-allow-and-block-lists"></a><span data-ttu-id="0cac6-106">验证允许和阻止名单</span><span class="sxs-lookup"><span data-stu-id="0cac6-106">Verify the Allow and block lists</span></span>

<span data-ttu-id="0cac6-107">验证联盟域的 SIP URI "Allow" 和 "Block" 列表，以确定列出的命名空间是否仍然有效。</span><span class="sxs-lookup"><span data-stu-id="0cac6-107">Verify the SIP URI "Allow" and "Block" lists for Federated domains—to determine whether listed namespaces are still valid.</span></span>

<span data-ttu-id="0cac6-108">您可以使用 Windows PowerShell 查看允许和阻止的列表。</span><span class="sxs-lookup"><span data-stu-id="0cac6-108">You can use Windows PowerShell to view the allowed and blocked lists.</span></span> <span data-ttu-id="0cac6-109">若要查看 "允许的域" 列表中的域，请运行以下 Windows PowerShell 命令：</span><span class="sxs-lookup"><span data-stu-id="0cac6-109">To review the domains on the Allowed Domains list, run the following Windows PowerShell command:</span></span>

`Get-CsAllowedDomain`

<span data-ttu-id="0cac6-110">该命令将针对 "允许的域" 列表中的域返回类似于以下内容的信息：</span><span class="sxs-lookup"><span data-stu-id="0cac6-110">That command returns information similar to this for the domains on the Allowed Domains list:</span></span>

<span data-ttu-id="0cac6-111">标识： contoso.com</span><span class="sxs-lookup"><span data-stu-id="0cac6-111">Identity : contoso.com</span></span>

<span data-ttu-id="0cac6-112">域： contoso.com</span><span class="sxs-lookup"><span data-stu-id="0cac6-112">Domain : contoso.com</span></span>

<span data-ttu-id="0cac6-113">ProxyFqdn</span><span class="sxs-lookup"><span data-stu-id="0cac6-113">ProxyFqdn :</span></span>

<span data-ttu-id="0cac6-114">注释</span><span class="sxs-lookup"><span data-stu-id="0cac6-114">Comment :</span></span>

<span data-ttu-id="0cac6-115">MarkForMonitoring： False</span><span class="sxs-lookup"><span data-stu-id="0cac6-115">MarkForMonitoring : False</span></span>

<span data-ttu-id="0cac6-116">注释</span><span class="sxs-lookup"><span data-stu-id="0cac6-116">Comment :</span></span>

<span data-ttu-id="0cac6-117">若要查看阻止的域列表中的域，请使用以下命令：</span><span class="sxs-lookup"><span data-stu-id="0cac6-117">To review the domains on the blocked domains list, use this command:</span></span>

`Get-CsBlockedDomain`

<span data-ttu-id="0cac6-118">反过来，你将收到有关每个被阻止的域的信息，例如：</span><span class="sxs-lookup"><span data-stu-id="0cac6-118">In turn, you'll receive information such as this for each blocked domain:</span></span>

<span data-ttu-id="0cac6-119">标识： tailspintoys.com</span><span class="sxs-lookup"><span data-stu-id="0cac6-119">Identity : tailspintoys.com</span></span>

<span data-ttu-id="0cac6-120">域： tailspintoys.com</span><span class="sxs-lookup"><span data-stu-id="0cac6-120">Domain : tailspintoys.com</span></span>

<span data-ttu-id="0cac6-121">Windows PowerShell 还允许您验证是否可以连接到允许的域列表中的域。</span><span class="sxs-lookup"><span data-stu-id="0cac6-121">Windows PowerShell also enables you to verify that you can connection to the domains on your Allowed Domains list.</span></span> <span data-ttu-id="0cac6-122">例如，以下命令将验证您的边缘服务器 (TargetFqdn) 和联盟域 contoso.com 之间的连接：</span><span class="sxs-lookup"><span data-stu-id="0cac6-122">For example, this command verifies the connection between your Edge Server (the TargetFqdn) and the federated domain contoso.com:</span></span>

`Test-CsFederatedPartner -TargetFqdn "atl-edge-001.litwareinc.com" -Domain "contoso.com"`

<span data-ttu-id="0cac6-123">此命令将验证您的边缘服务器与您在允许的域列表中找到的所有域之间的连接：</span><span class="sxs-lookup"><span data-stu-id="0cac6-123">And this command verifies the connection between your Edge Server and all of the domains found on your Allowed Domains list:</span></span>

`Get-CsAllowedDomain | ForEach-Object {Test-CsFederatedPartner -TargetFqdn "atl-edge-001.litwareinc.com" -Domain $_.Domain}`

</div>

<div>

## <a name="verify-multiple-edge-servers-are-identical"></a><span data-ttu-id="0cac6-124">验证多个边缘服务器是否相同</span><span class="sxs-lookup"><span data-stu-id="0cac6-124">Verify multiple Edge Servers are identical</span></span>

<span data-ttu-id="0cac6-125">如果在负载平衡阵列中部署多台边缘服务器，我们建议验证是否以相同方式配置了阵列中的所有边缘服务器。</span><span class="sxs-lookup"><span data-stu-id="0cac6-125">If multiple Edge Servers are deployed in a load balanced array, we recommend verifying that all Edge Servers in the array are configured in the same manner.</span></span>

<span data-ttu-id="0cac6-126">您可以在 "计算机管理" 管理单元的 Lync Server 2013 扩展的详细信息窗格中查看边缘服务器的设置。</span><span class="sxs-lookup"><span data-stu-id="0cac6-126">You can view settings for Edge Servers in the details pane of the Lync Server 2013 extension for the Computer Management snap-in.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="0cac6-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0cac6-127">See Also</span></span>


[<span data-ttu-id="0cac6-128">CsAllowedDomain</span><span class="sxs-lookup"><span data-stu-id="0cac6-128">Get-CsAllowedDomain</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsAllowedDomain)  
[<span data-ttu-id="0cac6-129">CsBlockedDomain</span><span class="sxs-lookup"><span data-stu-id="0cac6-129">Get-CsBlockedDomain</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsBlockedDomain)  
[<span data-ttu-id="0cac6-130">Test-CsFederatedPartner</span><span class="sxs-lookup"><span data-stu-id="0cac6-130">Test-CsFederatedPartner</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsFederatedPartner)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


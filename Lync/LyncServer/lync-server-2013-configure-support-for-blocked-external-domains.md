---
title: Lync Server 2013：配置对阻止的外部域的支持
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure support for blocked external domains
ms:assetid: 49103138-e1ab-42bf-91aa-57cf23bbf260
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ619176(v=OCS.15)
ms:contentKeyID: 49733638
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f24c7db21daa02ff67dc8eb4ddf375c78f96b6d8
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42179869"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-support-for-blocked-external-domains-in-lync-server-2013"></a><span data-ttu-id="942f4-102">在 Lync Server 2013 中配置对阻止的外部域的支持</span><span class="sxs-lookup"><span data-stu-id="942f4-102">Configure support for blocked external domains in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="942f4-103">_**上次修改的主题：** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="942f4-103">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="942f4-104">如果您配置了对联盟伙伴的支持，则可通过与您的组织联盟来管理将阻止的域。</span><span class="sxs-lookup"><span data-stu-id="942f4-104">If you have configured support for federated partners, you can manage which domains will be blocked from federating with your organization.</span></span> <span data-ttu-id="942f4-105">被阻止的域的列表将充当阻止名单（不允许使用的显式条目的列表）并将在联盟域发现中应用（如果您启用了此选项）。</span><span class="sxs-lookup"><span data-stu-id="942f4-105">The list of blocked domains will act as a block list (listing of explicit entries that are not to be allowed) and will apply in federated domain discovery, if you have this option enabled.</span></span> <span data-ttu-id="942f4-106">有关详细信息，请参阅[在 Lync Server 2013 中启用或禁用联合合作伙伴发现](lync-server-2013-enable-or-disable-discovery-of-federation-partners.md)。</span><span class="sxs-lookup"><span data-stu-id="942f4-106">For details, see [Enable or disable discovery of federation partners in Lync Server 2013](lync-server-2013-enable-or-disable-discovery-of-federation-partners.md).</span></span>

<span data-ttu-id="942f4-p102">阻止一个或多个外部域连接到您的组织。要执行此操作，请将相应的域添加到阻止域列表中。</span><span class="sxs-lookup"><span data-stu-id="942f4-p102">Block one or more external domains from connecting to your organization. To do this, add the domain to the list of blocked domains.</span></span>

<div>

## <a name="to-add-an-external-domain-to-the-list-of-blocked-domains"></a><span data-ttu-id="942f4-109">将外部域添加到阻止域列表中</span><span class="sxs-lookup"><span data-stu-id="942f4-109">To add an external domain to the list of blocked domains</span></span>

1.  <span data-ttu-id="942f4-110">从作为 RTCUniversalServerAdmins 组成员的用户帐户（或具有等效的用户权限）或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="942f4-110">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="942f4-111">打开浏览器窗口，然后输入管理员 URL 以打开 "Lync Server 控制面板"。</span><span class="sxs-lookup"><span data-stu-id="942f4-111">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="942f4-112">有关可用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅[Open Lync server 2013 "管理工具](lync-server-2013-open-lync-server-administrative-tools.md)"。</span><span class="sxs-lookup"><span data-stu-id="942f4-112">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="942f4-113">在左侧导航栏中，单击“外部用户访问”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="942f4-113">In the left navigation bar, click **External User Access**.</span></span>

4.  <span data-ttu-id="942f4-114">单击“联盟域”\*\*\*\*，再单击“新建”\*\*\*\*，然后单击“被阻止的域”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="942f4-114">Click **Federated Domains**, click **New**, and then click **Blocked domain**.</span></span>

5.  <span data-ttu-id="942f4-115">在“新建联盟域”\*\*\*\* 中，执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="942f4-115">In **New Federated Domains**, do the following:</span></span>
    
      - <span data-ttu-id="942f4-116">在“域名(或 FQDN)”\*\*\*\* 中，键入要阻止的联盟伙伴域的名称。</span><span class="sxs-lookup"><span data-stu-id="942f4-116">In **Domain name (or FQDN)**, type the name of the federated partner domain that you want to block.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="942f4-117">该名称的长度不能超过 256 个字符。</span><span class="sxs-lookup"><span data-stu-id="942f4-117">The name cannot exceed 256 characters in length.</span></span><BR><span data-ttu-id="942f4-p104">搜索联盟伙伴域名时执行后缀匹配。例如，如果键入 <STRONG>contoso.com</STRONG>，搜索还将返回域 <STRONG>it.contoso.com</STRONG>。</span><span class="sxs-lookup"><span data-stu-id="942f4-p104">The search on the federated partner domain name performs a suffix match. For example, if you type <STRONG>contoso.com</STRONG>, the search will also return the domain <STRONG>it.contoso.com</STRONG>.</span></span><BR><span data-ttu-id="942f4-120">无法同时阻止和允许联盟合作伙伴域。</span><span class="sxs-lookup"><span data-stu-id="942f4-120">A federated partner domain cannot simultaneously be blocked and allowed.</span></span> <span data-ttu-id="942f4-121">Lync Server 2013 阻止这种情况，因此您不必同步您的列表。</span><span class="sxs-lookup"><span data-stu-id="942f4-121">Lync Server 2013 prevents this from happening so that you do not have to synch up your lists.</span></span>

        
        </div>
    
      - <span data-ttu-id="942f4-122">（可选）在“注释”\*\*\*\* 中，键入要与其他系统管理员共享的有关此配置的信息。</span><span class="sxs-lookup"><span data-stu-id="942f4-122">(Optional) In **Comment**, type information that you want to share with other system administrators about this configuration.</span></span>

6.  <span data-ttu-id="942f4-123">单击“提交”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="942f4-123">Click **Commit**.</span></span>

7.  <span data-ttu-id="942f4-124">对要阻止的每个联盟伙伴，重复步骤 4 至 6。</span><span class="sxs-lookup"><span data-stu-id="942f4-124">Repeat steps 4 through 6 for each federated partner that you want to block.</span></span>

<span data-ttu-id="942f4-125">若要启用联盟用户的访问，还必须在组织中启用对联盟用户访问的支持。</span><span class="sxs-lookup"><span data-stu-id="942f4-125">To enable federated user access, you must also enable support for federated user access in your organization.</span></span> <span data-ttu-id="942f4-126">有关详细信息，请参阅[在 Lync Server 2013 中启用或禁用远程用户访问](lync-server-2013-enable-or-disable-remote-user-access.md)。</span><span class="sxs-lookup"><span data-stu-id="942f4-126">For details, see [Enable or disable remote user access in Lync Server 2013](lync-server-2013-enable-or-disable-remote-user-access.md).</span></span>

<span data-ttu-id="942f4-127">此外，还必须为希望能够与联盟用户协作的用户配置和应用策略。</span><span class="sxs-lookup"><span data-stu-id="942f4-127">Additionally, you must configure and apply the policy to users that you want to be able to collaborate with federated users.</span></span> <span data-ttu-id="942f4-128">有关详细信息，请参阅[在 Lync Server 2013 中配置用于控制联盟用户访问的策略](lync-server-2013-configure-policies-to-control-federated-user-access.md)。</span><span class="sxs-lookup"><span data-stu-id="942f4-128">For details, see [Configure policies to control federated user access in Lync Server 2013](lync-server-2013-configure-policies-to-control-federated-user-access.md).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>


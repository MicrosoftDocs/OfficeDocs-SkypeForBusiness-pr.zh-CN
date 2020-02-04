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
ms.openlocfilehash: 3fe73985687e7a1d6fcd2bbf615127c0757a5307
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763546"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-support-for-blocked-external-domains-in-lync-server-2013"></a><span data-ttu-id="b65eb-102">在 Lync Server 2013 中配置对阻止的外部域的支持</span><span class="sxs-lookup"><span data-stu-id="b65eb-102">Configure support for blocked external domains in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b65eb-103">_**主题上次修改时间：** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="b65eb-103">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="b65eb-104">如果你已为联盟伙伴配置支持，你可以管理阻止哪些域与你的组织进行联盟。</span><span class="sxs-lookup"><span data-stu-id="b65eb-104">If you have configured support for federated partners, you can manage which domains will be blocked from federating with your organization.</span></span> <span data-ttu-id="b65eb-105">被阻止域的列表将充当阻止列表（列出不允许的显式条目），并且将在联合域发现中应用（如果已启用此选项）。</span><span class="sxs-lookup"><span data-stu-id="b65eb-105">The list of blocked domains will act as a block list (listing of explicit entries that are not to be allowed) and will apply in federated domain discovery, if you have this option enabled.</span></span> <span data-ttu-id="b65eb-106">有关详细信息，请参阅[在 Lync Server 2013 中启用或禁用联合合作伙伴的发现](lync-server-2013-enable-or-disable-discovery-of-federation-partners.md)。</span><span class="sxs-lookup"><span data-stu-id="b65eb-106">For details, see [Enable or disable discovery of federation partners in Lync Server 2013](lync-server-2013-enable-or-disable-discovery-of-federation-partners.md).</span></span>

<span data-ttu-id="b65eb-107">阻止一个或多个外部域连接到你的组织。</span><span class="sxs-lookup"><span data-stu-id="b65eb-107">Block one or more external domains from connecting to your organization.</span></span> <span data-ttu-id="b65eb-108">若要执行此操作，请将该域添加到阻止域的列表中。</span><span class="sxs-lookup"><span data-stu-id="b65eb-108">To do this, add the domain to the list of blocked domains.</span></span>

<div>

## <a name="to-add-an-external-domain-to-the-list-of-blocked-domains"></a><span data-ttu-id="b65eb-109">将外部域添加到阻止域的列表</span><span class="sxs-lookup"><span data-stu-id="b65eb-109">To add an external domain to the list of blocked domains</span></span>

1.  <span data-ttu-id="b65eb-110">使用 RTCUniversalServerAdmins 组成员（或具有同等用户权限）的用户帐户，或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="b65eb-110">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="b65eb-111">打开一个浏览器窗口，然后输入 "管理员" URL 以打开 Lync Server "控制面板"。</span><span class="sxs-lookup"><span data-stu-id="b65eb-111">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="b65eb-112">有关可用于启动 Lync Server "控制面板" 的不同方法的详细信息，请参阅[打开 Lync server 2013 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="b65eb-112">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="b65eb-113">在左侧导航栏中，单击 "**外部用户访问**"。</span><span class="sxs-lookup"><span data-stu-id="b65eb-113">In the left navigation bar, click **External User Access**.</span></span>

4.  <span data-ttu-id="b65eb-114">单击 "**联盟域**"，单击 "**新建**"，然后单击 "**阻止的域**"。</span><span class="sxs-lookup"><span data-stu-id="b65eb-114">Click **Federated Domains**, click **New**, and then click **Blocked domain**.</span></span>

5.  <span data-ttu-id="b65eb-115">在**新的联盟域**中，执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="b65eb-115">In **New Federated Domains**, do the following:</span></span>
    
      - <span data-ttu-id="b65eb-116">在 "**域名（或 FQDN）**" 中，键入要阻止的联盟伙伴域的名称。</span><span class="sxs-lookup"><span data-stu-id="b65eb-116">In **Domain name (or FQDN)**, type the name of the federated partner domain that you want to block.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="b65eb-117">名称长度不能超过256个字符。</span><span class="sxs-lookup"><span data-stu-id="b65eb-117">The name cannot exceed 256 characters in length.</span></span><BR><span data-ttu-id="b65eb-118">"联盟伙伴" 域名上的搜索执行后缀匹配。</span><span class="sxs-lookup"><span data-stu-id="b65eb-118">The search on the federated partner domain name performs a suffix match.</span></span> <span data-ttu-id="b65eb-119">例如，如果您键入 " <STRONG>contoso.com</STRONG>"，搜索也将返回域<STRONG>it.contoso.com</STRONG>。</span><span class="sxs-lookup"><span data-stu-id="b65eb-119">For example, if you type <STRONG>contoso.com</STRONG>, the search will also return the domain <STRONG>it.contoso.com</STRONG>.</span></span><BR><span data-ttu-id="b65eb-120">联盟伙伴域不能同时被阻止和允许。</span><span class="sxs-lookup"><span data-stu-id="b65eb-120">A federated partner domain cannot simultaneously be blocked and allowed.</span></span> <span data-ttu-id="b65eb-121">Lync Server 2013 阻止这种情况，因此您不必同步您的列表。</span><span class="sxs-lookup"><span data-stu-id="b65eb-121">Lync Server 2013 prevents this from happening so that you do not have to synch up your lists.</span></span>

        
        </div>
    
      - <span data-ttu-id="b65eb-122">可选在 "**批注**" 中，键入要与其他系统管理员共享的有关此配置的信息。</span><span class="sxs-lookup"><span data-stu-id="b65eb-122">(Optional) In **Comment**, type information that you want to share with other system administrators about this configuration.</span></span>

6.  <span data-ttu-id="b65eb-123">单击“**提交**”。</span><span class="sxs-lookup"><span data-stu-id="b65eb-123">Click **Commit**.</span></span>

7.  <span data-ttu-id="b65eb-124">对要阻止的每个联盟伙伴重复步骤4到步骤6。</span><span class="sxs-lookup"><span data-stu-id="b65eb-124">Repeat steps 4 through 6 for each federated partner that you want to block.</span></span>

<span data-ttu-id="b65eb-125">若要启用联盟用户访问，还必须启用组织中的联合用户访问支持。</span><span class="sxs-lookup"><span data-stu-id="b65eb-125">To enable federated user access, you must also enable support for federated user access in your organization.</span></span> <span data-ttu-id="b65eb-126">有关详细信息，请参阅[在 Lync Server 2013 中启用或禁用远程用户访问](lync-server-2013-enable-or-disable-remote-user-access.md)。</span><span class="sxs-lookup"><span data-stu-id="b65eb-126">For details, see [Enable or disable remote user access in Lync Server 2013](lync-server-2013-enable-or-disable-remote-user-access.md).</span></span>

<span data-ttu-id="b65eb-127">此外，你必须配置策略并将其应用到你希望能够与联盟用户协作的用户。</span><span class="sxs-lookup"><span data-stu-id="b65eb-127">Additionally, you must configure and apply the policy to users that you want to be able to collaborate with federated users.</span></span> <span data-ttu-id="b65eb-128">有关详细信息，请参阅[在 Lync Server 2013 中配置用于控制联盟用户访问的策略](lync-server-2013-configure-policies-to-control-federated-user-access.md)。</span><span class="sxs-lookup"><span data-stu-id="b65eb-128">For details, see [Configure policies to control federated user access in Lync Server 2013](lync-server-2013-configure-policies-to-control-federated-user-access.md).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>


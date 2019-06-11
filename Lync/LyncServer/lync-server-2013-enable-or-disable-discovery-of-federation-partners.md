---
title: Lync Server 2013：启用或禁用联盟伙伴发现
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Enable or disable discovery of federation partners
ms:assetid: 91fd036b-b1af-47cf-b1cf-0aa0a783c2aa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182550(v=OCS.15)
ms:contentKeyID: 48184857
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7e83f261fe6fa3ece259518b7730239adf20944c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34830304"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enable-or-disable-discovery-of-federation-partners-in-lync-server-2013"></a><span data-ttu-id="e78f4-102">在 Lync Server 2013 中启用或禁用联盟伙伴发现</span><span class="sxs-lookup"><span data-stu-id="e78f4-102">Enable or disable discovery of federation partners in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e78f4-103">_**主题上次修改时间:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="e78f4-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="e78f4-104">在部署你的边缘服务器并为你的组织启用联盟时, 你应该已指定是否支持联盟伙伴域的自动发现。</span><span class="sxs-lookup"><span data-stu-id="e78f4-104">At the time you deployed your Edge Servers and enabled federation for your organization, you should have specified whether to support automatic discovery of federated partner domains.</span></span> <span data-ttu-id="e78f4-105">使用本主题中的过程更改该配置。</span><span class="sxs-lookup"><span data-stu-id="e78f4-105">Use the procedure in this topic to change that configuration.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="e78f4-106">以下过程假定你已为你的组织启用联盟。</span><span class="sxs-lookup"><span data-stu-id="e78f4-106">The following procedure assumes that you have already enabled federation for your organization.</span></span> <span data-ttu-id="e78f4-107">有关启用联盟的详细信息, 请参阅在部署文档或操作文档中<A href="lync-server-2013-enable-or-disable-remote-user-access.md">启用或禁用 Lync Server 2013 中的远程用户访问</A>。</span><span class="sxs-lookup"><span data-stu-id="e78f4-107">For details about enabling federation, see <A href="lync-server-2013-enable-or-disable-remote-user-access.md">Enable or disable remote user access in Lync Server 2013</A> in the Deployment documentation or the Operations documentation.</span></span>



</div>

<div>

## <a name="to-enable-or-disable-automatic-discovery-of-federated-domains-for-your-organization"></a><span data-ttu-id="e78f4-108">为你的组织启用或禁用自动发现联盟域</span><span class="sxs-lookup"><span data-stu-id="e78f4-108">To enable or disable automatic discovery of federated domains for your organization</span></span>

1.  <span data-ttu-id="e78f4-109">使用 RTCUniversalServerAdmins 组成员（或具有同等用户权限）的用户帐户，或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="e78f4-109">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="e78f4-110">打开一个浏览器窗口, 然后输入 "管理员" URL 以打开 Lync Server "控制面板"。</span><span class="sxs-lookup"><span data-stu-id="e78f4-110">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="e78f4-111">有关可用于启动 Lync Server "控制面板" 的不同方法的详细信息, 请参阅[打开 Lync server 2013 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="e78f4-111">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="e78f4-112">在左侧导航栏中, 单击 "**外部用户访问**", 然后单击 "**访问边缘配置**"。</span><span class="sxs-lookup"><span data-stu-id="e78f4-112">In the left navigation bar, click **External User Access**, click **Access Edge Configuration**.</span></span>

4.  <span data-ttu-id="e78f4-113">在 "**访问边缘配置**" 页面上, 单击 "**全局**", 单击 "**编辑**", 然后单击 "**显示详细信息**"。</span><span class="sxs-lookup"><span data-stu-id="e78f4-113">On the **Access Edge Configuration** page, click **Global**, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="e78f4-114">在 "**编辑访问边缘配置**" 下的 "**启用与联盟用户的通信**" 下, 选中或清除 "**启用合作伙伴域发现**" 复选框以启用或禁用自动发现合作伙伴域。</span><span class="sxs-lookup"><span data-stu-id="e78f4-114">In **Edit Access Edge Configuration**, under **Enable communications with federated users**, select or clear the **Enable partner domain discovery** check box to enable or disable automatic discovery of partner domains.</span></span>

6.  <span data-ttu-id="e78f4-115">单击“**提交**”。</span><span class="sxs-lookup"><span data-stu-id="e78f4-115">Click **Commit**.</span></span>

<span data-ttu-id="e78f4-116">若要使联盟用户能够与 Lync Server 部署中的用户进行协作, 你必须同时配置了至少一个外部访问策略来支持联合用户访问。</span><span class="sxs-lookup"><span data-stu-id="e78f4-116">To enable federated users to collaborate with users in your Lync Server deployment, you must have also configured at least one external access policy to support federated user access.</span></span> <span data-ttu-id="e78f4-117">有关详细信息, 请参阅在部署文档或操作文档中[启用或禁用 Lync Server 2013 中的联盟和公共 IM 连接](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md)。</span><span class="sxs-lookup"><span data-stu-id="e78f4-117">For details, see [Enable or disable federation and public IM connectivity in Lync Server 2013](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md) in the Deployment documentation or the Operations documentation.</span></span> <span data-ttu-id="e78f4-118">有关控制特定联盟域的访问权限的详细信息, 请参阅[在 lync server 2013 中管理您的组织的 sip 联盟域](lync-server-2013-manage-sip-federated-domains-for-your-organization.md)、[管理您的组织在 lync server 2013 中的 sip 联合提供商](lync-server-2013-manage-sip-federated-providers-for-your-organization.md)和[管理 XMPPLync Server 2013 中的联盟合作伙伴](lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md)在操作文档中。</span><span class="sxs-lookup"><span data-stu-id="e78f4-118">For details about controlling access for specific federated domains, see [Manage SIP federated domains for your organization in Lync Server 2013](lync-server-2013-manage-sip-federated-domains-for-your-organization.md), [Manage SIP federated providers for your organization in Lync Server 2013](lync-server-2013-manage-sip-federated-providers-for-your-organization.md) and [Manage XMPP federated partners in Lync Server 2013](lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md) in the Operations documentation.</span></span>

</div>

<div>

## <a name="enabling-or-disabling-discovery-of-federation-partners-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="e78f4-119">使用 Windows PowerShell Cmdlet 启用或禁用联合身份验证合作伙伴的发现</span><span class="sxs-lookup"><span data-stu-id="e78f4-119">Enabling or Disabling Discovery of Federation Partners by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="e78f4-120">可使用 Windows PowerShell 和 CsAccessEdgeConfiguration cmdlet 管理联合身份验证合作伙伴的发现。</span><span class="sxs-lookup"><span data-stu-id="e78f4-120">Discovery of federation partners can be managed by using Windows PowerShell and the Set-CsAccessEdgeConfiguration cmdlet.</span></span> <span data-ttu-id="e78f4-121">此 cmdlet 既可以从 Lync Server 2013 管理外壳运行, 也可以从 Windows PowerShell 的远程会话运行。</span><span class="sxs-lookup"><span data-stu-id="e78f4-121">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="e78f4-122">有关使用远程 Windows PowerShell 连接到 Lync Server 的详细信息, 请参阅 Lync Server Windows PowerShell 博客文章 "快速入门: 使用远程 PowerShell 管理 Microsoft Lync Server 2010" [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)。</span><span class="sxs-lookup"><span data-stu-id="e78f4-122">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-enable-discovery-of-federation-partners"></a><span data-ttu-id="e78f4-123">启用联合合作伙伴的发现</span><span class="sxs-lookup"><span data-stu-id="e78f4-123">To enable discovery of federation partners</span></span>

  - <span data-ttu-id="e78f4-124">若要启用联合合作伙伴的发现, 请将**EnablePartnerDiscovery**属性的值设置为 True ($True)。</span><span class="sxs-lookup"><span data-stu-id="e78f4-124">To enable discovery of federation partners, set the value of the **EnablePartnerDiscovery** property to True ($True).</span></span> <span data-ttu-id="e78f4-125">请注意, 必须启用 DNS SRV 路由才能更改此属性值。</span><span class="sxs-lookup"><span data-stu-id="e78f4-125">Note that you must enable DNS SRV routing in order to change this property value.</span></span>
    
        Set-CsAccessEdgeConfiguration -UseDnsSrvRouting -EnablePartnerDiscovery $True

</div>

<div>

## <a name="to-disable-discovery-of-federation-partners"></a><span data-ttu-id="e78f4-126">禁用联盟伙伴的发现</span><span class="sxs-lookup"><span data-stu-id="e78f4-126">To disable discovery of federation partners</span></span>

  - <span data-ttu-id="e78f4-127">若要禁用联盟伙伴的发现, 请将**EnablePartnerDiscovery**属性的值设置为 False ($False):</span><span class="sxs-lookup"><span data-stu-id="e78f4-127">To disable discovery of federation partners, set the value of the **EnablePartnerDiscovery** property to False ($False):</span></span>
    
        Set-CsAccessEdgeConfiguration -UseDnsSrvRouting -EnablePartnerDiscovery $False

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>


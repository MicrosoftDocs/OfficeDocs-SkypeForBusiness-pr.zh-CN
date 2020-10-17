---
title: Lync Server 2013：启用或禁用联合合作伙伴的发现
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enable or disable discovery of federation partners
ms:assetid: 91fd036b-b1af-47cf-b1cf-0aa0a783c2aa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182550(v=OCS.15)
ms:contentKeyID: 48184857
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ff9fb4e0b243cc1ce9b51deac1c4021f9b3dff56
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48526819"
---
# <a name="enable-or-disable-discovery-of-federation-partners-in-lync-server-2013"></a><span data-ttu-id="f2b42-102">在 Lync Server 2013 中启用或禁用联盟伙伴发现</span><span class="sxs-lookup"><span data-stu-id="f2b42-102">Enable or disable discovery of federation partners in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f2b42-103">_**上次修改的主题：** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="f2b42-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="f2b42-p101">在部署边缘服务器并为组织启用联盟时，应该已经指定了是否支持自动发现联盟伙伴域。使用本主题中的过程更改此配置。</span><span class="sxs-lookup"><span data-stu-id="f2b42-p101">At the time you deployed your Edge Servers and enabled federation for your organization, you should have specified whether to support automatic discovery of federated partner domains. Use the procedure in this topic to change that configuration.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="f2b42-106">以下过程假定您已为组织启用联盟。</span><span class="sxs-lookup"><span data-stu-id="f2b42-106">The following procedure assumes that you have already enabled federation for your organization.</span></span> <span data-ttu-id="f2b42-107">有关启用联合的详细信息，请参阅部署文档或操作文档中的在 <A href="lync-server-2013-enable-or-disable-remote-user-access.md">Lync Server 2013 中启用或禁用远程用户访问</A> 。</span><span class="sxs-lookup"><span data-stu-id="f2b42-107">For details about enabling federation, see <A href="lync-server-2013-enable-or-disable-remote-user-access.md">Enable or disable remote user access in Lync Server 2013</A> in the Deployment documentation or the Operations documentation.</span></span>



</div>

<div>

## <a name="to-enable-or-disable-automatic-discovery-of-federated-domains-for-your-organization"></a><span data-ttu-id="f2b42-108">为组织启用或禁用自动发现联盟域</span><span class="sxs-lookup"><span data-stu-id="f2b42-108">To enable or disable automatic discovery of federated domains for your organization</span></span>

1.  <span data-ttu-id="f2b42-109">从作为 RTCUniversalServerAdmins 组成员的用户帐户 (或具有等效的用户权限) 或分配给 CsAdministrator 角色，请登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="f2b42-109">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="f2b42-110">打开浏览器窗口，然后输入管理员 URL 以打开 "Lync Server 控制面板"。</span><span class="sxs-lookup"><span data-stu-id="f2b42-110">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="f2b42-111">有关可用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅 [Open Lync server 2013 "管理工具](lync-server-2013-open-lync-server-administrative-tools.md)"。</span><span class="sxs-lookup"><span data-stu-id="f2b42-111">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="f2b42-112">在左侧导航栏中，单击“外部用户访问”\*\*\*\*，然后单击“访问边缘配置”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="f2b42-112">In the left navigation bar, click **External User Access**, click **Access Edge Configuration**.</span></span>

4.  <span data-ttu-id="f2b42-113">在“访问边缘配置”\*\*\*\* 页上，单击“全局”\*\*\*\*，再单击“编辑”\*\*\*\*，然后单击“显示详细信息”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="f2b42-113">On the **Access Edge Configuration** page, click **Global**, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="f2b42-114">在“编辑访问边缘配置”\*\*\*\* 的“启用与联盟用户的通信”\*\*\*\* 下，选中或清除“启用伙伴域发现”\*\*\*\* 复选框以启用或禁用自动发现伙伴域。</span><span class="sxs-lookup"><span data-stu-id="f2b42-114">In **Edit Access Edge Configuration**, under **Enable communications with federated users**, select or clear the **Enable partner domain discovery** check box to enable or disable automatic discovery of partner domains.</span></span>

6.  <span data-ttu-id="f2b42-115">单击“提交”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="f2b42-115">Click **Commit**.</span></span>

<span data-ttu-id="f2b42-116">若要使联合用户能够与 Lync Server 部署中的用户进行协作，您还必须至少配置一个外部访问策略以支持联合用户访问。</span><span class="sxs-lookup"><span data-stu-id="f2b42-116">To enable federated users to collaborate with users in your Lync Server deployment, you must have also configured at least one external access policy to support federated user access.</span></span> <span data-ttu-id="f2b42-117">有关详细信息，请参阅部署文档或操作文档中的 [在 Lync Server 2013 中启用或禁用联盟和公共 IM 连接](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md) 。</span><span class="sxs-lookup"><span data-stu-id="f2b42-117">For details, see [Enable or disable federation and public IM connectivity in Lync Server 2013](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md) in the Deployment documentation or the Operations documentation.</span></span> <span data-ttu-id="f2b42-118">有关控制对特定联盟域的访问权限的详细信息，请参阅在 lync server [2013 中管理组织的 sip 联盟域](lync-server-2013-manage-sip-federated-domains-for-your-organization.md)、 [在 lync server 2013 中管理组织的 sip 联盟提供程序](lync-server-2013-manage-sip-federated-providers-for-your-organization.md) 和在操作文档中 [管理 LYNC server 2013 中的 XMPP 联盟伙伴](lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md) 。</span><span class="sxs-lookup"><span data-stu-id="f2b42-118">For details about controlling access for specific federated domains, see [Manage SIP federated domains for your organization in Lync Server 2013](lync-server-2013-manage-sip-federated-domains-for-your-organization.md), [Manage SIP federated providers for your organization in Lync Server 2013](lync-server-2013-manage-sip-federated-providers-for-your-organization.md) and [Manage XMPP federated partners in Lync Server 2013](lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md) in the Operations documentation.</span></span>

</div>

<div>

## <a name="enabling-or-disabling-discovery-of-federation-partners-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="f2b42-119">使用 Windows PowerShell Cmdlet 启用或禁用联盟伙伴发现</span><span class="sxs-lookup"><span data-stu-id="f2b42-119">Enabling or Disabling Discovery of Federation Partners by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="f2b42-120">可以使用 Windows PowerShell 和 Set-CsAccessEdgeConfiguration cmdlet 来管理联合合作伙伴的发现。</span><span class="sxs-lookup"><span data-stu-id="f2b42-120">Discovery of federation partners can be managed by using Windows PowerShell and the Set-CsAccessEdgeConfiguration cmdlet.</span></span> <span data-ttu-id="f2b42-121">此 cmdlet 可从 Lync Server 2013 命令行管理程序或从 Windows PowerShell 的远程会话中运行。</span><span class="sxs-lookup"><span data-stu-id="f2b42-121">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="f2b42-122">有关使用远程 Windows PowerShell 连接到 Lync Server 的详细信息，请参阅在上的 Lync Server Windows PowerShell 博客文章 "快速入门：使用远程 PowerShell 管理 Microsoft Lync Server 2010" [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) 。</span><span class="sxs-lookup"><span data-stu-id="f2b42-122">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-enable-discovery-of-federation-partners"></a><span data-ttu-id="f2b42-123">启用联合合作伙伴的发现</span><span class="sxs-lookup"><span data-stu-id="f2b42-123">To enable discovery of federation partners</span></span>

  - <span data-ttu-id="f2b42-p106">要启用联盟伙伴的发现，请将 **EnablePartnerDiscovery** 属性的值设置为 True ($True)。请注意，必须启用 DNS SRV 路由才能更改此属性值。</span><span class="sxs-lookup"><span data-stu-id="f2b42-p106">To enable discovery of federation partners, set the value of the **EnablePartnerDiscovery** property to True ($True). Note that you must enable DNS SRV routing in order to change this property value.</span></span>
    
        Set-CsAccessEdgeConfiguration -UseDnsSrvRouting -EnablePartnerDiscovery $True

</div>

<div>

## <a name="to-disable-discovery-of-federation-partners"></a><span data-ttu-id="f2b42-126">禁用联合合作伙伴的发现</span><span class="sxs-lookup"><span data-stu-id="f2b42-126">To disable discovery of federation partners</span></span>

  - <span data-ttu-id="f2b42-127">要禁用联盟伙伴的发现，请将 **EnablePartnerDiscovery** 属性的值设置为 False ($False)：</span><span class="sxs-lookup"><span data-stu-id="f2b42-127">To disable discovery of federation partners, set the value of the **EnablePartnerDiscovery** property to False ($False):</span></span>
    
        Set-CsAccessEdgeConfiguration -UseDnsSrvRouting -EnablePartnerDiscovery $False

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>


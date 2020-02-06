---
title: 启用或禁用联盟伙伴发现
ms.reviewer: ''
ms:assetid: 91fd036b-b1af-47cf-b1cf-0aa0a783c2aa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182550(v=OCS.15)
ms:contentKeyID: 48184857
mtps_version: v=OCS.15
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 在部署你的边缘服务器并为你的组织启用联盟时，你应该已指定是否支持联盟伙伴域的自动发现。
ms.openlocfilehash: a64e2056feacbee076fcaf9b0012a36f72c91523
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818393"
---
# <a name="enable-or-disable-discovery-of-federation-partners-in-skype-for-business-server"></a><span data-ttu-id="854b3-103">在 Skype for Business 服务器中启用或禁用联盟合作伙伴的发现</span><span class="sxs-lookup"><span data-stu-id="854b3-103">Enable or disable discovery of federation partners in Skype for Business Server</span></span>

<span data-ttu-id="854b3-104">在部署你的边缘服务器并为你的组织启用联盟时，你应该已指定是否支持联盟伙伴域的自动发现。</span><span class="sxs-lookup"><span data-stu-id="854b3-104">At the time you deployed your Edge Servers and enabled federation for your organization, you should have specified whether to support automatic discovery of federated partner domains.</span></span> <span data-ttu-id="854b3-105">使用本主题中的过程更改该配置。</span><span class="sxs-lookup"><span data-stu-id="854b3-105">Use the procedure in this topic to change that configuration.</span></span>

> [!NOTE]  
> <span data-ttu-id="854b3-106">以下过程假定你已为你的组织启用联盟。</span><span class="sxs-lookup"><span data-stu-id="854b3-106">The following procedure assumes that you have already enabled federation for your organization.</span></span> <span data-ttu-id="854b3-107">有关启用联盟的详细信息，请参阅[启用或禁用远程用户访问](enable-or-disable-remote-user-access.md)。</span><span class="sxs-lookup"><span data-stu-id="854b3-107">For details about enabling federation, see [Enable or disable remote user access](enable-or-disable-remote-user-access.md).</span></span>

## <a name="to-enable-or-disable-automatic-discovery-of-federated-domains-for-your-organization"></a><span data-ttu-id="854b3-108">为你的组织启用或禁用自动发现联盟域</span><span class="sxs-lookup"><span data-stu-id="854b3-108">To enable or disable automatic discovery of federated domains for your organization</span></span>

1.  <span data-ttu-id="854b3-109">使用 RTCUniversalServerAdmins 组成员（或具有同等用户权限）的用户帐户，或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="854b3-109">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="854b3-110">打开一个浏览器窗口，然后输入管理员 URL 以打开 Skype for Business 服务器控制面板。</span><span class="sxs-lookup"><span data-stu-id="854b3-110">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>

3.  <span data-ttu-id="854b3-111">在左侧导航栏中，单击 "**外部用户访问**"，然后单击 "**访问边缘配置**"。</span><span class="sxs-lookup"><span data-stu-id="854b3-111">In the left navigation bar, click **External User Access**, click **Access Edge Configuration**.</span></span>

4.  <span data-ttu-id="854b3-112">在 "**访问边缘配置**" 页面上，单击 "**全局**"，单击 "**编辑**"，然后单击 "**显示详细信息**"。</span><span class="sxs-lookup"><span data-stu-id="854b3-112">On the **Access Edge Configuration** page, click **Global**, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="854b3-113">在 "**编辑访问边缘配置**" 下的 "**启用与联盟用户的通信**" 下，选中或清除 "**启用合作伙伴域发现**" 复选框以启用或禁用自动发现合作伙伴域。</span><span class="sxs-lookup"><span data-stu-id="854b3-113">In **Edit Access Edge Configuration**, under **Enable communications with federated users**, select or clear the **Enable partner domain discovery** check box to enable or disable automatic discovery of partner domains.</span></span>

6.  <span data-ttu-id="854b3-114">单击“**提交**”。</span><span class="sxs-lookup"><span data-stu-id="854b3-114">Click **Commit**.</span></span>

<span data-ttu-id="854b3-115">若要使联盟用户能够与 Skype for Business Server 部署中的用户进行协作，你必须也配置了至少一个外部访问策略来支持联合用户访问。</span><span class="sxs-lookup"><span data-stu-id="854b3-115">To enable federated users to collaborate with users in your Skype for Business Server deployment, you must have also configured at least one external access policy to support federated user access.</span></span> <span data-ttu-id="854b3-116">有关详细信息，请参阅[启用或禁用联盟和公用 IM 连接](enable-or-disable-federation-and-public-im-connectivity.md)。</span><span class="sxs-lookup"><span data-stu-id="854b3-116">For details, see [Enable or disable federation and public IM connectivity](enable-or-disable-federation-and-public-im-connectivity.md).</span></span> <span data-ttu-id="854b3-117">有关控制特定联盟域的访问权限的详细信息，请参阅[管理 sip 联合域](../sip-domains/manage-sip-federated-domains-for-your-organization.md)和[管理 sip 联合提供程序](../sip-providers/manage-sip-federated-providers-for-your-organization.md)。</span><span class="sxs-lookup"><span data-stu-id="854b3-117">For details about controlling access for specific federated domains, see [Manage SIP federated domains](../sip-domains/manage-sip-federated-domains-for-your-organization.md) and [Manage SIP federated providers](../sip-providers/manage-sip-federated-providers-for-your-organization.md).</span></span>


## <a name="enabling-or-disabling-discovery-of-federation-partners-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="854b3-118">使用 Windows PowerShell cmdlet 启用或禁用联合身份验证合作伙伴的发现</span><span class="sxs-lookup"><span data-stu-id="854b3-118">Enabling or disabling discovery of federation partners by using Windows PowerShell cmdlets</span></span>

<span data-ttu-id="854b3-119">可使用 Windows PowerShell 和 CsAccessEdgeConfiguration cmdlet 管理联合身份验证合作伙伴的发现。</span><span class="sxs-lookup"><span data-stu-id="854b3-119">Discovery of federation partners can be managed by using Windows PowerShell and the Set-CsAccessEdgeConfiguration cmdlet.</span></span> <span data-ttu-id="854b3-120">此 cmdlet 既可以从 Skype for Business 服务器管理外壳运行，也可以从 Windows PowerShell 的远程会话运行。</span><span class="sxs-lookup"><span data-stu-id="854b3-120">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 


## <a name="to-enable-discovery-of-federation-partners"></a><span data-ttu-id="854b3-121">启用联合合作伙伴的发现</span><span class="sxs-lookup"><span data-stu-id="854b3-121">To enable discovery of federation partners</span></span>

  - <span data-ttu-id="854b3-122">若要启用联合合作伙伴的发现，请将**EnablePartnerDiscovery**属性的值设置为 True （$True）。</span><span class="sxs-lookup"><span data-stu-id="854b3-122">To enable discovery of federation partners, set the value of the **EnablePartnerDiscovery** property to True ($True).</span></span> <span data-ttu-id="854b3-123">请注意，必须启用 DNS SRV 路由才能更改此属性值。</span><span class="sxs-lookup"><span data-stu-id="854b3-123">Note that you must enable DNS SRV routing in order to change this property value.</span></span>
    
        Set-CsAccessEdgeConfiguration -UseDnsSrvRouting -EnablePartnerDiscovery $True


## <a name="to-disable-discovery-of-federation-partners"></a><span data-ttu-id="854b3-124">禁用联盟伙伴的发现</span><span class="sxs-lookup"><span data-stu-id="854b3-124">To disable discovery of federation partners</span></span>

  - <span data-ttu-id="854b3-125">若要禁用联盟伙伴的发现，请将**EnablePartnerDiscovery**属性的值设置为 False （$False）：</span><span class="sxs-lookup"><span data-stu-id="854b3-125">To disable discovery of federation partners, set the value of the **EnablePartnerDiscovery** property to False ($False):</span></span>
    
        Set-CsAccessEdgeConfiguration -UseDnsSrvRouting -EnablePartnerDiscovery $False


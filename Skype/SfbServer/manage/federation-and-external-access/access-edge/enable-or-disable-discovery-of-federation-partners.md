---
title: 启用或禁用联盟伙伴发现
ms.reviewer: ''
ms:assetid: 91fd036b-b1af-47cf-b1cf-0aa0a783c2aa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182550(v=OCS.15)
ms:contentKeyID: 48184857
mtps_version: v=OCS.15
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 次部署边缘服务器和启用联盟组织中，您应指定是否支持自动发现联盟的伙伴域。
ms.openlocfilehash: de61d8180a8f4e8f8be13abaab3d8911d2c6e22c
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32199939"
---
# <a name="enable-or-disable-discovery-of-federation-partners-in-skype-for-business-server"></a><span data-ttu-id="dc84c-103">启用或禁用业务服务器中 Skype 的联盟伙伴的发现</span><span class="sxs-lookup"><span data-stu-id="dc84c-103">Enable or disable discovery of federation partners in Skype for Business Server</span></span>

<span data-ttu-id="dc84c-104">次部署边缘服务器和启用联盟组织中，您应指定是否支持自动发现联盟的伙伴域。</span><span class="sxs-lookup"><span data-stu-id="dc84c-104">At the time you deployed your Edge Servers and enabled federation for your organization, you should have specified whether to support automatic discovery of federated partner domains.</span></span> <span data-ttu-id="dc84c-105">使用本主题中的过程来更改的配置。</span><span class="sxs-lookup"><span data-stu-id="dc84c-105">Use the procedure in this topic to change that configuration.</span></span>

> [!NOTE]  
> <span data-ttu-id="dc84c-106">下面的过程假定您已为您的组织中启用了联盟。</span><span class="sxs-lookup"><span data-stu-id="dc84c-106">The following procedure assumes that you have already enabled federation for your organization.</span></span> <span data-ttu-id="dc84c-107">有关启用联合身份验证的详细信息，请参阅[启用或禁用远程用户访问](enable-or-disable-remote-user-access.md)。</span><span class="sxs-lookup"><span data-stu-id="dc84c-107">For details about enabling federation, see [Enable or disable remote user access](enable-or-disable-remote-user-access.md).</span></span>

## <a name="to-enable-or-disable-automatic-discovery-of-federated-domains-for-your-organization"></a><span data-ttu-id="dc84c-108">启用或禁用组织的联合域的自动发现</span><span class="sxs-lookup"><span data-stu-id="dc84c-108">To enable or disable automatic discovery of federated domains for your organization</span></span>

1.  <span data-ttu-id="dc84c-109">使用 RTCUniversalServerAdmins 组成员（或具有同等用户权限）的用户帐户，或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="dc84c-109">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="dc84c-110">打开一个浏览器窗口，然后输入管理 URL 以打开 Skype 业务 Server Control Panel。</span><span class="sxs-lookup"><span data-stu-id="dc84c-110">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>

3.  <span data-ttu-id="dc84c-111">在左侧的导航栏中，单击**外部用户访问**，单击**访问边缘配置**。</span><span class="sxs-lookup"><span data-stu-id="dc84c-111">In the left navigation bar, click **External User Access**, click **Access Edge Configuration**.</span></span>

4.  <span data-ttu-id="dc84c-112">在**访问边缘配置**页上，单击**全局**，单击**编辑**，然后单击**显示详细信息**。</span><span class="sxs-lookup"><span data-stu-id="dc84c-112">On the **Access Edge Configuration** page, click **Global**, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="dc84c-113">在**编辑访问边缘配置**下**启用与联盟用户的通信**，请选中或清除**启用伙伴域发现**复选框以启用或禁用自动发现的伙伴域。</span><span class="sxs-lookup"><span data-stu-id="dc84c-113">In **Edit Access Edge Configuration**, under **Enable communications with federated users**, select or clear the **Enable partner domain discovery** check box to enable or disable automatic discovery of partner domains.</span></span>

6.  <span data-ttu-id="dc84c-114">单击“**提交**”。</span><span class="sxs-lookup"><span data-stu-id="dc84c-114">Click **Commit**.</span></span>

<span data-ttu-id="dc84c-115">若要启用联盟的用户与您 Skype 业务服务器部署中的用户进行协作，您必须还配置至少一个外部访问策略以支持联盟的用户访问。</span><span class="sxs-lookup"><span data-stu-id="dc84c-115">To enable federated users to collaborate with users in your Skype for Business Server deployment, you must have also configured at least one external access policy to support federated user access.</span></span> <span data-ttu-id="dc84c-116">有关详细信息，请参阅[启用或禁用联盟和公共 IM 连接](enable-or-disable-federation-and-public-im-connectivity.md)。</span><span class="sxs-lookup"><span data-stu-id="dc84c-116">For details, see [Enable or disable federation and public IM connectivity](enable-or-disable-federation-and-public-im-connectivity.md).</span></span> <span data-ttu-id="dc84c-117">有关控制对特定联盟域访问的详细信息，请参阅[管理 SIP 联盟域](../sip-domains/manage-sip-federated-domains-for-your-organization.md)和[管理 SIP 联盟提供商](../sip-providers/manage-sip-federated-providers-for-your-organization.md)。</span><span class="sxs-lookup"><span data-stu-id="dc84c-117">For details about controlling access for specific federated domains, see [Manage SIP federated domains](../sip-domains/manage-sip-federated-domains-for-your-organization.md) and [Manage SIP federated providers](../sip-providers/manage-sip-federated-providers-for-your-organization.md).</span></span>


## <a name="enabling-or-disabling-discovery-of-federation-partners-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="dc84c-118">启用或禁用联盟伙伴的发现，通过使用 Windows PowerShell cmdlet</span><span class="sxs-lookup"><span data-stu-id="dc84c-118">Enabling or disabling discovery of federation partners by using Windows PowerShell cmdlets</span></span>

<span data-ttu-id="dc84c-119">可以使用 Windows PowerShell 和 Set-csaccessedgeconfiguration cmdlet 来管理联盟伙伴的发现。</span><span class="sxs-lookup"><span data-stu-id="dc84c-119">Discovery of federation partners can be managed by using Windows PowerShell and the Set-CsAccessEdgeConfiguration cmdlet.</span></span> <span data-ttu-id="dc84c-120">从业务 Server 命令行管理程序 Skype 或 Windows PowerShell 远程会话，则可以运行此 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="dc84c-120">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 


## <a name="to-enable-discovery-of-federation-partners"></a><span data-ttu-id="dc84c-121">若要启用联盟伙伴的发现</span><span class="sxs-lookup"><span data-stu-id="dc84c-121">To enable discovery of federation partners</span></span>

  - <span data-ttu-id="dc84c-122">若要启用联盟伙伴的发现，设置为 True ($True)**将 EnablePartnerDiscovery**属性的值。</span><span class="sxs-lookup"><span data-stu-id="dc84c-122">To enable discovery of federation partners, set the value of the **EnablePartnerDiscovery** property to True ($True).</span></span> <span data-ttu-id="dc84c-123">请注意，您必须启用 DNS SRV 路由来更改此属性值。</span><span class="sxs-lookup"><span data-stu-id="dc84c-123">Note that you must enable DNS SRV routing in order to change this property value.</span></span>
    
        Set-CsAccessEdgeConfiguration -UseDnsSrvRouting -EnablePartnerDiscovery $True


## <a name="to-disable-discovery-of-federation-partners"></a><span data-ttu-id="dc84c-124">若要禁用联盟伙伴的发现</span><span class="sxs-lookup"><span data-stu-id="dc84c-124">To disable discovery of federation partners</span></span>

  - <span data-ttu-id="dc84c-125">若要禁用联盟伙伴的发现，设置为 False ($False)**将 EnablePartnerDiscovery**属性的值：</span><span class="sxs-lookup"><span data-stu-id="dc84c-125">To disable discovery of federation partners, set the value of the **EnablePartnerDiscovery** property to False ($False):</span></span>
    
        Set-CsAccessEdgeConfiguration -UseDnsSrvRouting -EnablePartnerDiscovery $False


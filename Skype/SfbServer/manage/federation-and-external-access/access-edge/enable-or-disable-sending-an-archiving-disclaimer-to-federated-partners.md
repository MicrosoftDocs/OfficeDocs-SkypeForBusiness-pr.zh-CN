---
title: 启用或禁用向联盟伙伴发送存档免责声明
ms.reviewer: ''
ms:assetid: c8e9a2fa-9dc1-4e4d-919f-56ece8004864
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182584(v=OCS.15)
ms:contentKeyID: 48185391
mtps_version: v=OCS.15
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: ''
ms.openlocfilehash: 2478d1f0a8b09fc8d2eff0f3131ad703a3bd72bb
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "33919526"
---
# <a name="enable-or-disable-sending-an-archiving-disclaimer-to-federated-partners-in-skype-for-business-server"></a><span data-ttu-id="3419b-102">启用或禁用业务服务器向 Skype 中的联盟伙伴发送存档免责声明</span><span class="sxs-lookup"><span data-stu-id="3419b-102">Enable or disable sending an Archiving disclaimer to federated partners in Skype for Business Server</span></span>

<span data-ttu-id="3419b-103">次部署边缘服务器和启用联盟组织中，您应具有指定是否自动向联盟伙伴发送存档免责声明。</span><span class="sxs-lookup"><span data-stu-id="3419b-103">At the time you deployed your Edge Servers and enabled federation for your organization, you should have specified whether to automatically send the archiving disclaimer to federated partners.</span></span> <span data-ttu-id="3419b-104">如果存档外部通信，您应启用发送存档免责声明。</span><span class="sxs-lookup"><span data-stu-id="3419b-104">If you archive external communications, you should enable the sending of an archiving disclaimer.</span></span> <span data-ttu-id="3419b-105">使用本主题中的过程来更改的配置。</span><span class="sxs-lookup"><span data-stu-id="3419b-105">Use the procedure in this topic to change that configuration.</span></span>

> [!NOTE]
> <span data-ttu-id="3419b-106">下面的过程假定您已为您的组织中启用了联盟。</span><span class="sxs-lookup"><span data-stu-id="3419b-106">The following procedure assumes that you have already enabled federation for your organization.</span></span> <span data-ttu-id="3419b-107">有关启用联合身份验证的详细信息，请参阅[启用或禁用远程用户访问](enable-or-disable-remote-user-access.md)。</span><span class="sxs-lookup"><span data-stu-id="3419b-107">For details about enabling federation, see [Enable or disable remote user access](enable-or-disable-remote-user-access.md).</span></span>


## <a name="to-enable-or-disable-sending-of-an-archiving-disclaimer-to-federated-partners"></a><span data-ttu-id="3419b-108">启用或禁用向联盟伙伴发送存档免责声明</span><span class="sxs-lookup"><span data-stu-id="3419b-108">To enable or disable sending of an archiving disclaimer to federated partners</span></span>

1.  <span data-ttu-id="3419b-109">使用 RTCUniversalServerAdmins 组成员（或具有同等用户权限）的用户帐户，或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="3419b-109">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="3419b-110">打开一个浏览器窗口，然后输入管理 URL 以打开 Skype 业务 Server Control Panel。</span><span class="sxs-lookup"><span data-stu-id="3419b-110">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="3419b-111">在左侧的导航栏中，单击**外部用户访问**，单击**访问边缘配置**。</span><span class="sxs-lookup"><span data-stu-id="3419b-111">In the left navigation bar, click **External User Access**, click **Access Edge Configuration**.</span></span>

4.  <span data-ttu-id="3419b-112">在“**访问边缘配置**”选项卡上，单击“**全局**”，再单击“**编辑**”，然后单击“**显示详细信息**”。</span><span class="sxs-lookup"><span data-stu-id="3419b-112">On the **Access Edge Configuration** tab, click **Global**, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="3419b-113">在**编辑访问边缘配置**下**启用与联盟用户的通信**，请选中或清除**向联盟伙伴发送存档免责声明**复选框以启用或禁用自动发送存档免责声明。</span><span class="sxs-lookup"><span data-stu-id="3419b-113">In **Edit Access Edge Configuration**, under **Enable communications with federated users**, select or clear the **Send archiving disclaimer to federated partners** check box to enable or disable automatically sending the archiving disclaimer.</span></span>

6.  <span data-ttu-id="3419b-114">单击“**提交**”。</span><span class="sxs-lookup"><span data-stu-id="3419b-114">Click **Commit**.</span></span>

<span data-ttu-id="3419b-115">若要启用联盟的用户与您 Skype 业务服务器部署中的用户进行协作，您必须还配置至少一个外部访问策略以支持联盟的用户访问。</span><span class="sxs-lookup"><span data-stu-id="3419b-115">To enable federated users to collaborate with users in your Skype for Business Server deployment, you must have also configured at least one external access policy to support federated user access.</span></span> <span data-ttu-id="3419b-116">有关控制对特定联盟域访问的详细信息，请参阅[支持的允许的外部域的配置](../sip-domains/manage-sip-federated-domains-for-your-organization.md#configure-support-for-allowed-external-domains-in-skype-for-business-server)。</span><span class="sxs-lookup"><span data-stu-id="3419b-116">For details about controlling access for specific federated domains, see [Configure support for allowed external domains](../sip-domains/manage-sip-federated-domains-for-your-organization.md#configure-support-for-allowed-external-domains-in-skype-for-business-server).</span></span>


## <a name="enabling-or-disabling-the-archiving-disclaimer-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="3419b-117">启用或禁用存档免责声明，通过使用 Windows PowerShell cmdlet</span><span class="sxs-lookup"><span data-stu-id="3419b-117">Enabling or disabling the archiving disclaimer by using Windows PowerShell cmdlets</span></span>

<span data-ttu-id="3419b-118">使用 Windows PowerShell 和 Set-csaccessedgeconfiguration cmdlet 可以管理存档免责声明的使用。</span><span class="sxs-lookup"><span data-stu-id="3419b-118">The use of the archiving disclaimer can be managed by using Windows PowerShell and the Set-CsAccessEdgeConfiguration cmdlet.</span></span> <span data-ttu-id="3419b-119">从业务 Server 命令行管理程序 Skype 或 Windows PowerShell 远程会话，则可以运行此 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="3419b-119">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 

## <a name="to-enable-the-archiving-disclaimer"></a><span data-ttu-id="3419b-120">若要启用存档免责声明</span><span class="sxs-lookup"><span data-stu-id="3419b-120">To enable the archiving disclaimer</span></span>

  - <span data-ttu-id="3419b-121">要启用存档免责声明，请将 **EnableArchivingDisclaimer** 属性的值设置为 True ($True)：</span><span class="sxs-lookup"><span data-stu-id="3419b-121">To enable the archiving disclaimer, set the value of the **EnableArchivingDisclaimer** property to True ($True):</span></span>
    
        Set-CsAccessEdgeConfiguration -EnableArchivingDisclaimer $True

## <a name="to-disable-the-archiving-disclaimer"></a><span data-ttu-id="3419b-122">若要禁用存档免责声明</span><span class="sxs-lookup"><span data-stu-id="3419b-122">To disable the archiving disclaimer</span></span>

  - <span data-ttu-id="3419b-123">要禁用存档免责声明，请将 **EnableArchivingDisclaimer** 属性的值设置为 False ($False)：</span><span class="sxs-lookup"><span data-stu-id="3419b-123">To disable the archiving disclaimer, set the value of the **EnableArchivingDisclaimer** property to False ($False):</span></span>
    
        Set-CsAccessEdgeConfiguration -EnableArchivingDisclaimer $False



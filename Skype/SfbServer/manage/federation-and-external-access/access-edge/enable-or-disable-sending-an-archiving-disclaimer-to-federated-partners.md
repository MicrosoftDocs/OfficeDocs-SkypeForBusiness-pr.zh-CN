---
title: 启用或禁用向联盟伙伴发送存档免责声明
ms.reviewer: ''
ms:assetid: c8e9a2fa-9dc1-4e4d-919f-56ece8004864
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182584(v=OCS.15)
ms:contentKeyID: 48185391
mtps_version: v=OCS.15
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: ''
ms.openlocfilehash: 1f0238e177e74dc1263208f9a6a350158825d825
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49817352"
---
# <a name="enable-or-disable-sending-an-archiving-disclaimer-to-federated-partners-in-skype-for-business-server"></a><span data-ttu-id="efa78-102">在 Skype for Business Server 中启用或禁用向联盟伙伴发送存档免责声明</span><span class="sxs-lookup"><span data-stu-id="efa78-102">Enable or disable sending an Archiving disclaimer to federated partners in Skype for Business Server</span></span>

<span data-ttu-id="efa78-p101">在部署边缘服务器并为组织启用联盟时，应该已经指定了是否自动向联盟伙伴发送存档免责声明。如果要对外部通信进行存档，应启用发送存档免责声明。使用本主题中的过程更改此配置。</span><span class="sxs-lookup"><span data-stu-id="efa78-p101">At the time you deployed your Edge Servers and enabled federation for your organization, you should have specified whether to automatically send the archiving disclaimer to federated partners. If you archive external communications, you should enable the sending of an archiving disclaimer. Use the procedure in this topic to change that configuration.</span></span>

> [!NOTE]
> <span data-ttu-id="efa78-106">以下过程假定您已为组织启用联盟。</span><span class="sxs-lookup"><span data-stu-id="efa78-106">The following procedure assumes that you have already enabled federation for your organization.</span></span> <span data-ttu-id="efa78-107">有关启用联盟的详细信息，请参阅["启用或禁用远程用户访问"。](enable-or-disable-remote-user-access.md)</span><span class="sxs-lookup"><span data-stu-id="efa78-107">For details about enabling federation, see [Enable or disable remote user access](enable-or-disable-remote-user-access.md).</span></span>


## <a name="to-enable-or-disable-sending-of-an-archiving-disclaimer-to-federated-partners"></a><span data-ttu-id="efa78-108">启用或禁用向联盟伙伴发送存档免责声明</span><span class="sxs-lookup"><span data-stu-id="efa78-108">To enable or disable sending of an archiving disclaimer to federated partners</span></span>

1.  <span data-ttu-id="efa78-109">从 RTCUniversalServerAdmins 组 (或具有同等用户权限) 或已分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任意计算机。</span><span class="sxs-lookup"><span data-stu-id="efa78-109">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="efa78-110">打开浏览器窗口，然后输入管理 URL 以打开 Skype for Business Server 控制面板。</span><span class="sxs-lookup"><span data-stu-id="efa78-110">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="efa78-111">在左侧导航栏中，单击“外部用户访问”，然后单击“访问边缘配置”。</span><span class="sxs-lookup"><span data-stu-id="efa78-111">In the left navigation bar, click **External User Access**, click **Access Edge Configuration**.</span></span>

4.  <span data-ttu-id="efa78-112">在“访问边缘配置”选项卡上，单击“全局”，再单击“编辑”，然后单击“显示详细信息”。</span><span class="sxs-lookup"><span data-stu-id="efa78-112">On the **Access Edge Configuration** tab, click **Global**, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="efa78-113">在“编辑访问边缘配置”的“启用与联盟用户的通信”下，选中或清除“向联盟伙伴发送存档免责声明”复选框以启用或禁用自动发送存档免责声明。</span><span class="sxs-lookup"><span data-stu-id="efa78-113">In **Edit Access Edge Configuration**, under **Enable communications with federated users**, select or clear the **Send archiving disclaimer to federated partners** check box to enable or disable automatically sending the archiving disclaimer.</span></span>

6.  <span data-ttu-id="efa78-114">单击“提交”。</span><span class="sxs-lookup"><span data-stu-id="efa78-114">Click **Commit**.</span></span>

<span data-ttu-id="efa78-115">若要使联盟用户能够与 Skype for Business Server 部署中的用户进行协作，还必须配置至少一个外部访问策略以支持联盟用户访问。</span><span class="sxs-lookup"><span data-stu-id="efa78-115">To enable federated users to collaborate with users in your Skype for Business Server deployment, you must have also configured at least one external access policy to support federated user access.</span></span> <span data-ttu-id="efa78-116">有关控制特定联盟域的访问的详细信息，请参阅配置 [对允许的外部域的支持](../sip-domains/manage-sip-federated-domains-for-your-organization.md#configure-support-for-allowed-external-domains-in-skype-for-business-server)。</span><span class="sxs-lookup"><span data-stu-id="efa78-116">For details about controlling access for specific federated domains, see [Configure support for allowed external domains](../sip-domains/manage-sip-federated-domains-for-your-organization.md#configure-support-for-allowed-external-domains-in-skype-for-business-server).</span></span>


## <a name="enabling-or-disabling-the-archiving-disclaimer-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="efa78-117">使用 cmdlet 启用或禁用Windows PowerShell免责声明</span><span class="sxs-lookup"><span data-stu-id="efa78-117">Enabling or disabling the archiving disclaimer by using Windows PowerShell cmdlets</span></span>

<span data-ttu-id="efa78-118">存档免责声明的使用可通过使用 Windows PowerShell 和 Set-CsAccessEdgeConfiguration cmdlet 进行管理。</span><span class="sxs-lookup"><span data-stu-id="efa78-118">The use of the archiving disclaimer can be managed by using Windows PowerShell and the Set-CsAccessEdgeConfiguration cmdlet.</span></span> <span data-ttu-id="efa78-119">此 cmdlet 可以从 Skype for Business Server 命令行管理程序运行，也可以从远程会话Windows PowerShell。</span><span class="sxs-lookup"><span data-stu-id="efa78-119">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 

## <a name="to-enable-the-archiving-disclaimer"></a><span data-ttu-id="efa78-120">启用存档免责声明</span><span class="sxs-lookup"><span data-stu-id="efa78-120">To enable the archiving disclaimer</span></span>

  - <span data-ttu-id="efa78-121">要启用存档免责声明，请将 **EnableArchivingDisclaimer** 属性的值设置为 True ($True)：</span><span class="sxs-lookup"><span data-stu-id="efa78-121">To enable the archiving disclaimer, set the value of the **EnableArchivingDisclaimer** property to True ($True):</span></span>
    
        Set-CsAccessEdgeConfiguration -EnableArchivingDisclaimer $True

## <a name="to-disable-the-archiving-disclaimer"></a><span data-ttu-id="efa78-122">禁用存档免责声明</span><span class="sxs-lookup"><span data-stu-id="efa78-122">To disable the archiving disclaimer</span></span>

  - <span data-ttu-id="efa78-123">要禁用存档免责声明，请将 **EnableArchivingDisclaimer** 属性的值设置为 False ($False)：</span><span class="sxs-lookup"><span data-stu-id="efa78-123">To disable the archiving disclaimer, set the value of the **EnableArchivingDisclaimer** property to False ($False):</span></span>
    
        Set-CsAccessEdgeConfiguration -EnableArchivingDisclaimer $False



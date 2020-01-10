---
title: 为 Skype for Business Server 中的外部用户配置存档免责声明
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 394ac291-05cd-4fa1-acb3-714af538b47f
description: 摘要：阅读本主题，了解如何配置 Skype for Business 服务器的存档免责声明。
ms.openlocfilehash: d6c08b6fe2eaa6c74231b96346661488c3f8e2b0
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/09/2020
ms.locfileid: "41001052"
---
# <a name="configure-archiving-disclaimers-for-external-users-in-skype-for-business-server"></a><span data-ttu-id="320e9-103">为 Skype for Business Server 中的外部用户配置存档免责声明</span><span class="sxs-lookup"><span data-stu-id="320e9-103">Configure archiving disclaimers for external users in Skype for Business Server</span></span>
 
<span data-ttu-id="320e9-104">**摘要：** 阅读本主题，了解如何配置 Skype for Business 服务器的存档免责声明。</span><span class="sxs-lookup"><span data-stu-id="320e9-104">**Summary:** Read this topic to learn how to configure an archiving disclaimer for Skype for Business Server.</span></span>
  
<span data-ttu-id="320e9-105">如果您的组织与外部合作伙伴通信，您需要让他们知道，您会存档与他们之间的通信。</span><span class="sxs-lookup"><span data-stu-id="320e9-105">If your organization communicates with external partners, you need to let them know that you are archiving communications with them.</span></span> <span data-ttu-id="320e9-106">当你部署边缘服务器并为你的组织启用联盟时，系统会询问你是否要将存档免责声明自动发送给外部合作伙伴。</span><span class="sxs-lookup"><span data-stu-id="320e9-106">When you deploy an Edge Server and enable federation for your organization, you are asked whether you want to automatically send an archiving disclaimer to external partners.</span></span> 
  
<span data-ttu-id="320e9-107">如果需要更改此配置，您可以使用 Skype for Business 服务器控制面板或 Windows PowerShell **CsAccessEdgeConfiguration** cmdlet。</span><span class="sxs-lookup"><span data-stu-id="320e9-107">If you need to change this configuration, you can use the Skype for Business Server Control Panel or the Windows PowerShell **Set-CsAccessEdgeConfiguration** cmdlet.</span></span> <span data-ttu-id="320e9-108">可以从 Skype for Business Server management shell 或 Windows PowerShell 的远程会话运行 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="320e9-108">Cmdlets can be run either from the Skype for Business Server management shell or from a remote session of Windows PowerShell.</span></span>
  
<span data-ttu-id="320e9-109">若要使外部用户能够与 Skype for Business Server 部署中的用户协作，还必须至少配置一个外部访问策略以支持外部用户访问。</span><span class="sxs-lookup"><span data-stu-id="320e9-109">To enable external users to collaborate with users in your Skype for Business Server deployment, you must also configure at least one external access policy to support external user access.</span></span> <span data-ttu-id="320e9-110">有关详细信息，请参阅管理你的组织的 XMPP 联盟合作伙伴。</span><span class="sxs-lookup"><span data-stu-id="320e9-110">For details, see Manage XMPP Federated Partners for Your Organization.</span></span> <span data-ttu-id="320e9-111">有关控制特定联盟域的访问的详细信息，请参阅“控制各个联盟域的访问”。</span><span class="sxs-lookup"><span data-stu-id="320e9-111">For details about controlling access for specific federated domains, see Control Access by Individual Federated Domains.</span></span>
  
## <a name="enable-or-disable-archiving-disclaimer-using-the-control-panel"></a><span data-ttu-id="320e9-112">使用控制面板启用或禁用存档免责声明</span><span class="sxs-lookup"><span data-stu-id="320e9-112">Enable or disable archiving disclaimer using the Control Panel</span></span>

1. <span data-ttu-id="320e9-113">使用 RTCUniversalServerAdmins 组成员（或具有同等用户权限）的用户帐户，或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="320e9-113">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="320e9-114">打开一个浏览器窗口，然后输入管理员 URL 以打开 Skype for Business 服务器控制面板。</span><span class="sxs-lookup"><span data-stu-id="320e9-114">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="320e9-115">在左侧导航栏中，单击“**联盟和外部访问**”，然后单击“**访问边缘配置**”。</span><span class="sxs-lookup"><span data-stu-id="320e9-115">In the left navigation bar, click **Federation and External Access**, and then click **Access Edge Configuration**.</span></span>
    
4. <span data-ttu-id="320e9-116">在“**访问边缘配置**”选项卡上，单击“**全局**”，再单击“**编辑**”，然后单击“**显示详细信息**”。</span><span class="sxs-lookup"><span data-stu-id="320e9-116">On the **Access Edge Configuration** tab, click **Global**, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="320e9-117">在“**编辑访问边缘配置**”的“**启用联盟和公共 IM 连接**”下，选中或清除“**向联盟伙伴发送存档免责声明**”复选框以启用或禁用自动发送存档免责声明。</span><span class="sxs-lookup"><span data-stu-id="320e9-117">In **Edit Access Edge Configuration**, under **Enable federation and public IM connectivity**, select or clear the **Send archiving disclaimer to federated partners** check box to enable or disable automatically sending the archiving disclaimer.</span></span>
    
6. <span data-ttu-id="320e9-118">单击“**提交**”。</span><span class="sxs-lookup"><span data-stu-id="320e9-118">Click **Commit**.</span></span>
    
## <a name="enable-or-disable-archiving-disclaimer-using-windows-powershell"></a><span data-ttu-id="320e9-119">使用 Windows PowerShell 启用或禁用存档免责声明</span><span class="sxs-lookup"><span data-stu-id="320e9-119">Enable or disable archiving disclaimer using Windows PowerShell</span></span>

<span data-ttu-id="320e9-120">要启用存档免责声明，请将 **EnableArchivingDisclaimer** 属性的值设置为 True ($True)：</span><span class="sxs-lookup"><span data-stu-id="320e9-120">To enable the archiving disclaimer, set the value of the **EnableArchivingDisclaimer** property to True ($True):</span></span>
  
```powershell
Set-CsAccessEdgeConfiguration -EnableArchivingDisclaimer $True
```

<span data-ttu-id="320e9-121">要禁用存档免责声明，请将 **EnableArchivingDisclaimer** 属性的值设置为 False ($False)：</span><span class="sxs-lookup"><span data-stu-id="320e9-121">To disable the archiving disclaimer, set the value of the **EnableArchivingDisclaimer** property to False ($False):</span></span>
  
```powershell
Set-CsAccessEdgeConfiguration -EnableArchivingDisclaimer $False
```



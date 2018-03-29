---
title: 在 Skype for Business Server 2015 中为外部用户配置存档免责声明
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 394ac291-05cd-4fa1-acb3-714af538b47f
description: 摘要： 阅读本主题，以了解如何配置存档放弃声明的 Skype 业务服务器 2015年。
ms.openlocfilehash: 3790160024010084c69df7d9865f17622fca4f0d
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="configure-archiving-disclaimers-for-external-users-in-skype-for-business-server-2015"></a><span data-ttu-id="c9b7b-103">在 Skype for Business Server 2015 中为外部用户配置存档免责声明</span><span class="sxs-lookup"><span data-stu-id="c9b7b-103">Configure archiving disclaimers for external users in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="c9b7b-104">**摘要：**阅读本主题，以了解如何配置存档放弃声明的 Skype 业务服务器 2015年。</span><span class="sxs-lookup"><span data-stu-id="c9b7b-104">**Summary:** Read this topic to learn how to configure an archiving disclaimer for Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="c9b7b-105">如果您的组织与外部合作伙伴通信，您需要让他们知道，您会存档与他们之间的通信。</span><span class="sxs-lookup"><span data-stu-id="c9b7b-105">If your organization communicates with external partners, you need to let them know that you are archiving communications with them.</span></span> <span data-ttu-id="c9b7b-106">当您部署边缘服务器，并为您的组织中启用联盟时，会询问您是否要自动将存档放弃声明发送给外部合作伙伴。</span><span class="sxs-lookup"><span data-stu-id="c9b7b-106">When you deploy an Edge Server and enable federation for your organization, you are asked whether you want to automatically send an archiving disclaimer to external partners.</span></span> 
  
<span data-ttu-id="c9b7b-107">如果您需要更改此配置，您可以使用 Skype 业务服务器的控制面板或 Windows PowerShell**集 CsAccessEdgeConfiguration** cmdlet。</span><span class="sxs-lookup"><span data-stu-id="c9b7b-107">If you need to change this configuration, you can use the Skype for Business Server Control Panel or the Windows PowerShell **Set-CsAccessEdgeConfiguration** cmdlet.</span></span> <span data-ttu-id="c9b7b-108">从业务服务器管理外壳的 Skype 或 Windows PowerShell 的远程会话，则可以运行 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="c9b7b-108">Cmdlets can be run either from the Skype for Business Server management shell or from a remote session of Windows PowerShell.</span></span>
  
<span data-ttu-id="c9b7b-109">若要启用外部用户与您 Skype 业务服务器部署中的用户进行协作，还必须配置至少一个外部访问策略，以支持外部用户访问权限。</span><span class="sxs-lookup"><span data-stu-id="c9b7b-109">To enable external users to collaborate with users in your Skype for Business Server deployment, you must also configure at least one external access policy to support external user access.</span></span> <span data-ttu-id="c9b7b-110">详细信息，请参阅您的组织的管理 XMPP 联合伙伴。</span><span class="sxs-lookup"><span data-stu-id="c9b7b-110">For details, see Manage XMPP Federated Partners for Your Organization.</span></span> <span data-ttu-id="c9b7b-111">有关控制特定联盟域的访问的详细信息，请参阅“控制各个联盟域的访问”。</span><span class="sxs-lookup"><span data-stu-id="c9b7b-111">For details about controlling access for specific federated domains, see Control Access by Individual Federated Domains.</span></span>
  
## <a name="enable-or-disable-archiving-disclaimer-using-the-control-panel"></a><span data-ttu-id="c9b7b-112">使用控制面板启用或禁用存档免责声明</span><span class="sxs-lookup"><span data-stu-id="c9b7b-112">Enable or disable archiving disclaimer using the Control Panel</span></span>

1. <span data-ttu-id="c9b7b-113">使用 RTCUniversalServerAdmins 组成员（或具有同等用户权限）的用户帐户，或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="c9b7b-113">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="c9b7b-114">打开浏览器窗口，然后输入管理员 URL 打开 Skype 业务服务器控件面板。</span><span class="sxs-lookup"><span data-stu-id="c9b7b-114">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="c9b7b-115">在左侧导航栏中，单击“**联盟和外部访问**”，然后单击“**访问边缘配置**”。</span><span class="sxs-lookup"><span data-stu-id="c9b7b-115">In the left navigation bar, click **Federation and External Access**, and then click **Access Edge Configuration**.</span></span>
    
4. <span data-ttu-id="c9b7b-116">在“**访问边缘配置**”选项卡上，单击“**全局**”，再单击“**编辑**”，然后单击“**显示详细信息**”。</span><span class="sxs-lookup"><span data-stu-id="c9b7b-116">On the **Access Edge Configuration** tab, click **Global**, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="c9b7b-117">在“**编辑访问边缘配置**”的“**启用联盟和公共 IM 连接**”下，选中或清除“**向联盟伙伴发送存档免责声明**”复选框以启用或禁用自动发送存档免责声明。</span><span class="sxs-lookup"><span data-stu-id="c9b7b-117">In **Edit Access Edge Configuration**, under **Enable federation and public IM connectivity**, select or clear the **Send archiving disclaimer to federated partners** check box to enable or disable automatically sending the archiving disclaimer.</span></span>
    
6. <span data-ttu-id="c9b7b-118">单击“**提交**”。</span><span class="sxs-lookup"><span data-stu-id="c9b7b-118">Click **Commit**.</span></span>
    
## <a name="enable-or-disable-archiving-disclaimer-using-windows-powershell"></a><span data-ttu-id="c9b7b-119">使用 Windows PowerShell 启用或禁用存档免责声明</span><span class="sxs-lookup"><span data-stu-id="c9b7b-119">Enable or disable archiving disclaimer using Windows PowerShell</span></span>

<span data-ttu-id="c9b7b-120">要启用存档免责声明，请将 **EnableArchivingDisclaimer** 属性的值设置为 True ($True)：</span><span class="sxs-lookup"><span data-stu-id="c9b7b-120">To enable the archiving disclaimer, set the value of the **EnableArchivingDisclaimer** property to True ($True):</span></span>
  
```
Set-CsAccessEdgeConfiguration -EnableArchivingDisclaimer $True
```

<span data-ttu-id="c9b7b-121">要禁用存档免责声明，请将 **EnableArchivingDisclaimer** 属性的值设置为 False ($False)：</span><span class="sxs-lookup"><span data-stu-id="c9b7b-121">To disable the archiving disclaimer, set the value of the **EnableArchivingDisclaimer** property to False ($False):</span></span>
  
```
Set-CsAccessEdgeConfiguration -EnableArchivingDisclaimer $False
```



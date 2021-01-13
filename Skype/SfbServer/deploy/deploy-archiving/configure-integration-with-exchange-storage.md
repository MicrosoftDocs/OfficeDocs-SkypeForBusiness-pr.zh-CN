---
title: 为 Skype for Business Server 配置与 Exchange 存储的集成
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 8f48b87f-a57f-4ed8-8c79-5c75b316b696
description: 摘要：阅读本主题，了解如何在 Skype for Business Server 中配置与 Exchange 存储的集成。
ms.openlocfilehash: 05a0c65aaca54e469f30dd5e732565f6ec0bbb4b
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49825062"
---
# <a name="configure-integration-with-exchange-storage-for-skype-for-business-server"></a><span data-ttu-id="5a9a1-103">为 Skype for Business Server 配置与 Exchange 存储的集成</span><span class="sxs-lookup"><span data-stu-id="5a9a1-103">Configure integration with Exchange storage for Skype for Business Server</span></span>
 
<span data-ttu-id="5a9a1-104">**摘要：** 阅读本主题，了解如何在 Skype for Business Server 中配置与 Exchange 存储的集成。</span><span class="sxs-lookup"><span data-stu-id="5a9a1-104">**Summary:** Read this topic to learn how to configure integration with Exchange storage in Skype for Business Server.</span></span>
  
<span data-ttu-id="5a9a1-105">如果在部署中为所有用户使用 Microsoft Exchange 集成，则无需为用户配置 Skype for Business Server 存档策略。</span><span class="sxs-lookup"><span data-stu-id="5a9a1-105">If you use Microsoft Exchange integration for all users in your deployment, you don't need to configure Skype for Business Server archiving policies for your users.</span></span> <span data-ttu-id="5a9a1-106">相反，您可以配置 Exchange In-Place 保留策略以支持对 Exchange 上用户进行存档，其邮箱将置于In-Place保留状态。</span><span class="sxs-lookup"><span data-stu-id="5a9a1-106">Instead, you configure Exchange In-Place Hold policies to support archiving for users homed on Exchange, with their mailboxes put on In-Place Hold.</span></span> <span data-ttu-id="5a9a1-107">配置与 Exchange 存储的集成之前，请阅读 [Plan for archiving in Skype for Business Server](../../plan-your-deployment/archiving/archiving.md)。</span><span class="sxs-lookup"><span data-stu-id="5a9a1-107">Before you configure integration with Exchange storage, read [Plan for archiving in Skype for Business Server](../../plan-your-deployment/archiving/archiving.md).</span></span> <span data-ttu-id="5a9a1-108">有关 Exchange In-Place保留策略的详细信息，请参阅 Exchange 产品文档。</span><span class="sxs-lookup"><span data-stu-id="5a9a1-108">For details about Exchange In-Place Hold policies, see the Exchange product documentation.</span></span> 
  
## <a name="configure-integration-with-microsoft-exchange-storage"></a><span data-ttu-id="5a9a1-109">配置与 Microsoft Exchange 存储的集成</span><span class="sxs-lookup"><span data-stu-id="5a9a1-109">Configure integration with Microsoft Exchange storage</span></span>

1. <span data-ttu-id="5a9a1-110">使用分配给 CsArchivingAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="5a9a1-110">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="5a9a1-111">打开浏览器窗口，然后输入管理 URL 以打开 Skype for Business Server 控制面板。</span><span class="sxs-lookup"><span data-stu-id="5a9a1-111">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="5a9a1-112">在左侧导航栏中，单击 **“监控和存档”**，然后单击 **“存档配置”**。</span><span class="sxs-lookup"><span data-stu-id="5a9a1-112">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Configuration**.</span></span>
    
4. <span data-ttu-id="5a9a1-113">单击存档配置列表中相应的全局、站点或池配置的名称，单击“编辑”，再单击“显示详细信息”，然后执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="5a9a1-113">Click the name of the appropriate global, site, or pool configuration in the list of archiving configurations, click **Edit**, click **Show details**, and then do the following:</span></span>
    
   - <span data-ttu-id="5a9a1-114">若要启用与 Exchange 存储的集成，请选中 **Microsoft Exchange 集成** 复选框。</span><span class="sxs-lookup"><span data-stu-id="5a9a1-114">To enable integration with Exchange storage, select the **Microsoft Exchange integration** check box.</span></span>
    
   - <span data-ttu-id="5a9a1-115">若要禁用与 Exchange 存储的集成，请清除 **Microsoft Exchange 集成** 复选框。</span><span class="sxs-lookup"><span data-stu-id="5a9a1-115">To disable integration with Exchange storage, clear the **Microsoft Exchange integration** check box.</span></span>
    
5. <span data-ttu-id="5a9a1-116">单击“提交”。</span><span class="sxs-lookup"><span data-stu-id="5a9a1-116">Click **Commit**.</span></span>
    
## <a name="when-skype-for-business-server-and-microsoft-exchange-are-deployed-in-different-forests"></a><span data-ttu-id="5a9a1-117">当 Skype for Business Server 和 Microsoft Exchange 部署在不同的林中时</span><span class="sxs-lookup"><span data-stu-id="5a9a1-117">When Skype for Business Server and Microsoft Exchange are deployed in different forests</span></span>

<span data-ttu-id="5a9a1-118">如果使用 Microsoft Exchange 集成，Microsoft Exchange Server未部署在 Skype for Business Server 的同一林中，则必须确保将以下 Exchange Active Directory 属性同步到部署 Skype for Business Server 的林：</span><span class="sxs-lookup"><span data-stu-id="5a9a1-118">If you use Microsoft Exchange integration and Microsoft Exchange Server is not deployed in the same forest as Skype for Business Server, you must make sure that the following Exchange Active Directory attributes are synchronized to the forest where Skype for Business Server is deployed:</span></span>
  
- <span data-ttu-id="5a9a1-119">msExchUserHoldPolicies</span><span class="sxs-lookup"><span data-stu-id="5a9a1-119">msExchUserHoldPolicies</span></span>
    
- <span data-ttu-id="5a9a1-120">proxyAddresses</span><span class="sxs-lookup"><span data-stu-id="5a9a1-120">proxyAddresses</span></span>
    
<span data-ttu-id="5a9a1-p102">这是一个多值属性。在同步此属性时，需要合并各个值（而不是将其替换）以确保现有值不会丢失。</span><span class="sxs-lookup"><span data-stu-id="5a9a1-p102">This is a multi-value attribute. When synchronizing this attribute, you need to merge the values, not replace them to ensure the existing values are not lost.</span></span>
  


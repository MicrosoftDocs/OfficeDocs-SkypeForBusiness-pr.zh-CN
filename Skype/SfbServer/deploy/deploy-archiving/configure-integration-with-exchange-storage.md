---
title: 配置与 Skype for Business Server 2015 的 Exchange 存储的集成
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8f48b87f-a57f-4ed8-8c79-5c75b316b696
description: 摘要： 阅读本主题，以了解如何使用 Exchange 存储在 Skype 业务服务器 2015年配置集成。
ms.openlocfilehash: 2d814bb297999062aaf93160286031afec51c3a9
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="configure-integration-with-exchange-storage-for-skype-for-business-server-2015"></a><span data-ttu-id="23456-103">配置与 Skype for Business Server 2015 的 Exchange 存储的集成</span><span class="sxs-lookup"><span data-stu-id="23456-103">Configure integration with Exchange storage for Skype for Business Server 2015</span></span>
 
<span data-ttu-id="23456-104">**摘要：**阅读本主题，以了解如何使用 Exchange 存储在 Skype 业务服务器 2015年配置集成。</span><span class="sxs-lookup"><span data-stu-id="23456-104">**Summary:** Read this topic to learn how to configure integration with Exchange storage in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="23456-105">如果部署中的所有用户使用 Microsoft Exchange 集成，您不需要为业务服务器归档策略，为您的用户配置 Skype。</span><span class="sxs-lookup"><span data-stu-id="23456-105">If you use Microsoft Exchange integration for all users in your deployment, you don't need to configure Skype for Business Server archiving policies for your users.</span></span> <span data-ttu-id="23456-106">相反，您可以配置支持归档的放在原位保存其邮箱上交换，驻留用户交换就地保存策略。</span><span class="sxs-lookup"><span data-stu-id="23456-106">Instead, you configure Exchange In-Place Hold policies to support archiving for users homed on Exchange, with their mailboxes put on In-Place Hold.</span></span> <span data-ttu-id="23456-107">使用 Exchange 存储中配置集成之前，请阅读[存档业务服务器 2015年的 Skype 的计划](../../plan-your-deployment/archiving/archiving.md)。</span><span class="sxs-lookup"><span data-stu-id="23456-107">Before you configure integration with Exchange storage, read [Plan for archiving in Skype for Business Server 2015](../../plan-your-deployment/archiving/archiving.md).</span></span> <span data-ttu-id="23456-108">有关 Exchange 就地保存策略的详细信息，请参阅 Exchange 产品文档。</span><span class="sxs-lookup"><span data-stu-id="23456-108">For details about Exchange In-Place Hold policies, see the Exchange product documentation.</span></span> 
  
## <a name="configure-integration-with-microsoft-exchange-storage"></a><span data-ttu-id="23456-109">使用 Microsoft Exchange 存储配置集成</span><span class="sxs-lookup"><span data-stu-id="23456-109">Configure integration with Microsoft Exchange storage</span></span>

1. <span data-ttu-id="23456-110">使用分配给 CsArchivingAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="23456-110">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="23456-111">打开浏览器窗口，然后输入管理员 URL 打开 Skype 业务服务器控件面板。</span><span class="sxs-lookup"><span data-stu-id="23456-111">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="23456-112">在左侧导航栏中，单击“**监控和存档**”，然后单击“**存档配置**”。</span><span class="sxs-lookup"><span data-stu-id="23456-112">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Configuration**.</span></span>
    
4. <span data-ttu-id="23456-113">单击存档配置列表中相应的全局、站点或池配置的名称，单击“**编辑**”，再单击“**显示详细信息**”，然后执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="23456-113">Click the name of the appropriate global, site, or pool configuration in the list of archiving configurations, click **Edit**, click **Show details**, and then do the following:</span></span>
    
  - <span data-ttu-id="23456-114">要启用与 Exchange 存储集成，请选择**Microsoft Exchange 集成**复选框。</span><span class="sxs-lookup"><span data-stu-id="23456-114">To enable integration with Exchange storage, select the **Microsoft Exchange integration** check box.</span></span>
    
  - <span data-ttu-id="23456-115">要禁用与 Exchange 存储集成，请清除**Microsoft Exchange 集成**复选框。</span><span class="sxs-lookup"><span data-stu-id="23456-115">To disable integration with Exchange storage, clear the **Microsoft Exchange integration** check box.</span></span>
    
5. <span data-ttu-id="23456-116">单击“**提交**”。</span><span class="sxs-lookup"><span data-stu-id="23456-116">Click **Commit**.</span></span>
    
## <a name="when-skype-for-business-server-and-microsoft-exchange-are-deployed-in-different-forests"></a><span data-ttu-id="23456-117">当 Skype 业务服务器和 Microsoft Exchange 部署在不同的目录林</span><span class="sxs-lookup"><span data-stu-id="23456-117">When Skype for Business Server and Microsoft Exchange are deployed in different forests</span></span>

<span data-ttu-id="23456-118">如果您使用 Microsoft Exchange 集成和 Microsoft Exchange Server 将不会部署在同一个林的 Skype 业务服务器，必须确保以下 Exchange Active Directory 属性将同步到林在 Skype 的部署企业服务器：</span><span class="sxs-lookup"><span data-stu-id="23456-118">If you use Microsoft Exchange integration and Microsoft Exchange Server is not deployed in the same forest as Skype for Business Server, you must make sure that the following Exchange Active Directory attributes are synchronized to the forest where Skype for Business Server is deployed:</span></span>
  
- <span data-ttu-id="23456-119">msExchUserHoldPolicies</span><span class="sxs-lookup"><span data-stu-id="23456-119">msExchUserHoldPolicies</span></span>
    
- <span data-ttu-id="23456-120">代理地址</span><span class="sxs-lookup"><span data-stu-id="23456-120">proxyAddresses</span></span>
    
<span data-ttu-id="23456-p102">这是一个多值属性。在同步此属性时，需要合并各个值（而不是将其替换）以确保现有值不会丢失。</span><span class="sxs-lookup"><span data-stu-id="23456-p102">This is a multi-value attribute. When synchronizing this attribute, you need to merge the values, not replace them to ensure the existing values are not lost.</span></span>
  


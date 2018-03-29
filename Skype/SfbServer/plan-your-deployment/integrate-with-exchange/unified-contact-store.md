---
title: 在 Skype for Business Server 2015 中规划统一联系人存储
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 6/8/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: d56e11be-43dd-45d4-8ac6-3adfb03f5d1a
description: 摘要： 计划集成为 Exchange 2013 具有的业务服务器 2015 Skype 时仔细阅读本主题。
ms.openlocfilehash: f3332f891d0c0a46a95c47d7fb860a7251f6fb3e
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="plan-for-unified-contact-store-in-skype-for-business-server-2015"></a><span data-ttu-id="b8c24-103">在 Skype for Business Server 2015 中规划统一联系人存储</span><span class="sxs-lookup"><span data-stu-id="b8c24-103">Plan for unified contact store in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="b8c24-104">**摘要：**计划为 Exchange 2013 具有的业务服务器 2015年集成 Skype 时仔细阅读本主题。</span><span class="sxs-lookup"><span data-stu-id="b8c24-104">**Summary:** Review this topic while planning to integrate Skype for Business Server 2015 with Exchange 2013.</span></span>
  
<span data-ttu-id="b8c24-105">统一联系人存储库提供一致的联系体验跨 Microsoft Office 产品，并使用户能够将所有联系人信息在 Exchange 存储 2013年但允许的信息可以在全局范围内整个 Skype 业务、 交换、 Outlook并且 Outlook Web Access。</span><span class="sxs-lookup"><span data-stu-id="b8c24-105">Unified contact store provides a consistent contact experience across Microsoft Office products, and enables users to store all contact information in Exchange 2013 but allows the information to be available globally across Skype for Business, Exchange, Outlook, and Outlook Web Access.</span></span>
  
## <a name="requirements-for-unified-contact-store"></a><span data-ttu-id="b8c24-106">统一联系人存储的要求</span><span class="sxs-lookup"><span data-stu-id="b8c24-106">Requirements for unified contact store</span></span>

<span data-ttu-id="b8c24-107">若要实现统一的业务服务器 2015年在 Skype 的联系人存储库：</span><span class="sxs-lookup"><span data-stu-id="b8c24-107">To implement unified contact store in Skype for Business Server 2015:</span></span>
  
- <span data-ttu-id="b8c24-108">您必须运行 Skype 业务服务器 2015年和 Exchange 2013。</span><span class="sxs-lookup"><span data-stu-id="b8c24-108">You must be running Skype for Business Server 2015 and Exchange 2013.</span></span>
    
- <span data-ttu-id="b8c24-109">用户必须使用 Skype 业务要迁移其联系人从 Skype 业务服务器 2015年至 Exchange 2013。</span><span class="sxs-lookup"><span data-stu-id="b8c24-109">Users must use Skype for Business to migrate their contacts from Skype for Business Server 2015 to Exchange 2013.</span></span>
    
- <span data-ttu-id="b8c24-110">必须将用户邮箱迁移到 Exchange 2013 中。</span><span class="sxs-lookup"><span data-stu-id="b8c24-110">User mailboxes must be migrated to Exchange 2013.</span></span>
    
- <span data-ttu-id="b8c24-111">您必须配置 Exchange 2013 业务服务器 2015年的 Skype 之间的服务器到服务器身份验证。</span><span class="sxs-lookup"><span data-stu-id="b8c24-111">You must have server-to-server authentication configured between Skype for Business Server 2015 and Exchange 2013.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="b8c24-112">有关设置业务服务器 2015年的 Skype 和 Exchange 2013 之间身份验证的详细要求，请参阅[管理服务器到服务器身份验证 (OAuth) 和业务服务器 2015年的 Skype 的合作伙伴应用程序](../../manage/authentication/server-to-server-and-partner-applications.md)操作文档。</span><span class="sxs-lookup"><span data-stu-id="b8c24-112">For detailed requirements about setting up authentication between Skype for Business Server 2015 and Exchange 2013, see [Manage server-to-server authentication (OAuth) and partner applications in Skype for Business Server 2015](../../manage/authentication/server-to-server-and-partner-applications.md) in the Operations documentation.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="b8c24-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b8c24-113">See also</span></span>

#### 

[<span data-ttu-id="b8c24-114">部署统一联系人存储库在 Skype 的业务服务器 2015</span><span class="sxs-lookup"><span data-stu-id="b8c24-114">Deploy unified contact store in Skype for Business Server 2015</span></span>](../../deploy/deploy-unified-contact-store.md)


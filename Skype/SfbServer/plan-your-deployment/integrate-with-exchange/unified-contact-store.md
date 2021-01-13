---
title: 在 Skype for Business Server 中规划统一联系人存储
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 6/8/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: d56e11be-43dd-45d4-8ac6-3adfb03f5d1a
description: 摘要：在计划将 Skype for Business Server 与 Exchange 2013 集成时，请查看本主题。
ms.openlocfilehash: 3ce06118f8225e78c5c84a8f9124e4815f79d593
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816252"
---
# <a name="plan-for-unified-contact-store-in-skype-for-business-server-2015"></a><span data-ttu-id="1e64a-103">在 Skype for Business Server 2015 中规划统一联系人存储</span><span class="sxs-lookup"><span data-stu-id="1e64a-103">Plan for unified contact store in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="1e64a-104">**摘要：** 在计划将 Skype for Business Server 与 Exchange 2013 或 Exchange 2016 集成时，请查看本主题。</span><span class="sxs-lookup"><span data-stu-id="1e64a-104">**Summary:** Review this topic while planning to integrate Skype for Business Server with Exchange 2013 or 2016.</span></span>
  
<span data-ttu-id="1e64a-105">统一联系人存储跨 Microsoft Office 产品提供一致的联系人体验，并使用户能够在 Exchange 2013 中存储所有联系人信息，但允许信息跨 Skype for Business、Exchange、Outlook 和 Outlook Web Access 全局提供。</span><span class="sxs-lookup"><span data-stu-id="1e64a-105">Unified contact store provides a consistent contact experience across Microsoft Office products, and enables users to store all contact information in Exchange 2013 but allows the information to be available globally across Skype for Business, Exchange, Outlook, and Outlook Web Access.</span></span>
  
## <a name="requirements-for-unified-contact-store"></a><span data-ttu-id="1e64a-106">统一联系人存储的要求</span><span class="sxs-lookup"><span data-stu-id="1e64a-106">Requirements for unified contact store</span></span>

<span data-ttu-id="1e64a-107">若要在 Skype for Business Server 中实现统一的联系人存储，</span><span class="sxs-lookup"><span data-stu-id="1e64a-107">To implement unified contact store in Skype for Business Server:</span></span>
  
- <span data-ttu-id="1e64a-108">必须运行 Skype for Business Server 和 Exchange 2013 或 2016。</span><span class="sxs-lookup"><span data-stu-id="1e64a-108">You must be running Skype for Business Server and Exchange 2013 or 2016.</span></span>
    
- <span data-ttu-id="1e64a-109">用户必须使用 Skype for Business 将其联系人从 Skype for Business Server 迁移到 Exchange 2013 或 2016。</span><span class="sxs-lookup"><span data-stu-id="1e64a-109">Users must use Skype for Business to migrate their contacts from Skype for Business Server to Exchange 2013 or 2016.</span></span>
    
- <span data-ttu-id="1e64a-110">用户邮箱必须迁移到 Exchange 2013。</span><span class="sxs-lookup"><span data-stu-id="1e64a-110">User mailboxes must be migrated to Exchange 2013.</span></span>
    
- <span data-ttu-id="1e64a-111">必须在 Skype for Business Server 和 Exchange 2013 或 Exchange 2016 之间配置服务器到服务器身份验证。</span><span class="sxs-lookup"><span data-stu-id="1e64a-111">You must have server-to-server authentication configured between Skype for Business Server and Exchange 2013 or 2016.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="1e64a-112">有关在 Skype for Business Server 和 Exchange 2013 或 Exchange 2016 之间设置身份验证的详细要求，请参阅操作文档中的"管理服务器到服务器身份验证 [ (OAuth) ](../../manage/authentication/server-to-server-and-partner-applications.md) 和 Skype for Business Server 中的合作伙伴应用程序"。</span><span class="sxs-lookup"><span data-stu-id="1e64a-112">For detailed requirements about setting up authentication between Skype for Business Server and Exchange 2013 or 2016, see [Manage server-to-server authentication (OAuth) and partner applications in Skype for Business Server](../../manage/authentication/server-to-server-and-partner-applications.md) in the Operations documentation.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="1e64a-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1e64a-113">See also</span></span>

[<span data-ttu-id="1e64a-114">在 Skype for Business Server 中部署统一的联系人存储</span><span class="sxs-lookup"><span data-stu-id="1e64a-114">Deploy unified contact store in Skype for Business Server</span></span>](../../deploy/deploy-unified-contact-store.md)

---
title: Plan for Business Server Skype 中的统一联系人存储
ms.reviewer: ''
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
description: 摘要： 查看 while planning to Exchange 2013 的业务服务器集成 Skype 本主题。
ms.openlocfilehash: fd408466034646938d002c609a263e71077e5b94
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/27/2019
ms.locfileid: "30882654"
---
# <a name="plan-for-unified-contact-store-in-skype-for-business-server-2015"></a><span data-ttu-id="75728-103">在 Skype for Business Server 2015 中规划统一联系人存储</span><span class="sxs-lookup"><span data-stu-id="75728-103">Plan for unified contact store in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="75728-104">**摘要：** While planning to Exchange 2013 或 2016年业务服务器集成 Skype 查看以下主题。</span><span class="sxs-lookup"><span data-stu-id="75728-104">**Summary:** Review this topic while planning to integrate Skype for Business Server with Exchange 2013 or 2016.</span></span>
  
<span data-ttu-id="75728-105">统一联系人存储库跨 Microsoft Office 产品提供一致的联系人体验并使用户能够在 Exchange 2013 存储所有联系人信息但允许可全局 Skype 的业务、 Exchange 和 Outlook 之间的信息和 Outlook Web Access。</span><span class="sxs-lookup"><span data-stu-id="75728-105">Unified contact store provides a consistent contact experience across Microsoft Office products, and enables users to store all contact information in Exchange 2013 but allows the information to be available globally across Skype for Business, Exchange, Outlook, and Outlook Web Access.</span></span>
  
## <a name="requirements-for-unified-contact-store"></a><span data-ttu-id="75728-106">统一联系人存储的要求</span><span class="sxs-lookup"><span data-stu-id="75728-106">Requirements for unified contact store</span></span>

<span data-ttu-id="75728-107">若要在 Skype 中实现统一联系人存储库，业务服务器：</span><span class="sxs-lookup"><span data-stu-id="75728-107">To implement unified contact store in Skype for Business Server:</span></span>
  
- <span data-ttu-id="75728-108">您必须为业务服务器和 Exchange 2013 或 2016年运行 Skype。</span><span class="sxs-lookup"><span data-stu-id="75728-108">You must be running Skype for Business Server and Exchange 2013 or 2016.</span></span>
    
- <span data-ttu-id="75728-109">用户必须使用 for Business 的 Skype 迁移其联系人从 Skype 业务服务器到 Exchange 2013 或 2016年。</span><span class="sxs-lookup"><span data-stu-id="75728-109">Users must use Skype for Business to migrate their contacts from Skype for Business Server to Exchange 2013 or 2016.</span></span>
    
- <span data-ttu-id="75728-110">用户邮箱必须迁移到 Exchange 2013。</span><span class="sxs-lookup"><span data-stu-id="75728-110">User mailboxes must be migrated to Exchange 2013.</span></span>
    
- <span data-ttu-id="75728-111">您必须具有业务服务器和 Exchange 2013 或 2016 Skype 之间配置服务器到服务器身份验证。</span><span class="sxs-lookup"><span data-stu-id="75728-111">You must have server-to-server authentication configured between Skype for Business Server and Exchange 2013 or 2016.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="75728-112">有关 Business Server 和 Exchange 2013 或 2016 Skype 之间设置身份验证的详细要求，请参阅[管理服务器到服务器身份验证 (OAuth) 和合作伙伴应用程序中的业务服务器 Skype](../../manage/authentication/server-to-server-and-partner-applications.md)操作中文档。</span><span class="sxs-lookup"><span data-stu-id="75728-112">For detailed requirements about setting up authentication between Skype for Business Server and Exchange 2013 or 2016, see [Manage server-to-server authentication (OAuth) and partner applications in Skype for Business Server](../../manage/authentication/server-to-server-and-partner-applications.md) in the Operations documentation.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="75728-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="75728-113">See also</span></span>

[<span data-ttu-id="75728-114">部署统一的联系人存储中 Skype 业务服务器</span><span class="sxs-lookup"><span data-stu-id="75728-114">Deploy unified contact store in Skype for Business Server</span></span>](../../deploy/deploy-unified-contact-store.md)

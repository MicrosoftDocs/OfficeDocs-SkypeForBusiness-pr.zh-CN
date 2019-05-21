---
title: 在 Skype for Business 服务器中规划统一联系人存储
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 6/8/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: d56e11be-43dd-45d4-8ac6-3adfb03f5d1a
description: '摘要: 在计划将 Skype for business 服务器与 Exchange 2013 集成时, 请查看本主题。'
ms.openlocfilehash: 4548773c382b4295ddfbfa141f18f0df8ba367ae
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34297391"
---
# <a name="plan-for-unified-contact-store-in-skype-for-business-server-2015"></a><span data-ttu-id="3c748-103">在 Skype for Business Server 2015 中规划统一联系人存储</span><span class="sxs-lookup"><span data-stu-id="3c748-103">Plan for unified contact store in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="3c748-104">**摘要:** 在计划将 Skype for business 服务器与 Exchange 2013 或2016集成时, 请查看此主题。</span><span class="sxs-lookup"><span data-stu-id="3c748-104">**Summary:** Review this topic while planning to integrate Skype for Business Server with Exchange 2013 or 2016.</span></span>
  
<span data-ttu-id="3c748-105">统一联系人存储跨 Microsoft Office 产品提供一致的联系人体验, 使用户能够在 Exchange 2013 中存储所有联系人信息, 但允许信息在 Skype for Business、Exchange、Outlook 中全球可用和 Outlook Web Access。</span><span class="sxs-lookup"><span data-stu-id="3c748-105">Unified contact store provides a consistent contact experience across Microsoft Office products, and enables users to store all contact information in Exchange 2013 but allows the information to be available globally across Skype for Business, Exchange, Outlook, and Outlook Web Access.</span></span>
  
## <a name="requirements-for-unified-contact-store"></a><span data-ttu-id="3c748-106">统一联系人存储的要求</span><span class="sxs-lookup"><span data-stu-id="3c748-106">Requirements for unified contact store</span></span>

<span data-ttu-id="3c748-107">要在 Skype for Business 服务器中实施统一的联系人存储, 请执行以下操作:</span><span class="sxs-lookup"><span data-stu-id="3c748-107">To implement unified contact store in Skype for Business Server:</span></span>
  
- <span data-ttu-id="3c748-108">您必须运行 Skype for Business 服务器以及 Exchange 2013 或2016。</span><span class="sxs-lookup"><span data-stu-id="3c748-108">You must be running Skype for Business Server and Exchange 2013 or 2016.</span></span>
    
- <span data-ttu-id="3c748-109">用户必须使用 Skype for business 将其联系人从 Skype for Business 服务器迁移到 Exchange 2013 或2016。</span><span class="sxs-lookup"><span data-stu-id="3c748-109">Users must use Skype for Business to migrate their contacts from Skype for Business Server to Exchange 2013 or 2016.</span></span>
    
- <span data-ttu-id="3c748-110">用户邮箱必须迁移到 Exchange 2013。</span><span class="sxs-lookup"><span data-stu-id="3c748-110">User mailboxes must be migrated to Exchange 2013.</span></span>
    
- <span data-ttu-id="3c748-111">您必须在 Skype for Business 服务器与 Exchange 2013 或2016之间配置服务器到服务器的身份验证。</span><span class="sxs-lookup"><span data-stu-id="3c748-111">You must have server-to-server authentication configured between Skype for Business Server and Exchange 2013 or 2016.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="3c748-112">有关在 Skype for business 服务器与 Exchange 2013 或2016之间设置身份验证的详细要求, 请参阅在操作中[管理 skype For Business 服务器中的服务器到服务器身份验证 (OAuth) 和合作伙伴应用程序](../../manage/authentication/server-to-server-and-partner-applications.md)文档.</span><span class="sxs-lookup"><span data-stu-id="3c748-112">For detailed requirements about setting up authentication between Skype for Business Server and Exchange 2013 or 2016, see [Manage server-to-server authentication (OAuth) and partner applications in Skype for Business Server](../../manage/authentication/server-to-server-and-partner-applications.md) in the Operations documentation.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="3c748-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3c748-113">See also</span></span>

[<span data-ttu-id="3c748-114">在 Skype for Business 服务器中部署统一联系人存储</span><span class="sxs-lookup"><span data-stu-id="3c748-114">Deploy unified contact store in Skype for Business Server</span></span>](../../deploy/deploy-unified-contact-store.md)

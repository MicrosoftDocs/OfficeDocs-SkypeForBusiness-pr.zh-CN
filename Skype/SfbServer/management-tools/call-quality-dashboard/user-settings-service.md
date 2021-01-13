---
title: '呼叫质量仪表板的用户设置服务 (CQD) '
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: eafeb54a-2574-415b-b991-a0ff0470d8c3
description: 摘要：了解用户设置服务，该服务是通话质量仪表板存储库 API 的一部分。 通话质量仪表板是 Skype for Business Server 的工具。
ms.openlocfilehash: 2b2fc9810f1eceb74974dc105263b0bdcf37ae01
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49803033"
---
# <a name="user-settings-service-for-call-quality-dashboard-cqd"></a><span data-ttu-id="cc70e-104">呼叫质量仪表板的用户设置服务 (CQD) </span><span class="sxs-lookup"><span data-stu-id="cc70e-104">User Settings Service for Call Quality Dashboard (CQD)</span></span>
 
<span data-ttu-id="cc70e-105">**摘要：** 了解用户设置服务，该服务是通话质量仪表板的存储库 API 的一部分。</span><span class="sxs-lookup"><span data-stu-id="cc70e-105">**Summary:** Learn about the User Settings Service, which is part of the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="cc70e-106">通话质量仪表板是 Skype for Business Server 的工具。</span><span class="sxs-lookup"><span data-stu-id="cc70e-106">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="cc70e-107">用户设置服务是通话质量仪表板存储库 API 的一部分。</span><span class="sxs-lookup"><span data-stu-id="cc70e-107">The User Settings Service is part of the Repository API for Call Quality Dashboard.</span></span>
  
## <a name="user-settings-service"></a><span data-ttu-id="cc70e-108">用户设置服务</span><span class="sxs-lookup"><span data-stu-id="cc70e-108">User Settings Service</span></span>

<span data-ttu-id="cc70e-109">用户设置是键值对，应用程序可用于存储各种目的的元数据，包括基于每个用户的应用程序行为的自定义。</span><span class="sxs-lookup"><span data-stu-id="cc70e-109">User settings are key-value pairs that applications can use to store metadata for various purposes including customization of application behaviors per-user basis.</span></span> <span data-ttu-id="cc70e-110">每个用户会收到用户设置的存储。</span><span class="sxs-lookup"><span data-stu-id="cc70e-110">Each user receives a storage for user settings.</span></span> <span data-ttu-id="cc70e-111">只有所有者可以添加、修改和删除用户设置。</span><span class="sxs-lookup"><span data-stu-id="cc70e-111">Only the owners can add, modify, and remove user settings.</span></span>
  
 <span data-ttu-id="cc70e-112">**全局设置**</span><span class="sxs-lookup"><span data-stu-id="cc70e-112">**Global Settings**</span></span>
  
<span data-ttu-id="cc70e-113">全局设置是系统用户所拥有的用户设置，所有用户均具有对这些设置的只读访问权限。</span><span class="sxs-lookup"><span data-stu-id="cc70e-113">Global settings are the user settings owned by the system user, and all users have read-only access to them.</span></span> <span data-ttu-id="cc70e-114">全局设置是常量：它们是在存储库创建期间创建的，并且永远不会更改。</span><span class="sxs-lookup"><span data-stu-id="cc70e-114">Global settings are constants: they are created during the repository creation, and they never change.</span></span>
  
<span data-ttu-id="cc70e-115">每个用户可以通过使用相同的键创建用户设置来覆盖全局设置。</span><span class="sxs-lookup"><span data-stu-id="cc70e-115">Each user can override global settings by creating user settings with the same keys.</span></span> <span data-ttu-id="cc70e-116">当应用程序请求有效的用户设置时，API 将返回一组与用户设置合并的全局设置，如果键相同，则每个用户的设置将取代各自的全局设置。</span><span class="sxs-lookup"><span data-stu-id="cc70e-116">When application requests the effective user settings, the API returns a set of global settings merged with the user settings, with each user setting superseding the respective global setting if keys are the same.</span></span> <span data-ttu-id="cc70e-117">API 还可以仅返回用户设置，以便应用程序可以找出被覆盖的设置。</span><span class="sxs-lookup"><span data-stu-id="cc70e-117">The API can also return just the user settings so that applications can find out which settings are overridden.</span></span> 
  
<span data-ttu-id="cc70e-118">REST 操作包含在下表中。</span><span class="sxs-lookup"><span data-stu-id="cc70e-118">The REST operations are included in the following table.</span></span>

|<span data-ttu-id="cc70e-119">**操作**</span><span class="sxs-lookup"><span data-stu-id="cc70e-119">**Operation**</span></span>|<span data-ttu-id="cc70e-120">**说明**</span><span class="sxs-lookup"><span data-stu-id="cc70e-120">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="cc70e-121">获取用户设置</span><span class="sxs-lookup"><span data-stu-id="cc70e-121">Get User Settings</span></span>](get-user-settings.md) <br/> |<span data-ttu-id="cc70e-122">Get User Settings returns a list of settings for a specified user.</span><span class="sxs-lookup"><span data-stu-id="cc70e-122">Get User Settings returns a list of settings for a specified user.</span></span>  <br/> |
|[<span data-ttu-id="cc70e-123">获取用户设置</span><span class="sxs-lookup"><span data-stu-id="cc70e-123">Get User Setting</span></span>](get-user-setting.md) <br/> |<span data-ttu-id="cc70e-124">获取用户设置返回单个用户设置。</span><span class="sxs-lookup"><span data-stu-id="cc70e-124">Get User Setting returns a single user setting.</span></span>  <br/> |
   


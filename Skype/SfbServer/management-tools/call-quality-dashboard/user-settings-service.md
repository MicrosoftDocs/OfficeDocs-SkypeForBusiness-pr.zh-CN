---
title: 呼叫质量仪表板（CQD）的用户设置服务
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: eafeb54a-2574-415b-b991-a0ff0470d8c3
description: 摘要：了解 "用户设置" 服务，该服务是 "呼叫质量" 仪表板的知识库 API 的一部分。 通话质量仪表板是 Skype for business 服务器的工具。
ms.openlocfilehash: 1eef869523bf1590a00ca199727b33ec9e13ccba
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41816641"
---
# <a name="user-settings-service-for-call-quality-dashboard-cqd"></a><span data-ttu-id="c54c7-104">呼叫质量仪表板（CQD）的用户设置服务</span><span class="sxs-lookup"><span data-stu-id="c54c7-104">User Settings Service for Call Quality Dashboard (CQD)</span></span>
 
<span data-ttu-id="c54c7-105">**摘要：** 了解 "用户设置" 服务，该服务是 "呼叫质量" 仪表板的 "存储库 API" 的一部分。</span><span class="sxs-lookup"><span data-stu-id="c54c7-105">**Summary:** Learn about the User Settings Service, which is part of the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="c54c7-106">通话质量仪表板是 Skype for business 服务器的工具。</span><span class="sxs-lookup"><span data-stu-id="c54c7-106">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="c54c7-107">"用户设置" 服务是 "呼叫质量" 仪表板的知识库 API 的一部分。</span><span class="sxs-lookup"><span data-stu-id="c54c7-107">The User Settings Service is part of the Repository API for Call Quality Dashboard.</span></span>
  
## <a name="user-settings-service"></a><span data-ttu-id="c54c7-108">用户设置服务</span><span class="sxs-lookup"><span data-stu-id="c54c7-108">User Settings Service</span></span>

<span data-ttu-id="c54c7-109">用户设置是一些键值对，应用程序可用于存储元数据以实现各种用途，包括根据用户自定义应用程序行为。</span><span class="sxs-lookup"><span data-stu-id="c54c7-109">User settings are key-value pairs that applications can use to store metadata for various purposes including customization of application behaviors per-user basis.</span></span> <span data-ttu-id="c54c7-110">每个用户都收到用户设置的存储空间。</span><span class="sxs-lookup"><span data-stu-id="c54c7-110">Each user receives a storage for user settings.</span></span> <span data-ttu-id="c54c7-111">只有所有者才能添加、修改和删除用户设置。</span><span class="sxs-lookup"><span data-stu-id="c54c7-111">Only the owners can add, modify, and remove user settings.</span></span>
  
 <span data-ttu-id="c54c7-112">**全局设置**</span><span class="sxs-lookup"><span data-stu-id="c54c7-112">**Global Settings**</span></span>
  
<span data-ttu-id="c54c7-113">全局设置是系统用户拥有的用户设置，并且所有用户都对其具有只读访问权限。</span><span class="sxs-lookup"><span data-stu-id="c54c7-113">Global settings are the user settings owned by the system user, and all users have read-only access to them.</span></span> <span data-ttu-id="c54c7-114">全局设置是常量：它们是在创建存储库期间创建的，它们永远不会更改。</span><span class="sxs-lookup"><span data-stu-id="c54c7-114">Global settings are constants: they are created during the repository creation, and they never change.</span></span>
  
<span data-ttu-id="c54c7-115">每个用户都可以通过使用相同的密钥创建用户设置来覆盖全局设置。</span><span class="sxs-lookup"><span data-stu-id="c54c7-115">Each user can override global settings by creating user settings with the same keys.</span></span> <span data-ttu-id="c54c7-116">当应用程序请求有效的用户设置时，API 将返回一组与用户设置合并的全局设置，并且如果键相同，则每个用户设置都将取代各自的全局设置。</span><span class="sxs-lookup"><span data-stu-id="c54c7-116">When application requests the effective user settings, the API returns a set of global settings merged with the user settings, with each user setting superseding the respective global setting if keys are the same.</span></span> <span data-ttu-id="c54c7-117">API 还可以仅返回用户设置，以便应用程序可以确定哪些设置被重写。</span><span class="sxs-lookup"><span data-stu-id="c54c7-117">The API can also return just the user settings so that applications can find out which settings are overridden.</span></span> 
  
<span data-ttu-id="c54c7-118">下表中包括其余操作。</span><span class="sxs-lookup"><span data-stu-id="c54c7-118">The REST operations are included in the following table.</span></span>

|<span data-ttu-id="c54c7-119">**操作**</span><span class="sxs-lookup"><span data-stu-id="c54c7-119">**Operation**</span></span>|<span data-ttu-id="c54c7-120">**说明**</span><span class="sxs-lookup"><span data-stu-id="c54c7-120">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="c54c7-121">获取用户设置</span><span class="sxs-lookup"><span data-stu-id="c54c7-121">Get User Settings</span></span>](get-user-settings.md) <br/> |<span data-ttu-id="c54c7-122">获取用户设置返回指定用户的设置列表。</span><span class="sxs-lookup"><span data-stu-id="c54c7-122">Get User Settings returns a list of settings for a specified user.</span></span>  <br/> |
|[<span data-ttu-id="c54c7-123">获取用户设置</span><span class="sxs-lookup"><span data-stu-id="c54c7-123">Get User Setting</span></span>](get-user-setting.md) <br/> |<span data-ttu-id="c54c7-124">获取用户设置返回单个用户设置。</span><span class="sxs-lookup"><span data-stu-id="c54c7-124">Get User Setting returns a single user setting.</span></span>  <br/> |
   


---
title: 呼叫质量仪表板 (CQD) 的用户设置服务
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: eafeb54a-2574-415b-b991-a0ff0470d8c3
description: 摘要： 了解用户设置服务，它是用于呼叫的质量仪表板的存储库 API 的一部分。 呼叫质量仪表板是用于业务服务器 Skype 的工具。
ms.openlocfilehash: 00d0662e777ef2f13c9783fe4b79d5c582faa8af
ms.sourcegitcommit: 30620021ceba916a505437ab641a23393f55827a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/15/2018
ms.locfileid: "26531889"
---
# <a name="user-settings-service-for-call-quality-dashboard-cqd"></a><span data-ttu-id="035b2-104">呼叫质量仪表板 (CQD) 的用户设置服务</span><span class="sxs-lookup"><span data-stu-id="035b2-104">User Settings Service for Call Quality Dashboard (CQD)</span></span>
 
<span data-ttu-id="035b2-105">**摘要：** 了解用户设置服务，它是用于呼叫的质量仪表板的存储库 API 的一部分。</span><span class="sxs-lookup"><span data-stu-id="035b2-105">**Summary:** Learn about the User Settings Service, which is part of the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="035b2-106">呼叫质量仪表板是用于业务服务器 Skype 的工具。</span><span class="sxs-lookup"><span data-stu-id="035b2-106">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="035b2-107">用户设置服务是呼叫质量仪表板的存储库 API 的一部分。</span><span class="sxs-lookup"><span data-stu-id="035b2-107">The User Settings Service is part of the Repository API for Call Quality Dashboard.</span></span>
  
## <a name="user-settings-service"></a><span data-ttu-id="035b2-108">用户设置服务</span><span class="sxs-lookup"><span data-stu-id="035b2-108">User Settings Service</span></span>

<span data-ttu-id="035b2-109">用户设置是应用程序可用于多种目的，包括自定义应用程序行为每个用户分别为存储元数据的键 / 值对。</span><span class="sxs-lookup"><span data-stu-id="035b2-109">User settings are key-value pairs that applications can use to store metadata for various purposes including customization of application behaviors per-user basis.</span></span> <span data-ttu-id="035b2-110">每个用户收到用户设置的存储。</span><span class="sxs-lookup"><span data-stu-id="035b2-110">Each user receives a storage for user settings.</span></span> <span data-ttu-id="035b2-111">只有所有者可以添加、 修改和删除用户设置。</span><span class="sxs-lookup"><span data-stu-id="035b2-111">Only the owners can add, modify, and remove user settings.</span></span>
  
 <span data-ttu-id="035b2-112">**全局设置**</span><span class="sxs-lookup"><span data-stu-id="035b2-112">**Global Settings**</span></span>
  
<span data-ttu-id="035b2-113">全局设置是由系统用户拥有的用户设置，所有用户都具有对它们的只读访问。</span><span class="sxs-lookup"><span data-stu-id="035b2-113">Global settings are the user settings owned by the system user, and all users have read-only access to them.</span></span> <span data-ttu-id="035b2-114">全局设置的常量： 创建存储库在创建期间，以及它们永远不会更改。</span><span class="sxs-lookup"><span data-stu-id="035b2-114">Global settings are constants: they are created during the repository creation, and they never change.</span></span>
  
<span data-ttu-id="035b2-115">通过使用相同的密钥创建用户设置，每个用户可以覆盖全局设置。</span><span class="sxs-lookup"><span data-stu-id="035b2-115">Each user can override global settings by creating user settings with the same keys.</span></span> <span data-ttu-id="035b2-116">当应用程序请求的有效用户设置时，API 返回一组与取代各自全局设置键时相同的每个用户设置的用户设置，合并的全局设置。</span><span class="sxs-lookup"><span data-stu-id="035b2-116">When application requests the effective user settings, the API returns a set of global settings merged with the user settings, with each user setting superseding the respective global setting if keys are the same.</span></span> <span data-ttu-id="035b2-117">API 还可以返回的用户设置，以便应用程序可以找出将重写的设置。</span><span class="sxs-lookup"><span data-stu-id="035b2-117">The API can also return just the user settings so that applications can find out which settings are overridden.</span></span> 
  
<span data-ttu-id="035b2-118">下表中包含的其余部分操作。</span><span class="sxs-lookup"><span data-stu-id="035b2-118">The REST operations are included in the following table.</span></span>

|<span data-ttu-id="035b2-119">**操作**</span><span class="sxs-lookup"><span data-stu-id="035b2-119">**Operation**</span></span>|<span data-ttu-id="035b2-120">**说明**</span><span class="sxs-lookup"><span data-stu-id="035b2-120">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="035b2-121">获取用户设置</span><span class="sxs-lookup"><span data-stu-id="035b2-121">Get User Settings</span></span>](get-user-settings.md) <br/> |<span data-ttu-id="035b2-122">获取用户设置返回指定用户的设置的列表。</span><span class="sxs-lookup"><span data-stu-id="035b2-122">Get User Settings returns a list of settings for a specified user.</span></span>  <br/> |
|[<span data-ttu-id="035b2-123">获取用户设置</span><span class="sxs-lookup"><span data-stu-id="035b2-123">Get User Setting</span></span>](get-user-setting.md) <br/> |<span data-ttu-id="035b2-124">获取用户设置返回的单个用户设置。</span><span class="sxs-lookup"><span data-stu-id="035b2-124">Get User Setting returns a single user setting.</span></span>  <br/> |
   


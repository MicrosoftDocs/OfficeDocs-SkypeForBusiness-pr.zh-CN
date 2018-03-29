---
title: 用户设置服务呼叫质量仪表板 (CQD)
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 8/18/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: eafeb54a-2574-415b-b991-a0ff0470d8c3
description: 摘要： 了解用户设置服务，这是呼叫质量仪表板存储库 API 的一部分。 通话质量仪表板是用于业务服务器 2015年的 Skype 的工具。
ms.openlocfilehash: fe51c96546903e09f28ffadf06451efc8c1a88b0
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="user-settings-service-for-call-quality-dashboard-cqd"></a><span data-ttu-id="c1c6e-104">用户设置服务呼叫质量仪表板 (CQD)</span><span class="sxs-lookup"><span data-stu-id="c1c6e-104">User Settings Service for Call Quality Dashboard (CQD)</span></span>
 
<span data-ttu-id="c1c6e-105">**摘要：**了解用户设置服务，这是呼叫质量仪表板存储库 API 的一部分。</span><span class="sxs-lookup"><span data-stu-id="c1c6e-105">**Summary:** Learn about the User Settings Service, which is part of the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="c1c6e-106">通话质量仪表板是用于业务服务器 2015年的 Skype 的工具。</span><span class="sxs-lookup"><span data-stu-id="c1c6e-106">Call Quality Dashboard is a tool for Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="c1c6e-107">用户设置服务被呼叫质量仪表板存储库 API 的一部分。</span><span class="sxs-lookup"><span data-stu-id="c1c6e-107">The User Settings Service is part of the Repository API for Call Quality Dashboard.</span></span>
  
## <a name="user-settings-service"></a><span data-ttu-id="c1c6e-108">用户设置服务</span><span class="sxs-lookup"><span data-stu-id="c1c6e-108">User Settings Service</span></span>

<span data-ttu-id="c1c6e-109">用户设置被应用程序可用于多种目的，包括自定义应用程序行为每个用户为基础的存储元数据的键 / 值对。</span><span class="sxs-lookup"><span data-stu-id="c1c6e-109">User settings are key-value pairs that applications can use to store metadata for various purposes including customization of application behaviors per-user basis.</span></span> <span data-ttu-id="c1c6e-110">每个用户将收到为用户设置存储。</span><span class="sxs-lookup"><span data-stu-id="c1c6e-110">Each user receives a storage for user settings.</span></span> <span data-ttu-id="c1c6e-111">只有所有者才可以添加、 修改和删除用户的设置。</span><span class="sxs-lookup"><span data-stu-id="c1c6e-111">Only the owners can add, modify, and remove user settings.</span></span>
  
 <span data-ttu-id="c1c6e-112">**全局设置**</span><span class="sxs-lookup"><span data-stu-id="c1c6e-112">**Global Settings**</span></span>
  
<span data-ttu-id="c1c6e-113">全局设置是系统用户，拥有的用户设置，所有用户都有只读访问它们。</span><span class="sxs-lookup"><span data-stu-id="c1c6e-113">Global settings are the user settings owned by the system user, and all users have read-only access to them.</span></span> <span data-ttu-id="c1c6e-114">全局设置为常量： 在存储库中创建，创建它们，它们永远不会更改。</span><span class="sxs-lookup"><span data-stu-id="c1c6e-114">Global settings are constants: they are created during the repository creation, and they never change.</span></span>
  
<span data-ttu-id="c1c6e-115">每个用户可以通过创建具有相同键的用户设置覆盖全局设置。</span><span class="sxs-lookup"><span data-stu-id="c1c6e-115">Each user can override global settings by creating user settings with the same keys.</span></span> <span data-ttu-id="c1c6e-116">当应用程序请求的有效用户设置时，该 API 返回一套合并在一起的用户设置，与每个用户设置取代各自全局设置如果键相同的全局设置。</span><span class="sxs-lookup"><span data-stu-id="c1c6e-116">When application requests the effective user settings, the API returns a set of global settings merged with the user settings, with each user setting superseding the respective global setting if keys are the same.</span></span> <span data-ttu-id="c1c6e-117">API 还可以返回的用户设置，以便应用程序可以找出哪些设置将重写。</span><span class="sxs-lookup"><span data-stu-id="c1c6e-117">The API can also return just the user settings so that applications can find out which settings are overridden.</span></span> 
  
<span data-ttu-id="c1c6e-118">下表中包括的其余操作。</span><span class="sxs-lookup"><span data-stu-id="c1c6e-118">The REST operations are included in the following table.</span></span>

|<span data-ttu-id="c1c6e-119">**操作**</span><span class="sxs-lookup"><span data-stu-id="c1c6e-119">**Operation**</span></span>|<span data-ttu-id="c1c6e-120">**说明**</span><span class="sxs-lookup"><span data-stu-id="c1c6e-120">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="c1c6e-121">获取用户设置</span><span class="sxs-lookup"><span data-stu-id="c1c6e-121">Get User Settings</span></span>](get-user-settings.md) <br/> |<span data-ttu-id="c1c6e-122">获取用户设置返回设置为指定的用户的列表。</span><span class="sxs-lookup"><span data-stu-id="c1c6e-122">Get User Settings returns a list of settings for a specified user.</span></span>  <br/> |
|[<span data-ttu-id="c1c6e-123">获取用户的设置</span><span class="sxs-lookup"><span data-stu-id="c1c6e-123">Get User Setting</span></span>](get-user-setting.md) <br/> |<span data-ttu-id="c1c6e-124">获取用户设置返回的单个用户设置。</span><span class="sxs-lookup"><span data-stu-id="c1c6e-124">Get User Setting returns a single user setting.</span></span>  <br/> |
   


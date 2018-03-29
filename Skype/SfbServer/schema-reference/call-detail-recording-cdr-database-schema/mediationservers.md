---
title: MediationServers 表
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 9f757377-ab79-4795-aaa9-1163cb9c8a59
description: MediationServers 表是支持表。 每个记录存储在数据库中具有记录的调用所涉及的一个中介服务器的信息。
ms.openlocfilehash: 5854e9787497316d76b7262821be8d4953532d56
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="mediationservers-table"></a><span data-ttu-id="0fd58-104">MediationServers 表</span><span class="sxs-lookup"><span data-stu-id="0fd58-104">MediationServers table</span></span>
 
<span data-ttu-id="0fd58-105">MediationServers 表是支持表。</span><span class="sxs-lookup"><span data-stu-id="0fd58-105">The MediationServers table is a supporting table.</span></span> <span data-ttu-id="0fd58-106">每个记录存储在数据库中具有记录的调用所涉及的一个中介服务器的信息。</span><span class="sxs-lookup"><span data-stu-id="0fd58-106">Each record stores information about one Mediation Server that is involved in calls that have records in the database.</span></span>
  
|<span data-ttu-id="0fd58-107">**列**</span><span class="sxs-lookup"><span data-stu-id="0fd58-107">**Column**</span></span>|<span data-ttu-id="0fd58-108">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="0fd58-108">**Data Type**</span></span>|<span data-ttu-id="0fd58-109">**键/索引**</span><span class="sxs-lookup"><span data-stu-id="0fd58-109">**Key/Index**</span></span>|<span data-ttu-id="0fd58-110">**详细信息**</span><span class="sxs-lookup"><span data-stu-id="0fd58-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="0fd58-111">**MediationServerId**</span><span class="sxs-lookup"><span data-stu-id="0fd58-111">**MediationServerId**</span></span> <br/> |<span data-ttu-id="0fd58-112">int</span><span class="sxs-lookup"><span data-stu-id="0fd58-112">int</span></span>  <br/> |<span data-ttu-id="0fd58-113">Primary</span><span class="sxs-lookup"><span data-stu-id="0fd58-113">Primary</span></span>  <br/> |<span data-ttu-id="0fd58-114">标识此中介服务器的唯一编号。</span><span class="sxs-lookup"><span data-stu-id="0fd58-114">Unique number identifying this Mediation Server.</span></span>  <br/> |
|<span data-ttu-id="0fd58-115">**MediationServer**</span><span class="sxs-lookup"><span data-stu-id="0fd58-115">**MediationServer**</span></span> <br/> |<span data-ttu-id="0fd58-116">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="0fd58-116">nvarchar(256)</span></span>  <br/> | <br/> |<span data-ttu-id="0fd58-117">中介服务器的名称。</span><span class="sxs-lookup"><span data-stu-id="0fd58-117">Mediation Server name.</span></span>  <br/> |
   


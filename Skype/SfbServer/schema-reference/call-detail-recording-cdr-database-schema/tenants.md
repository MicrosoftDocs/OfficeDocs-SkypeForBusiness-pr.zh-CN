---
title: Tenants 表
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c1b070c1-2c59-4ca9-910b-43f673f97fda
description: 承租人表是一个支持的表来存储各种承租人的列表。 每个表中的记录表示一个租户。
ms.openlocfilehash: 4dde1baaf553c1a0d8a0efe65d72e8326cbb3bad
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="tenants-table"></a><span data-ttu-id="93eb0-104">Tenants 表</span><span class="sxs-lookup"><span data-stu-id="93eb0-104">Tenants table</span></span>
 
<span data-ttu-id="93eb0-105">承租人表是一个支持的表来存储各种承租人的列表。</span><span class="sxs-lookup"><span data-stu-id="93eb0-105">The Tenants table is a supporting table that stores a list of the various tenants.</span></span> <span data-ttu-id="93eb0-106">每个表中的记录表示一个租户。</span><span class="sxs-lookup"><span data-stu-id="93eb0-106">Each record in the table represents one tenant.</span></span>
  
> [!NOTE]
> <span data-ttu-id="93eb0-107">在内部部署中，CDR 使用生成在租户 ID 来表示不同的身份验证类型，例如公用 IM 连接，联盟和匿名。</span><span class="sxs-lookup"><span data-stu-id="93eb0-107">In on-premises deployment, CDR uses the build-in Tenant ID to indicate different authentication type, such as public IM connectivity, Federated and Anonymous.</span></span> 
  
|<span data-ttu-id="93eb0-108">**列**</span><span class="sxs-lookup"><span data-stu-id="93eb0-108">**Column**</span></span>|<span data-ttu-id="93eb0-109">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="93eb0-109">**Data Type**</span></span>|<span data-ttu-id="93eb0-110">**键/索引**</span><span class="sxs-lookup"><span data-stu-id="93eb0-110">**Key/Index**</span></span>|<span data-ttu-id="93eb0-111">**详细信息**</span><span class="sxs-lookup"><span data-stu-id="93eb0-111">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="93eb0-112">**TenantId**</span><span class="sxs-lookup"><span data-stu-id="93eb0-112">**TenantId**</span></span> <br/> |<span data-ttu-id="93eb0-113">int</span><span class="sxs-lookup"><span data-stu-id="93eb0-113">int</span></span>  <br/> |<span data-ttu-id="93eb0-114">Primary</span><span class="sxs-lookup"><span data-stu-id="93eb0-114">Primary</span></span>  <br/> |<span data-ttu-id="93eb0-115">唯一的编号，用于标识此租户 id。</span><span class="sxs-lookup"><span data-stu-id="93eb0-115">Unique number identifying this Tenant ID.</span></span>  <br/> |
|<span data-ttu-id="93eb0-116">**TenantKey**</span><span class="sxs-lookup"><span data-stu-id="93eb0-116">**TenantKey**</span></span> <br/> |<span data-ttu-id="93eb0-117">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="93eb0-117">nvarchar(256)</span></span>  <br/> || <span data-ttu-id="93eb0-118">允许的值：</span><span class="sxs-lookup"><span data-stu-id="93eb0-118">Allowed values:</span></span> <br/>  <span data-ttu-id="93eb0-119">00000000-0000-0000-0000-000000000000-企业</span><span class="sxs-lookup"><span data-stu-id="93eb0-119">00000000-0000-0000-0000-000000000000 - Enterprise</span></span> <br/>  <span data-ttu-id="93eb0-120">00000000-0000-0000-0000-000000000001-联合</span><span class="sxs-lookup"><span data-stu-id="93eb0-120">00000000-0000-0000-0000-000000000001 - Federated</span></span> <br/>  <span data-ttu-id="93eb0-121">00000000-0000-0000-0000-000000000002-匿名</span><span class="sxs-lookup"><span data-stu-id="93eb0-121">00000000-0000-0000-0000-000000000002 - Anonymous</span></span> <br/>  <span data-ttu-id="93eb0-122">00000000-0000-0000-0000-000000000003-公用 IM 连接</span><span class="sxs-lookup"><span data-stu-id="93eb0-122">00000000-0000-0000-0000-000000000003 - Public IM connectivity</span></span> <br/> |
   


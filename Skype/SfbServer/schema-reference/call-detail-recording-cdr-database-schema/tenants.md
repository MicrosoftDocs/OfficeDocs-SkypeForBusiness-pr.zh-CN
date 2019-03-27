---
title: Tenants 表
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c1b070c1-2c59-4ca9-910b-43f673f97fda
description: Tenants 表是一个支持表，用于存储各种租户的列表。 表中的每条记录代表一个租户。
ms.openlocfilehash: cf7d0271c9cacfd76079a80a7e5db63d669a8dfb
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/27/2019
ms.locfileid: "30873988"
---
# <a name="tenants-table"></a><span data-ttu-id="8007a-104">Tenants 表</span><span class="sxs-lookup"><span data-stu-id="8007a-104">Tenants table</span></span>
 
<span data-ttu-id="8007a-105">Tenants 表是一个支持表，用于存储各种租户的列表。</span><span class="sxs-lookup"><span data-stu-id="8007a-105">The Tenants table is a supporting table that stores a list of the various tenants.</span></span> <span data-ttu-id="8007a-106">表中的每条记录代表一个租户。</span><span class="sxs-lookup"><span data-stu-id="8007a-106">Each record in the table represents one tenant.</span></span>
  
> [!NOTE]
> <span data-ttu-id="8007a-107">在本地部署中，CDR 使用内置租户 ID 指示不同的身份验证类型，如公共 IM 连接、 联盟和匿名。</span><span class="sxs-lookup"><span data-stu-id="8007a-107">In on-premises deployment, CDR uses the build-in Tenant ID to indicate different authentication type, such as public IM connectivity, Federated and Anonymous.</span></span> 
  
|<span data-ttu-id="8007a-108">**列**</span><span class="sxs-lookup"><span data-stu-id="8007a-108">**Column**</span></span>|<span data-ttu-id="8007a-109">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="8007a-109">**Data Type**</span></span>|<span data-ttu-id="8007a-110">**键/索引**</span><span class="sxs-lookup"><span data-stu-id="8007a-110">**Key/Index**</span></span>|<span data-ttu-id="8007a-111">**详细信息**</span><span class="sxs-lookup"><span data-stu-id="8007a-111">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="8007a-112">**TenantId**</span><span class="sxs-lookup"><span data-stu-id="8007a-112">**TenantId**</span></span> <br/> |<span data-ttu-id="8007a-113">int</span><span class="sxs-lookup"><span data-stu-id="8007a-113">int</span></span>  <br/> |<span data-ttu-id="8007a-114">Primary</span><span class="sxs-lookup"><span data-stu-id="8007a-114">Primary</span></span>  <br/> |<span data-ttu-id="8007a-115">标识此租户 id。 的唯一编号</span><span class="sxs-lookup"><span data-stu-id="8007a-115">Unique number identifying this Tenant ID.</span></span>  <br/> |
|<span data-ttu-id="8007a-116">**TenantKey**</span><span class="sxs-lookup"><span data-stu-id="8007a-116">**TenantKey**</span></span> <br/> |<span data-ttu-id="8007a-117">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="8007a-117">nvarchar(256)</span></span>  <br/> || <span data-ttu-id="8007a-118">允许的值：</span><span class="sxs-lookup"><span data-stu-id="8007a-118">Allowed values:</span></span> <br/>  <span data-ttu-id="8007a-119">00000000-0000-0000-0000-000000000000-企业</span><span class="sxs-lookup"><span data-stu-id="8007a-119">00000000-0000-0000-0000-000000000000 - Enterprise</span></span> <br/>  <span data-ttu-id="8007a-120">00000000-0000-0000-0000-000000000001-联盟</span><span class="sxs-lookup"><span data-stu-id="8007a-120">00000000-0000-0000-0000-000000000001 - Federated</span></span> <br/>  <span data-ttu-id="8007a-121">00000000-0000-0000-0000-000000000002-匿名</span><span class="sxs-lookup"><span data-stu-id="8007a-121">00000000-0000-0000-0000-000000000002 - Anonymous</span></span> <br/>  <span data-ttu-id="8007a-122">00000000-0000-0000-0000-000000000003-公共 IM 连接</span><span class="sxs-lookup"><span data-stu-id="8007a-122">00000000-0000-0000-0000-000000000003 - Public IM connectivity</span></span> <br/> |
   


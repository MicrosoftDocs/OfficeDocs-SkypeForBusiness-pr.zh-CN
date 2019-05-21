---
title: Tenants 表
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c1b070c1-2c59-4ca9-910b-43f673f97fda
description: 租户表是一个支持表, 用于存储各种租户的列表。 表中的每条记录表示一个租户。
ms.openlocfilehash: 58c8a2e36ed6d95da46523597b455d228a24586c
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295767"
---
# <a name="tenants-table"></a><span data-ttu-id="05cf0-104">Tenants 表</span><span class="sxs-lookup"><span data-stu-id="05cf0-104">Tenants table</span></span>
 
<span data-ttu-id="05cf0-105">租户表是一个支持表, 用于存储各种租户的列表。</span><span class="sxs-lookup"><span data-stu-id="05cf0-105">The Tenants table is a supporting table that stores a list of the various tenants.</span></span> <span data-ttu-id="05cf0-106">表中的每条记录表示一个租户。</span><span class="sxs-lookup"><span data-stu-id="05cf0-106">Each record in the table represents one tenant.</span></span>
  
> [!NOTE]
> <span data-ttu-id="05cf0-107">在本地部署中, CDR 使用内部版本租户 ID 指示不同的身份验证类型, 例如公共 IM 连接、联合和匿名。</span><span class="sxs-lookup"><span data-stu-id="05cf0-107">In on-premises deployment, CDR uses the build-in Tenant ID to indicate different authentication type, such as public IM connectivity, Federated and Anonymous.</span></span> 
  
|<span data-ttu-id="05cf0-108">**列**</span><span class="sxs-lookup"><span data-stu-id="05cf0-108">**Column**</span></span>|<span data-ttu-id="05cf0-109">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="05cf0-109">**Data Type**</span></span>|<span data-ttu-id="05cf0-110">**键/索引**</span><span class="sxs-lookup"><span data-stu-id="05cf0-110">**Key/Index**</span></span>|<span data-ttu-id="05cf0-111">**详细信息**</span><span class="sxs-lookup"><span data-stu-id="05cf0-111">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="05cf0-112">**TenantId**</span><span class="sxs-lookup"><span data-stu-id="05cf0-112">**TenantId**</span></span> <br/> |<span data-ttu-id="05cf0-113">int</span><span class="sxs-lookup"><span data-stu-id="05cf0-113">int</span></span>  <br/> |<span data-ttu-id="05cf0-114">Primary</span><span class="sxs-lookup"><span data-stu-id="05cf0-114">Primary</span></span>  <br/> |<span data-ttu-id="05cf0-115">标识此租户 ID 的唯一编号。</span><span class="sxs-lookup"><span data-stu-id="05cf0-115">Unique number identifying this Tenant ID.</span></span>  <br/> |
|<span data-ttu-id="05cf0-116">**TenantKey**</span><span class="sxs-lookup"><span data-stu-id="05cf0-116">**TenantKey**</span></span> <br/> |<span data-ttu-id="05cf0-117">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="05cf0-117">nvarchar(256)</span></span>  <br/> || <span data-ttu-id="05cf0-118">允许的值:</span><span class="sxs-lookup"><span data-stu-id="05cf0-118">Allowed values:</span></span> <br/>  <span data-ttu-id="05cf0-119">00000000-0000-0000-0000-000000000000-企业版</span><span class="sxs-lookup"><span data-stu-id="05cf0-119">00000000-0000-0000-0000-000000000000 - Enterprise</span></span> <br/>  <span data-ttu-id="05cf0-120">00000000-0000-0000-0000-000000000001-联合</span><span class="sxs-lookup"><span data-stu-id="05cf0-120">00000000-0000-0000-0000-000000000001 - Federated</span></span> <br/>  <span data-ttu-id="05cf0-121">00000000-0000-0000-0000-000000000002-匿名</span><span class="sxs-lookup"><span data-stu-id="05cf0-121">00000000-0000-0000-0000-000000000002 - Anonymous</span></span> <br/>  <span data-ttu-id="05cf0-122">00000000-0000-0000-0000-000000000003-公共 IM 连接</span><span class="sxs-lookup"><span data-stu-id="05cf0-122">00000000-0000-0000-0000-000000000003 - Public IM connectivity</span></span> <br/> |
   


---
title: Tenants 表
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: c1b070c1-2c59-4ca9-910b-43f673f97fda
description: Tenants 表是一个支持表，用于存储各个租户的列表。 表中的每条记录分别表示一个租户。
ms.openlocfilehash: f22837f21bd431c83848d3b055a36930c9db2fd5
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49831712"
---
# <a name="tenants-table"></a><span data-ttu-id="1f1ae-104">Tenants 表</span><span class="sxs-lookup"><span data-stu-id="1f1ae-104">Tenants table</span></span>
 
<span data-ttu-id="1f1ae-p102">Tenants 表是一个支持表，用于存储各个租户的列表。表中的每条记录分别表示一个租户。</span><span class="sxs-lookup"><span data-stu-id="1f1ae-p102">The Tenants table is a supporting table that stores a list of the various tenants. Each record in the table represents one tenant.</span></span>
  
> [!NOTE]
> <span data-ttu-id="1f1ae-107">在本地部署中，CDR 使用内置租户 ID 指示不同的身份验证类型，例如公共 IM 连接、联盟和匿名。</span><span class="sxs-lookup"><span data-stu-id="1f1ae-107">In on-premises deployment, CDR uses the build-in Tenant ID to indicate different authentication type, such as public IM connectivity, Federated and Anonymous.</span></span> 
  
|<span data-ttu-id="1f1ae-108">**列**</span><span class="sxs-lookup"><span data-stu-id="1f1ae-108">**Column**</span></span>|<span data-ttu-id="1f1ae-109">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="1f1ae-109">**Data Type**</span></span>|<span data-ttu-id="1f1ae-110">**键/索引**</span><span class="sxs-lookup"><span data-stu-id="1f1ae-110">**Key/Index**</span></span>|<span data-ttu-id="1f1ae-111">**Details**</span><span class="sxs-lookup"><span data-stu-id="1f1ae-111">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="1f1ae-112">**TenantId**</span><span class="sxs-lookup"><span data-stu-id="1f1ae-112">**TenantId**</span></span> <br/> |<span data-ttu-id="1f1ae-113">int</span><span class="sxs-lookup"><span data-stu-id="1f1ae-113">int</span></span>  <br/> |<span data-ttu-id="1f1ae-114">主</span><span class="sxs-lookup"><span data-stu-id="1f1ae-114">Primary</span></span>  <br/> |<span data-ttu-id="1f1ae-115">标识此租户 ID 的唯一编号。</span><span class="sxs-lookup"><span data-stu-id="1f1ae-115">Unique number identifying this Tenant ID.</span></span>  <br/> |
|<span data-ttu-id="1f1ae-116">**TenantKey**</span><span class="sxs-lookup"><span data-stu-id="1f1ae-116">**TenantKey**</span></span> <br/> |<span data-ttu-id="1f1ae-117">nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="1f1ae-117">nvarchar(256)</span></span>  <br/> || <span data-ttu-id="1f1ae-118">允许的值：</span><span class="sxs-lookup"><span data-stu-id="1f1ae-118">Allowed values:</span></span> <br/>  <span data-ttu-id="1f1ae-119">00000000-0000-0000-0000-000000000000 - Enterprise</span><span class="sxs-lookup"><span data-stu-id="1f1ae-119">00000000-0000-0000-0000-000000000000 - Enterprise</span></span> <br/>  <span data-ttu-id="1f1ae-120">00000000-0000-0000-0000-00000000001 - 联合</span><span class="sxs-lookup"><span data-stu-id="1f1ae-120">00000000-0000-0000-0000-000000000001 - Federated</span></span> <br/>  <span data-ttu-id="1f1ae-121">00000000-0000-0000-0000-000000000002 - 匿名</span><span class="sxs-lookup"><span data-stu-id="1f1ae-121">00000000-0000-0000-0000-000000000002 - Anonymous</span></span> <br/>  <span data-ttu-id="1f1ae-122">00000000-0000-0000-0000-000000000003 - 公共 IM 连接</span><span class="sxs-lookup"><span data-stu-id="1f1ae-122">00000000-0000-0000-0000-000000000003 - Public IM connectivity</span></span> <br/> |
   


---
title: Skype for Business Server 2015 中的 Gateways 表
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
ms.assetid: a909daad-d137-45e0-b149-1de9f8e1e029
description: Gateways 表是一个支持表。 每条记录都存储有关公用电话交换网中涉及的一个网关的信息， (PSTN) 数据库中具有记录的呼叫。
ms.openlocfilehash: e945e5464093eb0eb58965fa1ef8a734ea0afa75
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49821582"
---
# <a name="gateways-table-in-skype-for-business-server-2015"></a><span data-ttu-id="33476-104">Skype for Business Server 2015 中的 Gateways 表</span><span class="sxs-lookup"><span data-stu-id="33476-104">Gateways table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="33476-105">Gateways 表是一个支持表。</span><span class="sxs-lookup"><span data-stu-id="33476-105">The Gateways table is a supporting table.</span></span> <span data-ttu-id="33476-106">每条记录都存储有关公用电话交换网中涉及的一个网关的信息， (PSTN) 数据库中具有记录的呼叫。</span><span class="sxs-lookup"><span data-stu-id="33476-106">Each record stores information about one gateway that is involved in public switched telephone network (PSTN) calls that have records in the database.</span></span>
  
|<span data-ttu-id="33476-107">**列**</span><span class="sxs-lookup"><span data-stu-id="33476-107">**Column**</span></span>|<span data-ttu-id="33476-108">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="33476-108">**Data Type**</span></span>|<span data-ttu-id="33476-109">**键/索引**</span><span class="sxs-lookup"><span data-stu-id="33476-109">**Key/Index**</span></span>|<span data-ttu-id="33476-110">**Details**</span><span class="sxs-lookup"><span data-stu-id="33476-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="33476-111">**GatewayId**</span><span class="sxs-lookup"><span data-stu-id="33476-111">**GatewayId**</span></span> <br/> |<span data-ttu-id="33476-112">int</span><span class="sxs-lookup"><span data-stu-id="33476-112">int</span></span>  <br/> |<span data-ttu-id="33476-113">主</span><span class="sxs-lookup"><span data-stu-id="33476-113">Primary</span></span>  <br/> |<span data-ttu-id="33476-114">标识此网关的唯一编号。</span><span class="sxs-lookup"><span data-stu-id="33476-114">Unique number identifying this gateway.</span></span>  <br/> |
|<span data-ttu-id="33476-115">**网关**</span><span class="sxs-lookup"><span data-stu-id="33476-115">**Gateway**</span></span> <br/> |<span data-ttu-id="33476-116">nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="33476-116">nvarchar(256)</span></span>  <br/> | <br/> |<span data-ttu-id="33476-117">网关名称。</span><span class="sxs-lookup"><span data-stu-id="33476-117">Gateway name.</span></span>  <br/> |
   


---
title: Skype for Business Server 2015 中的网关表
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: a909daad-d137-45e0-b149-1de9f8e1e029
description: 网关表是支持表。 每条记录存储有关一个网关的信息，这些信息涉及到数据库中有记录的公共交换电话网络（PSTN）呼叫。
ms.openlocfilehash: ce85b36d5ad587a096c99ca3f3f496642d3a3dd5
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815160"
---
# <a name="gateways-table-in-skype-for-business-server-2015"></a><span data-ttu-id="d5347-104">Skype for Business Server 2015 中的网关表</span><span class="sxs-lookup"><span data-stu-id="d5347-104">Gateways table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="d5347-105">网关表是支持表。</span><span class="sxs-lookup"><span data-stu-id="d5347-105">The Gateways table is a supporting table.</span></span> <span data-ttu-id="d5347-106">每条记录存储有关一个网关的信息，这些信息涉及到数据库中有记录的公共交换电话网络（PSTN）呼叫。</span><span class="sxs-lookup"><span data-stu-id="d5347-106">Each record stores information about one gateway that is involved in public switched telephone network (PSTN) calls that have records in the database.</span></span>
  
|<span data-ttu-id="d5347-107">**列**</span><span class="sxs-lookup"><span data-stu-id="d5347-107">**Column**</span></span>|<span data-ttu-id="d5347-108">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="d5347-108">**Data Type**</span></span>|<span data-ttu-id="d5347-109">**键/索引**</span><span class="sxs-lookup"><span data-stu-id="d5347-109">**Key/Index**</span></span>|<span data-ttu-id="d5347-110">**详细信息**</span><span class="sxs-lookup"><span data-stu-id="d5347-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="d5347-111">**GatewayId**</span><span class="sxs-lookup"><span data-stu-id="d5347-111">**GatewayId**</span></span> <br/> |<span data-ttu-id="d5347-112">int</span><span class="sxs-lookup"><span data-stu-id="d5347-112">int</span></span>  <br/> |<span data-ttu-id="d5347-113">Primary</span><span class="sxs-lookup"><span data-stu-id="d5347-113">Primary</span></span>  <br/> |<span data-ttu-id="d5347-114">标识此网关的唯一号码。</span><span class="sxs-lookup"><span data-stu-id="d5347-114">Unique number identifying this gateway.</span></span>  <br/> |
|<span data-ttu-id="d5347-115">**网关**</span><span class="sxs-lookup"><span data-stu-id="d5347-115">**Gateway**</span></span> <br/> |<span data-ttu-id="d5347-116">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="d5347-116">nvarchar(256)</span></span>  <br/> | <br/> |<span data-ttu-id="d5347-117">网关名称。</span><span class="sxs-lookup"><span data-stu-id="d5347-117">Gateway name.</span></span>  <br/> |
   


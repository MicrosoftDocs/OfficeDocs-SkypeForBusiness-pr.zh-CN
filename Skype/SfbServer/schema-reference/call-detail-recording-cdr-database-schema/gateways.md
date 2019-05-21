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
localization_priority: Normal
ms.assetid: a909daad-d137-45e0-b149-1de9f8e1e029
description: 网关表是支持表。 每条记录存储有关一个网关的信息, 这些信息涉及到数据库中有记录的公共交换电话网络 (PSTN) 呼叫。
ms.openlocfilehash: 6c827b6661e6dadd0550506f1e593462ec9d8c7a
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34296180"
---
# <a name="gateways-table-in-skype-for-business-server-2015"></a><span data-ttu-id="a52af-104">Skype for Business Server 2015 中的网关表</span><span class="sxs-lookup"><span data-stu-id="a52af-104">Gateways table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="a52af-105">网关表是支持表。</span><span class="sxs-lookup"><span data-stu-id="a52af-105">The Gateways table is a supporting table.</span></span> <span data-ttu-id="a52af-106">每条记录存储有关一个网关的信息, 这些信息涉及到数据库中有记录的公共交换电话网络 (PSTN) 呼叫。</span><span class="sxs-lookup"><span data-stu-id="a52af-106">Each record stores information about one gateway that is involved in public switched telephone network (PSTN) calls that have records in the database.</span></span>
  
|<span data-ttu-id="a52af-107">**列**</span><span class="sxs-lookup"><span data-stu-id="a52af-107">**Column**</span></span>|<span data-ttu-id="a52af-108">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="a52af-108">**Data Type**</span></span>|<span data-ttu-id="a52af-109">**键/索引**</span><span class="sxs-lookup"><span data-stu-id="a52af-109">**Key/Index**</span></span>|<span data-ttu-id="a52af-110">**详细信息**</span><span class="sxs-lookup"><span data-stu-id="a52af-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="a52af-111">**GatewayId**</span><span class="sxs-lookup"><span data-stu-id="a52af-111">**GatewayId**</span></span> <br/> |<span data-ttu-id="a52af-112">int</span><span class="sxs-lookup"><span data-stu-id="a52af-112">int</span></span>  <br/> |<span data-ttu-id="a52af-113">Primary</span><span class="sxs-lookup"><span data-stu-id="a52af-113">Primary</span></span>  <br/> |<span data-ttu-id="a52af-114">标识此网关的唯一号码。</span><span class="sxs-lookup"><span data-stu-id="a52af-114">Unique number identifying this gateway.</span></span>  <br/> |
|<span data-ttu-id="a52af-115">**网关**</span><span class="sxs-lookup"><span data-stu-id="a52af-115">**Gateway**</span></span> <br/> |<span data-ttu-id="a52af-116">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="a52af-116">nvarchar(256)</span></span>  <br/> | <br/> |<span data-ttu-id="a52af-117">网关名称。</span><span class="sxs-lookup"><span data-stu-id="a52af-117">Gateway name.</span></span>  <br/> |
   


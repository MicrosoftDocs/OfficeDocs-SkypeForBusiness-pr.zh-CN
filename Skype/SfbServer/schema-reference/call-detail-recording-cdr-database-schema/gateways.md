---
title: Gateways 表中的业务服务器 2015 Skype
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: a909daad-d137-45e0-b149-1de9f8e1e029
description: Gateways 表是一个支持表。 每条记录将所涉及的一个网关信息存储在数据库中包含记录的公用电话交换网 (pstn) 呼叫。
ms.openlocfilehash: 16860e924fb69f1dfe337e05c13d54fb66a8ed81
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/27/2019
ms.locfileid: "30899079"
---
# <a name="gateways-table-in-skype-for-business-server-2015"></a><span data-ttu-id="9cd13-104">Gateways 表中的业务服务器 2015 Skype</span><span class="sxs-lookup"><span data-stu-id="9cd13-104">Gateways table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="9cd13-105">Gateways 表是一个支持表。</span><span class="sxs-lookup"><span data-stu-id="9cd13-105">The Gateways table is a supporting table.</span></span> <span data-ttu-id="9cd13-106">每条记录将所涉及的一个网关信息存储在数据库中包含记录的公用电话交换网 (pstn) 呼叫。</span><span class="sxs-lookup"><span data-stu-id="9cd13-106">Each record stores information about one gateway that is involved in public switched telephone network (PSTN) calls that have records in the database.</span></span>
  
|<span data-ttu-id="9cd13-107">**列**</span><span class="sxs-lookup"><span data-stu-id="9cd13-107">**Column**</span></span>|<span data-ttu-id="9cd13-108">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="9cd13-108">**Data Type**</span></span>|<span data-ttu-id="9cd13-109">**键/索引**</span><span class="sxs-lookup"><span data-stu-id="9cd13-109">**Key/Index**</span></span>|<span data-ttu-id="9cd13-110">**详细信息**</span><span class="sxs-lookup"><span data-stu-id="9cd13-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="9cd13-111">**GatewayId**</span><span class="sxs-lookup"><span data-stu-id="9cd13-111">**GatewayId**</span></span> <br/> |<span data-ttu-id="9cd13-112">int</span><span class="sxs-lookup"><span data-stu-id="9cd13-112">int</span></span>  <br/> |<span data-ttu-id="9cd13-113">Primary</span><span class="sxs-lookup"><span data-stu-id="9cd13-113">Primary</span></span>  <br/> |<span data-ttu-id="9cd13-114">标识此网关的唯一编号。</span><span class="sxs-lookup"><span data-stu-id="9cd13-114">Unique number identifying this gateway.</span></span>  <br/> |
|<span data-ttu-id="9cd13-115">**网关**</span><span class="sxs-lookup"><span data-stu-id="9cd13-115">**Gateway**</span></span> <br/> |<span data-ttu-id="9cd13-116">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="9cd13-116">nvarchar(256)</span></span>  <br/> | <br/> |<span data-ttu-id="9cd13-117">网关名称。</span><span class="sxs-lookup"><span data-stu-id="9cd13-117">Gateway name.</span></span>  <br/> |
   


---
title: Gateways 表中的业务服务器 2015 Skype
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: a909daad-d137-45e0-b149-1de9f8e1e029
description: Gateways 表是一个支持表。 每条记录将所涉及的一个网关信息存储在数据库中包含记录的公用电话交换网 (pstn) 呼叫。
ms.openlocfilehash: 2a3429b45a63c0c7765f4e9da0ea2baf3f0d11b1
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "33901036"
---
# <a name="gateways-table-in-skype-for-business-server-2015"></a><span data-ttu-id="95a67-104">Gateways 表中的业务服务器 2015 Skype</span><span class="sxs-lookup"><span data-stu-id="95a67-104">Gateways table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="95a67-105">Gateways 表是一个支持表。</span><span class="sxs-lookup"><span data-stu-id="95a67-105">The Gateways table is a supporting table.</span></span> <span data-ttu-id="95a67-106">每条记录将所涉及的一个网关信息存储在数据库中包含记录的公用电话交换网 (pstn) 呼叫。</span><span class="sxs-lookup"><span data-stu-id="95a67-106">Each record stores information about one gateway that is involved in public switched telephone network (PSTN) calls that have records in the database.</span></span>
  
|<span data-ttu-id="95a67-107">**列**</span><span class="sxs-lookup"><span data-stu-id="95a67-107">**Column**</span></span>|<span data-ttu-id="95a67-108">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="95a67-108">**Data Type**</span></span>|<span data-ttu-id="95a67-109">**键/索引**</span><span class="sxs-lookup"><span data-stu-id="95a67-109">**Key/Index**</span></span>|<span data-ttu-id="95a67-110">**详细信息**</span><span class="sxs-lookup"><span data-stu-id="95a67-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="95a67-111">**GatewayId**</span><span class="sxs-lookup"><span data-stu-id="95a67-111">**GatewayId**</span></span> <br/> |<span data-ttu-id="95a67-112">int</span><span class="sxs-lookup"><span data-stu-id="95a67-112">int</span></span>  <br/> |<span data-ttu-id="95a67-113">Primary</span><span class="sxs-lookup"><span data-stu-id="95a67-113">Primary</span></span>  <br/> |<span data-ttu-id="95a67-114">标识此网关的唯一编号。</span><span class="sxs-lookup"><span data-stu-id="95a67-114">Unique number identifying this gateway.</span></span>  <br/> |
|<span data-ttu-id="95a67-115">**网关**</span><span class="sxs-lookup"><span data-stu-id="95a67-115">**Gateway**</span></span> <br/> |<span data-ttu-id="95a67-116">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="95a67-116">nvarchar(256)</span></span>  <br/> | <br/> |<span data-ttu-id="95a67-117">网关名称。</span><span class="sxs-lookup"><span data-stu-id="95a67-117">Gateway name.</span></span>  <br/> |
   


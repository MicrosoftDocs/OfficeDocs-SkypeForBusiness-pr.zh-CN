---
title: Mcus 视图
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
ms.assetid: 8e8bbb1b-993b-4b66-862b-7e7654777203
description: Mcus 视图存储有关已参与会议会话的 MCU 的信息。 此视图是在 Microsoft Lync Server 2013 中引入的。
ms.openlocfilehash: 3b16505337c241f08b1da99ca2e9e7f8a17a4eaa
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49821462"
---
# <a name="mcus-view"></a><span data-ttu-id="88cb5-104">Mcus 视图</span><span class="sxs-lookup"><span data-stu-id="88cb5-104">Mcus view</span></span>
 
<span data-ttu-id="88cb5-105">Mcus 视图存储有关已参与会议会话的 MCU 的信息。</span><span class="sxs-lookup"><span data-stu-id="88cb5-105">The Mcus view stores information about the MCUs that have participated in conference sessions.</span></span> <span data-ttu-id="88cb5-106">此视图是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="88cb5-106">This view was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="88cb5-107">**列**</span><span class="sxs-lookup"><span data-stu-id="88cb5-107">**Column**</span></span>|<span data-ttu-id="88cb5-108">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="88cb5-108">**Data Type**</span></span>|<span data-ttu-id="88cb5-109">**Details**</span><span class="sxs-lookup"><span data-stu-id="88cb5-109">**Details**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="88cb5-110">**McuId**</span><span class="sxs-lookup"><span data-stu-id="88cb5-110">**McuId**</span></span> <br/> |<span data-ttu-id="88cb5-111">int</span><span class="sxs-lookup"><span data-stu-id="88cb5-111">int</span></span>  <br/> |<span data-ttu-id="88cb5-112">标识 MCU 的唯一编号。</span><span class="sxs-lookup"><span data-stu-id="88cb5-112">Unique number identifying the MCU.</span></span>  <br/> |
|<span data-ttu-id="88cb5-113">**McuUri**</span><span class="sxs-lookup"><span data-stu-id="88cb5-113">**McuUri**</span></span> <br/> |<span data-ttu-id="88cb5-114">nvarchar (450) </span><span class="sxs-lookup"><span data-stu-id="88cb5-114">nvarchar(450)</span></span>  <br/> |<span data-ttu-id="88cb5-115">MCU 的 URI。</span><span class="sxs-lookup"><span data-stu-id="88cb5-115">URI of the MCU.</span></span>  <br/> |
|<span data-ttu-id="88cb5-116">**McuUriType**</span><span class="sxs-lookup"><span data-stu-id="88cb5-116">**McuUriType**</span></span> <br/> |<span data-ttu-id="88cb5-117">nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="88cb5-117">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="88cb5-118">MCU URI 的类型。</span><span class="sxs-lookup"><span data-stu-id="88cb5-118">Type of MCU URI.</span></span> <span data-ttu-id="88cb5-119">有关详细信息， [请参阅 UriTypes](uritypes.md) 表。</span><span class="sxs-lookup"><span data-stu-id="88cb5-119">See the [UriTypes table](uritypes.md) for more information.</span></span> <br/> |
   


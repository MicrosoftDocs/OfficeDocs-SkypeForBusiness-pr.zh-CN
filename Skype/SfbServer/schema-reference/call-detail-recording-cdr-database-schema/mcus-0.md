---
title: Mcus 视图
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
ms.assetid: 8e8bbb1b-993b-4b66-862b-7e7654777203
description: Mcus 视图存储参与会议会话的 MCUs 的相关信息。 此视图已在 Microsoft Lync Server 2013 中引入。
ms.openlocfilehash: eee2438e9a4c6b222f2c9b77e3b02a1a733acbb0
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815070"
---
# <a name="mcus-view"></a><span data-ttu-id="cb4ea-104">Mcus 视图</span><span class="sxs-lookup"><span data-stu-id="cb4ea-104">Mcus view</span></span>
 
<span data-ttu-id="cb4ea-105">Mcus 视图存储参与会议会话的 MCUs 的相关信息。</span><span class="sxs-lookup"><span data-stu-id="cb4ea-105">The Mcus view stores information about the MCUs that have participated in conference sessions.</span></span> <span data-ttu-id="cb4ea-106">此视图已在 Microsoft Lync Server 2013 中引入。</span><span class="sxs-lookup"><span data-stu-id="cb4ea-106">This view was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="cb4ea-107">**列**</span><span class="sxs-lookup"><span data-stu-id="cb4ea-107">**Column**</span></span>|<span data-ttu-id="cb4ea-108">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="cb4ea-108">**Data Type**</span></span>|<span data-ttu-id="cb4ea-109">**详细信息**</span><span class="sxs-lookup"><span data-stu-id="cb4ea-109">**Details**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="cb4ea-110">**McuId**</span><span class="sxs-lookup"><span data-stu-id="cb4ea-110">**McuId**</span></span> <br/> |<span data-ttu-id="cb4ea-111">int</span><span class="sxs-lookup"><span data-stu-id="cb4ea-111">int</span></span>  <br/> |<span data-ttu-id="cb4ea-112">标识 MCU 的唯一号码。</span><span class="sxs-lookup"><span data-stu-id="cb4ea-112">Unique number identifying the MCU.</span></span>  <br/> |
|<span data-ttu-id="cb4ea-113">**McuUri**</span><span class="sxs-lookup"><span data-stu-id="cb4ea-113">**McuUri**</span></span> <br/> |<span data-ttu-id="cb4ea-114">nvarchar （450）</span><span class="sxs-lookup"><span data-stu-id="cb4ea-114">nvarchar(450)</span></span>  <br/> |<span data-ttu-id="cb4ea-115">MCU 的 URI。</span><span class="sxs-lookup"><span data-stu-id="cb4ea-115">URI of the MCU.</span></span>  <br/> |
|<span data-ttu-id="cb4ea-116">**McuUriType**</span><span class="sxs-lookup"><span data-stu-id="cb4ea-116">**McuUriType**</span></span> <br/> |<span data-ttu-id="cb4ea-117">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="cb4ea-117">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="cb4ea-118">MCU URI 的类型。</span><span class="sxs-lookup"><span data-stu-id="cb4ea-118">Type of MCU URI.</span></span> <span data-ttu-id="cb4ea-119">有关详细信息，请参阅[UriTypes 表](uritypes.md)。</span><span class="sxs-lookup"><span data-stu-id="cb4ea-119">See the [UriTypes table](uritypes.md) for more information.</span></span> <br/> |
   


---
title: ConferenceUris 视图
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 9a3cdcea-426e-4b6b-9876-ba746a8de706
description: ConfernceUris 视图存储有关参加讲座的 Uri 信息。 在 Microsoft Lync Server 2013 引入了此视图。
ms.openlocfilehash: 3e3533f693877c9571e9874b5b98173349188f7d
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="conferenceuris-view"></a><span data-ttu-id="04fe4-104">ConferenceUris 视图</span><span class="sxs-lookup"><span data-stu-id="04fe4-104">ConferenceUris view</span></span>
 
<span data-ttu-id="04fe4-105">ConfernceUris 视图存储有关参加讲座的 Uri 信息。</span><span class="sxs-lookup"><span data-stu-id="04fe4-105">The ConfernceUris view stores information about the URIs that have participated in conference sessions.</span></span> <span data-ttu-id="04fe4-106">在 Microsoft Lync Server 2013 引入了此视图。</span><span class="sxs-lookup"><span data-stu-id="04fe4-106">This view was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="04fe4-107">**列**</span><span class="sxs-lookup"><span data-stu-id="04fe4-107">**Column**</span></span>|<span data-ttu-id="04fe4-108">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="04fe4-108">**Data Type**</span></span>|<span data-ttu-id="04fe4-109">**详细信息**</span><span class="sxs-lookup"><span data-stu-id="04fe4-109">**Details**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="04fe4-110">ConferenceUriId</span><span class="sxs-lookup"><span data-stu-id="04fe4-110">ConferenceUriId</span></span>  <br/> |<span data-ttu-id="04fe4-111">int</span><span class="sxs-lookup"><span data-stu-id="04fe4-111">int</span></span>  <br/> |<span data-ttu-id="04fe4-112">会议的 URI 标识的唯一编号。</span><span class="sxs-lookup"><span data-stu-id="04fe4-112">Unique number identifying the conference URI.</span></span>  <br/> |
|<span data-ttu-id="04fe4-113">ConferenceUri</span><span class="sxs-lookup"><span data-stu-id="04fe4-113">ConferenceUri</span></span>  <br/> |<span data-ttu-id="04fe4-114">nvarchar(450)</span><span class="sxs-lookup"><span data-stu-id="04fe4-114">nvarchar(450)</span></span>  <br/> |<span data-ttu-id="04fe4-115">该会议的 URI。</span><span class="sxs-lookup"><span data-stu-id="04fe4-115">URI of the conference.</span></span>  <br/> |
|<span data-ttu-id="04fe4-116">ConferenceUriType</span><span class="sxs-lookup"><span data-stu-id="04fe4-116">ConferenceUriType</span></span>  <br/> |<span data-ttu-id="04fe4-117">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="04fe4-117">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="04fe4-118">会议 URI 的类型。</span><span class="sxs-lookup"><span data-stu-id="04fe4-118">Type of conference URI.</span></span> <span data-ttu-id="04fe4-119">[UriTypes 表](uritypes.md)的详细信息，请参阅。</span><span class="sxs-lookup"><span data-stu-id="04fe4-119">See the [UriTypes table](uritypes.md) for more information.</span></span> <br/> |
   


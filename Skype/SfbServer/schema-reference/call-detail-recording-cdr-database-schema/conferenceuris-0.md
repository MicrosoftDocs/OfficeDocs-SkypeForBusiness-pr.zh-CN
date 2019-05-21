---
title: ConferenceUris 视图
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 9a3cdcea-426e-4b6b-9876-ba746a8de706
description: ConfernceUris 视图存储参与会议会话的 Uri 的相关信息。 此视图已在 Microsoft Lync Server 2013 中引入。
ms.openlocfilehash: 03d8aae303a4161ab847d1b31b358fa236210b57
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34296404"
---
# <a name="conferenceuris-view"></a><span data-ttu-id="f71ba-104">ConferenceUris 视图</span><span class="sxs-lookup"><span data-stu-id="f71ba-104">ConferenceUris view</span></span>
 
<span data-ttu-id="f71ba-105">ConfernceUris 视图存储参与会议会话的 Uri 的相关信息。</span><span class="sxs-lookup"><span data-stu-id="f71ba-105">The ConfernceUris view stores information about the URIs that have participated in conference sessions.</span></span> <span data-ttu-id="f71ba-106">此视图已在 Microsoft Lync Server 2013 中引入。</span><span class="sxs-lookup"><span data-stu-id="f71ba-106">This view was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="f71ba-107">**列**</span><span class="sxs-lookup"><span data-stu-id="f71ba-107">**Column**</span></span>|<span data-ttu-id="f71ba-108">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="f71ba-108">**Data Type**</span></span>|<span data-ttu-id="f71ba-109">**详细信息**</span><span class="sxs-lookup"><span data-stu-id="f71ba-109">**Details**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="f71ba-110">ConferenceUriId</span><span class="sxs-lookup"><span data-stu-id="f71ba-110">ConferenceUriId</span></span>  <br/> |<span data-ttu-id="f71ba-111">int</span><span class="sxs-lookup"><span data-stu-id="f71ba-111">int</span></span>  <br/> |<span data-ttu-id="f71ba-112">标识会议 URI 的唯一编号。</span><span class="sxs-lookup"><span data-stu-id="f71ba-112">Unique number identifying the conference URI.</span></span>  <br/> |
|<span data-ttu-id="f71ba-113">ConferenceUri</span><span class="sxs-lookup"><span data-stu-id="f71ba-113">ConferenceUri</span></span>  <br/> |<span data-ttu-id="f71ba-114">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="f71ba-114">nvarchar(450)</span></span>  <br/> |<span data-ttu-id="f71ba-115">会议的 URI。</span><span class="sxs-lookup"><span data-stu-id="f71ba-115">URI of the conference.</span></span>  <br/> |
|<span data-ttu-id="f71ba-116">ConferenceUriType</span><span class="sxs-lookup"><span data-stu-id="f71ba-116">ConferenceUriType</span></span>  <br/> |<span data-ttu-id="f71ba-117">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="f71ba-117">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="f71ba-118">会议 URI 的类型。</span><span class="sxs-lookup"><span data-stu-id="f71ba-118">Type of conference URI.</span></span> <span data-ttu-id="f71ba-119">有关详细信息, 请参阅[UriTypes 表](uritypes.md)。</span><span class="sxs-lookup"><span data-stu-id="f71ba-119">See the [UriTypes table](uritypes.md) for more information.</span></span> <br/> |
   


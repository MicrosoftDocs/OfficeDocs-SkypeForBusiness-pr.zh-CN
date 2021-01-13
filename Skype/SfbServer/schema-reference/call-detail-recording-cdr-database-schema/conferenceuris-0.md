---
title: ConferenceUris 视图
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
ms.assetid: 9a3cdcea-426e-4b6b-9876-ba746a8de706
description: ConfernceUris 视图存储有关已参与会议会话的 URI 的信息。 此视图是在 Microsoft Lync Server 2013 中引入的。
ms.openlocfilehash: 0c3ab5d72c8058ea7d13d2e54df8cae25bf239c1
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816122"
---
# <a name="conferenceuris-view"></a><span data-ttu-id="39397-104">ConferenceUris 视图</span><span class="sxs-lookup"><span data-stu-id="39397-104">ConferenceUris view</span></span>
 
<span data-ttu-id="39397-105">ConfernceUris 视图存储有关已参与会议会话的 URI 的信息。</span><span class="sxs-lookup"><span data-stu-id="39397-105">The ConfernceUris view stores information about the URIs that have participated in conference sessions.</span></span> <span data-ttu-id="39397-106">此视图是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="39397-106">This view was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="39397-107">**列**</span><span class="sxs-lookup"><span data-stu-id="39397-107">**Column**</span></span>|<span data-ttu-id="39397-108">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="39397-108">**Data Type**</span></span>|<span data-ttu-id="39397-109">**Details**</span><span class="sxs-lookup"><span data-stu-id="39397-109">**Details**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="39397-110">ConferenceUriId</span><span class="sxs-lookup"><span data-stu-id="39397-110">ConferenceUriId</span></span>  <br/> |<span data-ttu-id="39397-111">int</span><span class="sxs-lookup"><span data-stu-id="39397-111">int</span></span>  <br/> |<span data-ttu-id="39397-112">标识此会议 URI 的唯一编号。</span><span class="sxs-lookup"><span data-stu-id="39397-112">Unique number identifying the conference URI.</span></span>  <br/> |
|<span data-ttu-id="39397-113">ConferenceUri</span><span class="sxs-lookup"><span data-stu-id="39397-113">ConferenceUri</span></span>  <br/> |<span data-ttu-id="39397-114">nvarchar (450) </span><span class="sxs-lookup"><span data-stu-id="39397-114">nvarchar(450)</span></span>  <br/> |<span data-ttu-id="39397-115">会议的 URI。</span><span class="sxs-lookup"><span data-stu-id="39397-115">URI of the conference.</span></span>  <br/> |
|<span data-ttu-id="39397-116">ConferenceUriType</span><span class="sxs-lookup"><span data-stu-id="39397-116">ConferenceUriType</span></span>  <br/> |<span data-ttu-id="39397-117">nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="39397-117">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="39397-118">会议 URI 的类型。</span><span class="sxs-lookup"><span data-stu-id="39397-118">Type of conference URI.</span></span> <span data-ttu-id="39397-119">有关详细信息， [请参阅 UriTypes](uritypes.md) 表。</span><span class="sxs-lookup"><span data-stu-id="39397-119">See the [UriTypes table](uritypes.md) for more information.</span></span> <br/> |
   


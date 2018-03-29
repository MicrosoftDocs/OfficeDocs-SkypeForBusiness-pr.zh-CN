---
title: CodecDescription 表
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3598acb8-7ea6-4748-8417-149c971c32a2
description: CodecDescription 表映射到它们相应的编解码器的编解码器的唯一标识符。 编解码器用于编码数字信号传输和广播，然后将解码播放这些信号。 此表是在 Microsoft Lync Server 2013 中引入
ms.openlocfilehash: 49dea2867ef7614fab3015efbd24e6ec47da8c55
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="codecdescription-table"></a><span data-ttu-id="12789-105">CodecDescription 表</span><span class="sxs-lookup"><span data-stu-id="12789-105">CodecDescription table</span></span>
 
<span data-ttu-id="12789-106">CodecDescription 表映射到它们相应的编解码器的编解码器的唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="12789-106">The CodecDescription table maps unique codec identifiers to their corresponding codec.</span></span> <span data-ttu-id="12789-107">编解码器用于编码数字信号传输和广播，然后将解码播放这些信号。</span><span class="sxs-lookup"><span data-stu-id="12789-107">Codecs are used to encode digital signals for transmission and broadcast, and then to decode those signals for playback.</span></span> <span data-ttu-id="12789-108">此表是在 Microsoft Lync Server 2013 中引入</span><span class="sxs-lookup"><span data-stu-id="12789-108">This table was introduced in Microsoft Lync Server 2013</span></span>
  
|<span data-ttu-id="12789-109">**列**</span><span class="sxs-lookup"><span data-stu-id="12789-109">**Column**</span></span>|<span data-ttu-id="12789-110">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="12789-110">**Data Type**</span></span>|<span data-ttu-id="12789-111">**键/索引**</span><span class="sxs-lookup"><span data-stu-id="12789-111">**Key/Index**</span></span>|<span data-ttu-id="12789-112">**详细信息**</span><span class="sxs-lookup"><span data-stu-id="12789-112">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="12789-113">**CodecDescriptionKey**</span><span class="sxs-lookup"><span data-stu-id="12789-113">**CodecDescriptionKey**</span></span> <br/> |<span data-ttu-id="12789-114">smallint</span><span class="sxs-lookup"><span data-stu-id="12789-114">smallint</span></span>  <br/> |<span data-ttu-id="12789-115">Primary</span><span class="sxs-lookup"><span data-stu-id="12789-115">Primary</span></span>  <br/> |<span data-ttu-id="12789-116">分配给该编解码器的唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="12789-116">Unique identifier assigned to the codec.</span></span>  <br/> |
|<span data-ttu-id="12789-117">**CodecDescription**</span><span class="sxs-lookup"><span data-stu-id="12789-117">**CodecDescription**</span></span> <br/> |<span data-ttu-id="12789-118">varchar(256)</span><span class="sxs-lookup"><span data-stu-id="12789-118">varchar(256)</span></span>  <br/> |<span data-ttu-id="12789-119">唯一</span><span class="sxs-lookup"><span data-stu-id="12789-119">Unique</span></span>  <br/> |<span data-ttu-id="12789-120">对应于 CodecDescriptionKey 的编解码器的唯一描述。</span><span class="sxs-lookup"><span data-stu-id="12789-120">Unique description of the codec corresponding to the CodecDescriptionKey.</span></span>  <br/> |
   


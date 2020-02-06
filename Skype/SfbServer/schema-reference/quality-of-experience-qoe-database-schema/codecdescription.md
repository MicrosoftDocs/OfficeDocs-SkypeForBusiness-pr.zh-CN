---
title: CodecDescription 表
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 3598acb8-7ea6-4748-8417-149c971c32a2
description: CodecDescription 表将唯一的编解码器标识符映射到相应的编解码器。 编解码器用于为传输和广播编码数字信号，然后解码这些信号以进行播放。 此表是在 Microsoft Lync Server 2013 中引入的
ms.openlocfilehash: 53410b1bdf4875bd66a80c107dc56c5316fc30a3
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41810360"
---
# <a name="codecdescription-table"></a><span data-ttu-id="516ad-105">CodecDescription 表</span><span class="sxs-lookup"><span data-stu-id="516ad-105">CodecDescription table</span></span>
 
<span data-ttu-id="516ad-106">CodecDescription 表将唯一的编解码器标识符映射到相应的编解码器。</span><span class="sxs-lookup"><span data-stu-id="516ad-106">The CodecDescription table maps unique codec identifiers to their corresponding codec.</span></span> <span data-ttu-id="516ad-107">编解码器用于为传输和广播编码数字信号，然后解码这些信号以进行播放。</span><span class="sxs-lookup"><span data-stu-id="516ad-107">Codecs are used to encode digital signals for transmission and broadcast, and then to decode those signals for playback.</span></span> <span data-ttu-id="516ad-108">此表是在 Microsoft Lync Server 2013 中引入的</span><span class="sxs-lookup"><span data-stu-id="516ad-108">This table was introduced in Microsoft Lync Server 2013</span></span>
  
|<span data-ttu-id="516ad-109">**列**</span><span class="sxs-lookup"><span data-stu-id="516ad-109">**Column**</span></span>|<span data-ttu-id="516ad-110">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="516ad-110">**Data Type**</span></span>|<span data-ttu-id="516ad-111">**键/索引**</span><span class="sxs-lookup"><span data-stu-id="516ad-111">**Key/Index**</span></span>|<span data-ttu-id="516ad-112">**详细信息**</span><span class="sxs-lookup"><span data-stu-id="516ad-112">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="516ad-113">**CodecDescriptionKey**</span><span class="sxs-lookup"><span data-stu-id="516ad-113">**CodecDescriptionKey**</span></span> <br/> |<span data-ttu-id="516ad-114">smallint</span><span class="sxs-lookup"><span data-stu-id="516ad-114">smallint</span></span>  <br/> |<span data-ttu-id="516ad-115">Primary</span><span class="sxs-lookup"><span data-stu-id="516ad-115">Primary</span></span>  <br/> |<span data-ttu-id="516ad-116">分配给编解码器的唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="516ad-116">Unique identifier assigned to the codec.</span></span>  <br/> |
|<span data-ttu-id="516ad-117">**CodecDescription**</span><span class="sxs-lookup"><span data-stu-id="516ad-117">**CodecDescription**</span></span> <br/> |<span data-ttu-id="516ad-118">varchar （256）</span><span class="sxs-lookup"><span data-stu-id="516ad-118">varchar(256)</span></span>  <br/> |<span data-ttu-id="516ad-119">唯一</span><span class="sxs-lookup"><span data-stu-id="516ad-119">Unique</span></span>  <br/> |<span data-ttu-id="516ad-120">与 CodecDescriptionKey 对应的编解码器的唯一说明。</span><span class="sxs-lookup"><span data-stu-id="516ad-120">Unique description of the codec corresponding to the CodecDescriptionKey.</span></span>  <br/> |
   


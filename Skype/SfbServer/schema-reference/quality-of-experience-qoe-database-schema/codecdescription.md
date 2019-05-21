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
localization_priority: Normal
ms.assetid: 3598acb8-7ea6-4748-8417-149c971c32a2
description: CodecDescription 表将唯一的编解码器标识符映射到相应的编解码器。 编解码器用于为传输和广播编码数字信号, 然后解码这些信号以进行播放。 此表是在 Microsoft Lync Server 2013 中引入的
ms.openlocfilehash: 678b458757c54385b608d89efd6b2c621c6cd42f
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295039"
---
# <a name="codecdescription-table"></a><span data-ttu-id="f8e35-105">CodecDescription 表</span><span class="sxs-lookup"><span data-stu-id="f8e35-105">CodecDescription table</span></span>
 
<span data-ttu-id="f8e35-106">CodecDescription 表将唯一的编解码器标识符映射到相应的编解码器。</span><span class="sxs-lookup"><span data-stu-id="f8e35-106">The CodecDescription table maps unique codec identifiers to their corresponding codec.</span></span> <span data-ttu-id="f8e35-107">编解码器用于为传输和广播编码数字信号, 然后解码这些信号以进行播放。</span><span class="sxs-lookup"><span data-stu-id="f8e35-107">Codecs are used to encode digital signals for transmission and broadcast, and then to decode those signals for playback.</span></span> <span data-ttu-id="f8e35-108">此表是在 Microsoft Lync Server 2013 中引入的</span><span class="sxs-lookup"><span data-stu-id="f8e35-108">This table was introduced in Microsoft Lync Server 2013</span></span>
  
|<span data-ttu-id="f8e35-109">**列**</span><span class="sxs-lookup"><span data-stu-id="f8e35-109">**Column**</span></span>|<span data-ttu-id="f8e35-110">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="f8e35-110">**Data Type**</span></span>|<span data-ttu-id="f8e35-111">**键/索引**</span><span class="sxs-lookup"><span data-stu-id="f8e35-111">**Key/Index**</span></span>|<span data-ttu-id="f8e35-112">**详细信息**</span><span class="sxs-lookup"><span data-stu-id="f8e35-112">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="f8e35-113">**CodecDescriptionKey**</span><span class="sxs-lookup"><span data-stu-id="f8e35-113">**CodecDescriptionKey**</span></span> <br/> |<span data-ttu-id="f8e35-114">smallint</span><span class="sxs-lookup"><span data-stu-id="f8e35-114">smallint</span></span>  <br/> |<span data-ttu-id="f8e35-115">Primary</span><span class="sxs-lookup"><span data-stu-id="f8e35-115">Primary</span></span>  <br/> |<span data-ttu-id="f8e35-116">分配给编解码器的唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="f8e35-116">Unique identifier assigned to the codec.</span></span>  <br/> |
|<span data-ttu-id="f8e35-117">**CodecDescription**</span><span class="sxs-lookup"><span data-stu-id="f8e35-117">**CodecDescription**</span></span> <br/> |<span data-ttu-id="f8e35-118">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="f8e35-118">varchar(256)</span></span>  <br/> |<span data-ttu-id="f8e35-119">唯一</span><span class="sxs-lookup"><span data-stu-id="f8e35-119">Unique</span></span>  <br/> |<span data-ttu-id="f8e35-120">与 CodecDescriptionKey 对应的编解码器的唯一说明。</span><span class="sxs-lookup"><span data-stu-id="f8e35-120">Unique description of the codec corresponding to the CodecDescriptionKey.</span></span>  <br/> |
   


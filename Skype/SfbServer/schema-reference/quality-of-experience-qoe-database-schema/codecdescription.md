---
title: CodecDescription 表
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3598acb8-7ea6-4748-8417-149c971c32a2
description: CodecDescription 表将唯一的编解码器标识符映射到其对应的编解码器。 编解码器用于编码数字信号传输和广播，然后进行解码播放这些信号。 此表是在 Microsoft Lync Server 2013 中引入
ms.openlocfilehash: 9881c802e332801d4990bf01894d5f8b68150fc2
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "33920101"
---
# <a name="codecdescription-table"></a><span data-ttu-id="61d80-105">CodecDescription 表</span><span class="sxs-lookup"><span data-stu-id="61d80-105">CodecDescription table</span></span>
 
<span data-ttu-id="61d80-106">CodecDescription 表将唯一的编解码器标识符映射到其对应的编解码器。</span><span class="sxs-lookup"><span data-stu-id="61d80-106">The CodecDescription table maps unique codec identifiers to their corresponding codec.</span></span> <span data-ttu-id="61d80-107">编解码器用于编码数字信号传输和广播，然后进行解码播放这些信号。</span><span class="sxs-lookup"><span data-stu-id="61d80-107">Codecs are used to encode digital signals for transmission and broadcast, and then to decode those signals for playback.</span></span> <span data-ttu-id="61d80-108">此表是在 Microsoft Lync Server 2013 中引入</span><span class="sxs-lookup"><span data-stu-id="61d80-108">This table was introduced in Microsoft Lync Server 2013</span></span>
  
|<span data-ttu-id="61d80-109">**列**</span><span class="sxs-lookup"><span data-stu-id="61d80-109">**Column**</span></span>|<span data-ttu-id="61d80-110">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="61d80-110">**Data Type**</span></span>|<span data-ttu-id="61d80-111">**键/索引**</span><span class="sxs-lookup"><span data-stu-id="61d80-111">**Key/Index**</span></span>|<span data-ttu-id="61d80-112">**详细信息**</span><span class="sxs-lookup"><span data-stu-id="61d80-112">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="61d80-113">**CodecDescriptionKey**</span><span class="sxs-lookup"><span data-stu-id="61d80-113">**CodecDescriptionKey**</span></span> <br/> |<span data-ttu-id="61d80-114">smallint</span><span class="sxs-lookup"><span data-stu-id="61d80-114">smallint</span></span>  <br/> |<span data-ttu-id="61d80-115">Primary</span><span class="sxs-lookup"><span data-stu-id="61d80-115">Primary</span></span>  <br/> |<span data-ttu-id="61d80-116">分配给编解码器的唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="61d80-116">Unique identifier assigned to the codec.</span></span>  <br/> |
|<span data-ttu-id="61d80-117">**CodecDescription**</span><span class="sxs-lookup"><span data-stu-id="61d80-117">**CodecDescription**</span></span> <br/> |<span data-ttu-id="61d80-118">varchar(256)</span><span class="sxs-lookup"><span data-stu-id="61d80-118">varchar(256)</span></span>  <br/> |<span data-ttu-id="61d80-119">唯一</span><span class="sxs-lookup"><span data-stu-id="61d80-119">Unique</span></span>  <br/> |<span data-ttu-id="61d80-120">与 CodecDescriptionKey 对应的编解码器的唯一说明。</span><span class="sxs-lookup"><span data-stu-id="61d80-120">Unique description of the codec corresponding to the CodecDescriptionKey.</span></span>  <br/> |
   


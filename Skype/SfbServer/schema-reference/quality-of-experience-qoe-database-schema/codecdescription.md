---
title: CodecDescription 表
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 3598acb8-7ea6-4748-8417-149c971c32a2
description: CodecDescription 表可将唯一编解码器标识符映射到其相应的编解码器。 编解码器用于对传输和广播的数字信号进行编码，然后解码这些信号以进行播放。 此表在 Microsoft Lync Server 2013 中引入
ms.openlocfilehash: 95ba2218ff20aa6c67de6f60d6966916b6648a58
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49831342"
---
# <a name="codecdescription-table"></a><span data-ttu-id="17228-105">CodecDescription 表</span><span class="sxs-lookup"><span data-stu-id="17228-105">CodecDescription table</span></span>
 
<span data-ttu-id="17228-106">CodecDescription 表可将唯一编解码器标识符映射到其相应的编解码器。</span><span class="sxs-lookup"><span data-stu-id="17228-106">The CodecDescription table maps unique codec identifiers to their corresponding codec.</span></span> <span data-ttu-id="17228-107">编解码器用于对传输和广播的数字信号进行编码，然后解码这些信号以进行播放。</span><span class="sxs-lookup"><span data-stu-id="17228-107">Codecs are used to encode digital signals for transmission and broadcast, and then to decode those signals for playback.</span></span> <span data-ttu-id="17228-108">此表在 Microsoft Lync Server 2013 中引入</span><span class="sxs-lookup"><span data-stu-id="17228-108">This table was introduced in Microsoft Lync Server 2013</span></span>
  
|<span data-ttu-id="17228-109">**列**</span><span class="sxs-lookup"><span data-stu-id="17228-109">**Column**</span></span>|<span data-ttu-id="17228-110">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="17228-110">**Data Type**</span></span>|<span data-ttu-id="17228-111">**键/索引**</span><span class="sxs-lookup"><span data-stu-id="17228-111">**Key/Index**</span></span>|<span data-ttu-id="17228-112">**Details**</span><span class="sxs-lookup"><span data-stu-id="17228-112">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="17228-113">**CodecDescriptionKey**</span><span class="sxs-lookup"><span data-stu-id="17228-113">**CodecDescriptionKey**</span></span> <br/> |<span data-ttu-id="17228-114">smallint</span><span class="sxs-lookup"><span data-stu-id="17228-114">smallint</span></span>  <br/> |<span data-ttu-id="17228-115">主</span><span class="sxs-lookup"><span data-stu-id="17228-115">Primary</span></span>  <br/> |<span data-ttu-id="17228-116">分配给编解码器的唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="17228-116">Unique identifier assigned to the codec.</span></span>  <br/> |
|<span data-ttu-id="17228-117">**CodecDescription**</span><span class="sxs-lookup"><span data-stu-id="17228-117">**CodecDescription**</span></span> <br/> |<span data-ttu-id="17228-118">varchar (256) </span><span class="sxs-lookup"><span data-stu-id="17228-118">varchar(256)</span></span>  <br/> |<span data-ttu-id="17228-119">独特</span><span class="sxs-lookup"><span data-stu-id="17228-119">Unique</span></span>  <br/> |<span data-ttu-id="17228-120">与 CodecDescriptionKey 对应的编解码器的唯一说明。</span><span class="sxs-lookup"><span data-stu-id="17228-120">Unique description of the codec corresponding to the CodecDescriptionKey.</span></span>  <br/> |
   


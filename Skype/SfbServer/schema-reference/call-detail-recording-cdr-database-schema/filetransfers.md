---
title: FileTransfers 视图
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e52c3ad0-152e-4a18-af1c-1aff0d205151
description: FileTransfer 视图存储有关对等文件传输会话的信息。 此视图已在 Microsoft Lync Server 2013 中引入。
ms.openlocfilehash: 303a8cf624b19f9701cabbd491fcb7b08dfba25d
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34296236"
---
# <a name="filetransfers-view"></a><span data-ttu-id="47281-104">FileTransfers 视图</span><span class="sxs-lookup"><span data-stu-id="47281-104">FileTransfers view</span></span>
 
<span data-ttu-id="47281-105">FileTransfer 视图存储有关对等文件传输会话的信息。</span><span class="sxs-lookup"><span data-stu-id="47281-105">The FileTransfer view stores information about peer-to-peer file transfer sessions.</span></span> <span data-ttu-id="47281-106">此视图已在 Microsoft Lync Server 2013 中引入。</span><span class="sxs-lookup"><span data-stu-id="47281-106">This view was introduced in Microsoft Lync Server 2013.</span></span>
  
> [!NOTE]
> <span data-ttu-id="47281-107">FileTransfers 视图包含[SessionDetails 视图](sessiondetails-0.md)中的所有列以及下面列出的列。</span><span class="sxs-lookup"><span data-stu-id="47281-107">The FileTransfers view contains all of the columns in the [SessionDetails view](sessiondetails-0.md) in addition the columns listed below.</span></span>
  
|<span data-ttu-id="47281-108">**列**</span><span class="sxs-lookup"><span data-stu-id="47281-108">**Column**</span></span>|<span data-ttu-id="47281-109">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="47281-109">**Data Type**</span></span>|<span data-ttu-id="47281-110">**详细信息**</span><span class="sxs-lookup"><span data-stu-id="47281-110">**Details**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="47281-111">**FileName**</span><span class="sxs-lookup"><span data-stu-id="47281-111">**FileName**</span></span> <br/> |<span data-ttu-id="47281-112">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="47281-112">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="47281-113">已传输的文件的名称。</span><span class="sxs-lookup"><span data-stu-id="47281-113">Name of the file transferred.</span></span>  <br/> |
|<span data-ttu-id="47281-114">**票证**</span><span class="sxs-lookup"><span data-stu-id="47281-114">**Cookie**</span></span> <br/> |<span data-ttu-id="47281-115">nvarchar</span><span class="sxs-lookup"><span data-stu-id="47281-115">nvarchar(128)</span></span>  <br/> |<span data-ttu-id="47281-116">用于标识要与此邮件关联的每个后续消息。</span><span class="sxs-lookup"><span data-stu-id="47281-116">Used to identify every follow-up message as being associated with this one.</span></span>  <br/> |
|<span data-ttu-id="47281-117">**FileIdentity**</span><span class="sxs-lookup"><span data-stu-id="47281-117">**FileIdentity**</span></span> <br/> |<span data-ttu-id="47281-118">标识符</span><span class="sxs-lookup"><span data-stu-id="47281-118">uniqueidentifier</span></span>  <br/> |<span data-ttu-id="47281-119">唯一标识符, 用于区分涉及相同文件名的文件传输。</span><span class="sxs-lookup"><span data-stu-id="47281-119">Unique identifier to distinguish between file transfers involving the same file name.</span></span>  <br/> |
|<span data-ttu-id="47281-120">**容纳**</span><span class="sxs-lookup"><span data-stu-id="47281-120">**Accept**</span></span> <br/> |<span data-ttu-id="47281-121">bit</span><span class="sxs-lookup"><span data-stu-id="47281-121">bit</span></span>  <br/> |<span data-ttu-id="47281-122">可以为 TRUE 或 NULL。</span><span class="sxs-lookup"><span data-stu-id="47281-122">Can be TRUE or NULL.</span></span> <span data-ttu-id="47281-123">如果为 TRUE, 则 "拒绝" 和 "取消" 将为 NULL。</span><span class="sxs-lookup"><span data-stu-id="47281-123">If TRUE, then Reject and Cancel will be NULL.</span></span>  <br/> |
|<span data-ttu-id="47281-124">**&**</span><span class="sxs-lookup"><span data-stu-id="47281-124">**Reject**</span></span> <br/> |<span data-ttu-id="47281-125">bit</span><span class="sxs-lookup"><span data-stu-id="47281-125">bit</span></span>  <br/> |<span data-ttu-id="47281-126">可以为 TRUE 或 NULL。</span><span class="sxs-lookup"><span data-stu-id="47281-126">Can be TRUE or NULL.</span></span> <span data-ttu-id="47281-127">如果为 TRUE, 则 "接受" 和 "取消" 将为 NULL。</span><span class="sxs-lookup"><span data-stu-id="47281-127">If TRUE, then Accept and Cancel will be NULL.</span></span>  <br/> |
|<span data-ttu-id="47281-128">**取消**</span><span class="sxs-lookup"><span data-stu-id="47281-128">**Cancel**</span></span> <br/> |<span data-ttu-id="47281-129">bit</span><span class="sxs-lookup"><span data-stu-id="47281-129">bit</span></span>  <br/> |<span data-ttu-id="47281-130">可以为 TRUE 或 NULL。</span><span class="sxs-lookup"><span data-stu-id="47281-130">Can be TRUE or NULL.</span></span> <span data-ttu-id="47281-131">如果为 TRUE, 则 "接受" 和 "拒绝" 将为 NULL。</span><span class="sxs-lookup"><span data-stu-id="47281-131">If TRUE, then Accept and Reject will be NULL.</span></span>  <br/> |
   


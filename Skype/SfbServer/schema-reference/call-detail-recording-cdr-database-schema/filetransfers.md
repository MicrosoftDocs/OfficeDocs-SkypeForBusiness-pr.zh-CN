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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: e52c3ad0-152e-4a18-af1c-1aff0d205151
description: FileTransfer 视图存储有关对等文件传输会话的信息。 此视图已在 Microsoft Lync Server 2013 中引入。
ms.openlocfilehash: d650c04b8dada5828eed5d7bc3039cb77570ce2b
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815200"
---
# <a name="filetransfers-view"></a><span data-ttu-id="f8a9e-104">FileTransfers 视图</span><span class="sxs-lookup"><span data-stu-id="f8a9e-104">FileTransfers view</span></span>
 
<span data-ttu-id="f8a9e-105">FileTransfer 视图存储有关对等文件传输会话的信息。</span><span class="sxs-lookup"><span data-stu-id="f8a9e-105">The FileTransfer view stores information about peer-to-peer file transfer sessions.</span></span> <span data-ttu-id="f8a9e-106">此视图已在 Microsoft Lync Server 2013 中引入。</span><span class="sxs-lookup"><span data-stu-id="f8a9e-106">This view was introduced in Microsoft Lync Server 2013.</span></span>
  
> [!NOTE]
> <span data-ttu-id="f8a9e-107">FileTransfers 视图包含[SessionDetails 视图](sessiondetails-0.md)中的所有列以及下面列出的列。</span><span class="sxs-lookup"><span data-stu-id="f8a9e-107">The FileTransfers view contains all of the columns in the [SessionDetails view](sessiondetails-0.md) in addition the columns listed below.</span></span>
  
|<span data-ttu-id="f8a9e-108">**列**</span><span class="sxs-lookup"><span data-stu-id="f8a9e-108">**Column**</span></span>|<span data-ttu-id="f8a9e-109">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="f8a9e-109">**Data Type**</span></span>|<span data-ttu-id="f8a9e-110">**详细信息**</span><span class="sxs-lookup"><span data-stu-id="f8a9e-110">**Details**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="f8a9e-111">**FileName**</span><span class="sxs-lookup"><span data-stu-id="f8a9e-111">**FileName**</span></span> <br/> |<span data-ttu-id="f8a9e-112">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="f8a9e-112">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="f8a9e-113">已传输的文件的名称。</span><span class="sxs-lookup"><span data-stu-id="f8a9e-113">Name of the file transferred.</span></span>  <br/> |
|<span data-ttu-id="f8a9e-114">**票证**</span><span class="sxs-lookup"><span data-stu-id="f8a9e-114">**Cookie**</span></span> <br/> |<span data-ttu-id="f8a9e-115">nvarchar</span><span class="sxs-lookup"><span data-stu-id="f8a9e-115">nvarchar(128)</span></span>  <br/> |<span data-ttu-id="f8a9e-116">用于标识要与此邮件关联的每个后续消息。</span><span class="sxs-lookup"><span data-stu-id="f8a9e-116">Used to identify every follow-up message as being associated with this one.</span></span>  <br/> |
|<span data-ttu-id="f8a9e-117">**FileIdentity**</span><span class="sxs-lookup"><span data-stu-id="f8a9e-117">**FileIdentity**</span></span> <br/> |<span data-ttu-id="f8a9e-118">标识符</span><span class="sxs-lookup"><span data-stu-id="f8a9e-118">uniqueidentifier</span></span>  <br/> |<span data-ttu-id="f8a9e-119">唯一标识符，用于区分涉及相同文件名的文件传输。</span><span class="sxs-lookup"><span data-stu-id="f8a9e-119">Unique identifier to distinguish between file transfers involving the same file name.</span></span>  <br/> |
|<span data-ttu-id="f8a9e-120">**容纳**</span><span class="sxs-lookup"><span data-stu-id="f8a9e-120">**Accept**</span></span> <br/> |<span data-ttu-id="f8a9e-121">bit</span><span class="sxs-lookup"><span data-stu-id="f8a9e-121">bit</span></span>  <br/> |<span data-ttu-id="f8a9e-122">可以为 TRUE 或 NULL。</span><span class="sxs-lookup"><span data-stu-id="f8a9e-122">Can be TRUE or NULL.</span></span> <span data-ttu-id="f8a9e-123">如果为 TRUE，则 "拒绝" 和 "取消" 将为 NULL。</span><span class="sxs-lookup"><span data-stu-id="f8a9e-123">If TRUE, then Reject and Cancel will be NULL.</span></span>  <br/> |
|<span data-ttu-id="f8a9e-124">**&**</span><span class="sxs-lookup"><span data-stu-id="f8a9e-124">**Reject**</span></span> <br/> |<span data-ttu-id="f8a9e-125">bit</span><span class="sxs-lookup"><span data-stu-id="f8a9e-125">bit</span></span>  <br/> |<span data-ttu-id="f8a9e-126">可以为 TRUE 或 NULL。</span><span class="sxs-lookup"><span data-stu-id="f8a9e-126">Can be TRUE or NULL.</span></span> <span data-ttu-id="f8a9e-127">如果为 TRUE，则 "接受" 和 "取消" 将为 NULL。</span><span class="sxs-lookup"><span data-stu-id="f8a9e-127">If TRUE, then Accept and Cancel will be NULL.</span></span>  <br/> |
|<span data-ttu-id="f8a9e-128">**取消**</span><span class="sxs-lookup"><span data-stu-id="f8a9e-128">**Cancel**</span></span> <br/> |<span data-ttu-id="f8a9e-129">bit</span><span class="sxs-lookup"><span data-stu-id="f8a9e-129">bit</span></span>  <br/> |<span data-ttu-id="f8a9e-130">可以为 TRUE 或 NULL。</span><span class="sxs-lookup"><span data-stu-id="f8a9e-130">Can be TRUE or NULL.</span></span> <span data-ttu-id="f8a9e-131">如果为 TRUE，则 "接受" 和 "拒绝" 将为 NULL。</span><span class="sxs-lookup"><span data-stu-id="f8a9e-131">If TRUE, then Accept and Reject will be NULL.</span></span>  <br/> |
   


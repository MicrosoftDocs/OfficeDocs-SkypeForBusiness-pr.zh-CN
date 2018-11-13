---
title: FileTransfers 视图
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e52c3ad0-152e-4a18-af1c-1aff0d205151
description: FileTranfer 视图存储有关对等文件传输会话的信息。 此视图是在 Microsoft Lync Server 2013 中引入的。
ms.openlocfilehash: 5b7369769d8091aa3354ea364c7073dfa388986f
ms.sourcegitcommit: 1cb5a3570032250aecd5a1a839cbbe4daeb77f2c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/13/2018
ms.locfileid: "26296408"
---
# <a name="filetransfers-view"></a><span data-ttu-id="f022a-104">FileTransfers 视图</span><span class="sxs-lookup"><span data-stu-id="f022a-104">FileTransfers view</span></span>
 
<span data-ttu-id="f022a-105">FileTranfer 视图存储有关对等文件传输会话的信息。</span><span class="sxs-lookup"><span data-stu-id="f022a-105">The FileTranfer view stores information about peer-to-peer file transfer sessions.</span></span> <span data-ttu-id="f022a-106">此视图是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="f022a-106">This view was introduced in Microsoft Lync Server 2013.</span></span>
  
> [!NOTE]
> <span data-ttu-id="f022a-107">FileTransfers 视图还包含[SessionDetails view](sessiondetails-0.md)中的列的所有中下面列出的列。</span><span class="sxs-lookup"><span data-stu-id="f022a-107">The FileTransfers view contains all of the columns in the [SessionDetails view](sessiondetails-0.md) in addition the columns listed below.</span></span>
  
|<span data-ttu-id="f022a-108">**列**</span><span class="sxs-lookup"><span data-stu-id="f022a-108">**Column**</span></span>|<span data-ttu-id="f022a-109">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="f022a-109">**Data Type**</span></span>|<span data-ttu-id="f022a-110">**详细信息**</span><span class="sxs-lookup"><span data-stu-id="f022a-110">**Details**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="f022a-111">**FileName**</span><span class="sxs-lookup"><span data-stu-id="f022a-111">**FileName**</span></span> <br/> |<span data-ttu-id="f022a-112">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="f022a-112">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="f022a-113">传输文件的名称。</span><span class="sxs-lookup"><span data-stu-id="f022a-113">Name of the file transferred.</span></span>  <br/> |
|<span data-ttu-id="f022a-114">**Cookie**</span><span class="sxs-lookup"><span data-stu-id="f022a-114">**Cookie**</span></span> <br/> |<span data-ttu-id="f022a-115">nvarchar(128)</span><span class="sxs-lookup"><span data-stu-id="f022a-115">nvarchar(128)</span></span>  <br/> |<span data-ttu-id="f022a-116">用于标识与此关联时每个后续消息。</span><span class="sxs-lookup"><span data-stu-id="f022a-116">Used to identify every follow-up message as being associated with this one.</span></span>  <br/> |
|<span data-ttu-id="f022a-117">**FileIdentity**</span><span class="sxs-lookup"><span data-stu-id="f022a-117">**FileIdentity**</span></span> <br/> |<span data-ttu-id="f022a-118">唯一标识符</span><span class="sxs-lookup"><span data-stu-id="f022a-118">uniqueidentifier</span></span>  <br/> |<span data-ttu-id="f022a-119">来区分涉及同一文件名的文件传输的唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="f022a-119">Unique identifier to distinguish between file transfers involving the same file name.</span></span>  <br/> |
|<span data-ttu-id="f022a-120">**接受**</span><span class="sxs-lookup"><span data-stu-id="f022a-120">**Accept**</span></span> <br/> |<span data-ttu-id="f022a-121">bit</span><span class="sxs-lookup"><span data-stu-id="f022a-121">bit</span></span>  <br/> |<span data-ttu-id="f022a-122">可以是 TRUE 或 NULL。</span><span class="sxs-lookup"><span data-stu-id="f022a-122">Can be TRUE or NULL.</span></span> <span data-ttu-id="f022a-123">如果为 TRUE，则拒绝和取消将为 NULL。</span><span class="sxs-lookup"><span data-stu-id="f022a-123">If TRUE, then Reject and Cancel will be NULL.</span></span>  <br/> |
|<span data-ttu-id="f022a-124">**拒绝**</span><span class="sxs-lookup"><span data-stu-id="f022a-124">**Reject**</span></span> <br/> |<span data-ttu-id="f022a-125">bit</span><span class="sxs-lookup"><span data-stu-id="f022a-125">bit</span></span>  <br/> |<span data-ttu-id="f022a-126">可以是 TRUE 或 NULL。</span><span class="sxs-lookup"><span data-stu-id="f022a-126">Can be TRUE or NULL.</span></span> <span data-ttu-id="f022a-127">如果为 TRUE，接受和取消都将为 NULL。</span><span class="sxs-lookup"><span data-stu-id="f022a-127">If TRUE, then Accept and Cancel will be NULL.</span></span>  <br/> |
|<span data-ttu-id="f022a-128">**取消**</span><span class="sxs-lookup"><span data-stu-id="f022a-128">**Cancel**</span></span> <br/> |<span data-ttu-id="f022a-129">bit</span><span class="sxs-lookup"><span data-stu-id="f022a-129">bit</span></span>  <br/> |<span data-ttu-id="f022a-130">可以是 TRUE 或 NULL。</span><span class="sxs-lookup"><span data-stu-id="f022a-130">Can be TRUE or NULL.</span></span> <span data-ttu-id="f022a-131">如果为 true，则接受和拒绝都将为 NULL。</span><span class="sxs-lookup"><span data-stu-id="f022a-131">If TRUE, then Accept and Reject will be NULL.</span></span>  <br/> |
   


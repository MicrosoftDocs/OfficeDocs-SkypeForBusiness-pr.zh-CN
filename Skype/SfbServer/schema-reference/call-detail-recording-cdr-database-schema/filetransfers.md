---
title: FileTransfers 视图
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
ms.assetid: e52c3ad0-152e-4a18-af1c-1aff0d205151
description: FileTransfer 视图存储有关对等文件传输会话的信息。 此视图是在 Microsoft Lync Server 2013 中引入的。
ms.openlocfilehash: 8b3c2db012b8969bd4b5b75ca19ed090f8227c53
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49821682"
---
# <a name="filetransfers-view"></a><span data-ttu-id="63247-104">FileTransfers 视图</span><span class="sxs-lookup"><span data-stu-id="63247-104">FileTransfers view</span></span>
 
<span data-ttu-id="63247-105">FileTransfer 视图存储有关对等文件传输会话的信息。</span><span class="sxs-lookup"><span data-stu-id="63247-105">The FileTransfer view stores information about peer-to-peer file transfer sessions.</span></span> <span data-ttu-id="63247-106">此视图是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="63247-106">This view was introduced in Microsoft Lync Server 2013.</span></span>
  
> [!NOTE]
> <span data-ttu-id="63247-107">FileTransfers 视图包含 [SessionDetails](sessiondetails-0.md) 视图中的所有列以及下面列出的列。</span><span class="sxs-lookup"><span data-stu-id="63247-107">The FileTransfers view contains all of the columns in the [SessionDetails view](sessiondetails-0.md) in addition the columns listed below.</span></span>
  
|<span data-ttu-id="63247-108">**列**</span><span class="sxs-lookup"><span data-stu-id="63247-108">**Column**</span></span>|<span data-ttu-id="63247-109">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="63247-109">**Data Type**</span></span>|<span data-ttu-id="63247-110">**Details**</span><span class="sxs-lookup"><span data-stu-id="63247-110">**Details**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="63247-111">**FileName**</span><span class="sxs-lookup"><span data-stu-id="63247-111">**FileName**</span></span> <br/> |<span data-ttu-id="63247-112">nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="63247-112">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="63247-113">文件传输的名称。</span><span class="sxs-lookup"><span data-stu-id="63247-113">Name of the file transferred.</span></span>  <br/> |
|<span data-ttu-id="63247-114">**Cookie**</span><span class="sxs-lookup"><span data-stu-id="63247-114">**Cookie**</span></span> <br/> |<span data-ttu-id="63247-115">nvarchar (128) </span><span class="sxs-lookup"><span data-stu-id="63247-115">nvarchar(128)</span></span>  <br/> |<span data-ttu-id="63247-116">用于标识与此关联时的每条后续消息。</span><span class="sxs-lookup"><span data-stu-id="63247-116">Used to identify every follow-up message as being associated with this one.</span></span>  <br/> |
|<span data-ttu-id="63247-117">**FileIdentity**</span><span class="sxs-lookup"><span data-stu-id="63247-117">**FileIdentity**</span></span> <br/> |<span data-ttu-id="63247-118">uniqueidentifier</span><span class="sxs-lookup"><span data-stu-id="63247-118">uniqueidentifier</span></span>  <br/> |<span data-ttu-id="63247-119">涉及相同文件名的文件传输之间标识的唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="63247-119">Unique identifier to distinguish between file transfers involving the same file name.</span></span>  <br/> |
|<span data-ttu-id="63247-120">**Accept**</span><span class="sxs-lookup"><span data-stu-id="63247-120">**Accept**</span></span> <br/> |<span data-ttu-id="63247-121">bit</span><span class="sxs-lookup"><span data-stu-id="63247-121">bit</span></span>  <br/> |<span data-ttu-id="63247-p103">可以是 TRUE 或 NULL。如果是 TRUE，则拒绝和取消将为 NULL。</span><span class="sxs-lookup"><span data-stu-id="63247-p103">Can be TRUE or NULL. If TRUE, then Reject and Cancel will be NULL.</span></span>  <br/> |
|<span data-ttu-id="63247-124">**Reject**</span><span class="sxs-lookup"><span data-stu-id="63247-124">**Reject**</span></span> <br/> |<span data-ttu-id="63247-125">bit</span><span class="sxs-lookup"><span data-stu-id="63247-125">bit</span></span>  <br/> |<span data-ttu-id="63247-p104">可以是 TRUE 或 NULL。如果是 TRUE，则接受和取消将为 NULL。</span><span class="sxs-lookup"><span data-stu-id="63247-p104">Can be TRUE or NULL. If TRUE, then Accept and Cancel will be NULL.</span></span>  <br/> |
|<span data-ttu-id="63247-128">**Cancel**</span><span class="sxs-lookup"><span data-stu-id="63247-128">**Cancel**</span></span> <br/> |<span data-ttu-id="63247-129">bit</span><span class="sxs-lookup"><span data-stu-id="63247-129">bit</span></span>  <br/> |<span data-ttu-id="63247-p105">可以是 TRUE 或 NULL。如果是 TRUE，则接受和拒绝将为 NULL。</span><span class="sxs-lookup"><span data-stu-id="63247-p105">Can be TRUE or NULL. If TRUE, then Accept and Reject will be NULL.</span></span>  <br/> |
   


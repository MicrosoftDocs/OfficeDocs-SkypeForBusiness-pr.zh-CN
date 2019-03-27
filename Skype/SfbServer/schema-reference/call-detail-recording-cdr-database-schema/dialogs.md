---
title: Dialogs 表中的业务服务器 2015 Skype
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 487a430b-af66-4ea6-b28e-4e33cfdb7f9e
description: Dialogs 表是一个支持表，用于存储对等会话的 Dialogid 的信息。
ms.openlocfilehash: af7816c202f995e826567391bf32c5c32a2d0d94
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/27/2019
ms.locfileid: "30889626"
---
# <a name="dialogs-table-in-skype-for-business-server-2015"></a><span data-ttu-id="f7c2b-103">Dialogs 表中的业务服务器 2015 Skype</span><span class="sxs-lookup"><span data-stu-id="f7c2b-103">Dialogs table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="f7c2b-104">Dialogs 表是一个支持表，用于存储对等会话的 Dialogid 的信息。</span><span class="sxs-lookup"><span data-stu-id="f7c2b-104">The Dialogs table is a supporting table that stores the information about DialogIDs for peer-to-peer sessions.</span></span>
  
|<span data-ttu-id="f7c2b-105">**列**</span><span class="sxs-lookup"><span data-stu-id="f7c2b-105">**Column**</span></span>|<span data-ttu-id="f7c2b-106">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="f7c2b-106">**Data Type**</span></span>|<span data-ttu-id="f7c2b-107">**键/索引**</span><span class="sxs-lookup"><span data-stu-id="f7c2b-107">**Key/Index**</span></span>|<span data-ttu-id="f7c2b-108">**详细信息**</span><span class="sxs-lookup"><span data-stu-id="f7c2b-108">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="f7c2b-109">**SessionIdTime**</span><span class="sxs-lookup"><span data-stu-id="f7c2b-109">**SessionIdTime**</span></span> <br/> |<span data-ttu-id="f7c2b-110">datetime</span><span class="sxs-lookup"><span data-stu-id="f7c2b-110">datetime</span></span>  <br/> |<span data-ttu-id="f7c2b-111">Primary</span><span class="sxs-lookup"><span data-stu-id="f7c2b-111">Primary</span></span>  <br/> |<span data-ttu-id="f7c2b-112">会话请求; 的时间与 SessionIDSeq 结合使用，来唯一地标识会话。</span><span class="sxs-lookup"><span data-stu-id="f7c2b-112">Time of session request; used in conjunction with SessionIDSeq to uniquely identify a session.</span></span>  <br/> |
|<span data-ttu-id="f7c2b-113">**SessionIdSeq**</span><span class="sxs-lookup"><span data-stu-id="f7c2b-113">**SessionIdSeq**</span></span> <br/> |<span data-ttu-id="f7c2b-114">int</span><span class="sxs-lookup"><span data-stu-id="f7c2b-114">int</span></span>  <br/> |<span data-ttu-id="f7c2b-115">Primary</span><span class="sxs-lookup"><span data-stu-id="f7c2b-115">Primary</span></span>  <br/> |<span data-ttu-id="f7c2b-116">标识会话的 ID 号。</span><span class="sxs-lookup"><span data-stu-id="f7c2b-116">ID number to identify the session.</span></span> <span data-ttu-id="f7c2b-117">与 SessionIDTime 结合使用，来唯一地标识会话。</span><span class="sxs-lookup"><span data-stu-id="f7c2b-117">Used in conjunction with SessionIDTime to uniquely identify a session.</span></span>  <br/> |
|<span data-ttu-id="f7c2b-118">**ExternalChecksum**</span><span class="sxs-lookup"><span data-stu-id="f7c2b-118">**ExternalChecksum**</span></span> <br/> |<span data-ttu-id="f7c2b-119">int</span><span class="sxs-lookup"><span data-stu-id="f7c2b-119">int</span></span>  <br/> | <br/> |<span data-ttu-id="f7c2b-120">ExternalID 的校验和。</span><span class="sxs-lookup"><span data-stu-id="f7c2b-120">Checksum of the ExternalID.</span></span> <span data-ttu-id="f7c2b-121">使用此字段来提高的搜索数据库的速度。</span><span class="sxs-lookup"><span data-stu-id="f7c2b-121">This field is used to increase the speed of database searches.</span></span>  <br/> |
|<span data-ttu-id="f7c2b-122">**ExternalId**</span><span class="sxs-lookup"><span data-stu-id="f7c2b-122">**ExternalId**</span></span> <br/> |<span data-ttu-id="f7c2b-123">varbinary(775)</span><span class="sxs-lookup"><span data-stu-id="f7c2b-123">varbinary(775)</span></span>  <br/> | <br/> |<span data-ttu-id="f7c2b-124">SIP 对话 ID，存储为二进制文件。</span><span class="sxs-lookup"><span data-stu-id="f7c2b-124">SIP dialog ID, stored as a binary.</span></span> <span data-ttu-id="f7c2b-125">二进制文件格式为：</span><span class="sxs-lookup"><span data-stu-id="f7c2b-125">The format of the binary is:</span></span>  <br/> <span data-ttu-id="f7c2b-126">对话框; 从标记; 到标记</span><span class="sxs-lookup"><span data-stu-id="f7c2b-126">dialog;from-tag;to-tag</span></span>  <br/> <span data-ttu-id="f7c2b-127">使用以下语法，可以是此数据转换为文本格式：</span><span class="sxs-lookup"><span data-stu-id="f7c2b-127">This data can be converted to text format by using this syntax:</span></span>  <br/>  `cast(cast(ExternalId as varbinary(max)) as varchar(max))` <br/> |
   


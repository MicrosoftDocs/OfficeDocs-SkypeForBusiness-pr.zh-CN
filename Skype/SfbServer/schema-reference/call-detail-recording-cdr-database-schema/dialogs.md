---
title: Skype for Business Server 2015 中的 Dialogs 表
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
ms.assetid: 487a430b-af66-4ea6-b28e-4e33cfdb7f9e
description: Dialogs 表是一个支持表，用于存储有关对等会话的 DialogID 的信息。
ms.openlocfilehash: a4f0bb8c63e165985ef09af8f9aafa071529bf1f
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816042"
---
# <a name="dialogs-table-in-skype-for-business-server-2015"></a><span data-ttu-id="ee599-103">Skype for Business Server 2015 中的 Dialogs 表</span><span class="sxs-lookup"><span data-stu-id="ee599-103">Dialogs table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="ee599-104">Dialogs 表是一个支持表，用于存储有关对等会话的 DialogID 的信息。</span><span class="sxs-lookup"><span data-stu-id="ee599-104">The Dialogs table is a supporting table that stores the information about DialogIDs for peer-to-peer sessions.</span></span>
  
|<span data-ttu-id="ee599-105">**列**</span><span class="sxs-lookup"><span data-stu-id="ee599-105">**Column**</span></span>|<span data-ttu-id="ee599-106">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="ee599-106">**Data Type**</span></span>|<span data-ttu-id="ee599-107">**键/索引**</span><span class="sxs-lookup"><span data-stu-id="ee599-107">**Key/Index**</span></span>|<span data-ttu-id="ee599-108">**Details**</span><span class="sxs-lookup"><span data-stu-id="ee599-108">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="ee599-109">**SessionIdTime**</span><span class="sxs-lookup"><span data-stu-id="ee599-109">**SessionIdTime**</span></span> <br/> |<span data-ttu-id="ee599-110">datetime</span><span class="sxs-lookup"><span data-stu-id="ee599-110">datetime</span></span>  <br/> |<span data-ttu-id="ee599-111">主</span><span class="sxs-lookup"><span data-stu-id="ee599-111">Primary</span></span>  <br/> |<span data-ttu-id="ee599-112">会话请求的时间;与 SessionIDSeq 结合使用来唯一地标识会话。</span><span class="sxs-lookup"><span data-stu-id="ee599-112">Time of session request; used in conjunction with SessionIDSeq to uniquely identify a session.</span></span>  <br/> |
|<span data-ttu-id="ee599-113">**SessionIdSeq**</span><span class="sxs-lookup"><span data-stu-id="ee599-113">**SessionIdSeq**</span></span> <br/> |<span data-ttu-id="ee599-114">int</span><span class="sxs-lookup"><span data-stu-id="ee599-114">int</span></span>  <br/> |<span data-ttu-id="ee599-115">主</span><span class="sxs-lookup"><span data-stu-id="ee599-115">Primary</span></span>  <br/> |<span data-ttu-id="ee599-116">用于标识会话的 ID 号。</span><span class="sxs-lookup"><span data-stu-id="ee599-116">ID number to identify the session.</span></span> <span data-ttu-id="ee599-117">与 SessionIDTime 结合使用来唯一地标识会话。</span><span class="sxs-lookup"><span data-stu-id="ee599-117">Used in conjunction with SessionIDTime to uniquely identify a session.</span></span>  <br/> |
|<span data-ttu-id="ee599-118">**ExternalChecksum**</span><span class="sxs-lookup"><span data-stu-id="ee599-118">**ExternalChecksum**</span></span> <br/> |<span data-ttu-id="ee599-119">int</span><span class="sxs-lookup"><span data-stu-id="ee599-119">int</span></span>  <br/> | <br/> |<span data-ttu-id="ee599-120">ExternalID 的校验和。</span><span class="sxs-lookup"><span data-stu-id="ee599-120">Checksum of the ExternalID.</span></span> <span data-ttu-id="ee599-121">此字段用于提高数据库搜索的速度。</span><span class="sxs-lookup"><span data-stu-id="ee599-121">This field is used to increase the speed of database searches.</span></span>  <br/> |
|<span data-ttu-id="ee599-122">**ExternalId**</span><span class="sxs-lookup"><span data-stu-id="ee599-122">**ExternalId**</span></span> <br/> |<span data-ttu-id="ee599-123">varbinary (775) </span><span class="sxs-lookup"><span data-stu-id="ee599-123">varbinary(775)</span></span>  <br/> | <br/> |<span data-ttu-id="ee599-124">SIP 对话框 ID，存储为二进制文件。</span><span class="sxs-lookup"><span data-stu-id="ee599-124">SIP dialog ID, stored as a binary.</span></span> <span data-ttu-id="ee599-125">二进制文件的格式为：</span><span class="sxs-lookup"><span data-stu-id="ee599-125">The format of the binary is:</span></span>  <br/> <span data-ttu-id="ee599-126">dialog;from-tag;to-tag</span><span class="sxs-lookup"><span data-stu-id="ee599-126">dialog;from-tag;to-tag</span></span>  <br/> <span data-ttu-id="ee599-127">可以使用以下语法将此数据转换为文本格式：</span><span class="sxs-lookup"><span data-stu-id="ee599-127">This data can be converted to text format by using this syntax:</span></span>  <br/>  `cast(cast(ExternalId as varbinary(max)) as varchar(max))` <br/> |
   


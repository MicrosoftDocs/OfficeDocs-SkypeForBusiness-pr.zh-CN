---
title: Skype for Business Server 2015 中的对话框表
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 487a430b-af66-4ea6-b28e-4e33cfdb7f9e
description: 对话框表是一个支持表, 用于存储有关对等会话的 DialogIDs 的信息。
ms.openlocfilehash: 61230cf7f72405c4c5f27ff7b159afe4e5a7842e
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34296320"
---
# <a name="dialogs-table-in-skype-for-business-server-2015"></a><span data-ttu-id="8e4a7-103">Skype for Business Server 2015 中的对话框表</span><span class="sxs-lookup"><span data-stu-id="8e4a7-103">Dialogs table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="8e4a7-104">对话框表是一个支持表, 用于存储有关对等会话的 DialogIDs 的信息。</span><span class="sxs-lookup"><span data-stu-id="8e4a7-104">The Dialogs table is a supporting table that stores the information about DialogIDs for peer-to-peer sessions.</span></span>
  
|<span data-ttu-id="8e4a7-105">**列**</span><span class="sxs-lookup"><span data-stu-id="8e4a7-105">**Column**</span></span>|<span data-ttu-id="8e4a7-106">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="8e4a7-106">**Data Type**</span></span>|<span data-ttu-id="8e4a7-107">**键/索引**</span><span class="sxs-lookup"><span data-stu-id="8e4a7-107">**Key/Index**</span></span>|<span data-ttu-id="8e4a7-108">**详细信息**</span><span class="sxs-lookup"><span data-stu-id="8e4a7-108">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="8e4a7-109">**SessionIdTime**</span><span class="sxs-lookup"><span data-stu-id="8e4a7-109">**SessionIdTime**</span></span> <br/> |<span data-ttu-id="8e4a7-110">datetime</span><span class="sxs-lookup"><span data-stu-id="8e4a7-110">datetime</span></span>  <br/> |<span data-ttu-id="8e4a7-111">Primary</span><span class="sxs-lookup"><span data-stu-id="8e4a7-111">Primary</span></span>  <br/> |<span data-ttu-id="8e4a7-112">会话请求的时间;与 SessionIDSeq 结合使用以唯一标识会话。</span><span class="sxs-lookup"><span data-stu-id="8e4a7-112">Time of session request; used in conjunction with SessionIDSeq to uniquely identify a session.</span></span>  <br/> |
|<span data-ttu-id="8e4a7-113">**SessionIdSeq**</span><span class="sxs-lookup"><span data-stu-id="8e4a7-113">**SessionIdSeq**</span></span> <br/> |<span data-ttu-id="8e4a7-114">int</span><span class="sxs-lookup"><span data-stu-id="8e4a7-114">int</span></span>  <br/> |<span data-ttu-id="8e4a7-115">Primary</span><span class="sxs-lookup"><span data-stu-id="8e4a7-115">Primary</span></span>  <br/> |<span data-ttu-id="8e4a7-116">标识会话的 ID 号。</span><span class="sxs-lookup"><span data-stu-id="8e4a7-116">ID number to identify the session.</span></span> <span data-ttu-id="8e4a7-117">与 SessionIDTime 结合使用以唯一标识会话。</span><span class="sxs-lookup"><span data-stu-id="8e4a7-117">Used in conjunction with SessionIDTime to uniquely identify a session.</span></span>  <br/> |
|<span data-ttu-id="8e4a7-118">**ExternalChecksum**</span><span class="sxs-lookup"><span data-stu-id="8e4a7-118">**ExternalChecksum**</span></span> <br/> |<span data-ttu-id="8e4a7-119">int</span><span class="sxs-lookup"><span data-stu-id="8e4a7-119">int</span></span>  <br/> | <br/> |<span data-ttu-id="8e4a7-120">ExternalID 的校验和。</span><span class="sxs-lookup"><span data-stu-id="8e4a7-120">Checksum of the ExternalID.</span></span> <span data-ttu-id="8e4a7-121">此字段用于提高数据库搜索的速度。</span><span class="sxs-lookup"><span data-stu-id="8e4a7-121">This field is used to increase the speed of database searches.</span></span>  <br/> |
|<span data-ttu-id="8e4a7-122">**ExternalId**</span><span class="sxs-lookup"><span data-stu-id="8e4a7-122">**ExternalId**</span></span> <br/> |<span data-ttu-id="8e4a7-123">varbinary (775)</span><span class="sxs-lookup"><span data-stu-id="8e4a7-123">varbinary(775)</span></span>  <br/> | <br/> |<span data-ttu-id="8e4a7-124">SIP 对话框 ID, 存储为二进制。</span><span class="sxs-lookup"><span data-stu-id="8e4a7-124">SIP dialog ID, stored as a binary.</span></span> <span data-ttu-id="8e4a7-125">二进制文件的格式为:</span><span class="sxs-lookup"><span data-stu-id="8e4a7-125">The format of the binary is:</span></span>  <br/> <span data-ttu-id="8e4a7-126">对话框; 从-标签; 到-标记</span><span class="sxs-lookup"><span data-stu-id="8e4a7-126">dialog;from-tag;to-tag</span></span>  <br/> <span data-ttu-id="8e4a7-127">可以使用以下语法将此数据转换为文本格式:</span><span class="sxs-lookup"><span data-stu-id="8e4a7-127">This data can be converted to text format by using this syntax:</span></span>  <br/>  `cast(cast(ExternalId as varbinary(max)) as varchar(max))` <br/> |
   


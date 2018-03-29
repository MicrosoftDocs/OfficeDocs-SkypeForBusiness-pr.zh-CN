---
title: 在业务服务器 2015年的 Skype 的对话表
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 487a430b-af66-4ea6-b28e-4e33cfdb7f9e
description: 对话表是一个支持的表来存储有关 DialogIDs 的对等会话的信息。
ms.openlocfilehash: b2953ff2bec35575221bc0d43785eb6c0d90e2d1
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="dialogs-table-in-skype-for-business-server-2015"></a><span data-ttu-id="2cdb0-103">在业务服务器 2015年的 Skype 的对话表</span><span class="sxs-lookup"><span data-stu-id="2cdb0-103">Dialogs table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="2cdb0-104">对话表是一个支持的表来存储有关 DialogIDs 的对等会话的信息。</span><span class="sxs-lookup"><span data-stu-id="2cdb0-104">The Dialogs table is a supporting table that stores the information about DialogIDs for peer-to-peer sessions.</span></span>
  
|<span data-ttu-id="2cdb0-105">**列**</span><span class="sxs-lookup"><span data-stu-id="2cdb0-105">**Column**</span></span>|<span data-ttu-id="2cdb0-106">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="2cdb0-106">**Data Type**</span></span>|<span data-ttu-id="2cdb0-107">**键/索引**</span><span class="sxs-lookup"><span data-stu-id="2cdb0-107">**Key/Index**</span></span>|<span data-ttu-id="2cdb0-108">**详细信息**</span><span class="sxs-lookup"><span data-stu-id="2cdb0-108">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="2cdb0-109">**SessionIdTime**</span><span class="sxs-lookup"><span data-stu-id="2cdb0-109">**SessionIdTime**</span></span> <br/> |<span data-ttu-id="2cdb0-110">datetime</span><span class="sxs-lookup"><span data-stu-id="2cdb0-110">datetime</span></span>  <br/> |<span data-ttu-id="2cdb0-111">Primary</span><span class="sxs-lookup"><span data-stu-id="2cdb0-111">Primary</span></span>  <br/> |<span data-ttu-id="2cdb0-112">会话的请求; 时间与 SessionIDSeq 配合使用，以唯一标识会话。</span><span class="sxs-lookup"><span data-stu-id="2cdb0-112">Time of session request; used in conjunction with SessionIDSeq to uniquely identify a session.</span></span>  <br/> |
|<span data-ttu-id="2cdb0-113">**SessionIdSeq**</span><span class="sxs-lookup"><span data-stu-id="2cdb0-113">**SessionIdSeq**</span></span> <br/> |<span data-ttu-id="2cdb0-114">int</span><span class="sxs-lookup"><span data-stu-id="2cdb0-114">int</span></span>  <br/> |<span data-ttu-id="2cdb0-115">Primary</span><span class="sxs-lookup"><span data-stu-id="2cdb0-115">Primary</span></span>  <br/> |<span data-ttu-id="2cdb0-116">以标识会话的 ID 号。</span><span class="sxs-lookup"><span data-stu-id="2cdb0-116">ID number to identify the session.</span></span> <span data-ttu-id="2cdb0-117">与 SessionIDTime 配合使用，以唯一标识会话。</span><span class="sxs-lookup"><span data-stu-id="2cdb0-117">Used in conjunction with SessionIDTime to uniquely identify a session.</span></span>  <br/> |
|<span data-ttu-id="2cdb0-118">**ExternalChecksum**</span><span class="sxs-lookup"><span data-stu-id="2cdb0-118">**ExternalChecksum**</span></span> <br/> |<span data-ttu-id="2cdb0-119">int</span><span class="sxs-lookup"><span data-stu-id="2cdb0-119">int</span></span>  <br/> | <br/> |<span data-ttu-id="2cdb0-120">ExternalID 的校验和。</span><span class="sxs-lookup"><span data-stu-id="2cdb0-120">Checksum of the ExternalID.</span></span> <span data-ttu-id="2cdb0-121">此字段用于提高数据库搜索的速度。</span><span class="sxs-lookup"><span data-stu-id="2cdb0-121">This field is used to increase the speed of database searches.</span></span>  <br/> |
|<span data-ttu-id="2cdb0-122">**ExternalId**</span><span class="sxs-lookup"><span data-stu-id="2cdb0-122">**ExternalId**</span></span> <br/> |<span data-ttu-id="2cdb0-123">varbinary(775)</span><span class="sxs-lookup"><span data-stu-id="2cdb0-123">varbinary(775)</span></span>  <br/> | <br/> |<span data-ttu-id="2cdb0-124">SIP 对话框 ID 存储为二进制文件。</span><span class="sxs-lookup"><span data-stu-id="2cdb0-124">SIP dialog ID, stored as a binary.</span></span> <span data-ttu-id="2cdb0-125">该二进制文件的格式为：</span><span class="sxs-lookup"><span data-stu-id="2cdb0-125">The format of the binary is:</span></span>  <br/> <span data-ttu-id="2cdb0-126">对话; 从标记; 到标记</span><span class="sxs-lookup"><span data-stu-id="2cdb0-126">dialog;from-tag;to-tag</span></span>  <br/> <span data-ttu-id="2cdb0-127">此数据可以转换为文本格式，使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="2cdb0-127">This data can be converted to text format by using this syntax:</span></span>  <br/>  `cast(cast(ExternalId as varbinary(max)) as varchar(max))` <br/> |
   


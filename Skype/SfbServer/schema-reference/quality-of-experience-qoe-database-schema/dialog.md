---
title: Dialog 表
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4d93424f-9072-43f5-83c2-3d539e3e9ca6
description: 对话框表是支持表;每个记录都表示一个会话启动协议 (SIP) 对话框。
ms.openlocfilehash: 0380f9c7c48ff7d3b26b9ea5442fb5ac2155f785
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="dialog-table"></a><span data-ttu-id="b571b-103">Dialog 表</span><span class="sxs-lookup"><span data-stu-id="b571b-103">Dialog table</span></span>
 
<span data-ttu-id="b571b-104">对话框表是支持表;每个记录都表示一个会话启动协议 (SIP) 对话框。</span><span class="sxs-lookup"><span data-stu-id="b571b-104">The Dialog table is a supporting table; each record represents one Session Initiation Protocol (SIP) dialog.</span></span>
  
|<span data-ttu-id="b571b-105">**列**</span><span class="sxs-lookup"><span data-stu-id="b571b-105">**Column**</span></span>|<span data-ttu-id="b571b-106">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="b571b-106">**Data Type**</span></span>|<span data-ttu-id="b571b-107">**键/索引**</span><span class="sxs-lookup"><span data-stu-id="b571b-107">**Key/Index**</span></span>|<span data-ttu-id="b571b-108">**详细信息**</span><span class="sxs-lookup"><span data-stu-id="b571b-108">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="b571b-109">**ConferenceDateTime**</span><span class="sxs-lookup"><span data-stu-id="b571b-109">**ConferenceDateTime**</span></span> <br/> |<span data-ttu-id="b571b-110">datetime</span><span class="sxs-lookup"><span data-stu-id="b571b-110">datetime</span></span>  <br/> |<span data-ttu-id="b571b-111">Primary</span><span class="sxs-lookup"><span data-stu-id="b571b-111">Primary</span></span>  <br/> |<span data-ttu-id="b571b-112">当卓越质量 (QoE) 代理程序从调用方或被调用方接收的第一个报告的时间。</span><span class="sxs-lookup"><span data-stu-id="b571b-112">Time when the Quality of Excellence (QoE) agent receives the first report from either caller or callee.</span></span> <span data-ttu-id="b571b-113">与 SessionSeq 配合使用，以唯一标识会话。</span><span class="sxs-lookup"><span data-stu-id="b571b-113">Used in conjunction with SessionSeq to uniquely identify a session.</span></span>  <br/> |
|<span data-ttu-id="b571b-114">**SessionSeq**</span><span class="sxs-lookup"><span data-stu-id="b571b-114">**SessionSeq**</span></span> <br/> |<span data-ttu-id="b571b-115">int</span><span class="sxs-lookup"><span data-stu-id="b571b-115">int</span></span>  <br/> |<span data-ttu-id="b571b-116">Primary</span><span class="sxs-lookup"><span data-stu-id="b571b-116">Primary</span></span>  <br/> |<span data-ttu-id="b571b-117">若要区分的会话时它们具有相同的 ConferenceDateTime 的序列号。</span><span class="sxs-lookup"><span data-stu-id="b571b-117">Sequence number to differentiate sessions when they have the same ConferenceDateTime.</span></span>  <br/> |
|<span data-ttu-id="b571b-118">**DialogID**</span><span class="sxs-lookup"><span data-stu-id="b571b-118">**DialogID**</span></span> <br/> |<span data-ttu-id="b571b-119">varchar(256)</span><span class="sxs-lookup"><span data-stu-id="b571b-119">varchar(256)</span></span>  <br/> ||<span data-ttu-id="b571b-120">这是全局唯一的对话框 ID。</span><span class="sxs-lookup"><span data-stu-id="b571b-120">Dialog ID which is globally unique.</span></span>  <br/> |
|<span data-ttu-id="b571b-121">**DialogIDChecksum**</span><span class="sxs-lookup"><span data-stu-id="b571b-121">**DialogIDChecksum**</span></span> <br/> |<span data-ttu-id="b571b-122">int</span><span class="sxs-lookup"><span data-stu-id="b571b-122">int</span></span>  <br/> |<span data-ttu-id="b571b-123">索引</span><span class="sxs-lookup"><span data-stu-id="b571b-123">index</span></span>  <br/> |<span data-ttu-id="b571b-124">校验和的对话框 id。</span><span class="sxs-lookup"><span data-stu-id="b571b-124">Checksum of the Dialog ID.</span></span>  <br/> |
   


---
title: Dialog 表
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
ms.assetid: 4d93424f-9072-43f5-83c2-3d539e3e9ca6
description: Dialog 表是一个支持表；每条记录代表一个会话初始协议 (SIP) 对话。
ms.openlocfilehash: 05d9519c9aef20b8c82d904a9d5718a4de8c092c
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49815842"
---
# <a name="dialog-table"></a><span data-ttu-id="8b044-103">Dialog 表</span><span class="sxs-lookup"><span data-stu-id="8b044-103">Dialog table</span></span>
 
<span data-ttu-id="8b044-104">Dialog 表是一个支持表；每条记录代表一个会话初始协议 (SIP) 对话。</span><span class="sxs-lookup"><span data-stu-id="8b044-104">The Dialog table is a supporting table; each record represents one Session Initiation Protocol (SIP) dialog.</span></span>
  
|<span data-ttu-id="8b044-105">**列**</span><span class="sxs-lookup"><span data-stu-id="8b044-105">**Column**</span></span>|<span data-ttu-id="8b044-106">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="8b044-106">**Data Type**</span></span>|<span data-ttu-id="8b044-107">**键/索引**</span><span class="sxs-lookup"><span data-stu-id="8b044-107">**Key/Index**</span></span>|<span data-ttu-id="8b044-108">**Details**</span><span class="sxs-lookup"><span data-stu-id="8b044-108">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="8b044-109">**ConferenceDateTime**</span><span class="sxs-lookup"><span data-stu-id="8b044-109">**ConferenceDateTime**</span></span> <br/> |<span data-ttu-id="8b044-110">datetime</span><span class="sxs-lookup"><span data-stu-id="8b044-110">datetime</span></span>  <br/> |<span data-ttu-id="8b044-111">主</span><span class="sxs-lookup"><span data-stu-id="8b044-111">Primary</span></span>  <br/> |<span data-ttu-id="8b044-p101">用户体验质量 (QoE) 代理从呼叫者或被叫方接收第一个报告的时间。与 SessionSeq 结合使用来唯一地标识会话。</span><span class="sxs-lookup"><span data-stu-id="8b044-p101">Time when the Quality of Excellence (QoE) agent receives the first report from either caller or callee. Used in conjunction with SessionSeq to uniquely identify a session.</span></span>  <br/> |
|<span data-ttu-id="8b044-114">**SessionSeq**</span><span class="sxs-lookup"><span data-stu-id="8b044-114">**SessionSeq**</span></span> <br/> |<span data-ttu-id="8b044-115">int</span><span class="sxs-lookup"><span data-stu-id="8b044-115">int</span></span>  <br/> |<span data-ttu-id="8b044-116">主</span><span class="sxs-lookup"><span data-stu-id="8b044-116">Primary</span></span>  <br/> |<span data-ttu-id="8b044-117">当会话具有相同的 ConferenceDateTime 时区分会话的序号。</span><span class="sxs-lookup"><span data-stu-id="8b044-117">Sequence number to differentiate sessions when they have the same ConferenceDateTime.</span></span>  <br/> |
|<span data-ttu-id="8b044-118">**DialogID**</span><span class="sxs-lookup"><span data-stu-id="8b044-118">**DialogID**</span></span> <br/> |<span data-ttu-id="8b044-119">varchar (256) </span><span class="sxs-lookup"><span data-stu-id="8b044-119">varchar(256)</span></span>  <br/> ||<span data-ttu-id="8b044-120">全局唯一的对话 ID。</span><span class="sxs-lookup"><span data-stu-id="8b044-120">Dialog ID which is globally unique.</span></span>  <br/> |
|<span data-ttu-id="8b044-121">**DialogIDChecksum**</span><span class="sxs-lookup"><span data-stu-id="8b044-121">**DialogIDChecksum**</span></span> <br/> |<span data-ttu-id="8b044-122">int</span><span class="sxs-lookup"><span data-stu-id="8b044-122">int</span></span>  <br/> |<span data-ttu-id="8b044-123">index</span><span class="sxs-lookup"><span data-stu-id="8b044-123">index</span></span>  <br/> |<span data-ttu-id="8b044-124">对话 ID 的校验和。</span><span class="sxs-lookup"><span data-stu-id="8b044-124">Checksum of the Dialog ID.</span></span>  <br/> |
   


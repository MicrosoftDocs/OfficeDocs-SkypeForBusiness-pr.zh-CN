---
title: Dialog 表
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4d93424f-9072-43f5-83c2-3d539e3e9ca6
description: Dialog 表是一个支持表;每条记录代表一个会话初始协议 (SIP) 对话。
ms.openlocfilehash: 36ab76d147673ca85371ca4cdfb151fa953e29b2
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "33920087"
---
# <a name="dialog-table"></a><span data-ttu-id="4192e-103">Dialog 表</span><span class="sxs-lookup"><span data-stu-id="4192e-103">Dialog table</span></span>
 
<span data-ttu-id="4192e-104">Dialog 表是一个支持表;每条记录代表一个会话初始协议 (SIP) 对话。</span><span class="sxs-lookup"><span data-stu-id="4192e-104">The Dialog table is a supporting table; each record represents one Session Initiation Protocol (SIP) dialog.</span></span>
  
|<span data-ttu-id="4192e-105">**列**</span><span class="sxs-lookup"><span data-stu-id="4192e-105">**Column**</span></span>|<span data-ttu-id="4192e-106">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="4192e-106">**Data Type**</span></span>|<span data-ttu-id="4192e-107">**键/索引**</span><span class="sxs-lookup"><span data-stu-id="4192e-107">**Key/Index**</span></span>|<span data-ttu-id="4192e-108">**详细信息**</span><span class="sxs-lookup"><span data-stu-id="4192e-108">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="4192e-109">**ConferenceDateTime**</span><span class="sxs-lookup"><span data-stu-id="4192e-109">**ConferenceDateTime**</span></span> <br/> |<span data-ttu-id="4192e-110">datetime</span><span class="sxs-lookup"><span data-stu-id="4192e-110">datetime</span></span>  <br/> |<span data-ttu-id="4192e-111">Primary</span><span class="sxs-lookup"><span data-stu-id="4192e-111">Primary</span></span>  <br/> |<span data-ttu-id="4192e-112">卓越质量 (QoE) 代理时接收从呼叫者或被叫方的第一个报告时间。</span><span class="sxs-lookup"><span data-stu-id="4192e-112">Time when the Quality of Excellence (QoE) agent receives the first report from either caller or callee.</span></span> <span data-ttu-id="4192e-113">与 SessionSeq 结合使用，来唯一地标识会话。</span><span class="sxs-lookup"><span data-stu-id="4192e-113">Used in conjunction with SessionSeq to uniquely identify a session.</span></span>  <br/> |
|<span data-ttu-id="4192e-114">**SessionSeq**</span><span class="sxs-lookup"><span data-stu-id="4192e-114">**SessionSeq**</span></span> <br/> |<span data-ttu-id="4192e-115">int</span><span class="sxs-lookup"><span data-stu-id="4192e-115">int</span></span>  <br/> |<span data-ttu-id="4192e-116">Primary</span><span class="sxs-lookup"><span data-stu-id="4192e-116">Primary</span></span>  <br/> |<span data-ttu-id="4192e-117">区分会话拥有相同的 ConferenceDateTime 时的序列号。</span><span class="sxs-lookup"><span data-stu-id="4192e-117">Sequence number to differentiate sessions when they have the same ConferenceDateTime.</span></span>  <br/> |
|<span data-ttu-id="4192e-118">**DialogID**</span><span class="sxs-lookup"><span data-stu-id="4192e-118">**DialogID**</span></span> <br/> |<span data-ttu-id="4192e-119">varchar(256)</span><span class="sxs-lookup"><span data-stu-id="4192e-119">varchar(256)</span></span>  <br/> ||<span data-ttu-id="4192e-120">全局唯一的对话 ID。</span><span class="sxs-lookup"><span data-stu-id="4192e-120">Dialog ID which is globally unique.</span></span>  <br/> |
|<span data-ttu-id="4192e-121">**DialogIDChecksum**</span><span class="sxs-lookup"><span data-stu-id="4192e-121">**DialogIDChecksum**</span></span> <br/> |<span data-ttu-id="4192e-122">int</span><span class="sxs-lookup"><span data-stu-id="4192e-122">int</span></span>  <br/> |<span data-ttu-id="4192e-123">索引</span><span class="sxs-lookup"><span data-stu-id="4192e-123">index</span></span>  <br/> |<span data-ttu-id="4192e-124">对话框 ID 的校验和。</span><span class="sxs-lookup"><span data-stu-id="4192e-124">Checksum of the Dialog ID.</span></span>  <br/> |
   


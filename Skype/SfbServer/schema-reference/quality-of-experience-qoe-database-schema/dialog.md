---
title: Dialog 表
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 4d93424f-9072-43f5-83c2-3d539e3e9ca6
description: 对话框表是支持表;每条记录表示一个会话初始协议（SIP）对话框。
ms.openlocfilehash: 85d4a9f16a88db386565c065161eedeb61fba913
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41809530"
---
# <a name="dialog-table"></a><span data-ttu-id="b8280-103">Dialog 表</span><span class="sxs-lookup"><span data-stu-id="b8280-103">Dialog table</span></span>
 
<span data-ttu-id="b8280-104">对话框表是支持表;每条记录表示一个会话初始协议（SIP）对话框。</span><span class="sxs-lookup"><span data-stu-id="b8280-104">The Dialog table is a supporting table; each record represents one Session Initiation Protocol (SIP) dialog.</span></span>
  
|<span data-ttu-id="b8280-105">**列**</span><span class="sxs-lookup"><span data-stu-id="b8280-105">**Column**</span></span>|<span data-ttu-id="b8280-106">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="b8280-106">**Data Type**</span></span>|<span data-ttu-id="b8280-107">**键/索引**</span><span class="sxs-lookup"><span data-stu-id="b8280-107">**Key/Index**</span></span>|<span data-ttu-id="b8280-108">**详细信息**</span><span class="sxs-lookup"><span data-stu-id="b8280-108">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="b8280-109">**ConferenceDateTime**</span><span class="sxs-lookup"><span data-stu-id="b8280-109">**ConferenceDateTime**</span></span> <br/> |<span data-ttu-id="b8280-110">datetime</span><span class="sxs-lookup"><span data-stu-id="b8280-110">datetime</span></span>  <br/> |<span data-ttu-id="b8280-111">Primary</span><span class="sxs-lookup"><span data-stu-id="b8280-111">Primary</span></span>  <br/> |<span data-ttu-id="b8280-112">优质（QoE） agent 接收来自呼叫方或被叫方的第一个报告的时间。</span><span class="sxs-lookup"><span data-stu-id="b8280-112">Time when the Quality of Excellence (QoE) agent receives the first report from either caller or callee.</span></span> <span data-ttu-id="b8280-113">与 SessionSeq 结合使用以唯一标识会话。</span><span class="sxs-lookup"><span data-stu-id="b8280-113">Used in conjunction with SessionSeq to uniquely identify a session.</span></span>  <br/> |
|<span data-ttu-id="b8280-114">**SessionSeq**</span><span class="sxs-lookup"><span data-stu-id="b8280-114">**SessionSeq**</span></span> <br/> |<span data-ttu-id="b8280-115">int</span><span class="sxs-lookup"><span data-stu-id="b8280-115">int</span></span>  <br/> |<span data-ttu-id="b8280-116">Primary</span><span class="sxs-lookup"><span data-stu-id="b8280-116">Primary</span></span>  <br/> |<span data-ttu-id="b8280-117">序列号，以便在具有相同的 ConferenceDateTime 时区分会话。</span><span class="sxs-lookup"><span data-stu-id="b8280-117">Sequence number to differentiate sessions when they have the same ConferenceDateTime.</span></span>  <br/> |
|<span data-ttu-id="b8280-118">**DialogID**</span><span class="sxs-lookup"><span data-stu-id="b8280-118">**DialogID**</span></span> <br/> |<span data-ttu-id="b8280-119">varchar （256）</span><span class="sxs-lookup"><span data-stu-id="b8280-119">varchar(256)</span></span>  <br/> ||<span data-ttu-id="b8280-120">全局唯一的对话框 ID。</span><span class="sxs-lookup"><span data-stu-id="b8280-120">Dialog ID which is globally unique.</span></span>  <br/> |
|<span data-ttu-id="b8280-121">**DialogIDChecksum**</span><span class="sxs-lookup"><span data-stu-id="b8280-121">**DialogIDChecksum**</span></span> <br/> |<span data-ttu-id="b8280-122">int</span><span class="sxs-lookup"><span data-stu-id="b8280-122">int</span></span>  <br/> |<span data-ttu-id="b8280-123">食指</span><span class="sxs-lookup"><span data-stu-id="b8280-123">index</span></span>  <br/> |<span data-ttu-id="b8280-124">对话框 ID 的校验和。</span><span class="sxs-lookup"><span data-stu-id="b8280-124">Checksum of the Dialog ID.</span></span>  <br/> |
   


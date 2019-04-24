---
title: Dialog 表
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4d93424f-9072-43f5-83c2-3d539e3e9ca6
description: Dialog 表是一个支持表;每条记录代表一个会话初始协议 (SIP) 对话。
ms.openlocfilehash: 017da65154d12c89aeed63ea59269639d23b2129
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32212570"
---
# <a name="dialog-table"></a><span data-ttu-id="2c7b8-103">Dialog 表</span><span class="sxs-lookup"><span data-stu-id="2c7b8-103">Dialog table</span></span>
 
<span data-ttu-id="2c7b8-104">Dialog 表是一个支持表;每条记录代表一个会话初始协议 (SIP) 对话。</span><span class="sxs-lookup"><span data-stu-id="2c7b8-104">The Dialog table is a supporting table; each record represents one Session Initiation Protocol (SIP) dialog.</span></span>
  
|<span data-ttu-id="2c7b8-105">**列**</span><span class="sxs-lookup"><span data-stu-id="2c7b8-105">**Column**</span></span>|<span data-ttu-id="2c7b8-106">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="2c7b8-106">**Data Type**</span></span>|<span data-ttu-id="2c7b8-107">**键/索引**</span><span class="sxs-lookup"><span data-stu-id="2c7b8-107">**Key/Index**</span></span>|<span data-ttu-id="2c7b8-108">**详细信息**</span><span class="sxs-lookup"><span data-stu-id="2c7b8-108">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="2c7b8-109">**ConferenceDateTime**</span><span class="sxs-lookup"><span data-stu-id="2c7b8-109">**ConferenceDateTime**</span></span> <br/> |<span data-ttu-id="2c7b8-110">datetime</span><span class="sxs-lookup"><span data-stu-id="2c7b8-110">datetime</span></span>  <br/> |<span data-ttu-id="2c7b8-111">Primary</span><span class="sxs-lookup"><span data-stu-id="2c7b8-111">Primary</span></span>  <br/> |<span data-ttu-id="2c7b8-112">卓越质量 (QoE) 代理时接收从呼叫者或被叫方的第一个报告时间。</span><span class="sxs-lookup"><span data-stu-id="2c7b8-112">Time when the Quality of Excellence (QoE) agent receives the first report from either caller or callee.</span></span> <span data-ttu-id="2c7b8-113">与 SessionSeq 结合使用，来唯一地标识会话。</span><span class="sxs-lookup"><span data-stu-id="2c7b8-113">Used in conjunction with SessionSeq to uniquely identify a session.</span></span>  <br/> |
|<span data-ttu-id="2c7b8-114">**SessionSeq**</span><span class="sxs-lookup"><span data-stu-id="2c7b8-114">**SessionSeq**</span></span> <br/> |<span data-ttu-id="2c7b8-115">int</span><span class="sxs-lookup"><span data-stu-id="2c7b8-115">int</span></span>  <br/> |<span data-ttu-id="2c7b8-116">Primary</span><span class="sxs-lookup"><span data-stu-id="2c7b8-116">Primary</span></span>  <br/> |<span data-ttu-id="2c7b8-117">区分会话拥有相同的 ConferenceDateTime 时的序列号。</span><span class="sxs-lookup"><span data-stu-id="2c7b8-117">Sequence number to differentiate sessions when they have the same ConferenceDateTime.</span></span>  <br/> |
|<span data-ttu-id="2c7b8-118">**DialogID**</span><span class="sxs-lookup"><span data-stu-id="2c7b8-118">**DialogID**</span></span> <br/> |<span data-ttu-id="2c7b8-119">varchar(256)</span><span class="sxs-lookup"><span data-stu-id="2c7b8-119">varchar(256)</span></span>  <br/> ||<span data-ttu-id="2c7b8-120">全局唯一的对话 ID。</span><span class="sxs-lookup"><span data-stu-id="2c7b8-120">Dialog ID which is globally unique.</span></span>  <br/> |
|<span data-ttu-id="2c7b8-121">**DialogIDChecksum**</span><span class="sxs-lookup"><span data-stu-id="2c7b8-121">**DialogIDChecksum**</span></span> <br/> |<span data-ttu-id="2c7b8-122">int</span><span class="sxs-lookup"><span data-stu-id="2c7b8-122">int</span></span>  <br/> |<span data-ttu-id="2c7b8-123">索引</span><span class="sxs-lookup"><span data-stu-id="2c7b8-123">index</span></span>  <br/> |<span data-ttu-id="2c7b8-124">对话框 ID 的校验和。</span><span class="sxs-lookup"><span data-stu-id="2c7b8-124">Checksum of the Dialog ID.</span></span>  <br/> |
   


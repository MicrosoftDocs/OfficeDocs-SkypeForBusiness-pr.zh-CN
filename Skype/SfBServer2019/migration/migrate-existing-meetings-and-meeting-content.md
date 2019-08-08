---
title: 迁移现有会议和会议内容
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: '将用户帐户移到 Skype for business Server 2019 服务器时, 以下信息将与该用户帐户一起移动:'
ms.openlocfilehash: c8f87b46054a93af87c938d3da7a2a86be9cb0bf
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/07/2019
ms.locfileid: "36237996"
---
# <a name="migrate-existing-meetings-and-meeting-content"></a><span data-ttu-id="73d1b-103">迁移现有会议和会议内容</span><span class="sxs-lookup"><span data-stu-id="73d1b-103">Migrate existing meetings and meeting content</span></span>

<span data-ttu-id="73d1b-104">当用户帐户移动到 Skype for business Server 2019 服务器时, 以下信息将与该用户帐户一起移动:</span><span class="sxs-lookup"><span data-stu-id="73d1b-104">When a user account is moved to a Skype for Business Server 2019 server, the following information is moved with that user account:</span></span>
  
- <span data-ttu-id="73d1b-105">**已由用户安排的会议**。</span><span class="sxs-lookup"><span data-stu-id="73d1b-105">**Meetings already scheduled by the user**.</span></span> <span data-ttu-id="73d1b-106">这包括移动会议目录和会议数据。</span><span class="sxs-lookup"><span data-stu-id="73d1b-106">This includes moving the conferencing directories and conferencing data.</span></span>
    
- <span data-ttu-id="73d1b-107">**用户的个人识别码 (PIN)**。</span><span class="sxs-lookup"><span data-stu-id="73d1b-107">**User's personal identification number (PIN)**.</span></span> <span data-ttu-id="73d1b-108">用户的当前 PIN 将继续工作, 直到过期或用户请求新的 PIN。</span><span class="sxs-lookup"><span data-stu-id="73d1b-108">The user's current PIN continues to work until it expires or the user requests a new PIN.</span></span>
    
<span data-ttu-id="73d1b-109">以下用户帐户信息不会移动到新服务器。</span><span class="sxs-lookup"><span data-stu-id="73d1b-109">The following user account information does not move to the new server.</span></span>
  
- <span data-ttu-id="73d1b-110">**会议内容**。</span><span class="sxs-lookup"><span data-stu-id="73d1b-110">**Meeting content**.</span></span> <span data-ttu-id="73d1b-111">为了移动在会议期间共享的内容 (如 PowerPoint、白板、附件或轮询数据), 请使用 **-MoveConferenceData**参数作为**move-csuser** cmdlet 的一部分。</span><span class="sxs-lookup"><span data-stu-id="73d1b-111">In order to move the content shared during a meeting, such as PowerPoint, Whiteboard, attachments, or poll data, use the **-MoveConferenceData** parameter as part of the **Move-CsUser** cmdlet.</span></span> 
    


---
title: 迁移现有会议和会议内容
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 将用户帐户从迁移到 Skype for business Server 2019 服务器时，将使用该用户帐户移动以下信息：
ms.openlocfilehash: 6513f581f55028ec28d4cf05f1f1b3df37c49e65
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752684"
---
# <a name="migrate-existing-meetings-and-meeting-content"></a><span data-ttu-id="9c107-103">迁移现有会议和会议内容</span><span class="sxs-lookup"><span data-stu-id="9c107-103">Migrate existing meetings and meeting content</span></span>

<span data-ttu-id="9c107-104">将用户帐户移动到 Skype for business Server 2019 服务器时，将使用该用户帐户移动以下信息：</span><span class="sxs-lookup"><span data-stu-id="9c107-104">When a user account is moved to a Skype for Business Server 2019 server, the following information is moved with that user account:</span></span>
  
- <span data-ttu-id="9c107-105">**用户已安排的会议**。</span><span class="sxs-lookup"><span data-stu-id="9c107-105">**Meetings already scheduled by the user**.</span></span> <span data-ttu-id="9c107-106">这包括移动会议目录和会议数据。</span><span class="sxs-lookup"><span data-stu-id="9c107-106">This includes moving the conferencing directories and conferencing data.</span></span>
    
- <span data-ttu-id="9c107-107">**用户的个人标识号（PIN）**。</span><span class="sxs-lookup"><span data-stu-id="9c107-107">**User's personal identification number (PIN)**.</span></span> <span data-ttu-id="9c107-108">用户的当前 PIN 将继续工作，直到过期或用户请求新的 PIN。</span><span class="sxs-lookup"><span data-stu-id="9c107-108">The user's current PIN continues to work until it expires or the user requests a new PIN.</span></span>
    
<span data-ttu-id="9c107-109">以下用户帐户信息不会移至新服务器。</span><span class="sxs-lookup"><span data-stu-id="9c107-109">The following user account information does not move to the new server.</span></span>
  
- <span data-ttu-id="9c107-110">**会议内容**。</span><span class="sxs-lookup"><span data-stu-id="9c107-110">**Meeting content**.</span></span> <span data-ttu-id="9c107-111">为了移动在会议期间共享的内容（如 PowerPoint、白板、附件或轮询数据），请使用 **-MoveConferenceData**参数作为**get-csuser** cmdlet 的一部分。</span><span class="sxs-lookup"><span data-stu-id="9c107-111">In order to move the content shared during a meeting, such as PowerPoint, Whiteboard, attachments, or poll data, use the **-MoveConferenceData** parameter as part of the **Move-CsUser** cmdlet.</span></span> 
    


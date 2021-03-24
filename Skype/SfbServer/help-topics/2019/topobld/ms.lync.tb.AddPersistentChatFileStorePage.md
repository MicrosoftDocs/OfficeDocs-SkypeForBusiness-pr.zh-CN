---
title: 添加持久聊天文件存储
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddPersistentChatFileStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e1068706-ff61-4a98-8e51-4202111d936a
ROBOTS: NOINDEX, NOFOLLOW
description: 必须为 Standard Edition Server 或 Enterprise Edition 前端池指定用作文件存储的文件共享。可以将现有的文件共享用作文件存储，也可以通过指定文件共享所在的文件服务器的完全限定域名 (FQDN) 和新文件共享的文件夹名称来指定新的文件共享。
ms.openlocfilehash: 54c72919d89c61fc134a396d46381a5b21254823
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51100058"
---
# <a name="add-persistent-chat-file-store"></a><span data-ttu-id="f10ae-104">添加持久聊天文件存储</span><span class="sxs-lookup"><span data-stu-id="f10ae-104">Add Persistent Chat File Store</span></span>

> [!NOTE] 
> <span data-ttu-id="f10ae-105">持久聊天在 Skype for Business Server 2015 中可用，但在 Skype for Business Server 2019 中不再受支持。</span><span class="sxs-lookup"><span data-stu-id="f10ae-105">Persistent chat is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="f10ae-106">Teams 中提供了相同的功能。</span><span class="sxs-lookup"><span data-stu-id="f10ae-106">The same functionality is available in Teams.</span></span> <span data-ttu-id="f10ae-107">有关详细信息，请参阅 [Skype for Business 到 Microsoft Teams 的升级](/MicrosoftTeams/upgrade-start-here)。</span><span class="sxs-lookup"><span data-stu-id="f10ae-107">For more information, see [Skype for Business to Microsoft Teams upgrade](/MicrosoftTeams/upgrade-start-here).</span></span> <span data-ttu-id="f10ae-108">如果需要使用持久聊天，你的选择是：将需要此功能的用户迁移到 Teams，或者继续使用 Skype for Business Server 2015。</span><span class="sxs-lookup"><span data-stu-id="f10ae-108">If you need to use Persistent chat, your choices are to either migrate users requiring this functionality to Teams or continue using Skype for Business Server 2015.</span></span>
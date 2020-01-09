---
title: 在 Skype for Business 服务器中创建会议目录
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b124b229-7df5-4b7e-8c11-6661c8c8c051
description: 摘要：了解如何在 Skype for Business Server 中创建会议目录。
ms.openlocfilehash: 0ed141b743d436ca2082b8a4f5010011a0256479
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/08/2020
ms.locfileid: "40991847"
---
# <a name="create-conference-directories-in-skype-for-business-server"></a><span data-ttu-id="4b604-103">在 Skype for Business 服务器中创建会议目录</span><span class="sxs-lookup"><span data-stu-id="4b604-103">Create conference directories in Skype for Business Server</span></span>
 
<span data-ttu-id="4b604-104">**摘要：** 了解如何在 Skype for Business 服务器中创建会议目录。</span><span class="sxs-lookup"><span data-stu-id="4b604-104">**Summary:** Learn how to create conference directories in Skype for Business Server.</span></span>
  
<span data-ttu-id="4b604-105">会议目录在使用 Skype for Business 时，在参与者用于加入会议的字母数字会议 ID 之间保留一个映射，以及电话拨入式会议参与者用于加入会议的仅限数字的会议 ID。</span><span class="sxs-lookup"><span data-stu-id="4b604-105">Conference directories maintain a mapping between the alphanumeric meeting ID that a participant uses to join a conference when using Skype for Business, and the numeric-only conference ID that a dial-in conferencing participant uses to join the conference.</span></span> 
  
## <a name="create-a-conference-directory"></a><span data-ttu-id="4b604-106">创建会议目录</span><span class="sxs-lookup"><span data-stu-id="4b604-106">Create a conference directory</span></span>

<span data-ttu-id="4b604-107">创建多个会议目录可以确保会议 ID 短暂停留，直到创建了大量会议。</span><span class="sxs-lookup"><span data-stu-id="4b604-107">Creating multiple conference directories will ensure that conference IDs will stay short until a significant amount of conferences have been created.</span></span> 
  
<span data-ttu-id="4b604-p101">如果组织中每个用户的会议数量为典型值，建议为池中的每 999 个用户创建一个会议目录。通过使用此指南，通常可使会议 ID 保持较小数量。但是，只要会议目录数（所有池中）超过 9，会议 ID 长度就会增加以支持更多会议。</span><span class="sxs-lookup"><span data-stu-id="4b604-p101">In an organization with a typical number of conferences per user, we recommend that you create one conference directory for every 999 users in the pool. Using this guideline, the conference IDs can generally be kept small. However, once the number of conference directories (across the pools) exceed 9, the Conference ID length will grow to support additional conferences.</span></span>
  
<span data-ttu-id="4b604-111">会议 ID 的格式如下：</span><span class="sxs-lookup"><span data-stu-id="4b604-111">The format of a conference ID is as follows:</span></span> 
  
```
  <housekeeping digit (1 digit)><conference directory (usually 1-2 digits> 
  <conference number (variable number of digits><check digit (1 digit)>
```

<span data-ttu-id="4b604-p102">若要创建会议目录，请使用 **New-CsConferenceDirectory** cmdlet。例如，下面的命令创建 Identify 为 42 的会议目录，托管在池 atl-cs-001.litwareinc.com 上面：</span><span class="sxs-lookup"><span data-stu-id="4b604-p102">To create a conference directory, use the **New-CsConferenceDirectory** cmdlet. For example, the following command creates a conference directory with the identity 42, hosted on the pool atl-cs-001.litwareinc.com:</span></span>
  
```PowerShell
New-CsConferenceDirectory -Identity 42 -HomePool "atl-cs-001.litwareinc.com"
```

<span data-ttu-id="4b604-114">有关详细信息，请参阅[CsConferenceDirectory](https://docs.microsoft.com/powershell/module/skype/new-csconferencedirectory?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="4b604-114">For more information, see [New-CsConferenceDirectory](https://docs.microsoft.com/powershell/module/skype/new-csconferencedirectory?view=skype-ps).</span></span>
  


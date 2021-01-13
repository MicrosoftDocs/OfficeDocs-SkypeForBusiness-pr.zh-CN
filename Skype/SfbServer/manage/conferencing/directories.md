---
title: 在 Skype for Business Server 中创建会议目录
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: b124b229-7df5-4b7e-8c11-6661c8c8c051
description: 摘要：了解如何在 Skype for Business Server 中创建会议目录。
ms.openlocfilehash: 6a7b8d110f06b089f166fc6ff2eb35ae35632370
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49828132"
---
# <a name="create-conference-directories-in-skype-for-business-server"></a><span data-ttu-id="7272e-103">在 Skype for Business Server 中创建会议目录</span><span class="sxs-lookup"><span data-stu-id="7272e-103">Create conference directories in Skype for Business Server</span></span>
 
<span data-ttu-id="7272e-104">**摘要：** 了解如何在 Skype for Business Server 中创建会议目录。</span><span class="sxs-lookup"><span data-stu-id="7272e-104">**Summary:** Learn how to create conference directories in Skype for Business Server.</span></span>
  
<span data-ttu-id="7272e-105">会议目录维护参与者使用 Skype for Business 加入会议时用于加入会议的字母数字会议 ID 与电话拨入式会议参与者用于加入会议的唯一数字会议 ID 之间的映射。</span><span class="sxs-lookup"><span data-stu-id="7272e-105">Conference directories maintain a mapping between the alphanumeric meeting ID that a participant uses to join a conference when using Skype for Business, and the numeric-only conference ID that a dial-in conferencing participant uses to join the conference.</span></span> 
  
## <a name="create-a-conference-directory"></a><span data-ttu-id="7272e-106">创建会议目录</span><span class="sxs-lookup"><span data-stu-id="7272e-106">Create a conference directory</span></span>

<span data-ttu-id="7272e-107">创建多个会议目录将确保会议 ID 将短暂停留，直到创建了大量会议。</span><span class="sxs-lookup"><span data-stu-id="7272e-107">Creating multiple conference directories will ensure that conference IDs will stay short until a significant amount of conferences have been created.</span></span> 
  
<span data-ttu-id="7272e-108">在每个用户需要参与典型数量会议的组织中，建议您为池中的每 999 个用户创建一个会议目录。</span><span class="sxs-lookup"><span data-stu-id="7272e-108">In an organization with a typical number of conferences per user, we recommend that you create one conference directory for every 999 users in the pool.</span></span> <span data-ttu-id="7272e-109">使用此指南，会议 ID 通常可以保持较小。</span><span class="sxs-lookup"><span data-stu-id="7272e-109">Using this guideline, the conference IDs can generally be kept small.</span></span> <span data-ttu-id="7272e-110">但是，一旦跨池 (数量超过 9) ，会议 ID 长度将增长以支持其他会议。</span><span class="sxs-lookup"><span data-stu-id="7272e-110">However, once the number of conference directories (across the pools) exceed 9, the Conference ID length will grow to support additional conferences.</span></span>
  
<span data-ttu-id="7272e-111">会议 ID 的格式如下所示：</span><span class="sxs-lookup"><span data-stu-id="7272e-111">The format of a conference ID is as follows:</span></span> 
  
```console
  <housekeeping digit (1 digit)><conference directory (usually 1-2 digits> 
  <conference number (variable number of digits><check digit (1 digit)>
```

<span data-ttu-id="7272e-112">若要创建会议目录，请使用 **New-CsConferenceDirectory** cmdlet。</span><span class="sxs-lookup"><span data-stu-id="7272e-112">To create a conference directory, use the **New-CsConferenceDirectory** cmdlet.</span></span> <span data-ttu-id="7272e-113">例如，以下命令创建标识为 42 的会议目录，该目录托管在池atl-cs-001.litwareinc.com：</span><span class="sxs-lookup"><span data-stu-id="7272e-113">For example, the following command creates a conference directory with the identity 42, hosted on the pool atl-cs-001.litwareinc.com:</span></span>
  
```PowerShell
New-CsConferenceDirectory -Identity 42 -HomePool "atl-cs-001.litwareinc.com"
```

<span data-ttu-id="7272e-114">有关详细信息，请参阅 [New-CsConferenceDirectory](https://docs.microsoft.com/powershell/module/skype/new-csconferencedirectory?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="7272e-114">For more information, see [New-CsConferenceDirectory](https://docs.microsoft.com/powershell/module/skype/new-csconferencedirectory?view=skype-ps).</span></span>
  


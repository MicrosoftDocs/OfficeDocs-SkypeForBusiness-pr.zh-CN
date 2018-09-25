---
title: 使用 PowerShell 管理团队
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.topic: article
ms.service: msteams
ms.collection: Teams_ITAdmin_Help
search.appverid: MET150
description: 了解如何使用 Windows PowerShell 管理所有的 Microsoft 团队中找到的功能。
appliesto:
- Microsoft Teams
ms.openlocfilehash: 0daff64e5a0f6f876de4adb7b60d913fbcce78cb
ms.sourcegitcommit: 9acf2f80cbd55ba2ff6aab034757cc053287485f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/25/2018
ms.locfileid: "25016074"
---
# <a name="using-powershell-to-manage-teams"></a><span data-ttu-id="de3b3-103">使用 PowerShell 管理团队</span><span class="sxs-lookup"><span data-stu-id="de3b3-103">Using PowerShell to manage Teams</span></span>

<span data-ttu-id="de3b3-104">可以使用 PowerShell 或 Microsoft 团队和 Skype for Business Admin Center 管理团队中的功能。</span><span class="sxs-lookup"><span data-stu-id="de3b3-104">Features in Teams can be managed using PowerShell or the Microsoft Teams and Skype for Business Admin Center.</span></span> 

> <span data-ttu-id="de3b3-105">![注意]可使用团队连接器模块管理不是所有团队中的功能。</span><span class="sxs-lookup"><span data-stu-id="de3b3-105">![Note] Not all of the features in Teams can be managed using the Teams connector module.</span></span> <span data-ttu-id="de3b3-106">您可能需要 Skype 用于业务连接器。</span><span class="sxs-lookup"><span data-stu-id="de3b3-106">You may need to use the Skype for Business connector.</span></span> <span data-ttu-id="de3b3-107">请参阅[下载并安装业务联机连接器 Skype](https://docs.microsoft.com/skypeforbusiness/set-up-your-computer-for-windows-powershell/download-and-install-the-skype-for-business-online-connector)</span><span class="sxs-lookup"><span data-stu-id="de3b3-107">See [Download and install the Skype for Business Online connector](https://docs.microsoft.com/skypeforbusiness/set-up-your-computer-for-windows-powershell/download-and-install-the-skype-for-business-online-connector)</span></span>

### <a name="step-1-prerequisites"></a><span data-ttu-id="de3b3-108">步骤 1： 必备组件</span><span class="sxs-lookup"><span data-stu-id="de3b3-108">Step 1: Prerequisites</span></span>

<span data-ttu-id="de3b3-109">使用 PowerShell 的 Microsoft 团队的远程管理支持只能在运行以下操作系统之一的 64 位计算机上：</span><span class="sxs-lookup"><span data-stu-id="de3b3-109">Remote management of Microsoft Teams by using PowerShell is supported only on 64-bit computers running one of the following operating systems:</span></span>
  
- <span data-ttu-id="de3b3-110">Windows 10</span><span class="sxs-lookup"><span data-stu-id="de3b3-110">Windows 10</span></span>
- <span data-ttu-id="de3b3-111">Windows 8.1</span><span class="sxs-lookup"><span data-stu-id="de3b3-111">Windows 8.1</span></span>
- <span data-ttu-id="de3b3-112">Windows 8</span><span class="sxs-lookup"><span data-stu-id="de3b3-112">Windows 8</span></span> 
- <span data-ttu-id="de3b3-113">Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="de3b3-113">Windows Server 2012 R2</span></span>
- <span data-ttu-id="de3b3-114">Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="de3b3-114">Windows Server 2012</span></span>
- <span data-ttu-id="de3b3-115">Windows Server 2008</span><span class="sxs-lookup"><span data-stu-id="de3b3-115">Windows Server 2008</span></span>
- <span data-ttu-id="de3b3-116">Windows 7</span><span class="sxs-lookup"><span data-stu-id="de3b3-116">Windows 7</span></span>
    
<span data-ttu-id="de3b3-117">受支持的操作系统，除了计算机也必须运行以下：</span><span class="sxs-lookup"><span data-stu-id="de3b3-117">In addition to a supported operating system, the computer must also be running the following:</span></span>
  
- <span data-ttu-id="de3b3-118">PowerShell 3.0 或更高</span><span class="sxs-lookup"><span data-stu-id="de3b3-118">PowerShell 3.0 or higher</span></span>
    
- <span data-ttu-id="de3b3-119">团队 PowerShell 连接器模块</span><span class="sxs-lookup"><span data-stu-id="de3b3-119">Teams PowerShell connector module</span></span>


### <a name="step-2-install-powershell-30-or-higher"></a><span data-ttu-id="de3b3-120">步骤 2： 安装 PowerShell 3.0 或更高</span><span class="sxs-lookup"><span data-stu-id="de3b3-120">Step 2: Install PowerShell 3.0 or higher</span></span>
[<span data-ttu-id="de3b3-121">使用本主题的帮助</span><span class="sxs-lookup"><span data-stu-id="de3b3-121">Use this topic for help</span></span>](https://docs.microsoft.com/skypeforbusiness/set-up-your-computer-for-windows-powershell/download-and-install-windows-powershell-3-0) 

### <a name="step-3-download-and-install-the-teams-connector-module"></a><span data-ttu-id="de3b3-122">步骤 3： 下载并安装团队连接器模块</span><span class="sxs-lookup"><span data-stu-id="de3b3-122">Step 3: Download and install the Teams connector module</span></span>
[<span data-ttu-id="de3b3-123">使用本主题的帮助</span><span class="sxs-lookup"><span data-stu-id="de3b3-123">Use this topic for help</span></span>](https://docs.microsoft.com/skypeforbusiness/set-up-your-computer-for-windows-powershell/download-and-install-the-skype-for-business-online-connector) 

<span data-ttu-id="de3b3-124">下面是从 Isabella 的下载链接：https://www.powershellgallery.com/packages/MicrosoftTeams/0.9.3</span><span class="sxs-lookup"><span data-stu-id="de3b3-124">Here is the download link from Isabella: https://www.powershellgallery.com/packages/MicrosoftTeams/0.9.3</span></span>

### <a name="step-4-connect-using-the-teams-connector-module"></a><span data-ttu-id="de3b3-125">步骤 4： 连接使用团队连接器模块</span><span class="sxs-lookup"><span data-stu-id="de3b3-125">Step 4: Connect using the Teams connector module</span></span>
[<span data-ttu-id="de3b3-126">使用本主题的帮助</span><span class="sxs-lookup"><span data-stu-id="de3b3-126">Use this topic for help</span></span>](https://docs.microsoft.com/skypeforbusiness/set-up-your-computer-for-windows-powershell/download-and-install-the-skype-for-business-online-connector) 

### <a name="related-topics"></a><span data-ttu-id="de3b3-127">相关主题</span><span class="sxs-lookup"><span data-stu-id="de3b3-127">Related topics</span></span>
- [<span data-ttu-id="de3b3-128">管理团队功能使用 PowerShell</span><span class="sxs-lookup"><span data-stu-id="de3b3-128">Manage Teams features with PowerShell</span></span>](manage-features-with-powershell.md)
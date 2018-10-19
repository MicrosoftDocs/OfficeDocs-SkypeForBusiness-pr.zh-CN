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
ms.openlocfilehash: 4c8eb0c37f71972bb20fac60706ff7a369d971d4
ms.sourcegitcommit: 044286f9dec2743a622bdaeac03469418cfdfa0d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/19/2018
ms.locfileid: "25678343"
---
# <a name="using-powershell-to-manage-teams"></a><span data-ttu-id="f0e81-103">使用 PowerShell 管理团队</span><span class="sxs-lookup"><span data-stu-id="f0e81-103">Using PowerShell to manage Teams</span></span>

<span data-ttu-id="f0e81-104">可以使用 PowerShell 或 Microsoft 团队和 Skype for Business Admin Center 管理团队中的功能。</span><span class="sxs-lookup"><span data-stu-id="f0e81-104">Features in Teams can be managed using PowerShell or the Microsoft Teams and Skype for Business Admin Center.</span></span> 

> <span data-ttu-id="f0e81-105">![注意]可使用团队连接器模块管理不是所有团队中的功能。</span><span class="sxs-lookup"><span data-stu-id="f0e81-105">![Note] Not all of the features in Teams can be managed using the Teams connector module.</span></span> <span data-ttu-id="f0e81-106">您可能需要 Skype 用于业务连接器。</span><span class="sxs-lookup"><span data-stu-id="f0e81-106">You may need to use the Skype for Business connector.</span></span> <span data-ttu-id="f0e81-107">请参阅[下载并安装业务联机连接器 Skype](https://docs.microsoft.com/skypeforbusiness/set-up-your-computer-for-windows-powershell/download-and-install-the-skype-for-business-online-connector)</span><span class="sxs-lookup"><span data-stu-id="f0e81-107">See [Download and install the Skype for Business Online connector](https://docs.microsoft.com/skypeforbusiness/set-up-your-computer-for-windows-powershell/download-and-install-the-skype-for-business-online-connector)</span></span>

### <a name="step-1-prerequisites"></a><span data-ttu-id="f0e81-108">步骤 1： 必备组件</span><span class="sxs-lookup"><span data-stu-id="f0e81-108">Step 1: Prerequisites</span></span>

<span data-ttu-id="f0e81-109">使用 PowerShell 的 Microsoft 团队的远程管理支持只能在运行以下操作系统之一的 64 位计算机上：</span><span class="sxs-lookup"><span data-stu-id="f0e81-109">Remote management of Microsoft Teams by using PowerShell is supported only on 64-bit computers running one of the following operating systems:</span></span>
  
- <span data-ttu-id="f0e81-110">Windows 10</span><span class="sxs-lookup"><span data-stu-id="f0e81-110">Windows 10</span></span>
- <span data-ttu-id="f0e81-111">Windows 8.1</span><span class="sxs-lookup"><span data-stu-id="f0e81-111">Windows 8.1</span></span>
- <span data-ttu-id="f0e81-112">Windows 8</span><span class="sxs-lookup"><span data-stu-id="f0e81-112">Windows 8</span></span> 
- <span data-ttu-id="f0e81-113">Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="f0e81-113">Windows Server 2012 R2</span></span>
- <span data-ttu-id="f0e81-114">Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="f0e81-114">Windows Server 2012</span></span>
- <span data-ttu-id="f0e81-115">Windows Server 2008</span><span class="sxs-lookup"><span data-stu-id="f0e81-115">Windows Server 2008</span></span>
- <span data-ttu-id="f0e81-116">Windows 7</span><span class="sxs-lookup"><span data-stu-id="f0e81-116">Windows 7</span></span>
    
<span data-ttu-id="f0e81-117">受支持的操作系统，除了计算机也必须运行以下：</span><span class="sxs-lookup"><span data-stu-id="f0e81-117">In addition to a supported operating system, the computer must also be running the following:</span></span>
  
- <span data-ttu-id="f0e81-118">PowerShell 3.0 或更高</span><span class="sxs-lookup"><span data-stu-id="f0e81-118">PowerShell 3.0 or higher</span></span>
    
- <span data-ttu-id="f0e81-119">团队 PowerShell 连接器模块</span><span class="sxs-lookup"><span data-stu-id="f0e81-119">Teams PowerShell connector module</span></span>


### <a name="step-2-install-powershell-30-or-higher"></a><span data-ttu-id="f0e81-120">步骤 2： 安装 PowerShell 3.0 或更高</span><span class="sxs-lookup"><span data-stu-id="f0e81-120">Step 2: Install PowerShell 3.0 or higher</span></span>
[<span data-ttu-id="f0e81-121">使用本主题的帮助</span><span class="sxs-lookup"><span data-stu-id="f0e81-121">Use this topic for help</span></span>](https://docs.microsoft.com/skypeforbusiness/set-up-your-computer-for-windows-powershell/download-and-install-windows-powershell-3-0) 

### <a name="step-3-download-and-install-the-teams-connector-module"></a><span data-ttu-id="f0e81-122">步骤 3： 下载并安装团队连接器模块</span><span class="sxs-lookup"><span data-stu-id="f0e81-122">Step 3: Download and install the Teams connector module</span></span>
[<span data-ttu-id="f0e81-123">使用本主题的帮助</span><span class="sxs-lookup"><span data-stu-id="f0e81-123">Use this topic for help</span></span>](https://docs.microsoft.com/skypeforbusiness/set-up-your-computer-for-windows-powershell/download-and-install-the-skype-for-business-online-connector) 

<span data-ttu-id="f0e81-124">从 PowerShell 库使用安装最新模块：</span><span class="sxs-lookup"><span data-stu-id="f0e81-124">Install the latest module from the PowerShell Gallery using:</span></span> 
  
  <span data-ttu-id="f0e81-125">安装模块 MicrosoftTeams</span><span class="sxs-lookup"><span data-stu-id="f0e81-125">Install-Module MicrosoftTeams</span></span>

<span data-ttu-id="f0e81-126">或者，有关详细信息，包可在此处找到：https://www.powershellgallery.com/packages/MicrosoftTeams/</span><span class="sxs-lookup"><span data-stu-id="f0e81-126">Or, for more information, the package can be found here: https://www.powershellgallery.com/packages/MicrosoftTeams/</span></span>

### <a name="step-4-connect-using-the-teams-connector-module"></a><span data-ttu-id="f0e81-127">步骤 4： 连接使用团队连接器模块</span><span class="sxs-lookup"><span data-stu-id="f0e81-127">Step 4: Connect using the Teams connector module</span></span>
[<span data-ttu-id="f0e81-128">使用本主题的帮助</span><span class="sxs-lookup"><span data-stu-id="f0e81-128">Use this topic for help</span></span>](https://docs.microsoft.com/skypeforbusiness/set-up-your-computer-for-windows-powershell/download-and-install-the-skype-for-business-online-connector) 

### <a name="related-topics"></a><span data-ttu-id="f0e81-129">相关主题</span><span class="sxs-lookup"><span data-stu-id="f0e81-129">Related topics</span></span>
- [<span data-ttu-id="f0e81-130">管理团队功能使用 PowerShell</span><span class="sxs-lookup"><span data-stu-id="f0e81-130">Manage Teams features with PowerShell</span></span>](manage-features-with-powershell.md)

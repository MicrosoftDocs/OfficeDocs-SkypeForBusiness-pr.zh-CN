---
title: 要从防病毒扫描中排除的团队文件和文件夹
author: msdmaguire
ms.author: dmaguire
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: ramesa
audience: admin
description: 通过从常规防病毒扫描中排除某些文件和文件夹，提高团队性能。
localization_priority: Normal
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_PracticalGuidance
appliesto:
- Microsoft Teams
ms.openlocfilehash: 4b4a4591bf25d7ef1a5b6efb9ab83c4508e26110
ms.sourcegitcommit: bcebe833d5ff4fcd3d6246fc5ed80980c6f31d0c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2019
ms.locfileid: "37578804"
---
<a name="teams-files-and-folders-to-exclude-from-antivirus-scanning"></a><span data-ttu-id="09431-103">要从防病毒扫描中排除的团队文件和文件夹</span><span class="sxs-lookup"><span data-stu-id="09431-103">Teams files and folders to exclude from antivirus scanning</span></span>
=================================

<span data-ttu-id="09431-104">你可以通过阻止防病毒程序扫描特定团队文件和文件夹来提高团队部署的整体性能。</span><span class="sxs-lookup"><span data-stu-id="09431-104">You can improve the overall performance of your Teams deployment by preventing your antivirus programs from scanning certain Teams files and folders.</span></span> <span data-ttu-id="09431-105">这将避免扫描不需要扫描的文件和文件夹的系统资源的支出。</span><span class="sxs-lookup"><span data-stu-id="09431-105">This will avoid the expenditure of system resources on scanning files and folders that don't need to be scanned.</span></span>

> [!NOTE]
> <span data-ttu-id="09431-106">当用户下载文件或共享文件时，这些文件不会传递到以下部分中列出的位置。</span><span class="sxs-lookup"><span data-stu-id="09431-106">When your users download files or share files with each other, those files don't pass through the locations listed in the following section.</span></span> <span data-ttu-id="09431-107">你的用户的上载、下载或共享文件的位置仍将由防病毒程序定期进行扫描。</span><span class="sxs-lookup"><span data-stu-id="09431-107">The locations where your users do upload, download, or share files will still be regularly scanned by your antivirus program.</span></span>

## <a name="files-and-folders-to-add-to-your-antivirus-safe-lists"></a><span data-ttu-id="09431-108">要添加到防病毒安全列表的文件和文件夹</span><span class="sxs-lookup"><span data-stu-id="09431-108">Files and folders to add to your antivirus safe lists</span></span>

<span data-ttu-id="09431-109">使用防病毒程序支持的过程将以下文件和文件夹添加到您的安全列表。</span><span class="sxs-lookup"><span data-stu-id="09431-109">Use the procedures supported by your antivirus program to add the following files and folders to your safe lists.</span></span> <span data-ttu-id="09431-110">这样做将通过避免对这些位置进行防病毒扫描来节省系统资源。</span><span class="sxs-lookup"><span data-stu-id="09431-110">Doing so will conserve system resources by avoiding antivirus scans of these locations.</span></span>

### <a name="programs"></a><span data-ttu-id="09431-111">节目</span><span class="sxs-lookup"><span data-stu-id="09431-111">Programs</span></span>

<span data-ttu-id="09431-112">将以下团队程序添加到你的防病毒安全列表中。</span><span class="sxs-lookup"><span data-stu-id="09431-112">Add the following Teams programs to your antivirus safe list.</span></span>

<span data-ttu-id="09431-113">**%localappdata%\Microsoft\Teams\current\Teams.exe**</span><span class="sxs-lookup"><span data-stu-id="09431-113">**%localappdata%\Microsoft\Teams\current\Teams.exe**</span></span>

<span data-ttu-id="09431-114">**%localappdata%\Microsoft\Teams\Update.exe**</span><span class="sxs-lookup"><span data-stu-id="09431-114">**%localappdata%\Microsoft\Teams\Update.exe**</span></span>

### <a name="folders"></a><span data-ttu-id="09431-115">Folders</span><span class="sxs-lookup"><span data-stu-id="09431-115">Folders</span></span>

<span data-ttu-id="09431-116">将以下团队文件夹添加到你的防病毒安全列表中。</span><span class="sxs-lookup"><span data-stu-id="09431-116">Add the following Teams folders to your antivirus safe list.</span></span>

|<span data-ttu-id="09431-117">类别</span><span class="sxs-lookup"><span data-stu-id="09431-117">Category</span></span>  |<span data-ttu-id="09431-118">位置</span><span class="sxs-lookup"><span data-stu-id="09431-118">Location</span></span>  |
|---------|---------|
|<span data-ttu-id="09431-119">程序文件</span><span class="sxs-lookup"><span data-stu-id="09431-119">Program files</span></span>  |<span data-ttu-id="09431-120">%localappdata%\Microsoft\Teams</span><span class="sxs-lookup"><span data-stu-id="09431-120">%localappdata%\Microsoft\Teams</span></span>|
|<span data-ttu-id="09431-121">数据文件</span><span class="sxs-lookup"><span data-stu-id="09431-121">Data files</span></span>     |<span data-ttu-id="09431-122">%appdata%\Microsoft\Teams</span><span class="sxs-lookup"><span data-stu-id="09431-122">%appdata%\Microsoft\Teams</span></span>\|
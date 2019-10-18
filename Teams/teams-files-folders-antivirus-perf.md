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
<a name="teams-files-and-folders-to-exclude-from-antivirus-scanning"></a>要从防病毒扫描中排除的团队文件和文件夹
=================================

你可以通过阻止防病毒程序扫描特定团队文件和文件夹来提高团队部署的整体性能。 这将避免扫描不需要扫描的文件和文件夹的系统资源的支出。

> [!NOTE]
> 当用户下载文件或共享文件时，这些文件不会传递到以下部分中列出的位置。 你的用户的上载、下载或共享文件的位置仍将由防病毒程序定期进行扫描。

## <a name="files-and-folders-to-add-to-your-antivirus-safe-lists"></a>要添加到防病毒安全列表的文件和文件夹

使用防病毒程序支持的过程将以下文件和文件夹添加到您的安全列表。 这样做将通过避免对这些位置进行防病毒扫描来节省系统资源。

### <a name="programs"></a>节目

将以下团队程序添加到你的防病毒安全列表中。

**%localappdata%\Microsoft\Teams\current\Teams.exe**

**%localappdata%\Microsoft\Teams\Update.exe**

### <a name="folders"></a>Folders

将以下团队文件夹添加到你的防病毒安全列表中。

|类别  |位置  |
|---------|---------|
|程序文件  |%localappdata%\Microsoft\Teams|
|数据文件     |%appdata%\Microsoft\Teams\|
---
title: 安装团队 PowerShell 模块的预发布版本
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: brandber
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Help
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: 请按照以下步骤从 PowerShell 测试库中安装团队 PowerShell 模块的预发布版本。
ms.openlocfilehash: 1d85fac2ee6a1c8565f8482f7208a2f5ae33db60
ms.sourcegitcommit: 1a6b4efad1e6a958cdbaae4b0e2e231145c9658f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/19/2020
ms.locfileid: "44321765"
---
# <a name="install-the-pre-release-version-of-the-teams-powershell-module"></a>安装团队 PowerShell 模块的预发布版本

本文介绍如何从[PowerShell 测试库](https://www.poshtestgallery.com/packages/MicrosoftTeams/)安装团队 PowerShell 模块的最新预发布版本。 你将需要使用团队 PowerShell 模块的预发布版本，在此方案中，不支持在模块的通用版本中不支持用于管理团队功能的 cmdlet，并且仅适用于预发布版本。

使用这些步骤从 PowerShell 测试库中安装团队 PowerShell 模块的最新预发布版本。

> [!NOTE]
> 不要使用来自[公共 Powershell 库](https://www.powershellgallery.com/packages/MicrosoftTeams/)的模块版本并排从 PowerShell 测试库中安装团队 powershell 模块。 按照以下步骤，首先从公共 PowerShell 库中卸载团队 PowerShell 模块，然后从 PowerShell 测试库中安装最新版本的模块。

1. 关闭所有现有 PowerShell 会话。
2. 启动 Windows PowerShell 模块的新实例。
3. 运行以下内容从公共 PowerShell 库中卸载团队 PowerShell 模块：

    ```PowerShell
    Uninstall-Module -Name MicrosoftTeams
    ```

4. 关闭所有现有 PowerShell 会话。
5. 再次启动 Windows PowerShell 模块，然后运行以下内容以将 PowerShell 测试库注册为受信任的来源：

    ```PowerShell
    Register-PSRepository -Name PSGalleryInt -SourceLocation https://www.poshtestgallery.com/ -InstallationPolicy Trusted
    ```

6. 运行以下内容从 PowerShell 测试库安装最新的团队 PowerShell 模块：

    ```PowerShell
    Install-Module -Name MicrosoftTeams -Repository PSGalleryInt -Force
    ```

7. 运行以下操作，验证是否已成功安装 PowerShell 测试库中的团队 PowerShell 模块的最新版本：

    ```PowerShell
    Get-Module -Name MicrosoftTeams
    ```

#### <a name="update-to-the-latest-version-of-the-teams-powershell-module-from-the-powershell-test-gallery"></a>从 PowerShell 测试库更新到团队 PowerShell 模块的最新版本

如果已从 PowerShell 测试库中安装了团队 PowerShell 模块，请使用以下步骤更新到最新版本。

1. 关闭所有现有 PowerShell 会话。
2. 启动 Windows PowerShell 模块的新实例。
3. 运行以下内容从 PowerShell 测试库更新当前安装的团队 PowerShell 模块版本：

    ```PowerShell
    Update-Module -Name MicrosoftTeams -Force
    ```

4. 运行以下操作，验证是否已成功安装 PowerShell 测试库中的团队 PowerShell 模块的最新版本：

    ```PowerShell
    Get-Module -Name MicrosoftTeams
    ```

## <a name="related-topics"></a>相关主题

- [Teams PowerShell 概览](teams-powershell-overview.md)

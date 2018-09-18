---
title: 使用 MSI 安装 Microsoft Teams
author: Lester-Hewett
ms.author: lehewe
manager: serdars
ms.date: 03/21/2018
ms.topic: article
ms.service: msteams
ms.reviewer: ''
description: 管理员可以使用 Teams MSI 批量部署 Microsoft Teams 来选择用户或计算机。
localization_priority: Normal
search.appverid: MET150
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 78ceb6fa0cd70b5cf6fc25bc9537939beea99b7c
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2018
ms.locfileid: "23882035"
---
<a name="install-microsoft-teams-using-msi"></a>使用 MSI 安装 Microsoft Teams
=================================

为了使用 System Center Configuration Manager、组策略或任何第三方分发机制进行广泛部署，Microsoft 提供了 MSI 文件（[32 位](https://aka.ms/teams32bitmsi)和 [64 位](https://aka.ms/teams64bitmsi)），管理员可以使用这些文件批量部署 Teams 来选择用户或计算机。 管理员可以使用这些文件远程部署 Teams，这样，用户不必手动下载 Teams 应用。 部署后，用户登录相应计算机时将会自动启动 Teams。 建议你将程序包部署到计算机上，以便计算机的所有新用户也会受益于此部署。 
 
> [!Note] 
> 要详细了解 SCCM，请参阅 [System Center Configuration Manager 简介](https://docs.microsoft.com/sccm/core/understand/introduction)。

## <a name="deployment-procedure-recommended"></a>部署过程（推荐）
1. 检索最新程序包。
2. 使用 MSI 预填充的默认值。
3. 部署到计算机（如果可能）。

## <a name="how-the-microsoft-teams-msi-package-works"></a>Microsoft Teams MSI 程序包工作方式

Teams MSI 将安装程序放在 Program Files 中。 每当用户登录新的 Windows 用户配置文件时，将启动该安装程序，并会在该用户的 appdata 文件夹中安装一份 Teams 应用。 如果用户的 appdata 文件夹中已安装 Teams 应用，MSI 安装程序将对该用户跳过该过程。

请勿使用 MSI 部署更新，因为客户端在检测到服务提供了新版本时会自动更新。 要重新部署最新的安装程序，请使用下文所述的 MSI 重新部署过程。 如果部署早期版本的 MSI 程序包，将会在可能的情况下为用户自动更新客户端。 如果部署的版本太低，MSI 将会在用户能够使用 Teams 之前触发应用更新。 

> [!Important] 
> 建议不要更改默认安装位置，因为这可能会中断更新流。 版本太低最终会导致用户无法访问服务。 


## <a name="target-computer-requirements"></a>目标计算机要求

- .NET framework 4.5 或更高版本
- Windows 7 或更高版本
- 每个用户配置文件 3 GB 磁盘空间（推荐）

## <a name="clean-up-and-redeployment-procedure"></a>清理和重新部署过程
如果用户从其用户配置文件中卸载 Teams，MSI 安装程序将会跟踪该用户了卸载 Teams 应用，因此不再为该用户配置文件安装 Teams。 要在卸载了 Teams 的特定计算机上为此用户重新部署 Teams，请执行以下操作：

1. 卸载为每个用户配置文件安装的 Teams 应用。 
2. 卸载后，递归地删除 %localappdata%\Microsoft\Teams\ 下面的目录。 
3. 将 MSI 程序包重新部署到该特定计算机。

> [!TIP] 
> 你可以使用我们的 [Microsoft Teams 部署清理](.\scripts\Powershell-script-teams-deployment-clean-up.md)脚本通过 SCCM 完成步骤 1 和 2。                              


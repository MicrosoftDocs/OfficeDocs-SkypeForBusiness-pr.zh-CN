---
title: 安装 Microsoft 小组使用 MSI
author: ninadara
ms.author: ninadara
manager: serdars
ms.date: 03/21/2018
ms.topic: article
ms.service: msteams
ms.reviewer: ninadara
description: 管理员可以使用批量团队 MSI 部署 Microsoft 小组要选择用户或计算机。
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: e8d1f8b77b4b362b95fb03d3f0202bfc6da619e8
ms.sourcegitcommit: a72a1b71a8ef8e9581038503130c2c1a58a4abdb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/20/2018
---
<a name="install-microsoft-teams-using-msi"></a>安装 Microsoft 小组使用 MSI
===========================================

若要使用系统中心配置管理器，或组策略中或任何第三方分发机制的广泛部署，Microsoft 提供了管理员可以使用批量部署团队选择的 MSI 文件 （ [32 位](http://aka.ms/teams32bitmsi)和[64 位](http://aka.ms/teams64bitmsi)）用户或计算机。 管理员可以使用这些文件，以便用户无需手动下载团队应用程序远程部署团队。 在部署时，团队将自动发布的登录该计算机的所有用户。 我们建议您部署包到计算机，使计算机的所有新用户也将受益于该部署。 
 
> [!Note] 
> 若要了解有关 SCCM 的详细信息，请参阅[引入到系统中心配置管理器](https://docs.microsoft.com/sccm/core/understand/introduction)。

## <a name="deployment-procedure-recommended"></a>部署过程 （推荐）
1. 获取最新的包
2. 使用预设的 MSI 的默认值
3. 部署到计算机时可能

## <a name="how-the-microsoft-teams-msi-package-works"></a>Microsoft 的团队 MSI 包的工作原理

团队 MSI 将在程序文件的安装程序。 只要到新的 Windows 用户配置文件用户迹象，安装程序将启动，一份工作组应用程序将被安装在该用户的应用程序数据文件夹中。 如果用户已有的团队应用程序安装在应用程序数据文件夹中，MSI 安装程序将跳过该用户的过程。

不使用 MSI 部署更新，当它检测到新的版本，则可从该服务，客户端将自动更新。 若要重新部署最新的安装程序，请使用重新部署 MSI 如下所述的过程。 如果您部署中的 MSI 程序包的旧版本，客户端将自动更新时可能的用户。 获取部署非常旧的版本，如果 MSI 将触发应用程序更新之前用户可使用团队。 

> [!Important] 
> 我们不建议您更改默认安装位置，因为这可能会中断更新流程。 具有版本太旧，最终将阻止用户访问该服务。 


## <a name="target-machine-requirements"></a>目标计算机要求

1. .NET framework 4.5 或更高版本
2. Windows 7 或更高版本
2. 3 GB 的磁盘空间，每个用户配置文件 （推荐）

## <a name="clean-up-and-redeployment-procedure"></a>清洁和重新部署过程
如果用户从其用户配置文件卸载团队，MSI 安装程序将跟踪用户已卸载团队的应用程序，并且不再为该用户配置文件安装团队。 若要为此用户卸载其中的特定机器上重新部署团队，执行以下操作：

1. 卸载团队为每个用户配置文件安装的应用程序 
2. 卸载后，删除在 %localappdata%\Microsoft\Teams\ 下，目录递归 
3. 重新部署到该特定计算机中的 MSI 程序包

> [!TIP] 
> 可以使用[Microsoft 小组部署清理](.\scripts\Powershell-script-teams-deployment-clean-up.md)脚本来完成通过 SCCM 的步骤 1 和 2。                              


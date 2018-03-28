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
ms.openlocfilehash: 4b092403be87eb4e87b058ba0e7363d5f2d691f4
ms.sourcegitcommit: 39228142658557890b2173c41db9661eb502b946
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
<a name="install-microsoft-teams-using-msi"></a>安装 Microsoft 小组使用 MSI
===========================================

利用系统中心配置管理器中，或组策略或广泛部署的任何第三方分发机制，Microsoft 提供了管理员能够利用批量部署期间的 MSI 文件 （ [32 位](http://aka.ms/teams32bitmsi)和[64 位](http://aka.ms/teams64bitmsi)）若要选择用户或计算机的 Microsoft 小组。 管理员可以使用这些文件，以便用户无需手动下载团队应用程序远程部署团队。 在部署时，团队将自动启动对于登录在该计算机上的所有用户。 建议您将程序包都部署到机器的因此到的计算机的所有新用户也将受益于该部署。 
 
> [!Note] 
> 若要了解有关 SCCM 的详细信息，请参阅。 [引入到系统中心配置管理器](https://docs.microsoft.com/sccm/core/understand/introduction)

## <a name="deployment-procedure-recommendations"></a>部署过程 （建议）
1. 获取最新的包
2. 使用预设的 MSI 的默认值
3. 部署到计算机时可能

## <a name="how-the-microsoft-teams-msi-package-works"></a>Microsoft 的团队 MSI 包的工作原理

团队 MSI 将在程序文件的安装程序。 只要到新的 Windows 用户配置文件用户迹象，安装程序将启动，一份工作组应用程序将被安装在该用户的应用程序数据文件夹中。 如果用户已有的团队应用程序安装在应用程序数据文件夹中，MSI 安装程序将跳过该用户的过程。

不利用 MSI 部署更新，当它检测到新的版本，则可从该服务，客户端将自动更新。 若要重新部署最新的安装程序，请使用重新部署 MSI 如下所述的过程。 如果您部署中的 MSI 程序包的旧版本，客户端将自动更新时可能的用户。 获取部署非常旧的版本，如果 MSI 将触发应用程序更新之前用户可使用团队。 

> [!Important] 
> 不建议您更改任何安装位置，因为这可能会中断更新流。 它然后最终将阻止用户访问该服务。 


## <a name="target-machine-requirements"></a>目标计算机的要求：

1. .NET framework 4.5 或更高版本
2. Windows 7 或更高版本
2. 32 GB 的磁盘空间，每个用户配置文件 （推荐）

## <a name="clean-upredeployment-procedure"></a>全新 up\redeployment 过程
如果用户对其用户配置文件卸载来自团队，MSI 安装程序将跟踪用户已卸载团队的应用程序，并且不再为该用户配置文件安装团队。 为此它所在的特定机器上的用户卸载您重新部署团队将需要：

1. 卸载团队为每个用户配置文件安装的应用程序 
2. 卸载后，删除在 %localappdata%\Microsoft\Teams\ 下，目录递归 
3. 重新部署到该特定计算机中的 MSI 程序包

> [!TIP] 
> 您可以利用我们的[Microsoft 小组部署清理](.\scripts\Powershell-script-teams-deployment-clean-up.md)脚本来完成通过 SCCM 此步骤 1 和 2。                                


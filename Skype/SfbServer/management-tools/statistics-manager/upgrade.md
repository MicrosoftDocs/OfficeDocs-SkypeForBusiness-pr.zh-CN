---
title: 更新 Skype for Business Server 的统计信息管理器
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 71f5d0a0-ca81-4ac1-b590-8f854504f21f
description: 摘要：阅读本主题，了解如何升级 Skype for business 服务器的统计管理器。
ms.openlocfilehash: de88257b628256c47b68036852d82fb6715c043f
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/08/2020
ms.locfileid: "40992499"
---
# <a name="upgrade-statistics-manager-for-skype-for-business-server"></a>更新 Skype for Business Server 的统计信息管理器
 
**摘要：** 阅读本主题，了解如何升级 Skype for Business 服务器的统计管理器。
  
本主题介绍了如何升级适用于 Skype for Business 服务器的统计信息管理器的现有安装，这是一种功能强大的工具，允许你实时查看 Skype for business Server 运行状况和性能数据。 你可以每隔几秒钟轮询数百台服务器的性能数据，并且在统计信息管理器网站上立即查看结果。 
  
有关统计信息管理器和版本2.0 中的新功能的详细信息，请参阅规划适用于 Skype for business[服务器的统计管理器](plan.md)和[部署 Skype for Business 服务器的统计信息管理器](deploy.md)。
  
升级方法有两种：
  
- **自动升级**。 此方法使用自动脚本。 这是最简单的方法，并且应适用于所有升级方案。
    
- **手动升级**。 此方法在自动升级失败的异常情况下作为备份计划提供。
    
## <a name="prerequisites"></a>先决条件

在升级之前，务必获得以下信息：
  
- 活动侦听器证书指纹
    
- 侦听器服务密码（在安装侦听器和每个代理时输入）
    
- 网站的 SSL 证书配置
    
## <a name="automated-upgrade"></a>自动升级

脚本将收集您的当前证书信息和侦听器密码，请卸载产品的旧版本，然后安装产品的新版本。 服务器上安装的 Redis 实例将不受影响，因此缓存中存储的任何数据在升级过程中将会保留。
  
1. 将代理、监听器和网站的新版本的 MSI 文件以及 Update-StatsMan 脚本连同脚本一起放置到侦听器计算机上的单个文件夹中。
    
2. 打开 PowerShell 管理窗口。 升级侦听器组件：
    
   ```PowerShell
   .\Update-StatsMan.ps1 -Service Listener
   ```

> [!NOTE]
> 统计信息管理器服务密码将在传递到安装程序的命令行中以明文形式显示。 必要时请务必遮蔽显示器。 
  
1. 在运行脚本时，系统将提示您卸载产品的旧版本。 请单击“是”。
    
2. 如果侦听器服务正在运行，系统将提示你关闭该应用程序，然后再继续。 允许应用程序关闭（统计信息管理器侦听器服务将停止）。
    
3. 继续执行安装过程。 您应该会注意到服务密码和证书指纹已预先填充。 如果不是，请添加您保存的值，然后继续。
    
4. 打开 PowerShell 管理窗口。 升级网站组件：
    
   ```PowerShell
   .\Update-StatsMan.ps1 -Service Website
   ```

5. 在运行脚本时，系统将提示您卸载产品的旧版本。 请单击“是”。
    
6. 如果代理服务正在运行，系统将提示你关闭该应用程序，然后再继续。 允许该应用程序关闭（StatsMan 代理服务将停止）。
    
7. 继续执行安装过程。 您应该会注意到服务密码和证书指纹已预先填充。 如果不是，请添加您保存的值，然后继续。
    
8. 打开 PowerShell 管理窗口。 升级代理组件：
    
   ```PowerShell
   .\Update-StatsMan.ps1 -Service Agent
   ```

9. 在运行脚本时，系统将提示您卸载产品的旧版本。 请单击“是”。
    
10. 继续执行安装过程。 您应该会注意到网站端口已预先填充。 如果不是，请添加您保存的值，然后继续。
    
11. 验证是否能够使用浏览器正常浏览该网站。
    
> [!NOTE]
> 代理升级时可使用 -NoPrompt 开关。 这将允许卸载/安装过程在无提示的情况下运行，让 PSExec 等工具能够在许多服务器上远程运行升级。 
  
### <a name="manual-upgrade"></a>手动升级

如果由于某些原因，自动升级失败，您始终可以执行手动升级，如下所示：
  
1. 	在侦听器计算机上，通过“程序和功能”控制面板卸载侦听器、网站和代理（如果安装在此服务器上）。 
    
    > [!NOTE]
    >   保留安装的 Redis，以便在升级过程中维护缓存中的数据。
  
2. 	安装组件的新版本，包括在前面的步骤中出现提示时保存的值。有关安装组件的更多信息，请参阅[部署统计信息管理器](deploy.md#BKMK_Deploy)

    
## <a name="for-more-information"></a>有关详细信息
<a name="BKMK_Fixed"> </a>

有关详细信息，请参阅：
  
- [Skype for Business Server 的统计信息管理器规划](plan.md)
    
- [部署 Skype for Business Server 的统计信息管理器](deploy.md)
    
- [对 Skype for Business Server 的统计信息管理器进行故障排除](troubleshoot.md)

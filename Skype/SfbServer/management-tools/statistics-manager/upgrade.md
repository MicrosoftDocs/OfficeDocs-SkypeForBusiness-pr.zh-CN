---
title: 更新 Skype for Business Server 的统计信息管理器
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: 71f5d0a0-ca81-4ac1-b590-8f854504f21f
description: 摘要：阅读本主题，了解如何升级统计信息管理器Skype for Business Server。
ms.openlocfilehash: 297da8efc1259c1128fd0d60584e1db761465217
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/08/2021
ms.locfileid: "60857329"
---
# <a name="upgrade-statistics-manager-for-skype-for-business-server"></a>更新 Skype for Business Server 的统计信息管理器
 
**摘要：** 阅读本主题，了解如何升级统计信息管理器Skype for Business Server。
  
本主题介绍如何升级现有安装的统计信息管理器 for Skype for Business Server，这是一种功能强大的工具，Skype for Business Server实时查看统计数据运行状况和性能数据。 你可以每隔几秒钟轮询数百台服务器的性能数据，并立即在统计信息管理器网站上查看结果。 
  
有关统计信息管理器和 2.0 版中新增功能的信息，请参阅为[](plan.md)统计信息管理器规划Skype for Business Server和部署统计信息管理器[Skype for Business Server。](deploy.md)
  
有两种升级方法：
  
- **自动升级。** 此方法使用自动化脚本。 这是最简单的方法，应该适用于所有升级方案。
    
- **手动升级。** 此方法作为备份计划提供，以防自动升级失败。
    
## <a name="prerequisites"></a>先决条件

在升级之前，请确保你拥有以下信息：
  
- 活动侦听器证书指纹
    
- 侦听器服务 (在安装侦听器和每个代理时输入) 
    
- 网站的 SSL 证书配置
    
## <a name="automated-upgrade"></a>自动升级

该脚本将收集当前的证书信息和侦听器密码，卸载产品的旧版本，然后安装产品的新版本。 不会触摸服务器上安装的 Redis 实例，因此缓存中存储的任何数据都将在升级过程中保留。
  
1. 将新版本的代理、侦听器和网站的 MSI 文件以及 Update-StatsMan.ps1 脚本放在侦听器计算机的单个文件夹中。
    
2. 打开 PowerShell 管理窗口。 升级侦听器组件：
    
   ```PowerShell
   .\Update-StatsMan.ps1 -Service Listener
   ```

> [!NOTE]
> 统计信息管理器服务密码在传递到安装程序时，将在命令行上以纯文本显示。 请务必根据需要保护监视器。 
  
1. 运行脚本时，系统将提示您卸载产品的旧版本。 回答是。
    
2. 如果侦听器服务正在运行，系统将提示你关闭应用程序，然后再继续。 允许应用程序关闭 (将停止统计信息管理器侦听器) 。
    
3. 继续安装过程。 您应该会注意到服务密码和证书指纹已预先填充。 如果不是，请添加您保存的值，然后再继续。
    
4. 打开 PowerShell 管理窗口。 升级网站组件：
    
   ```PowerShell
   .\Update-StatsMan.ps1 -Service Website
   ```

5. 运行脚本时，系统将提示您卸载产品的旧版本。 回答是。
    
6. 如果代理服务正在运行，系统将提示您关闭应用程序，然后再继续。 允许应用程序关闭 (StatsMan 代理服务将停止) 。
    
7. 继续安装过程。 您应该会注意到服务密码和证书指纹已预先填充。 如果不是，请添加您保存的值，然后再继续。
    
8. 打开 PowerShell 管理窗口。 升级代理组件：
    
   ```PowerShell
   .\Update-StatsMan.ps1 -Service Agent
   ```

9. 运行脚本时，系统将提示您卸载产品的旧版本。 回答是。
    
10. 继续安装过程。 您应注意到网站端口已预先填充。 如果不是，请添加您保存的值，然后再继续。
    
11. 使用浏览器验证网站是否正常工作。
    
> [!NOTE]
> 代理升级可以与 -NoPrompt 开关一同使用。 这将允许卸载/安装过程以静默方式运行，从而允许 PSExec 等工具在大量服务器上远程运行升级。 
  
### <a name="manual-upgrade"></a>手动升级

如果由于某种原因，自动升级失败，则始终可以按如下方式执行手动升级：
  
1. 在侦听器计算机上，卸载侦听器、网站和代理 (如果已在此服务器上安装它) "程序和功能"控制面板进行卸载。 
    
    > [!NOTE]
    >  保持安装 Redis，以便缓存中的数据随后在升级过程中得到维护。
  
2. 安装组件的新版本，包括上述系统提示时保存的值。 有关安装组件的信息，请参阅 [部署统计信息管理器](deploy.md#BKMK_Deploy)

    
## <a name="for-more-information"></a>更多详细信息
<a name="BKMK_Fixed"> </a>

有关详细信息，请参阅：
  
- [Skype for Business Server 的统计信息管理器规划](plan.md)
    
- [部署 Skype for Business Server 的统计信息管理器](deploy.md)
    
- [对 Skype for Business Server 的统计信息管理器进行故障排除](troubleshoot.md)

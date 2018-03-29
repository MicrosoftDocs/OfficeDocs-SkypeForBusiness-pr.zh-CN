---
title: Windows PowerShell 和 Skype for Business Server 2015 管理工具
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 12/20/2016
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6a285f7c-0ef5-4cab-9976-d03be276e35d
description: 在业务服务器 2015年的 Skype，管理工具是使用 Windows PowerShell 来实现的。 Windows PowerShell 包含命令行环境、 特定于产品的命令和完整的脚本语言。 Skype 使用 Windows PowerShell 实现的业务服务器 2015年工具如下所示：
ms.openlocfilehash: 25631ce7acf59567b431d7eebdf190c4b63d7913
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="windows-powershell-and-skype-for-business-server-2015-management-tools"></a>Windows PowerShell 和 Skype for Business Server 2015 管理工具
 
在业务服务器 2015年的 Skype，管理工具是使用 Windows PowerShell 来实现的。 Windows PowerShell 包含命令行环境、 特定于产品的命令和完整的脚本语言。 Skype 使用 Windows PowerShell 实现的业务服务器 2015年工具如下所示： 
  
- **拓扑生成器**。 使用拓扑生成器来创建、 调整和发布规划的拓扑，然后它开始服务器安装之前验证您的拓扑结构。 当您安装 Skype 业务服务器 2015年在单个服务器上时，服务器读取已发布的拓扑作为安装过程的一部分，安装程序部署服务器拓扑中的指导。 安装完成后，配置信息将自动复制到所有服务器。 只能使用拓扑生成器将组件添加到部署中。
    
- **Skype 的业务服务器管理程序**。 可用于 Skype 业务服务器管理外壳程序针对部署的完整命令行管理。
    
- **Skype 的业务服务器的控制面板**。 可以使用 Skype 业务服务器控制面板的用户界面来管理部署中最常见的任务。
    
这些工具管理您的部署，包括接近 550 特定于产品的 cmdlet 使用 Windows PowerShell cmdlet。 包含在 Skype 业务服务器 2015年个安全 cmdlet 主要用于管理身份验证、 用户权利和权限。 多种 cmdlet 可用于管理身份验证，包括用于证书和个人标识号 (PIN) 身份验证的 cmdlet。 此外，大量的 cmdlet 使您能够使用新的基于角色的访问控制 (RBAC) 功能 Skype 的管理控制权委派业务服务器 2015年个。 有关业务服务器 cmdlet 的 Skype 的详细信息，请参阅[业务服务器 2015年管理外壳的 Skype](../../manage/management-shell.md)。
  
专门设计用于 Windows PowerShell 的脚本安全功能有助于防止某些较旧的技术，包括 Microsoft Visual Basic 脚本版本 (VBScript) 的脚本编写相关的任何安全问题。 Windows PowerShell 安全功能是用于创建用户能轻松的环境，也不知不觉地运行脚本。 默认情况下，将启用 Windows PowerShell 的安全功能。 您可以修改以适应您的脚本需要这些功能的状态和各种安全目标。 这并不是说，shell 将使用户运行脚本。 相反，外壳使它困难 — — 默认情况下 — — 用户运行脚本却没有意识到他们这样做。 有关详细信息，请参阅[Windows PowerShell 脚本安全](https://go.microsoft.com/fwlink/p/?LinkId=213145)。
  


---
title: Windows PowerShell 和 Skype for business 服务器管理工具
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6a285f7c-0ef5-4cab-9976-d03be276e35d
description: '在 Skype for Business 服务器中, 管理工具是使用 Windows PowerShell 实现的。 Windows PowerShell 包含命令行环境、特定于产品的命令和完整的脚本语言。 使用 Windows PowerShell 实现的 Skype for Business 服务器工具包括以下内容:'
ms.openlocfilehash: 3eb156e002603378ec77fbbcbde4772870aad907
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34296880"
---
# <a name="windows-powershell-and-skype-for-business-server-management-tools"></a>Windows PowerShell 和 Skype for business 服务器管理工具
 
在 Skype for Business 服务器中, 管理工具是使用 Windows PowerShell 实现的。 Windows PowerShell 包含命令行环境、特定于产品的命令和完整的脚本语言。 使用 Windows PowerShell 实现的 Skype for Business 服务器工具包括以下内容: 
  
- **拓扑生成器**。 你可以使用拓扑生成器来创建、调整和发布你的计划拓扑, 并在开始服务器安装之前验证你的拓扑。 当您在单独的服务器上安装 Skype for Business 服务器时, 服务器会在安装过程中读取已发布的拓扑, 并且安装程序将按照拓扑中的指示部署服务器。 After setup, configuration information is automatically replicated to all servers. Components can be added to your deployment only by using Topology Builder.
    
- **Skype for Business 服务器命令行管理程序**。 你可以使用 Skype for Business Server Management Shell 执行部署的完整命令行管理。
    
- **Skype for Business 服务器 "控制面板"**。 你可以使用 Skype for Business Server 控制面板用户界面管理你的部署中的最常见任务。
    
这些工具使用 Windows PowerShell cmdlet 管理你的部署, 包括靠近550产品的特定 cmdlet。 Skype for Business 服务器中包含的安全 cmdlet 主要用于管理身份验证以及用户权利和权限。 多种 cmdlet 可用于管理身份验证，包括用于证书和个人标识号 (PIN) 身份验证的 cmdlet。 此外, 你可以使用多个 cmdlet 来使用新的基于角色的访问控制 (RBAC) 功能来委派对 Skype for Business 服务器的管理控制。 有关 Skype for business 服务器 cmdlet 的详细信息, 请参阅[skype for Business Server 命令行管理](../../manage/management-shell.md)程序。
  
Windows PowerShell 的脚本安全功能专门设计用于帮助避免较旧技术 (包括 Microsoft Visual Basic 脚本编写 Edition (VBScript)) 的某些脚本相关安全问题。 Windows PowerShell 安全功能旨在创建用户无法轻松或不知不觉地运行脚本的环境。 默认情况下, Windows PowerShell 安全功能已启用。 你可以修改这些功能的状态, 以满足你的脚本需求和各种安全目标。 这并不是说外壳程序使用户无法运行脚本。 相反, shell 使用户在运行脚本时无需意识到这样做会很困难———默认情况下。 有关详细信息, 请参阅[Windows PowerShell 脚本安全性](https://go.microsoft.com/fwlink/p/?LinkId=213145)。
  


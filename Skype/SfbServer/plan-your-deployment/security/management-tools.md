---
title: Windows PowerShell和 Skype for Business Server 管理工具
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 6a285f7c-0ef5-4cab-9976-d03be276e35d
description: 在 Skype for Business Server 中，管理工具使用 Windows PowerShell。 Windows PowerShell 包含命令行环境、产品特定命令和完整的脚本语言。 使用 Windows PowerShell实现的 Skype for Business Server 工具包括：
ms.openlocfilehash: 61f5acdacc1a401a3541ba9d08213ad7f054374a
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51104198"
---
# <a name="windows-powershell-and-skype-for-business-server-management-tools"></a>Windows PowerShell和 Skype for Business Server 管理工具
 
在 Skype for Business Server 中，管理工具使用 Windows PowerShell。 Windows PowerShell 包含命令行环境、产品特定命令和完整的脚本语言。 使用 Windows PowerShell实现的 Skype for Business Server 工具包括： 
  
- **拓扑生成器**。 使用拓扑生成器创建、调整和发布您规划的拓扑，并且它会在您开始安装服务器之前验证拓扑。 在单台服务器上安装 Skype for Business Server 时，服务器会读取发布的拓扑作为安装过程的一部分，并且安装程序将按照拓扑中的指示部署服务器。 安装完成后，配置信息将自动复制到所有服务器。 组件只能使用拓扑生成器添加到部署中。
    
- **Skype for Business Server 命令行管理程序**。 可以使用 Skype for Business Server 命令行管理程序对部署进行完整的命令行管理。
    
- **Skype for Business Server 控制面板**。 可以使用 Skype for Business Server 控制面板用户界面来管理部署中最常见的任务。
    
这些工具使用 Windows PowerShell cmdlet 对部署进行管理，其中包含了近 550 个产品特定的 cmdlet。 Skype for Business Server 中包含的安全 cmdlet 主要用于管理身份验证以及用户权限。 多种 cmdlet 可用于管理身份验证，包括用于证书和个人标识号 (PIN) 身份验证的 cmdlet。 此外，通过许多 cmdlet，您可以使用新的 Role-Based 访问控制 (RBAC) 功能委派 Skype for Business Server 的管理控制。 有关 Skype for Business Server cmdlet 的详细信息，请参阅 [Skype for Business Server Management Shell](../../manage/management-shell.md)。
  
Windows PowerShell 脚本安全功能专门设计用于帮助防止较早技术（包括 Microsoft Visual Basic Scripting Edition (VBScript) ）的一些脚本相关的安全问题。 这些功能Windows PowerShell旨在创建用户无法轻松或不知情地运行脚本的环境。 默认情况下，Windows PowerShell启用安全功能。 您可以修改这些功能的状态，以满足脚本编写需要和各种安全目标。 这不是说命令行管理程序使用户无法运行脚本。 相反，默认情况下，命令行管理程序会使用户难以运行脚本，而不会意识到他们这样做。 有关详细信息，请参阅脚本 [Windows PowerShell安全](/previous-versions/msdn10/gg261722(v=msdn.10))。

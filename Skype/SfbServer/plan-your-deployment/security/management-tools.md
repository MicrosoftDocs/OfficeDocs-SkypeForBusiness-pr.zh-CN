---
title: Windows PowerShell 和 Skype 的业务 Server 管理工具
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6a285f7c-0ef5-4cab-9976-d03be276e35d
description: Skype 业务服务器，在使用 Windows PowerShell 实现管理工具。 Windows PowerShell 包括命令行环境、 特定于产品的命令和完整的脚本语言。 使用 Windows PowerShell 实现的业务服务器工具的 Skype 包括：
ms.openlocfilehash: 743823e5465d6fa18f46d0f8f38802098416d7e6
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32213590"
---
# <a name="windows-powershell-and-skype-for-business-server-management-tools"></a>Windows PowerShell 和 Skype 的业务 Server 管理工具
 
Skype 业务服务器，在使用 Windows PowerShell 实现管理工具。 Windows PowerShell 包括命令行环境、 特定于产品的命令和完整的脚本语言。 使用 Windows PowerShell 实现的业务服务器工具的 Skype 包括： 
  
- **拓扑生成器**。 使用拓扑生成器来创建、 调整和发布您规划的拓扑和服务器安装之前，它会验证您的拓扑。 在安装时 Skype 业务服务器在单个服务器上，服务器作为一部分安装过程中，阅读发布的拓扑并安装程序将部署服务器，如拓扑中的说明。 After setup, configuration information is automatically replicated to all servers. Components can be added to your deployment only by using Topology Builder.
    
- **Skype 的业务 Server 命令行管理程序**。 可用于 Skype 业务 Server 命令行管理程序的完整命令行管理部署。
    
- **Skype 的业务 Server Control Panel**。 您可以使用业务 Server Control Panel 用户界面的 Skype 部署中管理最常见任务。
    
这些工具使用 Windows PowerShell cmdlet 进行管理部署，包括接近 550 特定于产品的 cmdlet。 Skype 中包含业务服务器的安全 cmdlet 主要用于管理身份验证和用户权限和权限。 多种 cmdlet 可用于管理身份验证，包括用于证书和个人标识号 (PIN) 身份验证的 cmdlet。 此外，数 cmdlet 使您能够使用新的基于角色的访问控制 (RBAC) 功能的 Skype 管理控制权限委派业务服务器。 有关 Business Server cmdlet Skype 详细信息，请参阅[Business Server Management Shell 的 Skype](../../manage/management-shell.md)。
  
有关 Windows PowerShell 脚本安全功能专门为了帮助防止的一些较旧的技术，包括 Microsoft Visual Basic Scripting Edition (VBScript) 编写脚本相关的安全问题。 Windows PowerShell 安全功能是用于创建用户无法轻松环境或不知情的情况下运行脚本。 默认情况下启用 Windows PowerShell 安全功能。 您可以修改这些功能，以容纳您脚本的需求的状态和各种安全目标。 这并不是说的命令行管理程序将使用户运行脚本。 相反，在命令行管理的难度 — 默认情况下 — 用户没有意识到运行脚本它们这样做。 有关详细信息，请参阅[Windows PowerShell 脚本 Security](https://go.microsoft.com/fwlink/p/?LinkId=213145)。
  


---
title: Lync Server 2013：Windows PowerShell 和 Lync Server 管理工具
TOCTitle: Windows PowerShell 和 Lync Server 2013 管理工具
ms:assetid: 6a285f7c-0ef5-4cab-9976-d03be276e35d
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Dn481130(v=OCS.15)
ms:contentKeyID: 59679361
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Windows PowerShell 和 Lync Server 2013 管理工具

 

_**上一次修改主题：** 2016-12-08_

在 Microsoft Lync Server 2013 中，管理工具使用 Windows PowerShell 实施。Windows PowerShell 包括命令行环境、产品特定命令和完整的脚本语言。使用 Windows PowerShell 实施的 Lync Server 2013 工具包括：

  - **拓扑生成器**。使用拓扑生成器可以创建、调整和发布您所规划的拓扑，还可以在开始安装服务器之前验证您的拓扑。在各个服务器上安装 Lync Server 2013 时，这些服务器会在安装过程中读取发布的拓扑，而安装程序会根据拓扑中的指示部署服务器。安装完成后，配置信息将自动复制到所有服务器。组件只能使用拓扑生成器添加到部署中。

  - **Lync Server 命令行管理程序**。可以使用 Lync Server 命令行管理程序 对部署进行完整的命令行管理。

  - **Lync Server 控制面板**。可以使用 Microsoft Lync Server 2013 控制面板 用户界面来管理部署内的最常见任务。

这些工具使用 Windows PowerShell cmdlet 对部署进行管理，其中包含了近 550 个产品特定的 cmdlet。Lync Server 2013 中包含的安全性 cmdlet 主要用于管理身份验证和用户权限。多种 cmdlet 可用于管理身份验证，包括用于证书和个人标识号 (PIN) 身份验证的 cmdlet。此外，还有很多 cmdlet 能够让您使用新的基于角色的访问控制 (RBAC) 功能委派 Lync Server 2013 的管理控制。有关 Lync Server cmdlet 的详细信息，请参阅操作文档中的 [Lync Server 命令行管理程序](lync-server-2013-lync-server-management-shell.md)。有关使用拓扑生成器和 Lync Server 2013 控制面板 管理部署的详细信息，请参阅操作文档中的 [Lync Server 2013 控制面板](https://technet.microsoft.com/zh-cn/library/gg133224\(v=ocs.15\))。

Windows PowerShell 的脚本安全功能专门帮助应对早期技术中存在的某些脚本相关的安全问题，包括 Microsoft Visual Basic Scripting Edition (VBScript)。Windows PowerShell 安全功能将创建一个用户无法轻易或无意中运行脚本的环境。Windows PowerShell 安全功能默认为启用状态。您可以根据您的脚本需要和各个安全目标，对这些功能的状态进行修改。这并不意味着此 shell 禁止用户运行脚本，而是让用户很难（默认设置）在无意中运行脚本。有关详细信息，请参阅 Windows PowerShell 脚本安全性，网址为 [http://go.microsoft.com/fwlink/p/?LinkId=213145](http://go.microsoft.com/fwlink/p/?linkid=213145)。


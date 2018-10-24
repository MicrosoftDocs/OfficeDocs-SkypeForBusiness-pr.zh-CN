---
title: Lync Server 2013：运行 Lync Server 2013 的服务器的系统要求
TOCTitle: 运行 Lync Server 2013 的服务器的系统要求
ms:assetid: 781d487d-5958-416a-becb-904d9af3cc0a
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398588(v=OCS.15)
ms:contentKeyID: 49313318
ms.date: 07/21/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 运行 Lync Server 2013 的服务器的系统要求

 

_**上一次修改主题：** 2016-12-08_

> [!NOTE]  
> 有关硬件要求的详细信息，请参阅<a href="lync-server-2013-server-hardware-platforms.md">适用于 Lync Server 2013 的服务器硬件平台</a>。


Standard Edition Server 和 Enterprise Edition Server 共享相同的软件要求。

运行 Lync Server 2013 Enterprise Edition 的服务器供大型组织用于主要组织部署。Enterprise Edition 服务器的设计规模为每个池大约承载 80,000 个用户。运行 Lync Server 2013 Standard Edition 的服务器供小型组织和主要组织部署的远程位置使用。一对 标准版 服务器最多可支持 5,000 个用户。有关 Standard Edition 服务器与 Enterprise Edition 服务器之间差异的详细信息，请参阅[Lync Server 2013 部署概述](lync-server-2013-deployment-overview.md)。

## 操作系统安装

> [!IMPORTANT]
> Lync Server 2013 只提供 64 位版本，要求使用 64 位硬件和 64 位版本的 Windows Server 操作系统。此发行版不提供 Lync Server 2013 的 32 位版本。


Standard Edition Server 和 Enterprise Edition Server 可以使用以下任意项：

  - Windows Server 2008 R2 SP1 或最新的 Service Pack

  - Windows Server 2012

  - Windows Server 2012 R2

在 Standard Edition Server 或 Enterprise Edition 前端服务器上安装操作系统软件。应用所有更新以使操作系统达到最新更新以及与组织标准一致的必需更新级别。有关操作要求的更多详细信息，请参阅可支持性文档中的 [Lync Server 2013 中的服务器和工具操作系统支持](lync-server-2013-server-and-tools-operating-system-support.md)。

> [!NOTE]  
> 若要使 Lync Server 2013 可在 Windows Server 2012 R2 上正常工作，您可能需要在 Windows Server 中更改一个注册表项的值。您可能需要此更改以使证书可以正常工作，并使客户可以通过 Survivable Branch Appliance 注册。如需了解详细信息，请参阅 <a href="http://support.microsoft.com/kb/2901554" class="uri">http://support.microsoft.com/kb/2901554</a>。


## 用于 Lync Server 2013 的其他软件

除操作系统必需的更新之外， Lync Server 2013 还需要操作系统角色、功能以及用于操作的软件。有关在发布拓扑和安装 Lync Server 2013 之前必须安装的其他软件的详细信息，请参阅规划文档中的 [Lync Server 2013 的其他软件要求](lync-server-2013-additional-software-requirements.md)。

## 所有服务器角色所需的其他软件

在所有服务器角色中，还必须确保已安装 Windows PowerShell 命令行接口 3.0 和 Microsoft .NET Framework 4.5。

此外，将运行 Lync Server 管理工具的任何计算机上都需要安装 Windows PowerShell 命令行接口 3.0 和 Microsoft .NET Framework 4.5。

## Windows PowerShell 3.0

Lync Server 2013 需要在将加入 Lync Server 拓扑的每台计算机上安装 Windows PowerShell 3.0。有关安装 Windows PowerShell 3.0 的详细信息，请参阅 [为 Lync Server 2013 安装 Windows PowerShell 3.0](lync-server-2013-installing-windows-powershell-3-0.md)。

> [!NOTE]  
> 在 Windows Server 2008 R2 SP1 中，在安装 Microsoft .NET Framework 4.5 之前，无法安装 Windows PowerShell 命令行接口 3.0。


## Microsoft .NET Framework 4.5

在将在 Windows Server 2012 或 Windows Server 2012 R2 上运行 Lync Server 2013 的服务器上安装 Microsoft .NET Framework 4.5 时，您必须执行一个额外步骤。安装 .NET Framework 4.5 之后，请使用服务器管理器安装 HTTP 激活。

**在 Windows Server 2012 或 Windows Server 2012 R2 上安装 .NET 4.5 HTTP 激活**

1.  从“开始”菜单中，依次单击“程序”、“管理工具”和“服务器管理器”。

2.  在服务器管理器的“功能摘要”下，选择“添加功能”。

3.  展开“.NET Framework 4.5”。

4.  选择“WCF 激活”（如果尚未选择它）。然后选择“HTTP 激活”。

5.  单击“下一步”，然后按照提示完成安装。


---
title: Lync Server 2013：管理工具软件要求
TOCTitle: 管理工具软件要求
ms:assetid: 2fb172c3-7b84-4e49-981c-2a17e7a00a29
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg195653(v=OCS.15)
ms:contentKeyID: 49312384
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 中的管理工具软件要求

 

_**上一次修改主题：** 2016-12-08_

该主题描述除了操作系统必备组件外，安装和使用 Lync Server 2013 管理工具所需的软件。

## Microsoft .NET Framework 4.5

Lync Server 2013 需要 64 位版本的 Microsoft .NET Framework 4.5。

## Windows PowerShell 3.0

Windows PowerShell 3.0 是运行 Microsoft Lync Server 2013 的任何组件所必需的。有关详细信息，请参阅 [为 Lync Server 2013 安装 Windows PowerShell 3.0](lync-server-2013-installing-windows-powershell-3-0.md)。

## Windows Installer 4.5

Lync Server 2013 使用 Windows Installer 技术安装、卸载和维护各种服务器角色。Windows Installer 4.5 可用作 Windows Server 操作系统的可再发行组件。Windows Installer 4.5 随 Windows Server 2012 R2、Windows Server 2012 和 Windows Server 2008 R2 提供，这意味着您无需为运行 Lync Server 2013 的任何计算机下载该实用程序。（Lync Server 2013 只能安装在运行 Windows Server 2012 R2、Windows Server 2012 或 Windows Server 2008 R2 的计算机上。）

但是，如果您想要在管理员工作站上安装 Lync Server 命令行管理程序 或 Lync Server 拓扑生成器，则可能需要下载 Windows Installer 4.5。该实用程序随 Windows 7 和 Windows 2008 R2 提供，但是不随 Windows 操作系统的任何早期版本提供。您可以从 Microsoft 下载中心下载 Windows Installer 4.5，网址为 <http://go.microsoft.com/fwlink/p/?linkid=197395>。

## Microsoft Silverlight 5 浏览器插件

Lync Server 2013 控制面板是基于 Web 的工具，需要安装最新版本的 Microsoft Silverlight 5 浏览器插件。如果启动 Lync Server 2013 控制面板时未安装此软件或者安装了早期版本， Lync Server 2013 控制面板将提示您安装需要的版本。

## 另请参阅

#### 概念

[Lync Server 2013 中的服务器和工具操作系统支持](lync-server-2013-server-and-tools-operating-system-support.md)  

#### 其他资源

[Lync Server 2013 中的管理工具基础结构要求](lync-server-2013-administrative-tools-infrastructure-requirements.md)  
[Lync Server 2013 的安装和管理所需的管理员权限](lync-server-2013-administrator-rights-and-permissions-required-for-setup-and-administration.md)


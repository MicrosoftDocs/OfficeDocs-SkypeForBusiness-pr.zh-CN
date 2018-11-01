---
title: Lync Server 2013：Lync Server 管理工具
TOCTitle: Lync Server 管理工具
ms:assetid: 9b006f93-4f3d-461d-89b8-e80a34fdb3c5
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg195756(v=OCS.15)
ms:contentKeyID: 49313708
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 管理工具

 

_**上一次修改主题：** 2016-12-08_

本主题介绍针对 Lync Server 2013 的管理工具。

默认情况下，这些管理工具安装在每个 Lync Server 服务器上。此外，您可在其他计算机（如专用管理控制台）上安装这些管理工具。有关安装管理工具的过程，请参阅 [安装 Lync Server 2013 管理工具](lync-server-2013-install-lync-server-administrative-tools.md)。有关打开这些管理工具来执行管理任务的过程，请参阅 [打开 Lync Server 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

在安装或使用 Lync Server 管理工具之前，请务必查看基础结构、操作系统、软件和管理员权限要求。有关基础结构要求的详细信息，请参阅 [Lync Server 2013 中的管理工具基础结构要求](lync-server-2013-administrative-tools-infrastructure-requirements.md)。有关安装 Lync Server 管理工具的操作系统和软件要求的详细信息，请参阅 [Lync Server 2013 中的服务器和工具操作系统支持](lync-server-2013-server-and-tools-operating-system-support.md)、 [Lync Server 2013 的其他软件要求](lync-server-2013-additional-software-requirements.md)和 [Lync Server 2013 中的其他服务器支持和要求](lync-server-2013-additional-server-support-and-requirements.md)。 [Lync Server 2013 的安装和管理所需的管理员权限](lync-server-2013-administrator-rights-and-permissions-required-for-setup-and-administration.md)中介绍了安装和使用这些管理工具所需的用户权限。

管理工具由以下几种工具组成：

  - **Lync Server 部署向导**   用于部署 Lync Server 和安装所有管理工具。

  - **Lync Server拓扑生成器**   用于定义部署中的组件。

  - **Lync Server 控制面板**   用于通过基于 Web 的界面持续管理部署。

  - **Lync Server 命令行管理程序**   用于通过命令行来持续管理部署。

  - **Lync Server 日志记录工具**   用于解决部署中出现的问题。

  - **集中日志记录服务**   从一台计算机、池、站点或全局收集日志和跟踪文件。选择和定义包含供应商、标志和跟踪级别的方案。通过诸如任何基于文本的工具或 Snooper.exe 之类的工具收集、汇总和显示日志记录。

您主要可使用 拓扑生成器和 Lync Server 控制面板来管理。

## 部署向导

您必须使用安装媒体中包含的 Lync Server 部署向导来将所有管理工具安装到尚未安装 Lync Server 的计算机。在安装管理工具的过程中， Lync Server 部署向导将与其他工具一起进行本地安装，以便您稍后能使用它来安装其他组件的文件或删除计算机上不需要的组件的文件。

有关如何首次从 Lync Server 安装媒体运行 Lync Server 部署向导的详细信息，请参阅 [安装 Lync Server 2013 管理工具](lync-server-2013-install-lync-server-administrative-tools.md)。

## 拓扑生成器

有关可使用 拓扑生成器执行的部署任务的详细信息，请参阅针对每个服务器角色的部署文档。

## Lync Server 控制面板

您可以使用 Lync Server 2013 控制面板执行管理和维护 Lync Server 2013 所需的大多数管理任务。 Lync Server 控制面板为您提供了一个图形用户界面 (GUI)，用于管理组织中运行 Lync Server 的服务器、用户、客户端和设备的配置。 Lync Server 命令行管理程序将 Lync Server 控制面板用作基础机制来执行 Lync Server 配置。

Lync Server 控制面板会自动安装在每台 Lync Server 前端服务器或 Standard Edition Server 上。在此版本中，您可以远程管理边缘服务器。您还可以在另一台计算机上安装 Lync Server 控制面板，如从其上集中管理 Lync Server 的管理控制台。有关详细信息，请参阅 [安装 Lync Server 2013 管理工具](lync-server-2013-install-lync-server-administrative-tools.md)。

> [!IMPORTANT]  
> <ul>
> <li><p>要使用 Lync Server 控制面板配置设置，必须使用分配给 CsAdministrator 角色的帐户登录。有关 Lync Server 2013 中提供的预定义管理角色的详细信息，请参阅<a href="lync-server-2013-planning-for-role-based-access-control.md">在 Lync Server 2013 中规划基于角色的访问控制</a>。</p></li>
> <li><p>要使用 Lync Server 控制面板配置设置，还必须使用的屏幕分辨率至少为 1024 x 768 的计算机。</p></li>
> </ul>

## Lync Server 命令行管理程序

在 Lync Server 中， Lync Server 命令行管理程序提供了一种新的管理和维护方法。 Lync Server 命令行管理程序是一类基于 Windows PowerShell 命令行接口 构建的功能强大的管理接口，包含一整套特定于 Lync Server 的 cmdlet。通过使用 Lync Server 命令行管理程序，可以获取一组丰富的配置和自动化控制功能。 拓扑生成器和 Lync Server 控制面板都实现了这些 cmdlet 的子集以支持对 Lync Server 的管理。 Lync Server 命令行管理程序包含用于所有 Lync Server 管理任务的 cmdlet，您可以单独使用这些 cmdlet 管理部署。有关详细信息，请参阅 [Lync Server 命令行管理程序](lync-server-2013-lync-server-management-shell.md)文档或针对每个 cmdlet 的命令行帮助。

## 日志记录工具

通过在产品运行期间捕获来自产品的日志记录和跟踪信息， Lync Server 日志记录工具可帮助进行故障排除。可以使用此工具在任何 Lync Server 服务器角色上运行调试会话。有关日志记录工具的详细信息，请参阅 TechNet 库中的 Lync Server 2010 日志记录工具文档，网址为 <http://go.microsoft.com/fwlink/?linkid=199265>。

> [!IMPORTANT]
> 建议在所有情况下，所有通过 Lync Server 日志记录工具进行的日志记录收集工作都使用 集中日志记录服务。虽然 Lync Server 日志记录工具仍可运行，但如果 集中日志记录服务已在运行，它会产生干扰或者表现得基本无效。您只能单独使用 集中日志记录服务或 Lync Server 日志记录工具，切勿两个同时使用。有关 集中日志记录服务以及为何应以独占方式使用它的详细信息，请参阅 <a href="lync-server-2013-using-the-centralized-logging-service.md">使用集中日志记录服务</a>。


## 本节内容

  - [Lync Server 2013 中的管理工具基础结构要求](lync-server-2013-administrative-tools-infrastructure-requirements.md)

  - [Lync Server 2013 中的服务器和工具操作系统支持](lync-server-2013-server-and-tools-operating-system-support.md)

  - [Lync Server 2013 中的管理工具软件要求](lync-server-2013-administrative-tools-software-requirements.md)

  - [Lync Server 2013 的安装和管理所需的管理员权限](lync-server-2013-administrator-rights-and-permissions-required-for-setup-and-administration.md)

  - [在 Lync Server 2013 中发布拓扑的要求](lync-server-2013-requirements-to-publish-a-topology.md)

  - [安装 Lync Server 2013 管理工具](lync-server-2013-install-lync-server-administrative-tools.md)

  - [打开 Lync Server 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)

  - [Lync Server 2013 控制面板疑难解答](lync-server-2013-troubleshooting-lync-server-2013-control-panel.md)

  - [使用集中日志记录服务](lync-server-2013-using-the-centralized-logging-service.md)

## 另请参阅

#### 其他资源

[Lync Server 命令行管理程序](lync-server-2013-lync-server-management-shell.md)


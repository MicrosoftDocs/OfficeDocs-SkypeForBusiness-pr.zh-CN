---
title: Lync Server 2013： Lync Server 管理工具
description: Lync Server 2013： Lync Server 管理工具。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Lync Server administrative tools
ms:assetid: 9b006f93-4f3d-461d-89b8-e80a34fdb3c5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg195756(v=OCS.15)
ms:contentKeyID: 48184972
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b654d48c6ad52175bfdfe745518007d76d626a37
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48571958"
---
# <a name="lync-server-2013-administrative-tools"></a>Lync Server 2013 管理工具

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2013-02-21_

本主题介绍了 Lync Server 2013 的管理工具。

默认情况下，在每台 Lync Server 服务器上安装管理工具。 此外，您可在其他计算机（如专用管理控制台）上安装这些管理工具。 有关安装管理工具的过程，请参阅 [Install Lync Server 2013 管理工具](lync-server-2013-install-lync-server-administrative-tools.md)。 有关打开用于执行管理任务的工具的过程，请参阅 [Open Lync Server 2013 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

在安装或使用 Lync Server 管理工具之前，请确保查看基础结构、操作系统、软件和管理员权限要求。 有关基础结构要求的详细信息，请参阅 [Lync Server 2013 中的管理工具基础结构要求](lync-server-2013-administrative-tools-infrastructure-requirements.md)。 有关操作系统和软件要求的详细信息，以安装 Lync Server 管理工具，请参阅 lync server [2013 中的服务器和工具操作系统支持](lync-server-2013-server-and-tools-operating-system-support.md)、 [lync server 2013 的其他软件要求](lync-server-2013-additional-software-requirements.md)以及 [Lync server 2013 中的其他服务器支持和要求](lync-server-2013-additional-server-support-and-requirements.md)。 安装和使用这些工具所需的用户权利和权限在 [设置和管理 Lync Server 2013 所需的管理员权限和权限](lync-server-2013-administrator-rights-and-permissions-required-for-setup-and-administration.md)中进行了说明。

管理工具由以下几种工具组成：

  - **Lync Server 部署向导**    使用部署 Lync Server 并安装所有管理工具。

  - **Lync Server 拓扑生成器**    用于定义部署中的组件。

  - **Lync Server 控制面板**    使用基于 web 的界面对部署进行日常管理。

  - **Lync Server 命令行**     管理程序使用命令行对部署进行日常管理。

  - **Lync Server 日志记录工具**    用于解决部署中的问题。

  - **集中日志记录服务**    从一台计算机、池、站点或全局文件收集日志和跟踪文件。 选择并定义包含提供程序、标志和跟踪级别的方案。 收集、聚合和显示包含工具（如任何基于文本的工具或 Snooper.exe）的日志记录。

您可以通过主要使用拓扑生成器和 Lync Server 控制面板来管理您的部署。

<div>

## <a name="deployment-wizard"></a>部署向导

必须使用安装媒体上包含的 Lync Server 部署向导将所有管理工具安装到尚未安装 Lync Server 的计算机上。 在管理工具安装过程中，会将 Lync Server 部署向导与其他工具一起安装在本地，以便以后可以使用它为其他组件安装文件或删除计算机上不需要的组件的文件。

有关如何在 Lync Server 安装介质中首次运行 Lync Server 部署向导的详细信息，请参阅 [Install Lync server 2013 管理工具](lync-server-2013-install-lync-server-administrative-tools.md)。

</div>

<div>

## <a name="topology-builder"></a>拓扑生成器

有关您可以使用拓扑生成器执行的部署任务的详细信息，请参阅部署文档中的每个服务器角色。

</div>

<div>

## <a name="lync-server-control-panel"></a>Lync 服务器控制面板

您可以使用 Lync Server 2013 控制面板执行管理和维护 Lync Server 2013 所需的大部分管理任务。 Lync Server 控制面板为您提供了图形用户界面 (GUI) 管理运行 Lync Server 的服务器的配置，以及组织中的用户、客户端和设备。 Lync Server 命令行管理程序使用 Lync Server 控制面板作为执行 Lync Server 配置的基础机制。

Lync Server 控制面板将自动安装在每个 Lync Server 前端服务器或 Standard Edition server 上。 在此版本中，您可以远程管理边缘服务器。 您还可以在另一台计算机上安装 Lync Server 控制面板，例如，要从中集中管理 Lync Server 的管理控制台。 有关详细信息，请参阅 [Install Lync Server 2013 管理工具](lync-server-2013-install-lync-server-administrative-tools.md)。

<div>


> [!IMPORTANT]  
> <UL>
> <LI>
> <P>若要使用 Lync Server 控制面板配置设置，必须使用分配给 CsAdministrator 角色的帐户登录。 有关 Lync Server 2013 中提供的预定义管理角色的详细信息，请参阅 <A href="lync-server-2013-planning-for-role-based-access-control.md">在 Lync server 2013 中规划基于角色的访问控制</A>。</P>
> <LI>
> <P>若要使用 Lync Server 控制面板配置设置，还必须使用最小屏幕分辨率为 1024 x 768 的计算机。</P></LI></UL>



</div>

</div>

<div>

## <a name="lync-server-management-shell"></a>Lync Server 命令行管理程序

在 Lync Server 中，Lync Server 命令行管理程序提供了一种新的管理和管理方法。 Lync Server 命令行管理程序是一种功能强大的管理界面，内置于 Windows PowerShell 命令行界面中，其中包含一组专用于 Lync Server 的 cmdlet。 借助 Lync Server 命令行管理程序，您可以获得一组丰富的配置和自动化控件。 拓扑生成器和 Lync Server 控制面板都实现这些 cmdlet 的子集，以支持 Lync Server 的管理。 Lync Server 命令行管理程序包含所有 Lync Server 管理任务的 cmdlet，您可以单独使用这些 cmdlet 来管理您的部署。 有关详细信息，请参阅 [Lync Server 2013](lync-server-2013-lync-server-management-shell.md) 命令行管理程序文档或每个 cmdlet 的命令行帮助。

</div>

<div>

## <a name="logging-tool"></a>日志记录工具

Lync Server 日志记录工具可通过在产品运行时捕获产品中的日志记录和跟踪信息来简化故障排除。 您可以使用该工具在任何 Lync Server 服务器角色上运行调试会话。 有关日志记录工具的详细信息，请参阅 TechNet Library 上的 Lync Server 2010 日志记录工具文档 [https://go.microsoft.com/fwlink/p/?linkId=199265](https://go.microsoft.com/fwlink/p/?linkid=199265) 。

<div>


> [!IMPORTANT]  
> 在所有情况下，建议通过 Lync Server 日志记录工具的所有日志记录收集的集中日志记录服务。 Lync Server 日志记录工具仍可正常运行，但如果集中日志记录服务已在运行，它将干扰或呈现为大部分的无效。 应仅使用集中式日志记录服务或 Lync Server 日志记录工具，但决不会同时使用这两个工具。 有关集中日志记录服务以及应以独占方式使用它的原因的详细信息，请参阅 <A href="lync-server-2013-using-the-centralized-logging-service.md">使用 Lync Server 2013 中的集中日志记录服务</A>。



</div>

</div>

<div>

## <a name="in-this-section"></a>本部分内容

  - [Lync Server 2013 中的管理工具基础结构要求](lync-server-2013-administrative-tools-infrastructure-requirements.md)

  - [Lync Server 2013 中的服务器和工具操作系统支持](lync-server-2013-server-and-tools-operating-system-support.md)

  - [Lync Server 2013 中的管理工具软件要求](lync-server-2013-administrative-tools-software-requirements.md)

  - [安装和管理 Lync Server 2013 所需的管理员权利和权限](lync-server-2013-administrator-rights-and-permissions-required-for-setup-and-administration.md)

  - [在 Lync Server 2013 中发布拓扑的要求](lync-server-2013-requirements-to-publish-a-topology.md)

  - [安装 Lync Server 2013 管理工具](lync-server-2013-install-lync-server-administrative-tools.md)

  - [打开 Lync Server 2013 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)

  - [Lync Server 2013 控制面板疑难解答](lync-server-2013-troubleshooting-lync-server-2013-control-panel.md)

  - [在 Lync Server 2013 中使用集中日志记录服务](lync-server-2013-using-the-centralized-logging-service.md)

</div>

<div>

## <a name="see-also"></a>另请参阅


[Lync Server 2013 命令行管理程序](lync-server-2013-lync-server-management-shell.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


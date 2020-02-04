---
title: Lync Server 2013：Lync Server 管理工具
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
ms.openlocfilehash: a34561e9880870b53cd8f7aaad2fe13cfe33c8d4
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41742222"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="lync-server-2013-administrative-tools"></a>Lync Server 2013 管理工具

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2013-02-21_

本主题介绍了 Lync Server 2013 的管理工具。

默认情况下，在每台 Lync 服务器服务器上安装 "管理工具"。 此外，还可以在其他计算机上安装管理工具，如专用管理控制台。 有关安装管理工具的过程，请参阅[安装 Lync Server 2013 管理工具](lync-server-2013-install-lync-server-administrative-tools.md)。 有关打开用于执行管理任务的工具的步骤，请参阅[打开 Lync Server 2013 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

在安装或使用 Lync Server 管理工具之前，请确保查看基础结构、操作系统、软件和管理员权限要求。 有关基础结构要求的详细信息，请参阅[Lync Server 2013 中的管理工具基础结构要求](lync-server-2013-administrative-tools-infrastructure-requirements.md)。 有关操作系统和软件要求安装 Lync Server 管理工具的详细信息，请参阅[lync server 2013 中的 "服务器和工具" 操作系统支持](lync-server-2013-server-and-tools-operating-system-support.md)、lync [server 2013 的其他软件要求](lync-server-2013-additional-software-requirements.md)以及[Lync server 2013 中的其他服务器支持和要求](lync-server-2013-additional-server-support-and-requirements.md)。 安装和使用工具所需的用户权利和权限在[设置和管理 Lync Server 2013 所需的管理员权限和权限](lync-server-2013-administrator-rights-and-permissions-required-for-setup-and-administration.md)中进行了说明。

管理工具包括以下内容：

  - **Lync server 部署向导**   用于部署 Lync Server 和安装所有管理工具。

  - **Lync Server 拓扑生成器**   用于在部署中定义组件。

  - **Lync Server 控制面板**   用于通过使用基于 web 的界面对部署进行日常管理。

  - **Lync Server Management Shell**   使用命令行对部署进行持续管理。

  - **Lync Server 日志记录工具**   用于解决部署中的问题。

  - **集中式日志记录服务**   从一台计算机、池、站点或全局位置收集日志和跟踪文件。 选择并定义包含提供程序、标志和跟踪级别的方案。 日志记录被收集、聚合并与工具（如任何基于文本的工具或 Snooper）一起显示。

你可以通过使用拓扑生成器和 Lync Server 控制面板来管理你的部署。

<div>

## <a name="deployment-wizard"></a>部署向导

必须使用安装媒体上包含的 Lync Server 部署向导将所有管理工具安装到尚未安装 Lync Server 的计算机上。 在 "管理工具" 安装过程中，将在本地安装 Lync Server 部署向导和其他工具，以便以后可以使用它为其他组件安装文件或删除不需要的组件的文件笔记本电脑.

有关如何首次从 Lync Server 安装媒体运行 Lync Server 部署向导的详细信息，请参阅[安装 Lync server 2013 管理工具](lync-server-2013-install-lync-server-administrative-tools.md)。

</div>

<div>

## <a name="topology-builder"></a>拓扑生成器

有关可使用拓扑生成器执行的部署任务的详细信息，请参阅每个服务器角色的部署文档。

</div>

<div>

## <a name="lync-server-control-panel"></a>Lync Server 控制面板

可以使用 Lync Server 2013 控制面板执行管理和维护 Lync Server 2013 所需的大部分管理任务。 Lync Server 控制面板为你提供了图形用户界面（GUI），用于管理运行 Lync Server 的服务器的配置，以及你的组织中的用户、客户端和设备。 Lync Server Management Shell 使用 Lync Server 控制面板作为执行 Lync Server 配置的基础机制。

Lync Server "控制面板" 将自动安装在每个 Lync Server 前端服务器或标准版服务器上。 在此版本中，您可以远程管理边缘服务器。 您也可以在另一台计算机上安装 Lync Server 控制面板，例如要集中管理 Lync Server 的管理控制台。 有关详细信息，请参阅[安装 Lync Server 2013 管理工具](lync-server-2013-install-lync-server-administrative-tools.md)。

<div>


> [!IMPORTANT]  
> <UL>
> <LI>
> <P>若要使用 Lync Server "控制面板" 配置设置，必须使用分配给 CsAdministrator 角色的帐户登录。 有关 Lync Server 2013 中可用的预定义管理角色的详细信息，请参阅<A href="lync-server-2013-planning-for-role-based-access-control.md">在 Lync server 2013 中规划基于角色的访问控制</A>。</P>
> <LI>
> <P>若要使用 Lync Server "控制面板" 配置设置，还必须使用最小屏幕分辨率为 1024 x 768 的计算机。</P></LI></UL>



</div>

</div>

<div>

## <a name="lync-server-management-shell"></a>Lync Server 命令行管理程序

在 Lync Server 中，Lync Server 命令行管理程序提供了一种用于管理和管理的新方法。 Lync Server 命令行管理程序是在 Windows PowerShell 命令行界面上构建的一种功能强大的管理界面，其中包括一组特定于 Lync Server 的全套 cmdlet。 使用 Lync Server 命令行管理程序，你可以获得一组丰富的配置和自动化控件。 拓扑生成器和 Lync Server 控制面板都实现这些 cmdlet 的子集以支持 Lync Server 的管理。 Lync Server Management Shell 包含所有 Lync Server 管理任务的 cmdlet，你可以单独使用这些 cmdlet 来管理你的部署。 有关详细信息，请参阅[Lync Server 2013](lync-server-2013-lync-server-management-shell.md)命令行管理程序文档或每个 cmdlet 的命令行帮助。

</div>

<div>

## <a name="logging-tool"></a>日志记录工具

通过在产品运行期间捕获产品的日志记录和跟踪信息，Lync Server 日志记录工具有助于进行故障排除。 你可以使用该工具在任何 Lync Server 服务器角色上运行调试会话。 有关日志记录工具的详细信息，请参阅 TechNet 库中的 Lync Server 2010 日志记录工具[http://go.microsoft.com/fwlink/p/?linkId=199265](http://go.microsoft.com/fwlink/p/?linkid=199265)文档。

<div>


> [!IMPORTANT]  
> 对于所有情况下 Lync Server 日志记录工具上的所有日志记录收集，建议使用集中式日志记录服务。 Lync Server 日志记录工具仍有效，但如果集中式日志记录服务已在运行，它将干扰或呈现为主要无效。 你应该仅使用集中式日志记录服务或 Lync Server 日志记录工具，但绝不会同时使用。 有关集中式日志记录服务以及应以独占方式使用它的详细信息，请参阅<A href="lync-server-2013-using-the-centralized-logging-service.md">在 Lync Server 2013 中使用集中式日志记录服务</A>。



</div>

</div>

<div>

## <a name="in-this-section"></a>本节内容

  - [Lync Server 2013 中的管理工具基础结构要求](lync-server-2013-administrative-tools-infrastructure-requirements.md)

  - [Lync Server 2013 中的服务器和工具操作系统支持](lync-server-2013-server-and-tools-operating-system-support.md)

  - [Lync Server 2013 中的管理工具软件要求](lync-server-2013-administrative-tools-software-requirements.md)

  - [Lync Server 2013 的安装和管理所需的管理员权限](lync-server-2013-administrator-rights-and-permissions-required-for-setup-and-administration.md)

  - [在 Lync Server 2013 中发布拓扑的要求](lync-server-2013-requirements-to-publish-a-topology.md)

  - [安装 Lync Server 2013 管理工具](lync-server-2013-install-lync-server-administrative-tools.md)

  - [打开 Lync Server 2013 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)

  - [Lync Server 2013 控制面板疑难解答](lync-server-2013-troubleshooting-lync-server-2013-control-panel.md)

  - [在 Lync Server 2013 中使用集中式日志记录服务](lync-server-2013-using-the-centralized-logging-service.md)

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


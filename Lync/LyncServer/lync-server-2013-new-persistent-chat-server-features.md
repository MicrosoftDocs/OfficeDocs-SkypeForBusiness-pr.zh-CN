---
title: Lync Server 2013：新的持久聊天服务器功能
description: Lync Server 2013：新的持久聊天服务器功能。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: New Persistent Chat Server features
ms:assetid: c3ec6f33-6261-4bf5-aa31-baa8ab2a87d8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412965(v=OCS.15)
ms:contentKeyID: 48185341
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 549fa43e115467c373fe8df08f8568aa8715c29d
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48579258"
---
# <a name="new-persistent-chat-server-features-in-lync-server-2013"></a>Lync Server 2013 中新的持久聊天服务器功能

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-10-29_

Lync Server 2013、持久聊天服务器使您能够参与在一段时间内保持的基于主题的多个会话。 持久聊天服务器可帮助您的组织执行以下操作：

  - 改善分散在不同地理位置的跨部门团队间的通信

  - 扩大信息的知晓和参与范围

  - 改善组织扩大后的通信

  - 减少信息过载

  - 提高信息感知能力

  - 扩大重要知识和信息的传播范围

Lync Server 2013、持久聊天服务器在 Microsoft 365 或 Office 365 中不可用。 目前，它仅适用于本地 Lync 2013 客户。

在 Lync 2013 中，持久聊天功能集成到 Lync 2013 客户端中。 因此，用户可以访问 Lync 2013 客户端中的即时消息/状态、音频/视频、会议和持久聊天。 有关 Lync 2013 客户端的详细信息，请参阅 <https://go.microsoft.com/fwlink/p/?linkid=270877> 。

本主题介绍新版本的 Lync Server 2013、持久聊天服务器和早期版本 (Microsoft Lync Server 2010，Group Chat) 之间的功能更改，其中包括：

  - 在 Lync Server 控制面板中提供管理体验，并消除组聊天管理工具

  - 通过消除组聊天配置工具将持久聊天服务器的配置设置集成到拓扑生成器中

  - 从以前版本的持久聊天服务器中轻松迁移和升级

  - 提供高可用性和灾难恢复解决方案

有关持久聊天服务器的最新版本的其他详细信息，请参阅以下内容：

  - 持续聊天帮助提供了 <https://go.microsoft.com/fwlink/p/?linkid=270945> 持久聊天功能的详细列表，以及它们的工作方式，以及如何在运行持久聊天服务器的情况下使用它们。

  - 在规划文档中 [规划 Lync server 2013 中的持久聊天服务器](lync-server-2013-planning-for-persistent-chat-server.md) ，在 [lync Server 2013 中部署持久聊天服务器](lync-server-2013-deploying-persistent-chat-server.md) 在部署文档中， [从 Lync server 2010、组聊天版或 Office 通信服务器迁移到 Lync Server 2013、持久聊天服务器在](migration-from-lync-server-2010-group-chat-or-office-communications-server-2007-r2-group-chat-to-lync-server-2013-persistent-chat-server.md) 迁移文档中2007以及在操作文档中 [管理 lync server 2013、持久聊天服务器](managing-lync-server-2013-persistent-chat-server.md) ，所有这些操作均提供有关设置持久聊天服务器的说明。

  - 持久聊天服务器 Documentation.msi 文件 (Windows Installer 文件) 允许用户访问有关持久聊天服务器的全面脱机文档。

<div>

## <a name="key-topology-changes-for-persistent-chat-server"></a>持久聊天服务器的关键拓扑更改

持久聊天服务器的以下高级别更改包括：

持久聊天服务器现在是一个服务器角色。 在 Microsoft Lync Server 2010 中，组聊天服务器是 Microsoft Lync Server 2010 的第三方受信任应用程序。 可以使用拓扑生成器将持久聊天添加到 Lync Server 2013 拓扑。 在 Lync Server 2013 中，持久聊天服务器功能是通过使用三个新的服务器角色来实现的：

  - **PersistentChatService：** 这是持续聊天的前端角色。 在标准版部署中，持久聊天服务器服务角色是由引导程序部署的 Standard Edition 服务器上的并置，与任何其他 Lync Server 角色一样。 在企业版部署中，持久聊天服务角色是按引导程序在独立计算机上部署的，与任何其他 Lync Server 角色一样。

  - **PersistentChatStore：** 与持久聊天内容数据库对应的后端服务器，其中存储了所有聊天内容。

  - **PersistentChatComplianceStore：** 与持久聊天合规性数据库相对应的后端服务器角色，其中存储了所有合规性事件。

这些持久聊天服务器角色是可选的，仅供需要全面持久聊天服务器功能的客户安装。 仅当您选择部署持久聊天合规性时，才需要 **PersistentChatComplianceStore** 角色。

**PersistentChatService**角色运行两项服务：

  - 持久聊天服务

  - 持久聊天合规性服务

在每台持久聊天服务器上运行这些服务，可为多服务器持久聊天服务器池中的这些服务提供高可用性。

此外，为了支持在持久聊天聊天室中使用文件上载和下载，持久聊天服务器包含 web 服务。 以前，在持久聊天服务器、前端服务器和所需的 Internet 信息服务 (IIS) 将此服务作为必备组件安装在并置中。 在 Lync Server 2013 持久聊天服务器中，文件上传/下载 web 服务与 Lync Server 2013 前端服务器并置。 这一副作用，Internet 信息服务 (IIS) 不再是持久聊天服务器的先决条件。 在 Internet 信息服务 (IIS) 管理器中，文件上载/下载 web 服务被标识为 **PersistentChat** 。

<div>


> [!IMPORTANT]  
> <STRONG>PersistentChatService</STRONG> &nbsp; 仅当该前端服务器是 Standard Edition 前端服务器时，PersistentChatService 角色才能在与 Lync Server 2013 前端服务器相同的服务器上运行 &nbsp; 。 <STRONG>PersistentChatService</STRONG>角色无法独立于 Lync server 2013 &nbsp; 前端服务器运行。 它只能在 Lync Server 2013 部署的上下文中进行安装。



</div>

在持久聊天服务器中，已消除了查找服务。 在 Lync Server 2010 中，"组聊天" 中，查找服务在每个组聊天服务器前端服务器上运行，并执行到其中一个通道服务器的路由。 Lync Server 2013 依靠 contact 对象进行路由，其中每个持久聊天服务器池都由 Lync Server 前端服务器使用的 contact 对象表示并将请求路由到相应的持久聊天服务器池，以及在池中运行持久聊天服务器的一台计算机。

在 Lync Server 2013 中，存在合规性服务修改：

  - 在 Lync Server 2010 中，合规性服务独立 (非并置) 运行，并且仅在一台服务器上运行。 合规性服务现在在所有持久聊天服务器前端服务器上运行，并在持久聊天服务的旁边运行，因此在多服务器持久聊天服务器池中提供了高可用性。 可以将单个合规性适配器配置为将数据从合规性数据库和其他系统中的一个系统中提取到另一个系统中 (XML 文件、Exchange 托管的存档，等等) 。 持久聊天服务器包括 XML 适配器。

  - 消息队列 (也称为持续聊天服务共享的 MSMQ) 队列，而每台持久聊天服务器前端服务器上的合规性服务现在是仅由两个服务共享的专用队列。 所有合规性服务均写入相同的合规性后端数据库。 它们也会从该数据库中读取，目的是将数据发送到其适配器实例。 合规性后端服务器表示为新的后端服务器角色。
    
    <div>
    

    > [!IMPORTANT]  
    > 与在以前的版本中一样，所有合规性数据只处理一次。 数据可能由在各种 Lync Server 2013、持久聊天服务器计算机上运行的合规性服务调用的任何适配器实例进行处理。 在持久聊天服务器中，任何一个适配器实例都可以处理数据。

    
    </div>
    
    <div>
    

    > [!NOTE]  
    > 有关安装消息队列的信息，请参阅部署文档中的在 <A href="lync-server-2013-install-operating-systems-and-prerequisite-software-on-servers.md">服务器上安装操作系统和必备软件（Lync Server 2013</A> ）。

    
    </div>

在 Lync Server 2013 中，高可用性和灾难恢复都有改进：

  - 高可用性改进： SQL Server 镜像用于在数据中心 (的站点内) 中为持久聊天服务器内容数据库和持久聊天合规性数据库提供高可用性。

  - 灾难恢复改进：持久聊天服务器支持扩展池体系结构，使单个持久聊天服务器池能够在两个站点之间扩展 (即拓扑中的单个逻辑池，且池中的服务器物理上位于两个站点) 。 SQL Server 日志传送用于跨站点灾难恢复。

有关高可用性和灾难恢复的详细信息，请参阅部署文档中的在 [Lync server 2013 中配置持久聊天服务器以实现高可用性和灾难恢复](lync-server-2013-configuring-persistent-chat-server-for-high-availability-and-disaster-recovery.md) 。

</div>

<div>

## <a name="key-administration-and-management-changes-for-persistent-chat-server"></a>持久聊天服务器的关键管理和管理更改

Lync Server 2013 通过提供以下功能使您更易于管理和管理持久聊天服务器：

  - 统一的管理和管理。 通过使用 Lync 管理员熟悉的工具，Lync Server 2013 可以更轻松地管理持久聊天服务器并对其进行管理。 持久聊天服务器包括与 Lync Server 控制面板集成的管理用户界面体验，可解决早期版本的组聊天服务器用户界面的性能问题。 此外，持久聊天服务器还包括用于管理和管理持久聊天服务器类别的 Windows PowerShell cmdlet 的集合、持久聊天服务器聊天室 (包括删除聊天室和清除过时内容) 和外接程序。

  - 简化了管理模型。 Lync Server 2013 通过解决以下关键客户要求来更改和简化了持久聊天服务器模型：
    
      - 删除作用域和类别的复杂嵌套层次结构。
    
      - 支持定义拒绝列表，以及为正在计划迁移到持久聊天服务器的当前 MindAlign 客户提供的允许的列表 (作用域) 。

</div>

<div>

## <a name="whats-different-about-user-roles-from-previous-group-chat-server-versions"></a>来自以前的组聊天服务器版本的用户角色有何不同？

Lync Server 2010，组聊天具有用户管理员角色、聊天室管理员角色和可管理外接程序的 Lync Server 管理员角色。持久聊天服务器只提供与其他基于 Lync Server 角色的访问控制 (RBAC) 角色) 类似的持久聊天管理员角色 (。 此 RBAC 角色的成员的任何人都可以管理聊天室、外接程序和类别 (，因此可以获取这些类别的用户访问权限) 以及持久聊天服务器池的配置。

</div>

<div>

## <a name="whats-different-about-chat-room-categories-from-previous-group-chat-server-versions"></a>来自以前的组聊天服务器版本的聊天室类别有何不同？

聊天室类别无法再嵌套，并且无法再修改根类别。 AllowedMembers/DeniedMembers 包含了在旧版组聊天服务器版本中使用的作用域，不同之处在于它不支持 (指定拒绝列表) 。 由于没有嵌套的类别，无法再覆盖作用域。 Lync Server 2013 中的持久聊天管理员可以创建和管理聊天室类别。 在创建和管理聊天室类别的过程中，持久聊天管理员可以配置 (Active Directory 组/容器/用户) 的主体，这些用户有权访问特定类别的聊天室的成员/创建者。 持久聊天管理员还可以将 DeniedMembers 添加到类别中，并将其显式排除在允许列表中。 DeniedMembers 将覆盖 AllowedMembers 中的成员。

</div>

<div>

## <a name="whats-different-about-chat-room-properties-from-previous-group-chat-server-versions"></a>从以前的组聊天服务器版本中聊天室属性的区别是什么？

Lync Server 2013、持久聊天服务器中存在开放式聊天室的新概念。 所有允许的成员都可以加入聊天室，而无需独占成员资格。

已消除持久聊天服务器的早期版本中所包含的以下聊天室属性：

  - 主题：聊天室现在仅有说明。

  - 创建新成员列表：在持久聊天服务器中，所有聊天室都将从空的成员资格开始 (，并且可以最大限度地 equaling 允许的成员) 的成员身份。

  - 文件上传：用于控制是否允许文件上载/下载的每个聊天室的设置。 现在，这仅设置了类别级别，并适用于该类别中的所有聊天室。

  - 聊天历史记录：用于在聊天室中控制是否启用聊天历史记录，但现在仅在类别级别设置，并适用于该类别中的所有聊天室的设置。

  - 邀请：会议室始终继承类别的 "邀请" 设置;也可以在聊天室上关闭它。 如果以前将类别设置为 "邀请关闭"，会议室将无法启用邀请。

</div>

<div>

## <a name="whats-different-about-policies-from-previous-group-chat-server-versions"></a>来自以前的组聊天服务器版本的策略有何不同？

持久聊天服务器启用了一个新的 Lync 策略，其中包含持续聊天、每用户/池/站点/全局设置。 在 Lync 2013 客户端中，持久聊天环境仅适用于通过直接或通过 "池/站点/全局设置") 启用的持久聊天 (的用户。

早期版本的组聊天服务器没有集成到 Lync Server 策略中的任何策略。 在每用户和每个类别/房间的基础上，通过使用 "可按用户 **上传文件** " 功能，可以让用户成为用户管理员、聊天室管理员或配置用户上传文件的能力。 持久聊天服务器 **文件上载** 功能仅在每个类别中。

</div>

<div>

## <a name="logging"></a>日志记录

持久聊天服务器和 System Center Operations Manager 的日志记录集成到 Lync Server 2013 跟踪日志记录中。

</div>

<div>

## <a name="see-also"></a>另请参阅


[在 Lync Server 2013 中规划持久聊天服务器](lync-server-2013-planning-for-persistent-chat-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

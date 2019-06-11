---
title: Lync Server 2013：新的持久聊天服务器功能
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: New Persistent Chat Server features
ms:assetid: c3ec6f33-6261-4bf5-aa31-baa8ab2a87d8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412965(v=OCS.15)
ms:contentKeyID: 48185341
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e6d5cd0b8197b64abfc0761dfb333f338b507ff7
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34826204"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="new-persistent-chat-server-features-in-lync-server-2013"></a>Lync Server 2013 中新的持久聊天服务器功能

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2012-10-29_

Lync Server 2013, 持久聊天服务器使你能够参与在一段时间内保持的基于主题的多个对话。 持久聊天服务器可帮助您的组织执行以下操作:

  - 改进地理分散的团队和跨职能团队之间的通信

  - 拓展信息意识和参与

  - 改善与您的扩展组织的沟通

  - 减少信息超载

  - 改善信息意识

  - 增加重要知识和信息的散布

Lync Server 2013, 持久聊天服务器在 Microsoft Office 365 中不可用。 目前, 它仅适用于本地 Lync 2013 客户。

在 Lync 2013 中, 永久聊天功能集成到 Lync 2013 客户端。 因此, 用户可以访问 Lync 2013 客户端中的即时消息/状态、音频/视频、会议和持久聊天。 有关 Lync 2013 客户端的详细信息, 请<http://go.microsoft.com/fwlink/p/?linkid=270877>参阅。

本主题介绍新版本的 Lync Server 2013、持久聊天服务器和早期版本 (Microsoft Lync Server 2010、群组聊天) 之间的功能更改, 包括:

  - 在 Lync Server "控制面板" 中提供管理体验, 并消除群组聊天管理工具

  - 通过消除群组聊天配置工具将持久聊天服务器的配置设置集成到拓扑生成器中

  - 从旧版本的持久聊天服务器中轻松迁移和升级

  - 提供高可用性和灾难恢复解决方案

有关持久聊天服务器的最新版本的其他详细信息, 请参阅以下内容:

  - 持续聊天帮助<http://go.microsoft.com/fwlink/p/?linkid=270945>提供了持久聊天功能的详细列表, 以及它们的工作方式, 以及如何在运行持久聊天服务器时使用它们。

  - 在[Lync server 2013 中规划 Lync server 中的持久聊天服务器](lync-server-2013-planning-for-persistent-chat-server.md)在部署文档中的[lync Server 2013 中部署持久聊天服务器](lync-server-2013-deploying-persistent-chat-server.md),[从 Lync server 2010、群组聊天或 Office 迁移通信服务器 2007 R2 群组在迁移文档中与 Lync Server 2013、持久聊天服务器进行聊天](migration-from-lync-server-2010-group-chat-or-office-communications-server-2007-r2-group-chat-to-lync-server-2013-persistent-chat-server.md)以及在操作文档中[管理 lync server 2013、持久聊天服务器](managing-lync-server-2013-persistent-chat-server.md), 所有这些操作均提供有关设置持久聊天服务器。

  - 持久聊天服务器文档 .msi 文件 (Windows Installer 文件) 允许用户访问有关持久聊天服务器的全面脱机文档。

<div>

## <a name="key-topology-changes-for-persistent-chat-server"></a>持久聊天服务器的关键拓扑更改

持久聊天服务器的以下高级别更改包括:

持久聊天服务器现在是服务器角色。 在 Microsoft Lync Server 2010 中, 群组聊天服务器是 Microsoft Lync Server 2010 的第三方受信任的应用程序。 可以使用拓扑生成器将持久聊天添加到 Lync Server 2013 拓扑。 在 Lync Server 2013 中, 持久聊天服务器功能是使用三个新的服务器角色实现的:

  - **PersistentChatService:** 这是持久聊天的前端角色。 在标准版部署中, 持久聊天服务器服务角色在由引导程序部署的标准版服务器上 collocated, 与任何其他 Lync 服务器角色一样。 在企业版部署中, 持久聊天服务角色由引导程序在独立计算机上部署, 与任何其他 Lync 服务器角色一样。

  - **PersistentChatStore:** 与持久聊天内容数据库 (其中存储了所有聊天内容) 对应的后端服务器。

  - **PersistentChatComplianceStore:** 与持久聊天合规性数据库 (其中存储了所有合规性事件) 相对应的后端服务器角色。

这些持久聊天服务器角色是可选的, 并且仅供需要全面持久聊天服务器功能的客户安装。 只有当你选择部署持久的聊天合规性时, 才需要**PersistentChatComplianceStore**角色。

**PersistentChatService**角色运行两个服务:

  - 持久聊天服务

  - 持久聊天合规性服务

在每个持久聊天服务器上运行这些服务可在多服务器持久聊天服务器池中为这些服务提供高可用性。

此外, 为了支持永久聊天室中的文件上载和下载, 持久聊天服务器包含 web 服务。 以前, 此服务在持久聊天服务器、前端服务器和所需的 Internet 信息服务 (IIS) 上 collocated, 以先决条件的形式安装。 在 Lync Server 2013 持久聊天服务器中, 文件上传/下载 web 服务与 Lync Server 2013 前端服务器 collocated。 作为副作用, Internet 信息服务 (IIS) 不再是持久聊天服务器的先决条件。 文件上传/下载 web 服务在 Internet Information Services (IIS) 管理器中被标识为**PersistentChat** 。

<div>


> [!IMPORTANT]  
> 只有当前端服务器是标准版&nbsp;前端服务器时, <STRONG>PersistentChatService</STRONG>角色才能&nbsp;在 Lync server 2013 前端服务器所在的服务器上运行。 <STRONG>PersistentChatService</STRONG>角色不能独立于 Lync server 2013&nbsp;前端服务器运行。 它只能安装在 Lync Server 2013 部署的上下文中。



</div>

在永久聊天服务器中, 已消除了查找服务。 在 Lync Server 2010 中, 群组聊天, 查找服务在每个群组聊天服务器前端服务器上运行, 并执行路由到其中一个频道服务器。 Lync Server 2013 依赖于使用 "联系人" 对象进行路由, 其中每个持久聊天服务器池由 Lync Server 前端服务器使用的联系人对象表示并将请求路由到适当的持久聊天服务器池, 以及池中运行持久聊天服务器的计算机之一。

在 Lync Server 2013 中, 存在合规性服务修改:

  - 在 Lync Server 2010 中, 合规性服务独立运行 (非 collocated), 并且仅在一台服务器上运行。 合规性服务现在在所有持久聊天服务器前端服务器上运行, 并与持久聊天服务一起运行, 从而在多服务器持久聊天服务器池中提供高可用性。 可将单个合规性适配器配置为从合规性数据库中提取数据, 并将数据提取到另一个系统 (XML 文件、Exchange 托管的存档等) 中。 持久聊天服务器包括 XML 适配器。

  - 持续聊天服务和每台持续聊天服务器前端服务器上的合规性服务共享的消息队列 (也称为 MSMQ) 队列现在是仅由两个服务共享的专用队列。 所有合规性服务均写入同一合规性后端数据库。 它们也会从该数据库中读取, 目的是将数据发送到其适配器实例。 合规性后端服务器表示为新的后端服务器角色。
    
    <div>
    

    > [!IMPORTANT]  
    > 与以前的版本一样, 所有合规性数据只处理一次。 数据可能由在各种 Lync Server 2013、持久聊天服务器计算机上运行的合规性服务调用的任何适配器实例处理。 在永久聊天服务器中, 任何一个适配器实例都可以处理数据。

    
    </div>
    
    <div>
    

    > [!NOTE]  
    > 有关安装消息队列的信息, 请参阅部署文档中的<A href="lync-server-2013-install-operating-systems-and-prerequisite-software-on-servers.md">Lync Server 2013 服务器上的 "安装操作系统和必备软件</A>"。

    
    </div>

在 Lync Server 2013 中, 在高可用性和灾难恢复方面有以下改进:

  - 高可用性改进: SQL Server 镜像用于在数据中心 (现场) 内为持久聊天服务器内容数据库和持久聊天合规性数据库提供高可用性。

  - 灾难恢复改进: 持久的聊天服务器支持扩展池体系结构, 使单个持久聊天服务器池能够跨两个站点 (即拓扑中的单个逻辑池) 进行扩展, 并以物理方式使用池中的服务器位于两个网站上)。 SQL Server 日志传送用于跨站点灾难恢复。

有关高可用性和灾难恢复的详细信息, 请参阅在部署文档中[为 Lync server 2013 中的高可用性和灾难恢复配置持久聊天服务器](lync-server-2013-configuring-persistent-chat-server-for-high-availability-and-disaster-recovery.md)。

</div>

<div>

## <a name="key-administration-and-management-changes-for-persistent-chat-server"></a>持久聊天服务器的关键管理和管理更改

Lync Server 2013 通过提供以下内容使管理和管理持久聊天服务器更容易:

  - 统一的管理和管理。 通过使用 Lync 管理员熟悉的工具, lync Server 2013 使管理和管理持久聊天服务器变得更容易。 持久聊天服务器包括与 Lync Server 控制面板集成的管理用户界面体验, 可解决早期版本的组聊天服务器用户界面的性能问题。 此外, 持久聊天服务器还包括 Windows PowerShell cmdlet 的集合, 用于管理和管理持久聊天服务器类别、持久聊天服务器聊天室 (包括删除聊天室和清除过时内容) 和加载项。

  - 简化的管理模型。 通过解决以下关键客户要求, Lync Server 2013 已更改并简化了持久聊天服务器模型:
    
      - 删除范围和类别的复杂嵌套层次结构。
    
      - 支持定义拒绝列表以及当前 MindAlign 客户的允许列表 (范围), 这些列表适用于计划迁移到持久聊天服务器的当前用户。

</div>

<div>

## <a name="whats-different-about-user-roles-from-previous-group-chat-server-versions"></a>以前群组聊天服务器版本中的用户角色有何区别？

Lync Server 2010, 群组聊天具有用户管理员角色、一个聊天室管理员角色和一个可管理外接程序的 Lync Server 管理员角色。持久聊天服务器只提供与其他 Lync 类似的持久聊天管理员角色 (类似于其他 Lync)基于服务器角色的访问控制 (RBAC) 角色。 此 RBAC 角色成员的任何人都可以管理聊天室、外接程序和类别 (因此可以获取这些类别的用户访问权限), 以及配置持久聊天服务器池。

</div>

<div>

## <a name="whats-different-about-chat-room-categories-from-previous-group-chat-server-versions"></a>以前的群组聊天服务器版本中的聊天室类别有何区别？

聊天室类别无法再嵌套, 并且无法再修改根类别。 AllowedMembers/DeniedMembers 包含了在旧式群组聊天服务器版本中使用的范围 (除了它不支持指定拒绝列表)。 由于没有嵌套类别, 无法再重写范围。 Lync Server 2013 中的持久聊天管理员可以创建和管理聊天室类别。 在创建和管理聊天室类别的过程中, 持久聊天管理员可以配置主体 (Active Directory 组/容器/用户), 该主体具有特定类别的聊天室成员/创建者的访问权限。 持久聊天管理员还可以将 DeniedMembers 添加到类别中, 并且它们将变为对允许列表的显式排除。 DeniedMembers 将覆盖 AllowedMembers 中的成员。

</div>

<div>

## <a name="whats-different-about-chat-room-properties-from-previous-group-chat-server-versions"></a>以前的群组聊天服务器版本中的聊天室属性有何区别？

Lync Server 2013 和持久聊天服务器中存在一个开放聊天室的新概念。 所有允许的成员都可以加入聊天室, 而无需独占成员身份。

已消除以前版本的永久聊天服务器中包含的以下聊天室属性:

  - 主题: 聊天室现在仅具有说明。

  - 创建新成员列表: 在持久聊天服务器中, 所有聊天室均从空成员身份开始 (并且可以最大化到允许的成员 equaling 的成员身份)。

  - 文件上传: 用于控制每个聊天室的设置, 用于控制是否允许文件上载/下载。 现在, 它仅设置类别级别, 并应用于该类别中的所有聊天室。

  - 聊天历史记录: 用于在聊天室中控制是否已启用聊天历史记录的设置, 但现在仅在类别级别设置, 并应用于该类别中的所有聊天室。

  - 邀请: 一个会议室始终继承该类别的 "邀请" 设置;或者, 它可以在聊天室上处于关闭状态。 如果以前已将该类别设置为 "邀请", 则会议室无法启用邀请。

</div>

<div>

## <a name="whats-different-about-policies-from-previous-group-chat-server-versions"></a>以前的群组聊天服务器版本中的策略有何区别？

持久聊天服务器已启用一个新的 Lync 策略, 其中包含持续聊天、每用户/池/网站/全局设置。 在 Lync 2013 客户端中, 持久聊天环境仅适用于通过策略启用持久聊天的用户 (直接或通过 "池/网站/全局设置")。

以前版本的组聊天服务器没有任何集成到 Lync Server 策略中的策略。 在每用户和每个类别/房间基础上, 通过使用 "可按用户**上传文件**" 功能, 您可以让用户成为用户管理员、聊天室管理员或配置用户上传文件的能力。 持久聊天服务器**文件上载**功能仅针对每个类别。

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


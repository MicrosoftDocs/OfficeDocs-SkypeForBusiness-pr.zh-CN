---
title: Lync Server 2013：新的持久聊天服务器功能
TOCTitle: 新的持久聊天服务器功能
ms:assetid: c3ec6f33-6261-4bf5-aa31-baa8ab2a87d8
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg412965(v=OCS.15)
ms:contentKeyID: 49314171
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 中新的持久聊天服务器功能

 

_**上一次修改主题：** 2016-12-08_

通过 Lync Server 2013持久聊天服务器，可以参加持续进行的、基于主题的多方对话。持久聊天服务器可帮助您的组织完成下列任务：

  - 改善分散在不同地理位置的跨部门团队间的通信

  - 扩大信息的知晓和参与范围

  - 改善组织扩大后的通信

  - 减少信息过载

  - 提高信息感知能力

  - 扩大重要知识和信息的传播范围

Lync Server 2013持久聊天服务器在 Microsoft Office 365 中不可用。此时，它仅可供内部 Lync 2013 客户可用。

在 Lync 2013 中，持久聊天功能集成到 Lync 2013 客户端中。因此，用户可以在 Lync 2013 客户端中访问即时消息/状态、音频/视频、会议和 持久聊天。有关 Lync 2013 客户端的详细信息，请参阅 <http://go.microsoft.com/fwlink/p/?linkid=270877>。

本主题介绍新版本的 Lync Server 2013持久聊天服务器和以前版本（ Microsoft Lync Server 2010 群聊）之间的功能变化，包括：

  - 提供 Lync Server 控制面板管理体验，并淘汰 群聊管理工具

  - 通过淘汰 群聊配置工具，将 持久聊天服务器的配置设置集成到拓扑生成器中

  - 从早期 持久聊天服务器版本轻松迁移和升级

  - 提供高可用性和灾难恢复解决方案

有关最新版本的 持久聊天服务器的更多详细信息，请参阅以下内容：

  - 持久聊天帮助，网址为 <http://go.microsoft.com/fwlink/p/?linkid=270945>，其中提供了 持久聊天功能的详细列表和工作原理以及有关如何在运行 持久聊天服务器时使用这些功能的详细信息。

  - 规划文档中的 [在 Lync Server 2013 中规划持久聊天服务器](lync-server-2013-planning-for-persistent-chat-server.md)、部署文档中的 [在 Lync Server 2013 中部署持久聊天服务器](lync-server-2013-deploying-persistent-chat-server.md)、迁移文档中的 [从 Lync Server 2010 群聊或 Office Communications Server 2007 R2 群聊迁移到 Lync Server 2013 持久聊天服务器](migration-from-lync-server-2010-group-chat-or-office-communications-server-2007-r2-group-chat-to-lync-server-2013-persistent-chat-server.md)和操作文档中的 [管理 Lync Server 2013 持久聊天服务器](managing-lync-server-2013-persistent-chat-server.md)，所有这些内容均提供了有关设置 持久聊天服务器的说明。

  - 持久聊天服务器 Documentation.msi 文件（Windows Installer 文件）使用户可以访问与 持久聊天服务器相关的综合性脱机文档。

## 持久聊天服务器的主要拓扑更改

以下 持久聊天服务器的高层次更改包括：

持久聊天服务器现在是一个服务器角色。在 Microsoft Lync Server 2010 中， 群聊服务器是 Microsoft Lync Server 2010 的第三方受信任的应用程序。可以使用 拓扑生成器将 持久聊天添加到 Lync Server 2013 拓扑中。在 Lync Server 2013 中，将使用以下三个新的服务器角色实现 持久聊天服务器功能：

  - **PersistentChatService ：** 这是 持久聊天的前端角色。在 标准版 部署中，与任何其他 Lync Server 角色类似， 持久聊天服务器服务角色并置在由引导程序部署的 Standard Edition Server 上。在 企业版 部署中，与任何其他 Lync Server 角色类似， 持久聊天服务角色由引导程序部署在独立计算机上。

  - **PersistentChatStore ：** 与 持久聊天内容数据库（在其中存储所有聊天内容）相对应的后端服务器。

  - **PersistentChatComplianceStore ：** 与 持久聊天合规性数据库（在其中存储所有合规性事件）相对应的后端服务器角色。

这些 持久聊天服务器角色是可选的，只有需要全面的 持久聊天服务器功能的客户才需要安装它们。只有选择部署 持久聊天合规性时才需要 **PersistentChatComplianceStore** 角色。

**PersistentChatService**角色运行以下两项服务：

  - 持久聊天服务

  - 持久聊天合规性服务

在每台 持久聊天服务器上运行这些服务可以在多服务器 持久聊天服务器池中提供这些服务的高可用性。

此外，为了支持 持久聊天聊天室中的文件上载和下载， 持久聊天服务器包含了 Web 服务。以前，此服务并置在 持久聊天服务器、 前端服务器，以及要作为必备组件安装的所需 Internet Information Services (IIS) 上。在 Lync Server 2013持久聊天服务器中，文件上载/下载 Web 服务与 Lync Server 2013前端服务器并置在一起。作为一种副作用， Internet Information Services (IIS) 不再是 持久聊天服务器的必备组件。在 Internet Information Services (IIS) 管理器中，将文件上载/下载 Web 服务标识为 **PersistentChat**。

> [!IMPORTANT]
> 只有 前端服务器是 标准版前端服务器时， <strong>PersistentChatService</strong> 角色才能与 Lync Server 2013前端服务器 在同一台服务器上运行。 <strong>PersistentChatService</strong> 角色无法独立于 Lync Server 2013前端服务器运行。它只能安装在 Lync Server 2013 部署的上下文中。


在 持久聊天服务器中，已淘汰查找服务。在 Lync Server 2010 群聊中，查找服务在每台 群聊服务器前端服务器上运行，并且执行至任一频道服务器的路由。 Lync Server 2013 依赖使用联系人对象的路由，在这种路由方式中，每个 持久聊天服务器池由一个联系人对象表示， Lync Server前端服务器使用该对象标识并将请求路由到相应的 持久聊天服务器池和该池中运行 持久聊天服务器的计算机之一。

在 Lync Server 2013 中，存在合规性服务修改：

  - 在 Lync Server 2010 中，合规性服务独立运行（非并置），并且仅在单一服务器上运行。现在，合规性服务在所有 持久聊天服务器前端服务器上与 持久聊天服务一起运行，因此，可在多服务器 持久聊天服务器池中提供高可用性。可以将单个合规性适配器配置为从合规性数据库中提取数据以及将数据提取到其他系统（XML 文件，承载 Exchange 的存档等）之一。 持久聊天服务器包含一个 XML 适配器。

  - 每台 持久聊天服务器前端服务器上的 持久聊天服务和合规性服务共享的消息队列（也称为 MSMQ）队列现在是仅由这两项服务共享的专用队列。所有合规性服务将写入同一个合规性后端数据库。此外，它们都从该数据库中进行读取，以便将数据发送到其适配器实例。合规性后端服务器用新的后端服务器角色表示。
    
    > [!IMPORTANT]
    > 与在早期版本中相同，所有合规性数据仅处理一次。该数据可以由在各个 Lync Server 2013持久聊天服务器计算机上运行的合规性服务所调用的任何配器实例进行处理。在 持久聊天服务器中，任一适配器实例都可处理这些数据。
    
    > [!NOTE]  
    > 有关安装消息队列的信息，请参阅部署文档中的 <a href="lync-server-2013-install-operating-systems-and-prerequisite-software-on-servers.md">在服务器上安装适用于 Lync Server 2013 的操作系统和必备软件</a>。
    


在 Lync Server 2013 中，对高可用性和灾难恢复方面都进行了改进：

  - 高可用性改进： SQL Server 镜像可用于为数据中心内（站内）的 持久聊天服务器内容数据库和 持久聊天合规性数据库提供高可用性。

  - 灾难恢复改进： 持久聊天服务器支持一个拉伸的池体系结构，该体系结构支持跨两个站点拉伸一个 持久聊天服务器池（即拓扑中的单个逻辑池，而池中的服务器跨两个站点放置）。 SQL Server 日志传送用于跨站点的灾难恢复。

有关高可用性和灾难恢复的详细信息，请参阅部署文档中的 [在 Lync Server 2013 中为持久聊天服务器配置高可用性和灾难恢复](lync-server-2013-configuring-persistent-chat-server-for-high-availability-and-disaster-recovery.md)。

## 持久聊天服务器的主要管理更改

Lync Server 2013 通过提供以下内容使 持久聊天服务器的管理变得更加简单：

  - 统一管理。 Lync Server 2013 使用 Lync 管理员熟悉的工具让 持久聊天服务器的管理变得更加简单。 持久聊天服务器包括与 Lync Server 控制面板集成的管理用户界面体验，并解决了早期版本的 群聊服务器用户界面的性能问题。此外， 持久聊天服务器包括可用于管理 持久聊天服务器类别、 持久聊天服务器房间（包括删除房间和清理过时内容）和外接程序的 Windows PowerShell cmdlet 集合。

  - 简化的管理模型。Lync Server 2013 通过满足以下主要的客户要求，更改并简化了 持久聊天服务器模型：
    
      - 删除复杂的范围和类别的嵌套层次结构。
    
      - 支持为计划迁移到 持久聊天服务器的当前 MindAlign 客户定义拒绝列表以及允许列表（范围）。

## 与以前的 群聊服务器版本中用户角色有何不同？

Lync Server 2010 群聊具有用户管理员角色、聊天室管理员角色和可管理外接程序的 Lync Server 管理员角色。 持久聊天服务器只提供了 持久聊天管理员角色（类似于其他基于 Lync Server 角色的访问控制 (RBAC) 角色）。任何人只要是 RBAC 角色的成员就可以管理聊天室、外接程序和类别（并因此获取对这些类别的用户访问权）以及 持久聊天服务器池的配置。

## 与以前的 群聊服务器版本中的聊天室类别有何不同？

无法再嵌套聊天室类别，并且无法再修改根类别。AllowedMembers/DeniedMembers 构成了旧的 群聊服务器版本中所使用的范围（除非它不支持定义“拒绝”列表）。无法再覆盖范围，因为不存在嵌套类别。Lync Server 2013 中的 持久聊天管理员具有创建和管理聊天室类别的能力。作为创建和管理聊天室类别的一部分， 持久聊天管理员可配置有权成为特定类别的聊天室的成员/创建者的主体（Active Directory 组/容器/用户）。持久聊天管理员还可向类别添加 DeniedMembers，这些成员将成为允许的列表的明确排除对象。DeniedMembers 将覆盖 AllowedMembers 中的成员。

## 与以前的 群聊服务器版本中的聊天室属性有何不同？

Lync Server 2013持久聊天服务器中出现了新的打开的聊天室的概念。所有允许的成员均可在没有独占成员身份的情况下加入聊天室。

淘汰了以前的 持久聊天服务器版本中包含的以下聊天室属性：

  - 主题：现在聊天室仅包含 Description。

  - 新建成员列表：在 持久聊天服务器中，所有聊天室在最开始时都没有成员（并且成员的数量最大可以等于允许的成员数）。

  - 文件上载：以前是每个聊天室中用于控制是否允许上载/下载文件的一项设置。现在此项仅在类别级别进行设置并适用于该类别中的所有聊天室。

  - 聊天历史记录：以前是每个聊天室中用于控制是否启用聊天历史记录的一项设置，但现在仅在类别级别进行设置并适用于该类别中的所有聊天室。

  - 邀请：聊天室始终继承类别的“邀请”设置；或者可以在聊天室将其关闭。如果之前将类别设置为关闭“邀请”，则聊天室无法打开“邀请”。

## 与以前的 群聊服务器版本中的策略有何不同？

持久聊天服务器包含一个针对每用户/每池/每站点/全局设置启用了 持久聊天的新 Lync 策略。在 Lync 2013 客户端中， 持久聊天环境仅适用于通过策略启用了 持久聊天（直接或通过池/站点/全局设置）的用户。

以前的 群聊服务器版本未将任何策略集成到 Lync Server 策略中。通过在每个用户和每个类别/房间的基础上针对每个用户功能使用“可上载文件”，您可使用户成为用户管理员、聊天室管理员或配置用户上载文件的能力。持久聊天服务器的“文件上载”功能只是一个针对每个类别的设置。

## 日志记录

持久聊天服务器和 System Center Operations Manager 的日志记录已集成到 Lync Server 2013 跟踪日志记录中。

## 另请参阅

#### 其他资源

[在 Lync Server 2013 中规划持久聊天服务器](lync-server-2013-planning-for-persistent-chat-server.md)


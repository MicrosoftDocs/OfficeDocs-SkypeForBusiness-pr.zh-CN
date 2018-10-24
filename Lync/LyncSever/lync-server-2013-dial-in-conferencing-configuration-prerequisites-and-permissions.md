---
title: Lync Server 2013：电话拨入式会议配置的先决条件和权限
TOCTitle: 电话拨入式会议配置的先决条件和权限
ms:assetid: b3b251e5-78ac-44a2-8c36-2a061c9b2314
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg412865(v=OCS.15)
ms:contentKeyID: 49313976
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 中电话拨入式会议配置的先决条件和权限

 

_**上一次修改主题：** 2012-06-20_

电话拨入式会议是 Lync Server 2013 会议工作负荷的可选组件。配置电话拨入式会议之前需要安装的组件是在使用 拓扑生成器设计拓扑，然后设置前端池或 Standard Edition Server 时进行部署的。本主题介绍配置电话拨入式会议之前需要完成的任务。

本节假定您已阅读与会议工作负荷和电话拨入式会议相关的规划部分。

## 电话拨入式会议配置先决条件

电话拨入式会议要求安装以下 Lync Server 2013 组件：

  - 统一通信应用程序服务 (UCAS)（称为“*应用程序服务*”）

  - 会议助理应用程序

  - 会议通知应用程序

  - 电话拨入式会议设置网页

  - 至少一个 Lync Server 2013 中介服务器，且至少一个 PSTN 网关

使用 拓扑生成器定义和发布拓扑时部署这些组件，然后部署前端池或 Standard Edition Server。如果要部署 企业语音，应在配置电话拨入式会议之前部署它。如果不部署 企业语音，可在部署前端池或 Standard Edition Server 时部署中介服务器和公用电话交换网 (PSTN) 网关。

> [!NOTE]  
> 如果要从 Office Communications Server 2007 R2 升级到 Lync Server 2013，请在计划用于承载 Lync Server 2013 会议的每个池中部署电话拨入式会议。有关迁移电话拨入式会议的详细信息，请参阅 <a href="migration-from-office-communications-server-2007-r2-to-lync-server-2013.md">从 Office Communications Server 2007 R2 迁移至 Lync Server 2013</a>。



本节假定您已执行以下操作：

  - 已将最新更新应用于 Office Communications Server 2007 R2 环境（如果要迁移到 Lync Server 2013）。

  - 已使用 拓扑生成器设计和配置拓扑。指定会议工作负荷时，已选择电话拨入式会议选项。有关定义拓扑的详细信息，请参阅部署文档中的 [在 Lync Server 2013 中定义和配置拓扑](lync-server-2013-defining-and-configuring-the-topology.md)。

  - 已发布拓扑，并已设置前端池或 Standard Edition Server。有关发布拓扑并安装 Lync Server 2013 的详细信息，请参阅部署文档中的 [部署 Lync Server 2013](lync-server-2013-deploying-lync-server.md)。
    
    > [!NOTE]  
    > 安装发布的拓扑时，电话拨入式会议设置网页将作为 Web 服务的一部分安装在前端服务器或 Standard Edition Server 上。
    
    
    > [!IMPORTANT]
    > 如果在部署 Lync Server 2013 后更改 拓扑生成器中“文件存储”的路径，则需要重新启动会议助理和会议通知应用程序才能使用新路径。


  - 已部署 企业语音。如果不打算部署 企业语音，则必须已将中介服务器并置到 Enterprise Edition 前端服务器或 Standard Edition Server 上，或已部署独立的中介服务器，并且已部署 PSTN 网关。有关部署 企业语音的详细信息，请参阅部署文档中的 [在 Lync Server 2013 中部署企业语音](lync-server-2013-deploying-enterprise-voice.md)。有关安装独立中介服务器和 PSTN 网关的详细信息，请参阅部署文档中的 [在 Lync Server 2013 中部署中介服务器和定义对等方](lync-server-2013-deploying-mediation-servers-and-defining-peers.md)。

下面的流程图显示配置电话拨入式会议之前必须执行的步骤，以及配置电话拨入式会议时需要执行的步骤。

**部署电话拨入式会议**

![电话拨入式会议部署流程图](images/Gg412865.fde8c246-b5ed-4323-a6e7-af1983a5ec86(OCS.15).jpg "电话拨入式会议部署流程图")

## 电话拨入式会议权限

要配置电话拨入式会议，需要使用以下管理工具：

  - Lync Server 2013 控制面板

  - Lync Server 命令行管理程序

使用这些管理工具配置电话拨入式会议设置、拨号计划、策略以及其他电话拨入式会议所需的设置。

配置电话拨入式会议需要以下任一管理角色，具体取决于任务：

  - **CsVoiceAdministrator** 此管理员角色可以创建、配置和管理所有语音相关的设置和策略。

  - **CsUserAdministrator** 此管理员角色可以对用户启用和禁用 Lync Server，并将现有策略（如会议策略和 PIN 策略）分配给用户。

  - **CsAdministrator** 此管理员角色可以执行 CsVoiceAdministrator 和 CsUserAdministrator 的所有任务。

## 另请参阅

#### 概念

[在 Lync Server 2013 中部署企业语音](lync-server-2013-deploying-enterprise-voice.md)


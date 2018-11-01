---
title: 用于会议的 Lync Server 2013 组件和拓扑
TOCTitle: 用于会议的组件和拓扑
ms:assetid: eb83052a-3360-4ba1-a6a0-6ee419942809
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg399061(v=OCS.15)
ms:contentKeyID: 49314631
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 中用于会议的组件和拓扑

 

_**上一次修改主题：** 2013-02-04_

在 拓扑生成器中选择会议时，会议会作为 前端服务器或 Standard Edition Server的一部分进行部署。电话拨入式会议和 PowerPoint 需要其他组件和配置。下面各部分介绍了支持 Web 会议、A/V 会议和电话拨入式会议的组件和拓扑。

## 支持的组件

Web 会议和 A/V 会议需要的唯一组件是组织的 前端服务器或 Standard Edition 服务器。有关 前端服务器和 Standard Edition 服务器 的软硬件和软件要求的列表，请参阅 [支持的适用于 Lync Server 2013 的硬件](lync-server-2013-supported-hardware.md)和 [Lync Server 2013 中的服务器软件和基础结构支持](lync-server-2013-server-software-and-infrastructure-support.md)。

Lync Server 2013 使用 Office Web Apps和 Office Web Apps Server处理 PowerPoint 演示文稿的共享和呈现。有关安装和配置 Office Web Apps Server的详细信息，请参阅 [配置与 Office Web Apps Server 和 Lync Server 2013 的集成](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md)。

除了 Web 会议和 A/V 会议的要求，电话拨入式会议还使用以下 Lync Server 2013 组件：

  - **应用程序服务**应用程序服务为部署、承载和管理统一通信 (UC) 应用程序提供了一个平台。电话拨入式会议使用两个需要 应用程序服务的 UC 应用程序：会议助理和会议通知。默认情况下，部署会议负载和选择电话拨入式会议选项时，会在 前端池中的每台 前端服务器和每台 Standard Edition Server 上安装并激活 应用程序服务。

  - **会议助理应用程序**会议助理应用程序是一个可接受公用电话交换网 (PSTN) 呼叫、播放提示并将呼叫加入 A/V 会议的统一通信应用程序。默认情况下，部署会议负载和选择电话拨入式选项时，会安装并激活 会议助理应用程序。

  - **会议通知应用程序**会议通知应用程序是在执行特定操作时（例如，当参与者加入或离开会议时，将参与者静音或取消静音时，有人进入会议厅时，以及锁定或取消锁定会议时）向 PSTN 参与者播放提示音和提示的统一通信应用程序。 会议通知应用程序还支持电话小键盘的双音多频 (DTMF) 命令。默认情况下，部署会议负载和选择电话拨入式选项时，会自动安装并激活 会议通知应用程序。

  - **电话拨入式会议设置页**电话拨入式会议设置页网页显示会议的拨入号码及其可用语言、分配的会议信息（即，对于不需要预定的会议）以及会议中的 DTMF 控制，并支持对个人标识号 (PIN) 和分配的会议信息的管理。 电话拨入式会议设置页网页作为 Web 服务的一部分自动安装。

  - **Lync Server 2013、 中介服务器和 PSTN 网关** 电话拨入式会议需要一台中 中介服务器来转换 Lync Server 2013 和 PSTN 网关之间的信号（在某些配置中还包括媒体），还需要一个 PSTN 网关来转换 中介服务器和 PSTN 网关之间的信号和媒体。对于电话拨入式会议，必须至少部署一台 中介服务器和以下各项之一：
    
      - PSTN 网关
    
      - IP-PBX
    
      - 会话边界控制器 (SBC)（用于通过配置 SIP 中继进行连接的 Internet 电话服务提供商）
    
    > [!NOTE]  
    > 如果还要部署 企业语音，则 中介服务器和 PSTN 网关是 企业语音部署的一部分。如果不部署 企业语音，则需要为电话拨入式会议部署至少一台 中介服务器，以及至少一个 PSTN 网关、IP-PBX 或 SBC。
    


  - **文件存储** 文件存储用于录制的名称音频文件。文件存储是每个 企业版 或 标准版 部署中的标准组件。

  - **用户存储** 用户存储用于存储用户 Lync Server 2013 PIN。PIN 是哈希值。用户存储是每个 企业版 或 标准版 部署中的标准组件。

  - **Lync Server 控制面板** 部分拨入设置可使用 Lync Server 控制面板进行配置。

  - **Lync Server 命令行管理程序** 使用 Lync Server 命令行管理程序 cmdlet 可以配置所有的拨入设置。 Lync Server 命令行管理程序 cmdlet 可用于部署、配置、运行、监控会议助理和会议通知，以及排除 会议助理应用程序和 会议通知应用程序的故障。有关特定 cmdlet 的详细信息，请参阅 Lync Server 命令行管理程序文档。

## 支持的拓扑

在 Lync Server 2013 中，始终将运行会议服务的服务器与 前端服务器或 Standard Edition 服务器 并置。初始部署期间， 拓扑生成器为您提供了在拓扑中包括会议的选项。您还可使用 拓扑生成器将会议添加到现有部署中。有关详细信息，请参阅 [在 Lync Server 2013 中定义和配置拓扑](lync-server-2013-defining-and-configuring-the-topology.md)。

## 电话拨入式会议拓扑

可以在以下拓扑和配置中部署电话拨入式会议：

  - Lync Server 2013标准版

  - Lync Server 2013企业版

  - 使用或不使用 企业语音

可以在中央站点上部署 应用程序服务、 会议助理应用程序和 会议通知应用程序，但不能在分支站点上部署。

> [!NOTE]  
> 如果部署电话拨入式会议，那么必须在每个部署 Lync Server 2013 会议的池中部署电话拨入式会议。无需在每个池中分配访问号码，但必须在每个池中部署电话拨入式会议功能。当用户呼叫一个池中的访问号码以加入另一个池中的 Lync Server 2013 会议时，此要求支持记录名称功能。



## Lync Server 2013 和 Office Web Apps 的受支持的拓扑

Lync Server 2013 提供下列方法来配置 Office Web Apps Server。根据您的需要，可以：

  - **在您的组织的防火墙后及在相同的网络区域中内部安装 Lync Server 2013 和 Office Web Apps Server。**借助此拓扑，将通过反向代理服务器提供对 Office Web Apps Server 的外部访问权限。内部和组织的防火墙后将安装 Lync Server 2013 和 Office Web Apps Server（或 Office Web Apps Server 场）。理想情况下，应该在与 Lync Server 相同的网络区域安装 Office Web Apps Server。
    
    通过使用反向代理服务器（它是一个从 Internet 获得请求并将其转发到内部网络的服务器），外部 Lync 客户端可连接到 Lync Server 2013 和 Office Web Apps Server（内部客户端无需使用反向代理服务器，因为它们可直接连接到 Office Web Apps Server）。如果您想使用仅由 Lync Server 2013 使用的专用 Office Web Apps Server 场，则此拓扑最适合。

  - **使用外部部署的 Office Web Apps Server**
    
    在此拓扑中，可进行内部部署 Lync Server 2013，并使用在 Lync Server 网络区域外部部署的 Office Web Apps Server。当 Office Web Apps Server 跨公司内多个应用程序共享及在要求 Lync Server 使用 Office Web Apps Server 的外部接口的网络中部署时会发生这种情况，反之易然。
    
    您无需安装反向代理服务器，但是，来自 Office Web Apps Server 到 Lync Server 2013 的所有请求都会通过您的 边缘服务器进行路由。使用外部 URL，可将内部和外部 Lync 客户端连接到 Office Web Apps Server。
    
    如果在内部防火墙之外部署了 Office Web Apps Server，则可以选择拓扑生成器中的“Office Web Apps 服务器部署在外部网络（外围/Internet）中”。有关更多详细信息，请访问[配置与 Office Web Apps Server 和 Lync Server 2013 的集成](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md)。

无论您选择什么拓扑，打开正确的防火墙端口至关重要。必须确保 Office Web Apps Server、负载平衡器或 Lync Server 上的防火墙不会阻止 DNS 名称、IP 地址和端口。

> [!NOTE]  
> 提供对 Office Web Apps Server 外部访问权限的另一选项是在外围网络中部署服务器。如果选择执行此操作，请记住， Office Web Apps Server 安装要求该服务器计算机是 Active Directory 域的成员。除非您的网络策略允许外围网络中的计算机是 Active Directory 域成员，否则，建议您不要在外围网络中安装 Office Web Apps Server。但是，应该在内部网络中安装 Office Web Apps Server，并提供外部用户通过反向代理服务器的访问权限。



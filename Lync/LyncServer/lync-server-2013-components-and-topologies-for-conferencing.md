---
title: 用于会议的 Lync Server 2013 组件和拓扑
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Components and topologies for conferencing
ms:assetid: eb83052a-3360-4ba1-a6a0-6ee419942809
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399061(v=OCS.15)
ms:contentKeyID: 48185707
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5caf5ba33e863e08bf4f728d2bf11394f37f20b6
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34837534"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="components-and-topologies-for-conferencing-in-lync-server-2013"></a>Lync Server 2013 中用于会议的组件和拓扑

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2013-02-04_

当您在拓扑生成器中选择 "会议" 时, 会议将作为前端服务器或标准版服务器的一部分进行部署。 电话拨入式会议和 PowerPoint 共享需要其他组件和配置。 以下部分介绍了 web 会议、A/V 会议和电话拨入式会议所支持的组件和拓扑。

<div>

## <a name="supported-components"></a>支持的组件

只有你的组织的前端服务器或标准版服务器才需要组件 web 会议和 A/V 会议。 有关前端服务器和标准版服务器的硬件和软件要求的列表, 请参阅 Lync Server 2013[支持的适用于 Lync server 2013](lync-server-2013-supported-hardware.md)和[服务器软件和基础结构支持](lync-server-2013-server-software-and-infrastructure-support.md)的硬件。

Lync Server 2013 使用 Office Web Apps 和 Office Web Apps 服务器处理 PowerPoint 演示文稿的共享和呈现。 有关安装和配置 Office Web Apps 服务器的详细信息, 请参阅[配置与 Office web Apps server 和 Lync server 2013 的集成](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md)。

除了 web 会议和 A/V 会议的要求外, 电话拨入式会议使用以下 Lync Server 2013 组件:

  - **应用程序服务**   应用程序服务提供了用于部署、托管和管理统一通信 (UC) 应用程序的平台。 电话拨入式会议使用需要应用程序服务的两个 UC 应用程序: 会议助理和会议公告。 在部署会议工作负荷和选择 "电话拨入式会议" 选项时, 默认情况下, 应用程序服务在前端池的每个前端服务器上和每个标准版服务器上都安装和激活。

  - **会议助理应用程序**   会议助理应用程序是一个统一通信应用程序, 可接受公共交换电话网络 (PSTN) 呼叫、播放提示以及将呼叫联接到 a/V 会议。 当您部署会议工作负荷并选择 "电话拨入式会议" 选项时, 会议助理应用程序默认安装并激活。

  - **会议公告应用程序**   会议公告应用程序是一种统一通信应用程序, 用于在某些操作 (如参与者加入或离开会议) 上向 PSTN 参与者播放声音和提示。参与者已静音或已取消静音, 某人进入了会议厅, 或者会议已锁定或已解锁。 会议公告应用程序还支持电话键盘中的双音调 multifrequency (DTMF) 命令。 会议公告应用程序在你部署会议工作负荷和选择电话拨入式会议选项时, 默认情况下会自动安装和激活。

  - ****"电话拨入式会议设置" 页面 "电话拨入式会议设置" 页面显示会议拨入号码及其可用语言、分配的会议信息 (即, 对于不需要安排的会议) 和   电话会议内 DTMF 控件, 并支持个人识别码 (PIN) 和分配的会议信息的管理。 “电话拨入式会议设置”页作为 Web 服务的一部分自动安装。

  - **Lync server 2013、中介服务器和 PSTN 网关**   电话拨入式会议需要中介服务器在 Lync server 2013 和 pstn 网关之间转换信号 (和媒体, 在某些配置中), 以及用于转换的 pstn 网关中介服务器和 PSTN 网关之间的信号和媒体。 对于电话拨入式会议, 必须至少部署一个中介服务器和以下至少一个服务器:
    
      - PSTN 网关
    
      - IP-PBX
    
      - 会话边界控制器 (SBC)（用于通过配置 SIP 中继进行连接的 Internet 电话服务提供商）
    
    <div>
    

    > [!NOTE]  
    > 如果您还在部署企业语音, 则中介服务器和 PSTN 网关是企业语音部署的一部分。 如果不部署企业语音, 则需要为电话拨入式会议至少部署一个中介服务器和至少一个 PSTN 网关、IP PBX 或 SBC。

    
    </div>

  - **文件存储**   文件存储用于录制的名称音频文件。 文件存储是每个 Enterprise Edition 或 Standard Edition 部署中的标准组件。

  - **用户存储**   用户存储用于存储用户 Lync Server 2013 pin。 PIN 是哈希值。 用户存储是每个 Enterprise Edition 或 Standard Edition 部署中的标准组件。

  - **Lync server 控制面板**   某些拨入设置可通过使用 Lync Server 控制面板进行配置。

  - **Lync server management shell**   可以使用 Lync Server management shell cmdlet 配置所有拨入设置。 Lync Server Management Shell cmdlet 可用于部署、配置、运行、监视会议助理应用程序和会议公告应用程序以及对其进行故障排除。 有关特定 cmdlet 的详细信息, 请参阅 Lync Server 命令行管理程序文档。

</div>

<div>

## <a name="supported-topologies"></a>支持的拓扑

在 Lync Server 2013 中, 运行会议服务的服务器始终与前端服务器或标准版服务器 collocated。 在初始部署期间, 拓扑生成器提供了在拓扑中包括会议的选项。 还可以使用拓扑生成器将会议添加到现有部署。 有关详细信息, 请参阅[在 Lync Server 2013 中定义和配置拓扑](lync-server-2013-defining-and-configuring-the-topology.md)。

<div>

## <a name="dial-in-conferencing-toplogies"></a>拨入会议 Toplogies

可以在下列拓扑和配置中部署电话拨入式会议:

  - Lync Server 2013 标准版

  - Lync Server 2013 企业版

  - 使用或不使用企业语音

可以在中心网站 (而不是分支站点) 中部署应用程序服务、会议助理应用程序和会议公告应用程序。

<div>


> [!NOTE]  
> 如果你部署电话拨入式会议, 则必须在部署 Lync Server 2013 会议的每个池中部署它。 无需在每个池中分配访问号码，但必须在每个池中部署电话拨入式会议功能。 当用户从一个池中调用访问号码以在其他池中加入 Lync Server 2013 会议时, 此要求支持录制的名称功能。



</div>

</div>

<div>

## <a name="supported-topologies-for-lync-server-2013-and-office-web-apps"></a>Lync Server 2013 和 Office Web Apps 支持的拓扑

Lync Server 2013 提供了以下配置 Office Web Apps 服务器的方法。 根据你的需要，你可以：

  - **在您的组织的防火墙后面和同一网络区域中安装 Lync Server 2013 和 Office Web Apps 本地服务器。** 使用此拓扑, 将通过反向代理服务器提供对 Office Web Apps 的外部访问。 Lync Server 2013 和 Office Web Apps 服务器 (或 Office Web Apps 服务器场) 都在本地和组织的防火墙之后安装。 理想情况下, 你应在 Lync Server 所在的网络区域中安装 Office Web Apps 服务器。
    
    外部 Lync 客户端可以使用反向代理服务器连接到 Lync Server 2013 和 Office Web Apps 服务器, 这是一个服务器, 该服务器接受来自 Internet 的请求并将其转发到内部网络。 (内部客户端不需要使用反向代理服务器, 因为它们可以直接连接到 Office Web Apps 服务器。)如果你希望使用仅由 Lync Server 2013 使用的专用 Office Web Apps 服务器场, 则此拓扑最适用。

  - **使用外部部署的 Office Web Apps 服务器**
    
    在此拓扑中, 将在本地部署 Lync Server 2013, 并使用在 Lync Server 网络区域外部部署的 Office Web Apps 服务器。 当 Office Web Apps 服务器在公司中的多个应用程序之间共享并部署在需要 Lync 服务器才能使用 Office Web Apps 服务器的外部接口的网络中时, 可能会发生这种情况。
    
    无需安装反向代理服务器;而是从 Office Web Apps 服务器到 Lync Server 2013 的所有请求都通过 Edge 服务器进行路由。 内部和外部 Lync 客户端都使用外部 URL 连接到 Office Web Apps 服务器。
    
    如果 Office Web Apps 服务器是在内部防火墙外部部署的, 请选择 "Office Web Apps" 服务器在拓扑生成器中的**外部网络 (即, 周边/Internet) 中部署**。 有关更多详细信息, 请参阅[配置与 Office Web Apps server 和 Lync server 2013 的集成](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md)。

无论你选择什么拓扑，打开正确的防火墙端口至关重要。 你必须确保 DNS 名称、IP 地址和端口未被 Office Web Apps 服务器、负载平衡器或 Lync Server 上的防火墙阻止。

<div>


> [!NOTE]  
> 用于提供对 Office Web Apps 服务器的外部访问的另一个选项是在外围网络中部署服务器。 如果你选择执行此操作, 请记住 Office Web Apps 服务器安装要求服务器计算机是你的 Active Directory 域的成员。 除非你的网络策略允许外围网络中的计算机成为 Active Directory 域成员, 否则建议你不要在外围网络中安装 Office Web Apps 服务器。 相反, 你应该在内部网络中安装 Office Web Apps 服务器, 并通过反向代理服务器提供外部用户访问。



</div>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>


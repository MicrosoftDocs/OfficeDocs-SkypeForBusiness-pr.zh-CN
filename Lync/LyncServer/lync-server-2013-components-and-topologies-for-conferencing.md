---
title: 适用于会议的 Lync Server 2013 组件和拓扑
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Components and topologies for conferencing
ms:assetid: eb83052a-3360-4ba1-a6a0-6ee419942809
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399061(v=OCS.15)
ms:contentKeyID: 48185707
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e4c843bbe5c34aaf0ad98ca73e8ebd33820b87d2
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42209348"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="components-and-topologies-for-conferencing-in-lync-server-2013"></a>Lync Server 2013 中的会议的组件和拓扑

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2013-02-04_

在拓扑生成器中选择 "会议" 时，会将会议作为前端服务器或 Standard Edition 服务器的一部分进行部署。 电话拨入式会议和 PowerPoint 需要其他组件和配置。 下面各部分介绍了支持 Web 会议、A/V 会议和电话拨入式会议的组件和拓扑。

<div>

## <a name="supported-components"></a>支持的组件

仅有的组件 web 会议和 A/V 会议需要您的组织的前端服务器或 Standard Edition 服务器。 有关前端服务器和 Standard Edition 服务器的硬件和软件要求的列表，请参阅 Lync Server 2013 中的[支持的适用于 Lync server 2013](lync-server-2013-supported-hardware.md)和[服务器软件和基础结构支持](lync-server-2013-server-software-and-infrastructure-support.md)的硬件。

Lync Server 2013 使用 Office Web Apps 和 Office Web Apps Server 处理 PowerPoint 演示文稿的共享和呈现。 有关安装和配置 Office Web Apps Server 的详细信息，请参阅[配置与 Office Web Apps server 和 Lync Server 2013 的集成](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md)。

除了 web 会议和 A/V 会议的要求外，电话拨入式会议使用以下 Lync Server 2013 组件：

  - **Application service**   Application service 提供用于部署、托管和管理统一通信（UC）应用程序的平台。 电话拨入式会议使用两个需要应用程序服务的 UC 应用程序：会议助理和会议通知。 在部署会议工作负载和选择 "电话拨入式会议" 选项时，默认情况下，应用程序服务在前端池的每台前端服务器上和每个 Standard Edition 服务器上的默认安装和激活。

  - **会议助理应用程序**   会议助理应用程序是一个统一通信应用程序，它接受公共交换电话网络（PSTN）呼叫、播放提示，并将呼叫加入 a/V 会议。 会议助理应用程序在您部署会议工作负荷并选择 "电话拨入式会议" 选项时默认情况下会安装和激活。

  - **会议通知应用程序**   会议通知应用程序是一种统一通信应用程序，它在特定操作（如参与者加入会议或离开会议时）对 PSTN 参与者播放声音和提示，参与者是静音或 unmuted、某人进入了会议会议厅，或者会议已锁定或已解锁。 会议通知应用程序还支持电话键盘中的双音多频（DTMF）命令。 会议通知应用程序在你部署会议工作负载和选择电话拨入式会议选项时，默认情况下会自动安装和激活。

  - **"电话拨入式会议设置**" 页 "电话拨入式会议设置" 页显示会议拨入号码及其可用语言、分配的会议信息（即，对于不需要安排的会议）以及会议 DTMF 控制，并支持对个人标识号（PIN）和分配的会议信息的管理。    "电话拨入式会议设置" 页将作为 Web 服务的一部分自动安装。

  - **Lync server 2013、中介服务器和 PSTN 网关**   电话拨入式会议要求中介服务器在 Lync server 2013 和 pstn 网关之间转换信号（和媒体，在某些配置中），以及在中介服务器和 pstn 网关之间转换信号和媒体的 pstn 网关。 对于电话拨入式会议，必须至少部署一个中介服务器和以下至少一个：
    
      - PSTN 网关
    
      - IP-PBX
    
      - 会话边界控制器 (SBC)（用于通过配置 SIP 中继进行连接的 Internet 电话服务提供商）
    
    <div>
    

    > [!NOTE]  
    > 如果还部署企业语音，中介服务器和 PSTN 网关是企业语音部署的一部分。 如果不部署企业语音，则需要为电话拨入式会议部署至少一台中介服务器，以及至少一个 PSTN 网关、IP-PBX 或 SBC。

    
    </div>

  - **文件存储**   文件存储用于记录的名称音频文件。 文件存储是每个 Enterprise Edition 或 Standard Edition 部署中的一个标准组件。

  - **用户存储**   用户存储用于存储用户 Lync Server 2013 pin。 对 Pin 进行哈希处理。 用户存储是每个 Enterprise Edition 或 Standard Edition 部署中的标准组件。

  - **Lync server 控制面板**   通过使用 Lync Server 控制面板，可以配置某些拨入设置。

  - **Lync server 命令行**   管理程序可以使用 Lync server 命令行管理程序 cmdlet 配置所有拨入设置。 Lync Server 命令行管理程序 cmdlet 可用于部署、配置、运行、监视会议助理应用程序和会议通知应用程序并对其进行故障排除。 有关特定 cmdlet 的详细信息，请参阅 Lync Server 命令行管理程序文档。

</div>

<div>

## <a name="supported-topologies"></a>支持的拓扑

在 Lync Server 2013 中，运行会议服务的服务器始终与前端服务器或 Standard Edition 服务器并置。 在初始部署过程中，拓扑生成器将为您提供在拓扑中包括会议的选项。 还可以使用拓扑生成器向现有部署中添加会议。 有关详细信息，请参阅[在 Lync Server 2013 中定义和配置拓扑](lync-server-2013-defining-and-configuring-the-topology.md)。

<div>

## <a name="dial-in-conferencing-toplogies"></a>电话拨入式会议拓扑

可以在以下拓扑和配置中部署电话拨入式会议：

  - Lync Server 2013 Standard Edition

  - Lync Server 2013 企业版

  - 有或没有企业语音

您可以在中央站点中部署应用程序服务、会议助理应用程序和会议通知应用程序，但不能在分支站点中进行部署。

<div>


> [!NOTE]  
> 如果要部署电话拨入式会议，则必须在部署 Lync Server 2013 会议的每个池中部署它。 无需在每个池中分配访问号码，但必须在每个池中部署电话拨入式会议功能。 当用户从一个池中调用访问号码以在不同的池中加入 Lync Server 2013 会议时，此要求支持所记录的名称功能。



</div>

</div>

<div>

## <a name="supported-topologies-for-lync-server-2013-and-office-web-apps"></a>Lync Server 2013 和 Office Web Apps 支持的拓扑

Lync Server 2013 提供了以下配置 Office Web Apps Server 的方法。 根据您的需要，可以：

  - **在组织的防火墙后面和同一网络区域中安装 Lync Server 2013 和 Office Web Apps Server 内部部署。** 使用此拓扑，将通过反向代理服务器提供对 Office Web Apps Server 的外部访问。 Lync Server 2013 和 Office Web Apps Server （或 Office Web Apps Server 服务器场）都在本地和组织的防火墙后面安装。 理想情况下，应在与 Lync Server 相同的网络区域中安装 Office Web Apps Server。
    
    外部 Lync 客户端可以使用反向代理服务器连接到 Lync Server 2013 和 Office Web Apps Server，这是一台接收来自 Internet 的请求并将其转发到内部网络的服务器。 （内部客户端无需使用反向代理服务器，因为它们可直接连接到 Office Web Apps Server。）如果要使用仅由 Lync Server 2013 使用的专用 Office Web Apps Server 场，则此拓扑最适用。

  - **使用外部部署的 Office Web Apps Server**
    
    在此拓扑中，Lync Server 2013 部署在本地，并使用在 Lync Server 网络区域外部部署的 Office Web Apps 服务器。 如果 Office Web Apps Server 在公司中的多个应用程序之间共享，并且部署在要求 Lync Server 使用 Office Web Apps Server 外部接口的网络中，则可能会发生这种情况，反之亦然。
    
    您无需安装反向代理服务器;相反，从 Office Web Apps Server 到 Lync Server 2013 的所有请求都将通过边缘服务器进行路由。 内部和外部 Lync 客户端都使用外部 URL 连接到 Office Web Apps Server。
    
    如果 Office Web Apps Server 部署在内部防火墙之外，则选择 " **Office Web Apps server 部署在拓扑生成器中的外部网络（即，外围/Internet）中**" 选项。 有关更多详细信息，请参阅[配置与 Office Web Apps server 和 Lync Server 2013 的集成](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md)。

无论您选择什么拓扑，打开正确的防火墙端口至关重要。 必须确保 Office Web Apps Server、负载平衡器或 Lync Server 上的防火墙不会阻止 DNS 名称、IP 地址和端口。

<div>


> [!NOTE]  
> 提供对 Office Web Apps Server 的外部访问权限的另一种方法是在外围网络中部署服务器。 如果选择执行此操作，请注意 Office Web Apps Server 安装程序要求服务器计算机是 Active Directory 域的成员。 除非您的网络策略允许外围网络中的计算机成为 Active Directory 域成员，否则建议您不要在外围网络中安装 Office Web Apps Server。 相反，应在内部网络中安装 Office Web Apps Server，并通过反向代理服务器提供外部用户访问权限。



</div>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>


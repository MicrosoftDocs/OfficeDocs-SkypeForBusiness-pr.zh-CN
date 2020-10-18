---
title: 电话拨入式会议配置的先决条件和权限
description: 电话拨入式会议配置的先决条件和权限。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Dial-in conferencing configuration prerequisites and permissions
ms:assetid: b3b251e5-78ac-44a2-8c36-2a061c9b2314
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412865(v=OCS.15)
ms:contentKeyID: 48185165
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: eced67f33e35c711c4fcd31120480b6d5c2e41ce
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48576168"
---
# <a name="dial-in-conferencing-configuration-prerequisites-and-permissions-in-lync-server-2013"></a>Lync Server 2013 中的电话拨入式会议配置先决条件和权限

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-06-20_

电话拨入式会议是 Lync Server 2013 会议工作负荷的可选组件。 在您使用拓扑生成器设计拓扑并设置前端池或 Standard Edition server 时，您需要安装的组件才能配置电话拨入式会议。 本主题介绍配置电话拨入式会议之前需要完成的任务。

本节假定您已阅读与会议工作负荷和电话拨入式会议相关的规划部分。

<div>

## <a name="dial-in-conferencing-configuration-prerequisites"></a>电话拨入式会议配置先决条件

电话拨入式会议需要以下 Lync Server 2013 组件：

  - 统一通信应用程序服务 (UCAS)（称为“应用程序服务”**）

  - 会议助理应用程序

  - 会议通知应用程序

  - 电话拨入式会议设置网页

  - 至少一个 Lync Server 2013 中介服务器和至少一个 PSTN 网关

当您使用拓扑生成器定义和发布拓扑，然后部署前端池或 Standard Edition server 时，可以部署这些组件。 如果要部署企业语音，应先部署它，然后再配置电话拨入式会议。 如果不部署企业语音，则可以在部署前端池或 Standard Edition Server 时，将中介服务器和公共交换电话网络 (PSTN) 网关部署。

<div>


> [!NOTE]
> 如果要从 Office 通信服务器 2007 R2 升级到 Lync Server 2013，请在您计划用于承载 Lync Server 2013 会议的每个池中部署电话拨入式会议。 有关迁移电话拨入式会议的详细信息，请参阅 <A href="migration-from-office-communications-server-2007-r2-to-lync-server-2013.md">从 Office 通信服务器 2007 R2 迁移到 Lync Server 2013</A>。



</div>

本节假定您已执行以下操作：

  - 如果要迁移到 Lync Server 2013，请将最新的更新应用到 Office 通信服务器 2007 R2 环境。

  - 使用拓扑生成器来设计和配置拓扑。 指定会议工作负荷时，已选择电话拨入式会议选项。 有关定义拓扑的详细信息，请参阅部署文档中的在 [Lync Server 2013 中定义和配置拓扑](lync-server-2013-defining-and-configuring-the-topology.md) 。

  - 已发布拓扑，并已设置前端池或 Standard Edition Server。 有关发布拓扑和安装 Lync Server 2013 的详细信息，请参阅部署文档中的 [部署 Lync server 2013](lync-server-2013-deploying-lync-server.md) 。
    
    <div>
    

    > [!NOTE]
    > 安装发布的拓扑时，电话拨入式会议设置网页将作为 Web 服务的一部分安装在前端服务器或 Standard Edition Server 上。

    
    </div>
    
    <div>
    

    > [!IMPORTANT]
    > 如果您在部署 Lync Server 2013 之后在拓扑生成器中更改文件存储的路径，则需要重新启动会议助理和会议通知应用程序才能使用新路径。

    
    </div>

  - 部署了企业语音。 如果不部署企业语音，请在 Enterprise Edition 前端服务器或 Standard Edition 服务器上并置中介服务器，或者部署了独立的中介服务器，并且部署了 PSTN 网关。 有关部署企业语音的详细信息，请参阅部署文档中的在 [Lync Server 2013 中部署企业语音](lync-server-2013-deploying-enterprise-voice.md) 。 有关安装独立中介服务器和 PSTN 网关的详细信息，请参阅部署文档中的在 [Lync Server 2013 中部署中介服务器和定义对等方](lync-server-2013-deploying-mediation-servers-and-defining-peers.md) 。

下面的流程图显示配置电话拨入式会议之前必须执行的步骤，以及配置电话拨入式会议时需要执行的步骤。

**部署电话拨入式会议**

![电话拨入式会议部署流程图](images/Gg412865.fde8c246-b5ed-4323-a6e7-af1983a5ec86(OCS.15).jpg "电话拨入式会议部署流程图")

</div>

<div>

## <a name="dial-in-conferencing-permissions"></a>电话拨入式会议权限

要配置电话拨入式会议，需要使用以下管理工具：

  - Lync Server 2013 控制面板

  - Lync Server 命令行管理程序

使用这些管理工具配置电话拨入式会议设置、拨号计划、策略以及其他电话拨入式会议所需的设置。

配置电话拨入式会议需要以下任一管理角色，具体取决于任务：

  - **CsVoiceAdministrator**    此管理员角色可以创建、配置和管理与语音相关的设置和策略。

  - **CsUserAdministrator**    此管理员角色可以为用户启用和禁用 Lync Server，并将现有策略（如会议策略和 PIN 策略）分配给用户。

  - **CsAdministrator**    此管理员角色可以执行 CsVoiceAdministrator 和 CsUserAdministrator 的所有任务。

</div>

<div>

## <a name="see-also"></a>另请参阅


[在 Lync Server 2013 中部署企业语音](lync-server-2013-deploying-enterprise-voice.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


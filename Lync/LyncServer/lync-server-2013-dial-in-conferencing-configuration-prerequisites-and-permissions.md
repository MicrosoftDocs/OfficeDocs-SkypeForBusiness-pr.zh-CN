---
title: 电话拨入式会议配置的先决条件和权限
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Dial-in conferencing configuration prerequisites and permissions
ms:assetid: b3b251e5-78ac-44a2-8c36-2a061c9b2314
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412865(v=OCS.15)
ms:contentKeyID: 48185165
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a60fc58e0ec40dadff044257d43629c2f3cb01ea
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34830407"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dial-in-conferencing-configuration-prerequisites-and-permissions-in-lync-server-2013"></a>Lync Server 2013 中电话拨入式会议配置的先决条件和权限

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2012-06-20_

电话拨入式会议是 Lync Server 2013 会议工作负荷的可选组件。 在你使用拓扑生成器设计拓扑, 然后设置你的前端池或标准版服务器之前, 你需要安装的组件才能配置拨入式会议。 本主题介绍了在配置拨入式会议之前需要完成的操作。

本部分假设你已阅读与会议工作负荷和电话拨入式会议相关的计划部分。

<div>

## <a name="dial-in-conferencing-configuration-prerequisites"></a>电话拨入式会议配置先决条件

电话拨入式会议需要以下 Lync Server 2013 组件:

  - 统一通信应用程序服务 (UCAS)（称为“*应用程序服务*”）

  - 会议助理应用程序

  - 会议通知应用程序

  - 电话拨入式会议设置网页

  - 至少一个 Lync Server 2013 中介服务器和至少一个 PSTN 网关

在使用拓扑生成器定义和发布拓扑, 然后部署前端池或标准版服务器时, 可部署这些组件。 如果要部署企业语音, 则应在配置拨入式会议之前部署它。 如果不部署企业语音, 则可以在部署前端池或标准版服务器时部署中介服务器和公共交换式电话网络 (PSTN) 网关。

<div>


> [!NOTE]
> 如果要从 Office 通信服务器 2007 R2 升级到 Lync Server 2013, 请在你计划用于托管 Lync Server 2013 会议的每个池中部署电话拨入式会议。 有关迁移拨入式会议的详细信息, 请参阅<A href="migration-from-office-communications-server-2007-r2-to-lync-server-2013.md">从 Office 通信服务器 2007 R2 迁移到 Lync Server 2013</A>。



</div>

本部分假设你已完成以下操作:

  - 如果要迁移到 Lync Server 2013, 请将最新更新应用到 Office 通信服务器 2007 R2 环境。

  - 使用拓扑生成器设计和配置拓扑。 在指定会议工作负荷时, 您选择了 "电话拨入式会议" 选项。 有关定义拓扑的详细信息, 请参阅部署文档中[Lync Server 2013 中的 "定义和配置拓扑](lync-server-2013-defining-and-configuring-the-topology.md)"。

  - 发布了拓扑, 并设置了前端池或标准版服务器。 有关发布拓扑和安装 Lync Server 2013 的详细信息, 请参阅部署文档中的 "[部署 Lync server 2013](lync-server-2013-deploying-lync-server.md) "。
    
    <div>
    

    > [!NOTE]
    > 安装已发布的拓扑时, "电话拨入式会议设置" 网页安装在前端服务器或标准版服务器上, 作为 Web 服务的一部分。

    
    </div>
    
    <div>
    

    > [!IMPORTANT]
    > 如果在部署 Lync Server 2013 后更改拓扑生成器中文件存储的路径, 则需要重新启动会议助理和会议公告应用程序才能使用新路径。

    
    </div>

  - 已部署企业语音。 如果您不是在部署企业语音, 您可以在企业版前端服务器或标准版服务器上 collocated 中介服务器, 或者部署了一个独立的中介服务器, 并且部署了 PSTN 网关。 有关部署企业语音的详细信息, 请参阅部署文档中的[Lync Server 2013 中的 "部署企业语音](lync-server-2013-deploying-enterprise-voice.md)"。 有关安装独立中介服务器和 PSTN 网关的详细信息, 请参阅部署文档中的在[Lync Server 2013 中部署中介服务器和定义对等](lync-server-2013-deploying-mediation-servers-and-defining-peers.md)。

以下流程图显示了在配置拨入式会议之前必须执行的步骤以及配置电话拨入式会议所执行的步骤。

**部署电话拨入式会议**

![电话拨入式会议部署流程图](images/Gg412865.fde8c246-b5ed-4323-a6e7-af1983a5ec86(OCS.15).jpg "电话拨入式会议部署流程图")

</div>

<div>

## <a name="dial-in-conferencing-permissions"></a>电话拨入式会议权限

要配置电话拨入式会议, 您需要使用以下管理工具:

  - Lync Server 2013 控制面板

  - Lync Server 命令行管理程序

使用这些管理工具配置电话拨入式会议设置, 以及拨入式会议所需的拨号计划、策略和其他设置。

配置拨入式会议需要以下任何管理角色, 具体取决于任务:

  - **CsVoiceAdministrator**   此管理员角色可以创建、配置和管理与语音相关的设置和策略。

  - **CsUserAdministrator**   此管理员角色可为用户启用和禁用 Lync Server 的用户, 并将现有策略 (如会议策略和 PIN 策略) 分配给用户。

  - **CsAdministrator**   此管理员角色可以执行 CsVoiceAdministrator 和 CsUserAdministrator 的所有任务。

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


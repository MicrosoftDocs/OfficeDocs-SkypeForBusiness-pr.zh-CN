---
title: Lync Server 2013：远程呼叫控制的部署任务
description: Lync Server 2013：远程呼叫控制的部署任务。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment tasks for remote call control
ms:assetid: 20218871-4f27-4611-9b7e-c0ca55908284
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558624(v=OCS.15)
ms:contentKeyID: 48183599
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 61d0d57489bd93d7e6ce0209c605f05a2417bded
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48553578"
---
# <a name="deployment-tasks-for-remote-call-control-in-lync-server-2013"></a>Lync Server 2013 中的远程呼叫控制的部署任务

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-10-05_

本主题介绍为 Lync Server 环境中的用户启用远程呼叫控制而必须执行的部署任务。

<div>


> [!NOTE]  
> 如果要在 Microsoft Office Communicator 2007 R2 中迁移以前为远程呼叫控制启用的用户，则在开始执行本主题中所述的远程呼叫控制部署任务之前，必须执行额外的部署任务。 在将迁移过程迁移到 Lync Server 时， (之前称为 "已 <EM>授权主机条目</EM> " 的受信任的应用程序条目) 必须使用 Office 通信服务器 2007 R2 管理工具（如适用）删除。<BR>有关删除已授权主机的详细信息，请参阅 <A href="lync-server-2013-remove-a-legacy-authorized-host-optional.md">在 Lync Server 2013 中删除旧版授权主机 (可选) </A>。



</div>

<div>

## <a name="step-1-install-and-configure-the-sipcsta-gateway-to-communicate-with-your-pbx"></a>步骤 1：安装和配置 SIP/CSTA 网关，以与 PBX 进行通信

您需要安装至少一个 SIP/CSTA 网关，以便在您的环境中连接到 Lync Server 和现有的专用分支 exchange (PBX) ，以便为用户提供远程呼叫控制功能。 SIP/CSTA 网关是 SIP 和计算机支持的电信应用程序 (CSTA) 之间的网关。 不管是安装多个网关，还是只安装一个网关，都只能为每个用户配置一个网关或 PBX。 如果现有 PBX 没有 SIP/CSTA 接口，请确保部署可支持 PBX（包括支持专用于 PBX 的供应商特定的信号协议）的 SIP/CSTA 网关。 有关功能的详细信息，请直接咨询各个供应商。

当您准备好部署可与 Lync Server 集成以进行远程呼叫控制的 SIP/CSTA 网关时，请咨询您的网关供应商或供应商的网关文档，以了解有关网关所需的以下信息的语法：

  - 网关的线路服务器 URI

  - 要分配给网关的用户的线路 URI

用户配置期间需要上述设置，且网关必须按预期指定这些设置，以正确路由并连接到 PBX。

你可以在上的 Microsoft 统一通信开放式互操作性计划网站上参阅供应商 [https://go.microsoft.com/fwlink/p/?linkId=203309](https://go.microsoft.com/fwlink/p/?linkid=203309) 。

</div>

<div>

## <a name="step-2-configure-lync-server-to-route-csta-requests-to-the-sipcsta-gateway"></a>步骤2：将 Lync Server 配置为将 CSTA 请求路由到 SIP/CSTA 网关

您必须在您打算路由远程呼叫控制请求的部署中的所有 SIP/CSTA 网关 (Server URI) 的目标地址，在 Lync Server 池上创建静态路由。 还必须创建与每个目标地址相对应的受信任应用程序项。 将网关指定为受信任的应用程序时，它被授予作为 Lync Server 环境的一部分运行的受信任状态，即使它是由第三 (方开发的，也会运行作为 *外部服务* 的服务，因为它不是产品) 的内置部件。 最后，如果 Lync Server 将使用传输控制协议 (TCP) 连接而不是传输层安全性 (TLS) 连接连接到 SIP/CSTA 网关，则还必须使用拓扑生成器定义网关 IP 地址。

有关配置静态路由的详细信息，请参阅 [Lync Server 2013 中的为远程呼叫控制配置静态路由](lync-server-2013-configure-a-static-route-for-remote-call-control.md)。

有关配置受信任的应用程序项的详细信息，请参阅 [Lync Server 2013 中的为远程呼叫控制配置受信任的应用程序条目](lync-server-2013-configure-a-trusted-application-entry-for-remote-call-control.md)。

有关在拓扑生成器中定义 SIP/CSTA 网关 IP 地址的详细信息，请参阅 [在 Lync Server 2013 中定义 sip/CSTA 网关 ip 地址](lync-server-2013-define-a-sip-csta-gateway-ip-address.md)。

</div>

<div>

## <a name="step-3-configure-lync-users-for-remote-call-control"></a>步骤3：配置 Lync 用户的远程呼叫控制

为用户启用 Lync Server 后，可以使用 Lync Server 控制面板或 Lync Server 命令行管理程序来启用远程呼叫控制。 在此部署步骤期间，为每个用户分配线路服务器 URI 和线路 URI。 线路服务器 URI 是计划分配给用户的 SIP/CSTA 网关的 SIP URI。 线路 URI 是分配给用户的唯一电话号码。

有关为用户配置远程呼叫控制的详细信息，请参阅 [在 Lync Server 2013 中为远程呼叫控制启用 lync 用户](lync-server-2013-enable-lync-users-for-remote-call-control.md)。

</div>

<div>

## <a name="step-4-define-the-lync-server-phone-number-normalization-rules"></a>步骤 4：定义 Lync Server 电话号码规范化规则

在远程呼叫控制方案中，Lync Server 使用电话号码规范化规则将其收到的电话号码从 SIP/CSTA 网关转换为 e.164 格式。 电话号码必须使用此标准化格式，远程呼叫控制的某些功能才能正常工作。 远程呼叫控制使用的电话号码规范化规则与为通讯簿服务电话号码规范化配置的规则相同，但不同于企业语音使用的电话号码规范化规则。

有关远程呼叫控制如何使用电话号码规范化规则的详细信息，请参阅 [Lync Server 2013 中的远程呼叫控制和电话号码规范化](lync-server-2013-remote-call-control-and-phone-number-normalization.md)。 有关通讯簿服务的电话号码规范化规则的详细信息，请参阅操作文档中的在 [Lync Server 2013 主题中管理通讯簿服务](lync-server-2013-administering-the-address-book-service.md) 。

</div>

</div>

<span> </span>

</div>

</div>

</div>


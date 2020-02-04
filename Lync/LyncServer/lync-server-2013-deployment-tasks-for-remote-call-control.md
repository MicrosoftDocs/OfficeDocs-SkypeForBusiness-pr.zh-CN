---
title: Lync Server 2013：远程呼叫控制的部署任务
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
ms.openlocfilehash: df80ebcdc879598677a037d60c9eeeee46ba5209
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762550"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-tasks-for-remote-call-control-in-lync-server-2013"></a>Lync Server 2013 中远程呼叫控制的部署任务

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2012-10-05_

本主题介绍为您的 Lync Server 环境中的用户启用远程呼叫控制时必须执行的部署任务。

<div>


> [!NOTE]  
> 如果你在 Microsoft Office Communicator 2007 R2 中迁移以前为远程呼叫控制启用的用户，则必须先执行其他部署任务，然后再开始执行本主题中所述的远程呼叫控制部署任务。 在迁移到 Lync Server 的过程中，必须根据需要使用 Office 通信服务器 2007 R2 管理工具删除受信任的应用程序条目（以前称为<EM>授权主机条目</EM>）。<BR>有关删除授权的主机的详细信息，请参阅<A href="lync-server-2013-remove-a-legacy-authorized-host-optional.md">在 Lync Server 2013 中删除旧版授权主机（可选）</A>。



</div>

<div>

## <a name="step-1-install-and-configure-the-sipcsta-gateway-to-communicate-with-your-pbx"></a>步骤1：安装并配置 SIP/CSTA 网关以与你的 PBX 通信

要为用户提供远程呼叫控制功能，您需要至少安装一个 SIP/CSTA 网关，该网关可以连接到您的环境中的 Lync Server 和现有专用分支 exchange （PBX）。 SIP/CSTA 网关是 SIP 和计算机支持的电信应用程序（CSTA）之间的网关。 无论是安装多个网关还是仅安装一个网关，每个用户都只能配置一个网关或 PBX。 如果现有 PBX 没有 SIP/CSTA 接口，请确保部署可支持 PBX 的 SIP/CSTA 网关，包括针对专用 PBX 供应商特定的信号协议的支持。 有关功能的详细信息，请直接向每个供应商咨询。

当您准备好部署可与 Lync Server 进行远程呼叫控制的 SIP/CSTA 网关时，请咨询您的网关供应商或供应商的网关文档，了解有关网关的以下信息所需的语法：

  - 网关的行服务器 URI

  - 将分配给网关的用户的行 URI

在用户配置期间需要前面的设置，并且必须按网关的预期指定，才能正确路由和连接到 PBX。

您可以在 Microsoft 统一通信打开互操作性计划网站上参考供应[http://go.microsoft.com/fwlink/p/?linkId=203309](http://go.microsoft.com/fwlink/p/?linkid=203309)商。

</div>

<div>

## <a name="step-2-configure-lync-server-to-route-csta-requests-to-the-sipcsta-gateway"></a>步骤2：将 Lync Server 配置为将 CSTA 请求路由到 SIP/CSTA 网关

你必须在你想要路由远程呼叫控制请求的部署中的所有 SIP/CSTA 网关的目标地址（服务器 URI）上创建 Lync 服务器池的静态路由。 还必须创建对应于每个目标地址的受信任的应用程序条目。 将网关指定为受信任的应用程序时，它将获得受信任状态以作为 Lync Server 环境的一部分运行，即使它由第三方开发（并且运行的是作为*外部服务*的服务，因为它不是产品的内置部分）。 最后，如果 Lync Server 将使用传输控制协议（TCP）连接（而不是传输层安全性（TLS）连接）连接到 SIP/CSTA 网关，则还必须使用拓扑生成器定义网关 IP 地址。

有关配置静态路由的详细信息，请参阅[在 Lync Server 2013 中配置远程呼叫控制的静态路由](lync-server-2013-configure-a-static-route-for-remote-call-control.md)。

有关配置受信任的应用程序条目的详细信息，请参阅[在 Lync Server 2013 中配置远程呼叫控制的受信任的应用程序条目](lync-server-2013-configure-a-trusted-application-entry-for-remote-call-control.md)。

有关在拓扑结构生成器中定义 SIP/CSTA 网关 IP 地址的详细信息，请参阅[在 Lync Server 2013 中定义 sip/CSTA 网关 ip 地址](lync-server-2013-define-a-sip-csta-gateway-ip-address.md)。

</div>

<div>

## <a name="step-3-configure-lync-users-for-remote-call-control"></a>步骤3：为远程呼叫控制配置 Lync 用户

为 Lync Server 启用用户后，您可以使用 Lync Server 控制面板或 Lync Server Management Shell 为远程呼叫控制启用它们。 在此部署步骤中，你为每个用户分配了一行服务器 URI 和行 URI。 线路服务器 URI 是你计划分配给用户的 SIP/CSTA 网关的 SIP URI。 行 URI 是分配给用户的唯一电话号码。

有关为远程呼叫控制配置用户的详细信息，请参阅[在 Lync Server 2013 中启用远程呼叫控制的 Lync 用户](lync-server-2013-enable-lync-users-for-remote-call-control.md)。

</div>

<div>

## <a name="step-4-define-the-lync-server-phone-number-normalization-rules"></a>步骤4：定义 Lync 服务器电话号码规范化规则

在远程呼叫控制方案中，Lync Server 使用电话号码规范化规则将从 SIP/CSTA 网关接收的电话号码转换为 E-164 格式。 要正常运行某些远程呼叫控制功能，电话号码必须采用这种标准化格式。 "远程呼叫控制" 使用为通讯簿服务电话号码规范化配置的相同电话号码规范化规则，这与用于企业语音的电话号码规范化规则不同。

有关远程呼叫控制如何使用电话号码规范化规则的详细信息，请参阅[Lync Server 2013 中的远程呼叫控制和电话号码规范化](lync-server-2013-remote-call-control-and-phone-number-normalization.md)。 有关通讯簿服务的电话号码规范化规则的详细信息，请参阅操作文档中的[管理 Lync Server 2013 主题中的 "通讯簿" 服务](lync-server-2013-administering-the-address-book-service.md)。

</div>

</div>

<span> </span>

</div>

</div>

</div>


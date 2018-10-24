---
title: Lync Server 2013：远程呼叫控制的部署任务
TOCTitle: 远程呼叫控制的部署任务
ms:assetid: 20218871-4f27-4611-9b7e-c0ca55908284
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg558624(v=OCS.15)
ms:contentKeyID: 49312216
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 中远程呼叫控制的部署任务

 

_**上一次修改主题：** 2016-12-08_

本主题介绍为 Lync Server 环境中的用户启用远程呼叫控制时必须执行的部署任务。

> [!NOTE]  
> 如果要迁移以前在 Microsoft Office Communicator 2007 R2 中启用了远程呼叫控制的用户，则在开始执行本主题中介绍的远程呼叫控制部署任务之前，必须先执行另外一个部署任务。在迁移到 Lync Server 的过程中，必须使用适当的 Office Communications Server 2007 R2 管理工具删除受信任应用程序项（以前称为 <em>授权主机项</em> ）。<br />
有关删除授权主机的详细信息，请参阅<a href="lync-server-2013-remove-a-legacy-authorized-host-optional.md">在 Lync Server 2013 中删除旧版授权主机（可选）</a>。



## 步骤 1：安装和配置 SIP/CSTA 网关，以与 PBX 进行通信

要向用户提供远程呼叫控制功能，需在环境中安装至少一个可连接到 Lync Server 和现有专用交换机 (PBX) 的 SIP/CSTA 网关。SIP/CSTA 网关是 SIP 和计算机支持的电信应用程序 (CSTA) 之间的网关。不管是安装多个网关，还是只安装一个网关，都只能为每个用户配置一个网关或 PBX。如果现有 PBX 没有 SIP/CSTA 接口，请确保部署可支持 PBX（包括支持专用于 PBX 的供应商特定的信号协议）的 SIP/CSTA 网关。有关功能的详细信息，请直接咨询各个供应商。

当您准备好为远程呼叫控制部署可与 Lync Server 集成的 SIP/CSTA 网关时，还应咨询网关供应商，或参阅有关网关所需语法的供应商网关文档，以了解以下信息：

  - 网关的线路服务器 URI

  - 要分配给网关的用户的线路 URI

用户配置期间需要上述设置，且网关必须按预期指定这些设置，以正确路由并连接到 PBX。

您可参考 Microsoft 统一通信 开放互操作性计划网站上的供应商，网址为 [http://go.microsoft.com/fwlink/p/?linkId=203309](http://go.microsoft.com/fwlink/p/?linkid=203309)。

## 步骤 2：配置 Lync Server 以将 CSTA 请求路由到 SIP/CSTA 网关

必须在 Lync Server 池上创建到部署中所有 SIP/CSTA 网关的目标地址（服务器 URI）的静态路由，这些目标地址是要将远程呼叫控制请求路由到的地址。还必须创建与每个目标地址相对应的受信任应用程序项。将网关指定为受信任应用程序时，会为其指定受信任状态，以作为 Lync Server 环境的一部分运行，即使该网关由第三方开发（并运行因不属于产品内置部分而被称为 *外部服务* 的服务）也是如此。最后，如果 Lync Server 将使用传输控制协议 (TCP) 连接连接到 SIP/CSTA 网关，而不是传输层安全性 (TLS) 连接，则还必须使用 拓扑生成器定义网关 IP 地址。

有关配置静态路由的详细信息，请参阅[在 Lync Server 2013 中为远程呼叫控制配置静态路由](lync-server-2013-configure-a-static-route-for-remote-call-control.md)。

有关配置受信任应用程序项的详细信息，请参阅[在 Lync Server 2013 中为远程呼叫控制配置受信任的应用程序项](lync-server-2013-configure-a-trusted-application-entry-for-remote-call-control.md)。

有关在拓扑生成器中定义 SIP/CSTA 网关 IP 地址的详细信息，请参阅[在 Lync Server 2013 中定义 SIP/CSTA 网关 IP 地址](lync-server-2013-define-a-sip-csta-gateway-ip-address.md)。

## 步骤 3：为 Lync 用户配置远程呼叫控制

为用户启用 Lync Server 后，即可使用 Lync Server 控制面板或 Lync Server 命令行管理程序为这些用户启用远程呼叫控制。在此部署步骤期间，为每个用户分配线路服务器 URI 和线路 URI。线路服务器 URI 是计划分配给用户的 SIP/CSTA 网关的 SIP URI。线路 URI 是分配给用户的唯一电话号码。

有关为用户配置远程呼叫控制的详细信息，请参阅[在 Lync Server 2013 中为 Lync 用户启用远程呼叫控制](lync-server-2013-enable-lync-users-for-remote-call-control.md)。

## 步骤 4：定义 Lync Server 电话号码规范化规则

在远程呼叫控制方案中， Lync Server 使用电话号码规范化规则将从 SIP/CSTA 网关接收的电话号码转换为 E.164 格式。电话号码必须使用此标准化格式，远程呼叫控制的某些功能才能正常工作。远程呼叫控制使用的电话号码规范化规则与为通讯簿服务电话号码规范化配置的规则相同，但不同于企业语音使用的电话号码规范化规则。

有关远程呼叫控制如何使用电话号码规范化规则的详细信息，请参阅 [Lync Server 2013 中的远程呼叫控制和电话号码规范化](lync-server-2013-remote-call-control-and-phone-number-normalization.md)。有关用于通讯簿服务的电话号码规范化规则的详细信息，请参阅操作文档中的 [在 Lync Server 2013 中管理通讯簿服务](lync-server-2013-administering-the-address-book-service.md)主题。


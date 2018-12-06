---
title: 启用远程呼叫控制
TOCTitle: 启用远程呼叫控制
ms:assetid: 0b91d418-e6ed-4556-97af-e8523e01f249
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ204664(v=OCS.15)
ms:contentKeyID: 49311963
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 启用远程呼叫控制

 

_**上一次修改主题：** 2012-10-02_

通过远程呼叫控制，用户可使用 Lync Server 2013 控制他们的桌面专用交换机 (PBX) 电话。如果您在旧环境中部署了远程呼叫控制，并且希望将它迁移到 Lync Server 2013，需要执行以下任务：

1.  安装并配置 SIP/CSTA 网关以便与 PBX 通信。您需要在部署 Lync Server 2013 试点池时执行该步骤。

2.  合并拓扑并迁移策略和设置后，配置 Lync Server 2013 以将 CSTA 请求路由到 SIP/CSTA 网关。该步骤是自动迁移后要执行的手动步骤。要配置 CSTA 请求的路由，请执行以下操作：
    
      - 删除旧的授权主机条目（在 Lync Server 2013 中称为 *受信任服务器条目* ）。要从旧部署中迁移用户，请确保在 Lync Server 2013 试点池中配置新受信任应用程序条目之前，删除为 SIP/CSTA 网关创建的所有现有授权主机条目。有关如何删除旧授权主机条目的详细信息，请参阅 [删除授权主机条目](remove-an-authorized-host-entry.md)。
    
      - 为远程呼叫控制配置静态路由。您可以为希望支持远程呼叫控制的单个池配置静态路由，也可以配置一个全局静态路由，以便未配置池级静态路由的每个池使用全局静态路由。有关如何配置静态路由的详细信息，请参阅部署文档中的 [在 Lync Server 2013 中为远程呼叫控制配置静态路由](lync-server-2013-configure-a-static-route-for-remote-call-control.md)。
    
      - 在您希望支持远程呼叫控制的每个池中为远程呼叫控制配置受信任应用程序条目。有关如何配置受信任应用程序条目的详细信息，请参阅部署文档中的 [在 Lync Server 2013 中为远程呼叫控制配置受信任的应用程序项](lync-server-2013-configure-a-trusted-application-entry-for-remote-call-control.md)。

3.  如果部署的 SIP/CSTA 网关使用传输控制协议 (TCP) 连接到 Lync Server 2013，请在拓扑生成器中定义网关的 IP 地址。有关定义 IP 地址的详细信息，请参阅部署文档中的 [在 Lync Server 2013 中定义 SIP/CSTA 网关 IP 地址](lync-server-2013-define-a-sip-csta-gateway-ip-address.md)。

4.  通过启用远程呼叫控制并分配线路服务器统一资源标识符 (URI) 和线路 URI，为远程呼叫控制配置 Lync 2013 用户。从将用户从旧部署迁移到 Lync Server 2013 时，远程呼叫控制设置随其他用户设置一起迁移。

5.  如果您在旧部署中自定义了通讯簿电话号码规范化规则，则完成策略和设置的自动迁移后，需要执行一些手动操作以迁移自定义的规范化规则。如果未自定义规范化规则，通讯簿将随拓扑的其余部分一起迁移。有关手动迁移自定义规范化规则的详细信息，请参阅 [迁移通讯簿](migrate-address-book_1.md)。


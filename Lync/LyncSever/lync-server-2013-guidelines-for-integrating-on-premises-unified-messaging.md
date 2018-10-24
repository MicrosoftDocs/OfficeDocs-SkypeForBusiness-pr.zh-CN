---
title: Lync Server 2013：集成本地统一消息的指南
TOCTitle: 集成本地统一消息与 Lync Server 的指南
ms:assetid: 829ac017-6907-40f9-be22-787a28eae0ac
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398656(v=OCS.15)
ms:contentKeyID: 49313441
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 集成本地统一消息与 Lync Server 2013 的指南

 

_**上一次修改主题：** 2016-12-08_

以下是部署企业语音时要考虑的准则和最佳做法：

> [!IMPORTANT]
> 仅当您也使用 UCMA 4 时， Exchange 统一消息 (UM) 才支持 IPv6。


  - 部署 Lync Server 2013 Standard Edition Server 或 前端池。有关安装的详细信息，请参阅部署文档中的 [部署 Lync Server 2013](lync-server-2013-deploying-lync-server.md)。

  - 与 Exchange 管理员一起确认每个人将要执行的任务，以确保顺利、成功地集成。

  - 在要为用户启用 Exchange UM 的每个 Exchange 统一消息 (UM) 林中部署 Exchange 邮箱服务器角色。有关安装 Exchange 服务器角色的详细信息，请参阅 Microsoft Exchange Server 2013 文档。
    
    > [!IMPORTANT]  
    > 安装 Exchange 统一消息 (UM) 后，将其配置为使用自签名证书。<br />
    > 但是，该自签名证书不允许 Lync Server 2013 和 Exchange UM 相互信任，这就是必须从两个服务器都信任的证书颁发机构请求单独证书的原因。


  - 如果 Lync Server 2013 和 Exchange UM 安装在不同的林中，请将每个 Exchange 林都配置为信任 Lync Server 2013 林，并将 Lync Server 2013 林配置为信任每个 Exchange 林。另外，在 Lync Server 2013 林中的用户对象上设置用户的 Exchange UM 设置，通常使用脚本或跨林工具（如 Identity Lifecycle Manager (ILM)）来完成。

  - 必要时，安装 Exchange 管理控制台以管理统一消息服务器。

  - 获取有效的电话号码，供 Outlook Voice Access 和自动助理使用。

  - 如果要使用早于 Microsoft Exchange Server 2010 Service Pack 1 (SP1) 的 Exchange UM 版本，则 Exchange UM SIP URI 拨号计划的名称需与企业语音拨号计划相匹配。

## 部署冗余 Exchange UM 服务器

> [!IMPORTANT]
> 对于为组织配置的每个 Exchange UM SIP URI 拨号计划，我们建议您至少为其部署两台运行 Exchange UM 服务的服务器。除了提供扩展容量之外，部署冗余服务还可提供高可用性。如果服务器发生故障，则可将 Lync Server 2013 配置为故障转移到其他服务器。


以下示例配置提供 Exchange UM 恢复能力。

**示例 1：Exchange UM 恢复能力**

![Exchange UM 示例 1](images/Gg398656.3644b847-0847-4550-a989-e3fc51de5c4b(OCS.15).jpg "Exchange UM 示例 1")

在示例 1 中，Tukwila 数据中心启用了 Exchange UM 服务器 1 和 2，Dublin 数据中心启用了 Exchange UM 服务器 3 和 4。如果 Tukwila 发生 Exchange UM 中断，则应将服务器 1 和 2 的域名系统 (DNS) A 记录分别配置为指向服务器 3 和 4。如果 Dublin 发生 Exchange UM 中断，则应将服务器 3 和 4 的 DNS A 记录分别配置为指向服务器 1 和 2。

> [!NOTE]  
> 对于示例 1，还应在每台 Exchange UM 服务器上分配以下证书之一：
<ul>
<li><p>在使用者替代名称 (SAN) 中使用具有通配符的证书。</p></li>
<li><p>在 SAN 中使用四台 Exchange UM 服务器的完全限定域名 (FQDN)。</p></li>
</ul>



**示例 2：Exchange UM 恢复能力**

![Exchange UM 示例 2](images/Gg398656.15754273-306e-448d-b258-84bc2936a2e8(OCS.15).jpg "Exchange UM 示例 2")

在示例 2 中，一般操作情况下，Tukwila 数据中心启用了 Exchange UM 服务器 1 和 2，Dublin 数据中心启用了 Exchange UM 服务器 3 和 4。Tukwila 用户的 SIP URI 拨号计划中包含全部四台服务器；但服务器 3 和 4 已被禁用。如果 Tukwila 发生 Exchange UM 中断，则应禁用 Exchange UM 服务器 1 和 2，并启用 Exchange UM 服务器 3 和 4，这样才会将 Tukwila Exchange UM 流量路由至 Dublin 的服务器。

有关如何在 Exchange 2013 上启用或禁用统一消息的详细信息，请参阅“将 Exchange 2013 UM 与 Lync Server 集成”，网址为 [http://go.microsoft.com/fwlink/p/?LinkId=265372](http://go.microsoft.com/fwlink/p/?linkid=265372)。

有关如何在 Microsoft Exchange Server 2010 上启用或禁用统一消息的详细信息，请参阅：

  - “在 Exchange 2010 中启用统一消息”，网址为 [http://go.microsoft.com/fwlink/p/?LinkId=204418](http://go.microsoft.com/fwlink/p/?linkid=204418)。

  - “在 Exchange 2010 中禁用统一消息”，网址为 [http://go.microsoft.com/fwlink/p/?LinkId=204416](http://go.microsoft.com/fwlink/p/?linkid=204416)。

## 另请参阅

#### 概念

[集成本地统一消息与 Lync Server 2013 的部署过程](lync-server-2013-deployment-process-for-integrating-on-premises-unified-messaging.md)


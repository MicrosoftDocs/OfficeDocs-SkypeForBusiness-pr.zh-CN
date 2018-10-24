---
title: Lync Server 2013：Exchange 统一消息 (UM) 支持
TOCTitle: Exchange 统一消息 (UM) 支持
ms:assetid: 0da62b8d-7416-4fb8-a405-381ca805c53a
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398179(v=OCS.15)
ms:contentKeyID: 49311993
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 中的 Exchange 统一消息 (UM) 支持

 

_**上一次修改主题：** 2012-09-21_

Lync Server 2013 支持与 Exchange 统一消息 (UM) 集成，以便将语音消息传递和电子邮件传递组合到单个消息传递基础结构中。在 Exchange 2013 中， Exchange UM 由安装并运行于邮箱服务器的 Exchange UM 服务和安装并运行于客户端访问服务器的 UM 呼叫路由器组成。 对于 Lync Server 2013 企业语音部署， Exchange UM 将语音消息传递和电子邮件传递组合到一个可通过电话（即 Outlook Voice Access）或计算机访问的存储区中。同时使用 Exchange UM 和 Lync Server 2013 可向企业语音用户提供呼叫应答、Outlook Voice Access 和自动助理服务。

除了支持与 Exchange UM 本地部署集成之外， Lync Server 2013 还支持与托管 Exchange UM 集成。这样可使您在将某些或所有用户迁移到托管 Exchange 服务提供商（如 Microsoft Exchange Online）时，为用户提供语音消息传递。

Lync Server 2013 支持以下版本：

  - Microsoft Exchange 2013

  - Microsoft Exchange Server 2010（必需）或最新的 Service Pack（推荐）

  - Microsoft Exchange Server 2007 Service Pack 1 (SP1)（必需）或最新的 Service Pack（推荐）

不能将 Exchange UM 与 Lync Server 2013 或 Lync Server 2013 数据库并置。可在单独的林中安装 Exchange UM 和 Lync Server 2013。

> [!NOTE]  
> Exchange UM 对于部署了 PBX 的企业语音部署可能并非必需，因为 PBX 可以继续向所有用户提供语音邮件和相关服务。如果您最终终止了 PBX（例如为公用电话交换网 (PSTN) 连接部署 SIP 中继），则必须重新配置 Exchange UM 以向之前使用 PBX 语音邮件系统的用户提供语音邮件。



## 本部分内容

  - [Lync Server 2013 中的本地统一消息的组件和拓扑](lync-server-2013-components-and-topologies-for-on-premises-unified-messaging.md)

  - [Lync Server 2013 中的托管 Exchange UM 集成支持](lync-server-2013-support-for-hosted-exchange-um-integration.md)


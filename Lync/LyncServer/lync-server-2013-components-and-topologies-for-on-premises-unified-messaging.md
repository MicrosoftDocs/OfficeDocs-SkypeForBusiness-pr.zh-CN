---
title: Lync Server 2013：本地统一消息的组件和拓扑
TOCTitle: 本地统一消息的组件和拓扑
ms:assetid: 22fc87cf-a7e5-4c8c-bb9b-101e5380cdcf
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg425711(v=OCS.15)
ms:contentKeyID: 49312251
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 中的本地统一消息的组件和拓扑

 

_**上一次修改主题：** 2012-09-25_

本主题介绍为 Lync Server 2013 部署提供 Exchange 统一消息 (UM) 功能所需的 Microsoft Exchange Server 2013 组件，还介绍了本地 Exchange UM 集成支持的拓扑。

## Exchange Server 组件

要为组织中的 企业语音用户提供 [集成统一消息和 Lync Server 2013 的功能](lync-server-2013-features-of-integrated-unified-messaging.md)中所述的 Exchange UM 功能和服务，您必须部署 Microsoft Exchange 邮箱服务器和客户端访问服务器，以便托管用户邮箱并为电子邮件和语音邮件提供一个存储位置。 Exchange UM 作为 Exchange 邮箱服务器和客户端访问服务器上的服务运行。

有关 Microsoft Exchange Server 2007 和 Microsoft Exchange Server 2010 中 Exchange UM 组件的详细信息，请参阅部署文档中的[部署本地 Exchange UM 以提供 Lync Server 2013 语音邮件](lync-server-2013-deploying-on-premises-exchange-um-to-provide-lync-server-2013-voice-mail.md)。

## 支持的拓扑

可将 Lync Server 2013 和 Exchange 统一消息 (UM) 部署到同一个林或多个林中。如果部署跨多个林，则必须为每个 Exchange UM 林执行 Exchange 集成步骤。此外，还必须将每个 Microsoft Exchange 林配置为信任 Lync Server 2013 林，并将 Lync Server 2013 林配置为信任每个 Exchange UM 林。除了此林信任之外，还必须在 Lync Server 2013 林中的用户对象上设置所有用户的 Exchange UM 设置。

Lync Server 2013 支持 Exchange UM 集成的以下拓扑：

  - 单林

  - 单域（即具有单个域的单林）。Lync Server 2013、 Microsoft Exchange 和用户全部驻留在同一域中。

  - 多域（即具有一个或多个子域的根域）。 Lync Server 2013 和 Microsoft Exchange 服务器部署在与在其中创建用户的域不同的域中。 Exchange UM 服务器可部署在与其支持的 Lync Server 2013 池不同的域中。

  - 多林（即资源林）。 Lync Server 2013 部署在单林中，然后将用户分布在多个林中。用户的 Exchange UM 属性必须复制到 Lync Server 2013 林。
    
    > [!NOTE]  
    > 可在多个林中部署 Exchange。每个 Exchange 组织可以向其用户提供 Exchange UM，也可以在 Lync Server 2013 所属的同一林中部署 Exchange UM。
    


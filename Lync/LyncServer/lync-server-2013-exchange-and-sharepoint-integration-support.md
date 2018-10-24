---
title: Lync Server 2013：Exchange Server 和 SharePoint 集成支持
TOCTitle: Exchange Server 和 SharePoint 集成支持
ms:assetid: 72bf8aa5-55b1-4851-8a59-c96bf85d215a
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ205005(v=OCS.15)
ms:contentKeyID: 49313228
ms.date: 01/19/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 中的 Exchange Server 和 SharePoint 集成支持

 

_**上一次修改主题：** 2017-01-18_

Lync Server 2013 和 Lync 2013 可以安全、无缝地与其他应用程序和服务器产品通信，其中包括 Office 2013、Exchange 2013 和 SharePoint（如果集成这些产品）。将 Lync Server 2013 与 Office 集成使用户可以根据情况访问 Lync 的即时消息 (IM)、增强状态、电话服务和会议功能。Office 用户可以从 Outlook 2013 消息和协作客户端及其他 Office 程序内部或从 Microsoft SharePoint Server 2010 页面访问 Lync 功能。用户还可以在 Outlook 的“对话历史记录”文件夹中查看 Lync 对话记录。在与 Exchange 2013 或 Exchange Online 集成时，Lync Server 2013 还支持以下内容：

  - 统一联系人存储，使用户可在 Exchange 2013 或 Exchange Online 中存储所有联系人信息，这样在 Lync 2013、Exchange、Outlook 和 Outlook Web App 中可全局使用该信息。

  - 会话历史记录和 Web 会议历史记录，存储在 Exchange 用户文件夹中。

  - 来自 Lync 的存档内容（如 IM 和会议内容）可以存储在 Exchange 存储中。

> [!NOTE]  
> Lync Server 2013 支持与 Microsoft Exchange Server 和 SharePoint 的早期版本集成，但这些早期版本并不支持所有功能，如存档存储与 Microsoft Exchange 的集成。<br />
如果要将用户迁移至 Exchange 2013，则可临时同时使用 Exchange 存储和 Lync Server 存储，同时完成迁移。不支持永久同时使用 Exchange 和 Lync Server 存储。



Lync Server 2013 与 Exchange 2013 和 SharePoint Server 的集成需要在运行 Lync Server 2013、 Microsoft Exchange Server 和 SharePoint Server 的服务器之间进行服务器到服务器身份验证。 Lync Server 2013 支持用于服务器到服务器身份验证和授权的 OAuth (Open Authorization) 协议。对于在两台 Microsoft 服务器之间进行的本地服务器到服务器身份验证，无需使用第三方令牌服务器。 Lync Server 2013、 Exchange 2013 和 SharePoint 具有内置的令牌服务器，可用于彼此之间的身份验证用途。例如， Lync Server 2013 可以发出并自行签署安全令牌，并在与 Exchange 2013 通信时使用该令牌。在此情况下，无需使用第三方令牌服务器。

Lync Server 2013 支持两种服务器到服务器身份验证方案。其中包括在以下各项之间配置服务器到服务器身份验证：

  - Lync Server 2013 的本地安装以及 Exchange 2013 和/或 SharePoint Server 的本地安装。

  - 一对 Office 组件（例如，在 Microsoft Exchange 365 与 Microsoft Lync Server 365 之间或 Microsoft Lync Server 365 与 Microsoft SharePoint 365 之间）。

> [!NOTE]  
> 在 Lync Server 2013 版本中不支持本地服务器与 Office 365 组件之间的服务器到服务器身份验证。此外，这意味着不能在 Lync Server 2013 与 Microsoft Exchange 365 的本地安装之间设置服务器到服务器身份验证。



有关服务器到服务器身份验证的详细信息，请参阅部署文档或操作文档中的 [在 Lync Server 2013 中管理服务器到服务器身份验证 (Oauth) 和合作伙伴应用程序](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md)。


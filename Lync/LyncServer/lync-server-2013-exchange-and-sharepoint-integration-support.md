---
title: Lync Server 2013： Exchange 和 SharePoint 集成支持
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Exchange and SharePoint integration support
ms:assetid: 72bf8aa5-55b1-4851-8a59-c96bf85d215a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205005(v=OCS.15)
ms:contentKeyID: 48184504
ms.date: 01/20/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1fdfaffa12d84b57f0ae0203ebc14491bb6d8d4f
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42146815"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="exchange-and-sharepoint-integration-support-in-lync-server-2013"></a>Lync Server 2013 中的 Exchange 和 SharePoint 集成支持

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2017-01-18_

如果集成这些产品，lync Server 2013 和 Lync 2013 可以与其他应用程序和服务器产品（包括 Office 2013、Exchange Server 2013、Exchange Server 2016 和 SharePoint）进行安全和无缝通信。 集成 Lync Server 2013 和 Office 可为用户提供对即时消息（IM）的上下文中访问权限，并增强了 Lync 的状态、电话服务和会议功能。 Office 用户可以从 Outlook 2013 消息和协作客户端以及其他 Office 程序或 SharePoint 页面中访问 Lync 功能。 用户还可以在 "Outlook 对话历史记录" 文件夹中查看 Lync 对话的记录。 当与 Exchange 2013、Exchange 2016 或 Exchange Online 集成时，Lync Server 2013 还支持以下内容：

  - 统一的联系人存储库，使用户能够在 Exchange 或 Exchange Online 中存储所有联系人信息，以便信息在 Lync 2013、Exchange、Outlook 和 Outlook Web App 中全局可用。

  - 会话历史记录和 Web 会议历史记录，存储在 Exchange 用户文件夹中。

  - Lync 中存档的内容（如 IM 和会议内容）可以存储在 Exchange 存储中。

<div>


> [!NOTE]  
> Lync Server 2013 支持与 Microsoft Exchange Server 和 SharePoint Server 的早期版本集成，但并不是所有这些早期版本都支持的功能，例如，将存档存储与 Microsoft Exchange 集成。<BR>如果要将用户迁移到 Exchange 2013 或 Exchange 2016，可以在完成迁移的同时，临时使用 Exchange 存储和 Lync Server 存储。 不支持永久使用 Exchange 和 Lync Server 存储。



</div>

将 Lync Server 2013 与 Exchange Server 和 SharePoint Server 集成需要在运行 Lync Server 2013、Exchange Server 和 SharePoint Server 的服务器之间进行服务器到服务器的身份验证。 Lync Server 2013 支持用于服务器到服务器身份验证和授权的 OAuth （开放式授权）协议。 对于在两台 Microsoft 服务器之间进行的本地服务器到服务器身份验证，无需使用第三方令牌服务器。 Lync Server 2013、Exchange Server 和 SharePoint Server 具有可用于相互进行身份验证的内置令牌服务器。 例如，Lync Server 2013 本身可以颁发和签名安全令牌，并在与 Exchange 通信时使用该令牌。 在此情况下，无需使用第三方令牌服务器。

Lync Server 2013 支持两种服务器到服务器身份验证方案。 其中包括在以下各项之间配置服务器到服务器身份验证：

  - 安装了 Lync Server 2013 的本地安装以及 Exchange Server 2013、Exchange Server 2016 和/或 SharePoint Server 的本地安装。

  - 一对 Office 组件（例如，在 Microsoft Exchange 365 和 Microsoft Lync Server 365 之间，或 Microsoft Lync Server 365 与 Microsoft SharePoint 365 之间）。

<div>


> [!NOTE]  
> 在此 Lync Server 2013 版本中不支持在本地服务器和 Office 365 组件之间进行服务器到服务器的身份验证。 此外，这意味着您不能在本地安装 Lync Server 2013 和 Microsoft Exchange 365 之间设置服务器到服务器的身份验证。



</div>

有关服务器到服务器身份验证的详细信息，请参阅部署文档或操作文档中的在[Lync server 2013 中管理服务器到服务器身份验证（OAuth）和合作伙伴应用程序](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md)。

</div>

<span> </span>

</div>

</div>

</div>


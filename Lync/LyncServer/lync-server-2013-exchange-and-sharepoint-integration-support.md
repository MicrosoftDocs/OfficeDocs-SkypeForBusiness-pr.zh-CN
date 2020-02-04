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
ms.openlocfilehash: 198df79f63415affa4fb9b41d55265b58ae00a8a
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41756256"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="exchange-and-sharepoint-integration-support-in-lync-server-2013"></a>Lync Server 2013 中的 Exchange 和 SharePoint 集成支持

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2017-01-18_

如果集成这些产品，lync Server 2013 和 Lync 2013 可以安全、无缝地与其他应用程序和服务器产品进行通信，包括 Office 2013、Exchange Server 2013、Exchange Server 2016 和 SharePoint。 集成 Lync Server 2013 和 Office 为用户提供了对 Lync 的上下文内访问即时消息（IM）、增强状态、电话服务和会议功能的用户。 Office 用户可以从 Outlook 2013 消息和协作客户端以及其他 Office 程序或 SharePoint 页面中访问 Lync 功能。 用户还可以在 "Outlook 对话历史记录" 文件夹中查看 Lync 对话的记录。 当集成到 Exchange 2013、Exchange 2016 或 Exchange Online 时，Lync Server 2013 还支持以下内容：

  - 统一联系人存储，使用户能够在 Exchange 或 Exchange Online 中存储所有联系人信息，以便信息在 Lync 2013、Exchange、Outlook 和 Outlook Web App 中全局可用。

  - 对话历史记录和网络会议历史记录，存储在 Exchange 用户文件夹中。

  - 来自 Lync 的存档内容（如 IM 和会议内容）可以存储在 Exchange 存储中。

<div>


> [!NOTE]  
> Lync Server 2013 支持与早期版本的 Microsoft Exchange Server 和 SharePoint Server 进行集成，但并非所有功能都受这些以前版本的支持，例如将存档存储与 Microsoft Exchange 集成。<BR>如果你要将用户迁移到 Exchange 2013 或 Exchange 2016，则可以在完成迁移时定期使用 Exchange 存储和 Lync 服务器存储。 不支持永久使用 Exchange 和 Lync Server 存储。



</div>

将 Lync Server 2013 与 Exchange Server 和 SharePoint Server 集成需要在运行 Lync Server 2013、Exchange Server 和 SharePoint Server 的服务器之间进行服务器到服务器的身份验证。 Lync Server 2013 支持用于服务器到服务器身份验证和授权的 OAuth （开放授权）协议。 对于两个 Microsoft 服务器之间的本地服务器到服务器身份验证，无需使用第三方令牌服务器。 Lync Server 2013、Exchange Server 和 SharePoint Server 具有内置的令牌服务器，可用于彼此进行身份验证。 例如，Lync Server 2013 可以自行颁发和签名安全令牌，并在与 Exchange 通信时使用该令牌。 在这种情况下，不需要使用第三方令牌服务器。

Lync Server 2013 支持两种服务器到服务器身份验证方案。 其中包括以下各项之间的服务器到服务器身份验证配置：

  - Lync Server 2013 的内部部署和 Exchange Server 2013、Exchange Server 2016 和/或 SharePoint Server 的本地安装。

  - 一对 Office 组件（例如，在 Microsoft Exchange 365 和 Microsoft Lync Server 365 之间或 Microsoft Lync Server 365 和 Microsoft SharePoint 365 之间）。

<div>


> [!NOTE]  
> 在此 Lync Server 2013 版本中不支持本地服务器与 Office 365 组件之间的服务器到服务器身份验证。 此外，这意味着你无法在 Lync Server 2013 和 Microsoft Exchange 365 的本地安装之间设置服务器到服务器的身份验证。



</div>

有关服务器到服务器身份验证的详细信息，请参阅在部署文档或操作文档中[管理 Lync server 2013 中的服务器到服务器身份验证（OAuth）和合作伙伴应用程序](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md)。

</div>

<span> </span>

</div>

</div>

</div>


---
title: Lync Server 2013：配置持久聊天服务器
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure Persistent Chat Server
ms:assetid: 85028aff-a38e-4748-958e-59e707a47532
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205054(v=OCS.15)
ms:contentKeyID: 48184709
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3762679b8926370b85e03d0ffac2981c5c7d13a3
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41741342"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-persistent-chat-server-in-lync-server-2013"></a>在 Lync Server 2013 中配置持久聊天服务器

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2012-10-06_

创建新的持久聊天配置

    New-CsPersistentChatConfiguration -Identity <XdsIdentity> [-DefaultChatHistory <Integer>] [-MaxChatContentSizeMB <Integer>] [-MaxFileSizeKB <Integer>] [-ParticipantUpdateLimit <Integer>] [-FileServiceUrl <UrlForFileUpload>] [-RoomManagementUrl <RoomManagementUrl>] [-Instance <PSObject>] [-Force <Switch Parameter>] [-Confirm <Switch Parameter>] [-WhatIf <Switch Parameter>]

获取持久聊天配置

    Get-CsPersistentChatConfiguration [-LocalStore <Switch Parameter>] [-Identity <XdsIdentity>]

删除持久聊天配置

    Remove-CsPersistentChatConfiguration -Identity <XdsIdentity>

设置持久聊天配置

    Set-CsPersistentChatConfiguration [-DefaultChatHistory <Integer>] [-MaxChatContentSizeMB <Integer>] [-MaxFileSizeKB <Integer>] [-ParticipantUpdateLimit <Integer>] [-FileServiceUrl <UrlForFileUpload>] [-RoomManagementUrl <RoomManagementUrl>] [-Instance <PSObject >] [-Force <Switch Parameter>] [-Confirm <Switch Parameter>] [-WhatIf <Switch Parameter>]

对于 Lync Server 2013，所有 web 服务流量均受 Lync Server 2013 的前端服务器支持。 因此，不需要持久聊天服务器上的 gcweb01 地址。 我们仍然支持内部 web 服务访问，因为我们仅向*内部*网站提供文件上载/下载 web 服务（不适用于远程用户的*外部*网站）。

</div>

<span> </span>

</div>

</div>

</div>


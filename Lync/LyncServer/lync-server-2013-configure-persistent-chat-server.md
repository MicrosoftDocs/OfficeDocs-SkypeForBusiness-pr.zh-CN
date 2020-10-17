---
title: Lync Server 2013：配置持久聊天服务器
description: Lync Server 2013：配置持久聊天服务器。
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
ms.openlocfilehash: d45320e1fa6b247f13cfffa9945b45390f2ae6c5
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48564978"
---
# <a name="configure-persistent-chat-server-in-lync-server-2013"></a><span data-ttu-id="131f7-103">在 Lync Server 2013 中配置持久聊天服务器</span><span class="sxs-lookup"><span data-stu-id="131f7-103">Configure Persistent Chat Server in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="131f7-104">_**上次修改的主题：** 2012-10-06_</span><span class="sxs-lookup"><span data-stu-id="131f7-104">_**Topic Last Modified:** 2012-10-06_</span></span>

<span data-ttu-id="131f7-105">创建新的持久聊天配置</span><span class="sxs-lookup"><span data-stu-id="131f7-105">To create a new Persistent Chat configuration</span></span>

    New-CsPersistentChatConfiguration -Identity <XdsIdentity> [-DefaultChatHistory <Integer>] [-MaxChatContentSizeMB <Integer>] [-MaxFileSizeKB <Integer>] [-ParticipantUpdateLimit <Integer>] [-FileServiceUrl <UrlForFileUpload>] [-RoomManagementUrl <RoomManagementUrl>] [-Instance <PSObject>] [-Force <Switch Parameter>] [-Confirm <Switch Parameter>] [-WhatIf <Switch Parameter>]

<span data-ttu-id="131f7-106">获取持久聊天配置</span><span class="sxs-lookup"><span data-stu-id="131f7-106">To get Persistent Chat configuration</span></span>

    Get-CsPersistentChatConfiguration [-LocalStore <Switch Parameter>] [-Identity <XdsIdentity>]

<span data-ttu-id="131f7-107">删除持久聊天配置</span><span class="sxs-lookup"><span data-stu-id="131f7-107">To remove Persistent Chat configuration</span></span>

    Remove-CsPersistentChatConfiguration -Identity <XdsIdentity>

<span data-ttu-id="131f7-108">设置持久聊天配置</span><span class="sxs-lookup"><span data-stu-id="131f7-108">To set Persistent Chat configuration</span></span>

    Set-CsPersistentChatConfiguration [-DefaultChatHistory <Integer>] [-MaxChatContentSizeMB <Integer>] [-MaxFileSizeKB <Integer>] [-ParticipantUpdateLimit <Integer>] [-FileServiceUrl <UrlForFileUpload>] [-RoomManagementUrl <RoomManagementUrl>] [-Instance <PSObject >] [-Force <Switch Parameter>] [-Confirm <Switch Parameter>] [-WhatIf <Switch Parameter>]

<span data-ttu-id="131f7-109">对于 Lync Server 2013，所有 web 服务流量在 Lync Server 2013 前端服务器上均受支持。</span><span class="sxs-lookup"><span data-stu-id="131f7-109">For Lync Server 2013, all web service traffic is supported on the Lync Server 2013, Front End Servers.</span></span> <span data-ttu-id="131f7-110">因此，不需要在持久聊天服务器上的 gcweb01 地址。</span><span class="sxs-lookup"><span data-stu-id="131f7-110">Therefore, the gcweb01 address on Persistent Chat Server is not necessary.</span></span> <span data-ttu-id="131f7-111">我们仍支持内部 Web 服务访问，因为我们仅为*内部* 网站提供了文件上载/下载 Web 服务（不是远程用户的*外部* 网站）。</span><span class="sxs-lookup"><span data-stu-id="131f7-111">We still support internal web service access because we provide the File Upload/Download Web service to the *internal* website only (not to the *external* website for remote users).</span></span>

</div>

<span> </span>

</div>

</div>

</div>


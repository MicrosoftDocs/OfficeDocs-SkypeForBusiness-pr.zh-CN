---
title: Lync Server 2013：配置持久聊天服务器
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure Persistent Chat Server
ms:assetid: 85028aff-a38e-4748-958e-59e707a47532
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205054(v=OCS.15)
ms:contentKeyID: 48184709
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c8ff9c59efeb2eb8106a3fe823c8256c86474f51
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34837339"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-persistent-chat-server-in-lync-server-2013"></a><span data-ttu-id="443bb-102">在 Lync Server 2013 中配置持久聊天服务器</span><span class="sxs-lookup"><span data-stu-id="443bb-102">Configure Persistent Chat Server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="443bb-103">_**主题上次修改时间:** 2012-10-06_</span><span class="sxs-lookup"><span data-stu-id="443bb-103">_**Topic Last Modified:** 2012-10-06_</span></span>

<span data-ttu-id="443bb-104">创建新的持久聊天配置</span><span class="sxs-lookup"><span data-stu-id="443bb-104">To create a new Persistent Chat configuration</span></span>

    New-CsPersistentChatConfiguration -Identity <XdsIdentity> [-DefaultChatHistory <Integer>] [-MaxChatContentSizeMB <Integer>] [-MaxFileSizeKB <Integer>] [-ParticipantUpdateLimit <Integer>] [-FileServiceUrl <UrlForFileUpload>] [-RoomManagementUrl <RoomManagementUrl>] [-Instance <PSObject>] [-Force <Switch Parameter>] [-Confirm <Switch Parameter>] [-WhatIf <Switch Parameter>]

<span data-ttu-id="443bb-105">获取持久聊天配置</span><span class="sxs-lookup"><span data-stu-id="443bb-105">To get Persistent Chat configuration</span></span>

    Get-CsPersistentChatConfiguration [-LocalStore <Switch Parameter>] [-Identity <XdsIdentity>]

<span data-ttu-id="443bb-106">删除持久聊天配置</span><span class="sxs-lookup"><span data-stu-id="443bb-106">To remove Persistent Chat configuration</span></span>

    Remove-CsPersistentChatConfiguration -Identity <XdsIdentity>

<span data-ttu-id="443bb-107">设置持久聊天配置</span><span class="sxs-lookup"><span data-stu-id="443bb-107">To set Persistent Chat configuration</span></span>

    Set-CsPersistentChatConfiguration [-DefaultChatHistory <Integer>] [-MaxChatContentSizeMB <Integer>] [-MaxFileSizeKB <Integer>] [-ParticipantUpdateLimit <Integer>] [-FileServiceUrl <UrlForFileUpload>] [-RoomManagementUrl <RoomManagementUrl>] [-Instance <PSObject >] [-Force <Switch Parameter>] [-Confirm <Switch Parameter>] [-WhatIf <Switch Parameter>]

<span data-ttu-id="443bb-108">对于 Lync Server 2013, 所有 web 服务流量均受 Lync Server 2013 的前端服务器支持。</span><span class="sxs-lookup"><span data-stu-id="443bb-108">For Lync Server 2013, all web service traffic is supported on the Lync Server 2013, Front End Servers.</span></span> <span data-ttu-id="443bb-109">因此, 不需要持久聊天服务器上的 gcweb01 地址。</span><span class="sxs-lookup"><span data-stu-id="443bb-109">Therefore, the gcweb01 address on Persistent Chat Server is not necessary.</span></span> <span data-ttu-id="443bb-110">我们仍然支持内部 web 服务访问, 因为我们仅向*内部*网站提供文件上载/下载 web 服务 (不适用于远程用户的*外部*网站)。</span><span class="sxs-lookup"><span data-stu-id="443bb-110">We still support internal web service access because we provide the File Upload/Download Web service to the *internal* website only (not to the *external* website for remote users).</span></span>

</div>

<span> </span>

</div>

</div>

</div>


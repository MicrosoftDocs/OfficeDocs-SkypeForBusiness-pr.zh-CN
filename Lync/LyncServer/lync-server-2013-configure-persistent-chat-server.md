---
title: Lync Server 2013：配置持久聊天服务器
TOCTitle: 配置持久聊天服务器
ms:assetid: 85028aff-a38e-4748-958e-59e707a47532
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ205054(v=OCS.15)
ms:contentKeyID: 49313488
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 在 Lync Server 2013 中配置持久聊天服务器

 

_**上一次修改主题：** 2012-10-06_

创建新的 持久聊天配置

    New-CsPersistentChatConfiguration -Identity <XdsIdentity> [-DefaultChatHistory <Integer>] [-MaxChatContentSizeMB <Integer>] [-MaxFileSizeKB <Integer>] [-ParticipantUpdateLimit <Integer>] [-FileServiceUrl <UrlForFileUpload>] [-RoomManagementUrl <RoomManagementUrl>] [-Instance <PSObject>] [-Force <Switch Parameter>] [-Confirm <Switch Parameter>] [-WhatIf <Switch Parameter>]

获取 持久聊天配置

    Get-CsPersistentChatConfiguration [-LocalStore <Switch Parameter>] [-Identity <XdsIdentity>]

删除 持久聊天配置

    Remove-CsPersistentChatConfiguration -Identity <XdsIdentity>

设置 持久聊天配置

    Set-CsPersistentChatConfiguration [-DefaultChatHistory <Integer>] [-MaxChatContentSizeMB <Integer>] [-MaxFileSizeKB <Integer>] [-ParticipantUpdateLimit <Integer>] [-FileServiceUrl <UrlForFileUpload>] [-RoomManagementUrl <RoomManagementUrl>] [-Instance <PSObject >] [-Force <Switch Parameter>] [-Confirm <Switch Parameter>] [-WhatIf <Switch Parameter>]

对于 Lync Server 2013， Lync Server 2013前端服务器上支持所有 Web 服务通信。因此，无需 持久聊天服务器上的 gcweb01 地址。我们仍支持内部 Web 服务访问，因为我们仅为 *内部* 网站提供了文件上载/下载 Web 服务（不是远程用户的 *外部* 网站）。


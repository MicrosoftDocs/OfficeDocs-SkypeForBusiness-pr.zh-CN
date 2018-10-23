---
title: 管理加载项
TOCTitle: 管理加载项
ms:assetid: b84f868e-b36e-4ab4-b284-7db212d401c3
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ205193(v=OCS.15)
ms:contentKeyID: 49314056
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 管理加载项

 

_**上一次修改主题：** 2012-10-06_

创建新的 持久聊天服务器外接程序

    New-CsPersistentChatAddin -Name Contoso -PersistentChatPoolFqdn client.contoso.com -Url http://contoso.com 

## 创建、获取、设置或删除外接程序

创建新的外接程序

    New-CsPersistentChatAddin -PersistentChatPoolFqdn <String> -Name <String> -Url<String>

> [!IMPORTANT]
> 仅当有多个 持久聊天服务器池时，才需要 PersistentChatPoolFqdn &lt;String&gt;。


获取外接程序

    Get-CsPersistentChatAddin -Identity <String>]

或者

    Get-CsPersistentChatAddin -PersistentChatPoolFqdn <String>

设置外接程序

    Set-CsPersistentChatAddIn -Instance <AddinObject> [-Force <Switch Parameter>] [-Confirm <Switch Parameter>]

或者

    Set-CsPersistentChatAddIn -Identity <String> [-Name <String>] [-Url<String>] [-Force <Switch Parameter>] [-Confirm <Switch Parameter>]

删除外接程序

    Remove-CsPersistentChatAddIn -Instance <AddinObject> [-Force <Switch Parameter>] [-Confirm <Switch Parameter>]

或者

    Remove-CsPersistentChatAddIn -Identity <String> [-Force <Switch Parameter>] [-Confirm <Switch Parameter>]


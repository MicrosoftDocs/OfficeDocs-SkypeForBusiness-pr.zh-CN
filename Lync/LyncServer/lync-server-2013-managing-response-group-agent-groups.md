---
title: 管理响应组代理组
TOCTitle: 管理响应组代理组
ms:assetid: 36084cdc-38f1-4c45-922f-f81c7e86210c
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg520976(v=OCS.15)
ms:contentKeyID: 49312476
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 管理响应组代理组

 

_**上一次修改主题：** 2012-10-01_

代理组由指定应答响应组呼叫的一组人员组成。创建代理组时，要选择分配给该组的代理并指定其他组设置，如路由方法以及代理能否登录到组和从组注销。

> [!NOTE]  
> 必须先为用户启用企业语音，然后才能将其添加到代理组。有关如何为用户启用企业语音的详细信息，请参阅<a href="lync-server-2013-enable-users-for-enterprise-voice.md">在 Lync Server 2013 中为用户启用企业语音</a>。



> [!NOTE]  
> 只有内部部署用户可以成为代理。如果代理从内部部署移动到联机状态，则不会将响应组呼叫路由到该代理。



必须登录到组和从组注销（与登录到 Lync Server 或从中注销不同）的代理称为*正式代理*。正式代理必须登录到组，然后才能接收路由至该组的呼叫。这对于以兼职形式应答组中的呼叫的代理很有用。正式代理通过单击 Lync 2013 中的菜单项打开 Windows Internet Explorer Internet 浏览器并显示网页控制台，以登录到组或从组注销。

不登录到组或从组注销的代理称为*非正式代理*。非正式代理登录到 Lync Server 后，将自动登录到组，但无法从组注销。

> [!IMPORTANT]
> 如果将用户分配为响应组代理，需告知用户，如果他们已启用隐私模式，则需搜索“RGS Presence Watcher”联系人并将其添加到联系人列表。已启用隐私模式但未将“RGS Presence Watcher”添加到联系人列表中的代理将无法接收拨打到响应组的呼叫。未启用隐私模式的代理不受影响。


## 本部分内容

  - [在 Lync Server 2013 中创建或修改代理组](lync-server-2013-create-or-modify-an-agent-group.md)

  - [删除代理组](lync-server-2013-delete-an-agent-group.md)


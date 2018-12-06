---
title: Lync Server 2013：将聊天室从一个类别移动到另一个类别
TOCTitle: 将聊天室从一个类别移动到另一个类别
ms:assetid: 7e93b8f6-5a18-4476-a432-3918e01bcfa6
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ215877(v=OCS.15)
ms:contentKeyID: 49313393
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 在 Lync Server 2013 中将聊天室从一个类别移动到另一个类别

 

_**上一次修改主题：** 2012-11-01_

建议在创建 持久聊天聊天室后不要更改聊天室的类别。但是，如果聊天室管理员在其他类别中具有 **Creator** 特权，则他/她可以将聊天室从一个类别移动到另一个类别。将不会删除和重新创建该聊天室。这是数据库中的关联的更改。

应该尽量不要更改聊天室类别。类别用于确定聊天室允许的成员身份，因此当聊天室移动到另一个类别时，新类别不再支持的所有系统访问控制列表 (SACL) 都将清除。例如，如果用户是聊天室的成员，且不再是新类别中的 **AllowedMember**，则系统会修改聊天室成员身份，并将用户从聊天室中删除。

有关使用 Windows PowerShell 命令行接口移动聊天室的详细信息，请参阅 [使用 Windows PowerShell Cmdlet 配置持久聊天服务器](configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md)中的“聊天室管理”。

有关配置聊天室的详细信息，请参阅部署文档中的 [在 Lync Server 2013 中配置聊天室](lync-server-2013-configure-rooms.md)。


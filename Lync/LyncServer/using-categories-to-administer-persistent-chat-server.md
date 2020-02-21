---
title: 使用类别管理持久聊天服务器
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Using categories to administer Persistent Chat Server
ms:assetid: dfcb3ad1-da90-467e-b08c-f4e68673b7b5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398988(v=OCS.15)
ms:contentKeyID: 48185628
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0e02a780772cd0e9592bb078ab526a4085a234bc
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42189005"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="using-categories-to-administer-persistent-chat-server"></a>使用类别管理持久聊天服务器

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2013-10-01_

持久聊天服务器部署可承载多个并发持久聊天室。 聊天室可以组织到服务器上的一组类别中。 每个聊天室属于一个类别，并可从该类别继承部分设置。 这种组织方式可创建一种非常有用的结构以基于对话的业务目的识别对话，并有助于方便委托管理和简化控制。

<div>


> [!NOTE]  
> 虽然聊天室的许多管理功能在运行持久聊天（Lync 客户端）的计算机中可用，但持久聊天管理员（在<STRONG>cspersistentchatadministrator</STRONG>角色中）必须使用 Lync Server 控制面板或 Windows PowerShell cmdlet 来创建或管理类别。



</div>

持久聊天管理员使用 Lync Server 控制面板或 Windows PowerShell cmdlet 来创建和管理类别，并为组织中的用户设计聊天室的访问权限。

持久聊天室管理员（能够管理一个或多个聊天室）可以使用 Lync 客户端启动聊天室管理 Web 应用程序，以创建和管理会议室（或客户可以创建要调用的自定义解决方案和工作流）。 持久聊天管理员还可以使用 Lync Server 控制面板或 Windows PowerShell cmdlet 来创建和管理聊天室。

<div>


> [!NOTE]  
> 持久聊天室不能与持久聊天类别具有相同的名称。



</div>

除聊天室的类别外，聊天室管理员可以更改所有聊天室的属性。管理员可以执行以下操作：

  - 禁用聊天室

  - 更改聊天室名称

  - 更改聊天室说明

  - 更改聊天室类型（大会堂还是普通）

  - 更改聊天室的隐私（打开还是关闭还是保密）

  - 添加或删除成员

  - 添加或删除聊天室管理者

  - 添加或删除加载项

  - 更改诸如邀请等设置（取决于类别允许的内容）

<div>

## <a name="delegated-administration"></a>委派管理

通过正确使用类别，创建和管理持久聊天室更容易。 持续聊天管理员可以为每个类别定义**AllowedMembers**和**创建者**，还可以定义将应用于在类别中创建的所有聊天室的默认聊天室设置和行为。 持久聊天管理员使用 Lync Server 控制面板或 Windows PowerShell cmdlet 创建和管理类别。

标识为类别创建者的用户、组织单位 (OU) 和用户组是唯一允许在该类别中创建聊天室的个人和组。类别创建后，他们可以从类别的 **AllowedMembers** 列表中选择用户、OU 和用户组作为聊天室管理员和成员来管理和参与聊天室。

在类别中创建的聊天室遵循由类别强制实施的策略和设置（例如谁可以在会议室的成员身份、谁可以管理聊天室、是否允许文件上载、是否已发送邀请等）。

</div>

</div>

<span> </span>

</div>

</div>

</div>


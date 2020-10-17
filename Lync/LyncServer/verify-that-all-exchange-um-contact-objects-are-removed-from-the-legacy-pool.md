---
title: 验证是否已从旧版池中删除所有 Exchange UM 联系人对象
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Verify that all Exchange UM Contact objects are removed from the legacy pool
ms:assetid: 5a813169-0ed7-4f84-a242-ed2cd4ea5c43
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688068(v=OCS.15)
ms:contentKeyID: 49733664
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: eae8f82016f8dd78c3ecd568e34c3cc408a204ae
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48515949"
---
# <a name="verify-that-all-exchange-um-contact-objects-are-removed-from-the-legacy-pool"></a>验证是否已从旧版池中删除所有 Exchange UM 联系人对象

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-09-26_

使用 **ocsumutil.exe** 工具或 **CsExumContact** cmdlet 验证 Exchange UM contact 对象是否已从旧版 Office 通信服务器 2007 R2 池中删除。 **OCSUmUtil** 位于以下文件夹中：

% Program Files% \\ 常用文件 \\ Lync Server 2013 \\ 支持 \\OcsUMUtil.exe

**OCSUmUtil** 必须从具有以下权限的用户帐户运行：

  - RTCUniversalServerAdmins 和 RTCUniversalUserAdmins 组中的成员身份（包括读取 Exchange Server 统一消息设置的权限）

  - 在指定的组织单位 (OU) 容器中创建联系对象的域权限

有关使用 **CsExumContact** cmdlet 的详细信息，请参阅 Lync Server 命令行管理程序文档中的 [CsExumContact](https://docs.microsoft.com/powershell/module/skype/Get-CsExUmContact) 。

</div>

<span> </span>

</div>

</div>

</div>


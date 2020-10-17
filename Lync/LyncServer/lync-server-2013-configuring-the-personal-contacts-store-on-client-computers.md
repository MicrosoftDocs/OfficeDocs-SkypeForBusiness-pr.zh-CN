---
title: Lync Server 2013：在客户端计算机上配置个人联系人存储
description: Lync Server 2013：在客户端计算机上配置个人联系人存储。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring the personal contacts store on client computers
ms:assetid: ec69a6cb-07f2-4057-9544-55035f83eeae
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721922(v=OCS.15)
ms:contentKeyID: 49733857
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c1040b3eb9aa38e3e0c537d690b9292ab8f1ead2
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48544188"
---
# <a name="configuring-the-personal-contacts-store-on-client-computers-for-lync-server-2013"></a>在客户端计算机上为 Lync Server 2013 配置个人联系人存储

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2014-02-05_

如果要集成 Microsoft Lync Server 2013 和 Microsoft Exchange Server 2013，建议您在运行 Microsoft Lync 2010 的任何客户端计算机上配置个人联系人存储。 特别是，应将 Lync 配置为将 Exchange 用作个人联系人存储，同时确保用户无法覆盖该决定。 这可以通过在每个客户端计算机上创建和配置注册表值来完成。

请注意，运行 Lync 2013 的计算机上不需要执行此项。

要在单个计算机上配置此值，请完成下列过程：

1.  在客户端计算机上，单击 " **开始** "，然后单击 " **运行**"。

2.  在 " **运行** " 对话框中，键入 "regedit"，然后按 enter。

3.  在注册表编辑器中，展开 " **HKEY \_ 本地 \_ 计算机**"，展开 " **软件**"，展开 " **策略**"，展开 " **Microsoft**"，然后展开 " **Communicator**"。

4.  右键单击 " **Communicator**"，指向 " **新建**"，然后单击 " **DWORD (32-位) 值**"。

5.  创建新值后，键入 **PersonalContactStoreOverride** ，然后按 enter 以重命名该值。

6.  验证将 PersonalContactStoreOverride 的值设置为 0，然后关闭注册表编辑器。

如果您要在多台计算机上执行相同的更改，则可以通过创建自定义组策略对象执行此操作。 有关详细信息，请参阅中的组策略文档 [https://go.microsoft.com/fwlink/p/?LinkId=268543](https://go.microsoft.com/fwlink/p/?linkid=268543) 。

</div>

<span> </span>

</div>

</div>

</div>


---
title: Lync Server 2013：删除位置策略
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deleting a location policy
ms:assetid: 8ca9ba10-f45f-435a-b39c-519d251e9085
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688125(v=OCS.15)
ms:contentKeyID: 49733724
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2ea7f585e42164c8387853c7525cd0478eeb4db4
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763244"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deleting-a-location-policy-in-lync-server-2013"></a>在 Lync Server 2013 中删除位置策略

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2012-10-10_

在 Lync Server 2013 中，你可以使用位置策略应用与增强的9-1-1 （E9）功能以及用户或联系人的位置设置相关的设置。 位置策略确定用户是否启用了 E9-1，如果是紧急呼叫，该行为是什么。 例如，您可以使用位置策略定义哪个号码构成紧急呼叫（例如，美国911）、是否应自动通知企业安全以及如何路由呼叫。

你可以从 Lync Server 2013 控制面板中的 "**网络配置**" 组配置位置策略。 从 Lync Server 控制面板，您可以查看、创建、修改或删除位置策略。 使用以下过程删除位置策略。 有关创建或修改位置策略的详细信息，请参阅[在 Lync Server 2013 中创建或修改位置策略](lync-server-2013-creating-or-modifying-a-location-policy.md)。

<div>

## <a name="to-delete-a-location-policy"></a>删除位置策略

1.  使用 RTCUniversalServerAdmins 组成员（或具有同等用户权限）的用户帐户，或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。

2.  打开一个浏览器窗口，然后输入 "管理员" URL 以打开 Lync Server "控制面板"。 有关可用于启动 Lync Server "控制面板" 的不同方法的详细信息，请参阅[打开 Lync server 2013 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左侧导航栏中，单击 "**网络配置**"，然后单击 "**位置策略**"。

4.  在 "**位置策略**" 页面上，选择要删除的位置策略。
    
    <div>
    

    > [!NOTE]  
    > 您可以一次删除多个位置策略。 若要执行此操作，请在按住 CTRL 键的同时按 CTRL 并选择多个策略。 或者，若要选择所有策略，请单击 "<STRONG>编辑</STRONG>" 菜单上的 "<STRONG>全选</STRONG>"。

    
    </div>

5.  在 "**编辑**" 菜单上，单击 "**删除**"。

6.  单击“**确定**”。
    
    <div>
    

    > [!IMPORTANT]  
    > 您不能删除全局位置策略。 如果你尝试删除全局策略，你将收到一条警告消息，并且该策略将重置为其默认值。

    
    </div>

</div>

<div>

## <a name="see-also"></a>另请参阅


[在 Lync Server 2013 中创建或修改位置策略](lync-server-2013-creating-or-modifying-a-location-policy.md)  
[在 Lync Server 2013 中查看位置策略信息](lync-server-2013-viewing-location-policy-information.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


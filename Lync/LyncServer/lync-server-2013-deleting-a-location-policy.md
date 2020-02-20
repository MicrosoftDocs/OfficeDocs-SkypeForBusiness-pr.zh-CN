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
ms.openlocfilehash: be70f56f2a33ef92769a129e8fd9f84fe467c93e
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42146175"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deleting-a-location-policy-in-lync-server-2013"></a>在 Lync Server 2013 中删除位置策略

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-10-10_

在 Lync Server 2013 中，可以使用位置策略将与增强的9-1-1 （E9-1）功能相关的设置应用于用户或联系人的位置设置。 位置策略可确定用户是否启用了 E9-1-1，以及在启用了该服务时紧急呼叫的行为。 例如，您可以使用位置策略定义哪些数字构成紧急呼叫（例如，美国的 911）、是否应自动通知企业安全人员以及应如何路由该呼叫。

您可以在 Lync Server 2013 控制面板中的 "**网络配置**" 组中配置位置策略。 从 Lync Server 控制面板中，您可以查看、创建、修改或删除位置策略。 使用以下过程删除位置策略。 有关创建或修改位置策略的详细信息，请参阅[在 Lync Server 2013 中创建或修改位置策略](lync-server-2013-creating-or-modifying-a-location-policy.md)。

<div>

## <a name="to-delete-a-location-policy"></a>删除位置策略

1.  从作为 RTCUniversalServerAdmins 组成员的用户帐户（或具有等效的用户权限）或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。

2.  打开浏览器窗口，然后输入管理员 URL 以打开 "Lync Server 控制面板"。 有关可用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅[Open Lync server 2013 "管理工具](lync-server-2013-open-lync-server-administrative-tools.md)"。

3.  在左侧导航栏中，单击“网络配置”****，然后单击“位置策略”****。

4.  在“位置策略”**** 页上，选择要删除的位置策略。
    
    <div>
    

    > [!NOTE]  
    > 可一次性删除多个位置策略。要执行此操作，请按住 Ctrl 键，同时选择多个策略。或者，要选中全部策略，请单击“编辑”<STRONG></STRONG>菜单中的“全选”<STRONG></STRONG>。

    
    </div>

5.  在“编辑”**** 菜单上，单击“删除”****。

6.  单击“确定”****。
    
    <div>
    

    > [!IMPORTANT]  
    > 无法删除“全局”位置策略。如果尝试删除“全局”策略，您将收到一条警告消息，而该策略将重置为其默认值。

    
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


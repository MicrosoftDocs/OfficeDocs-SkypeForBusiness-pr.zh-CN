---
title: Lync Server 2013：向用户分配组呼叫装货号码
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Assign Group Call Pickup numbers to users
ms:assetid: b8e79275-8e7e-4799-b908-f34f61df22f0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945647(v=OCS.15)
ms:contentKeyID: 51541508
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8b437b9da1abaa62d34a177c0188396c30bf7a3e
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42203348"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="assign-group-call-pickup-numbers-to-users-in-lync-server-2013"></a>在 Lync Server 2013 中向用户分配组呼叫装货号码

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2013-01-30_

将组呼叫应答组号码添加到呼叫寄存通道表后，可以将组分配给用户。 使用辅助扩展功能激活（SEFAUtil）资源工具包工具向用户分配呼叫应答组。

<div>


> [!NOTE]  
> 在混合部署中，不要向驻留在线的用户分配组呼叫应答组。 联机托管的用户不能参与组内呼叫应答。 也就是说，其他用户无法应答其呼叫，也不能应答其他用户的呼叫。



</div>

<div>

## <a name="to-assign-a-group-call-pickup-group-to-a-user"></a>将组呼叫装货组分配给用户

1.  使用管理员权限登录到安装了 SEFAUtil 工具的计算机。

2.  在命令行中运行：
    
        SEFAUtil.exe sip:<sip address of user> /server:<pool FQDN> /enablegrouppickup:<group number>
    
    例如：
    
        SEFAUtil.exe katarina@contoso.com /server:pool01.contoso.com /enablegrouppickup:199

</div>

<div>

## <a name="see-also"></a>请参阅


[在 Lync Server 2013 中为用户启用组呼叫装货](lync-server-2013-enable-group-call-pickup-for-users.md)  
[在 Lync Server 2013 中为用户禁用组呼叫装货](lync-server-2013-disable-group-call-pickup-for-users.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


---
title: Lync Server 2013：为用户启用组呼叫应答并分配组号码
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enable Group Call Pickup for users and assign a group number
ms:assetid: c33bb6c2-d43b-4fb6-a0fa-6d82a7b09abe
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945650(v=OCS.15)
ms:contentKeyID: 51541517
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: edba55fcfdedc04eb2d8a8356c3d295c381d7c70
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48528739"
---
# <a name="enable-group-call-pickup-for-users-in-lync-server-2013-and-assign-a-group-number"></a>为 Lync Server 2013 中的用户启用组内呼叫应答并分配组号码

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2013-01-30_

将呼叫应答组号码添加到呼叫寄存通道表之后，将组号码分配给用户并为其启用组呼叫应答。 使用辅助扩展功能激活 (SEFAUtil) 资源工具包工具分配组号码并启用组呼叫应答。

<div>


> [!NOTE]  
> 在混合部署中，不要向驻留在线的用户分配组呼叫应答组。 联机托管的用户不能参与组内呼叫应答。 也就是说，其他用户无法应答其呼叫，也不能应答其他用户的呼叫。



</div>

<div>

## <a name="to-assign-a-group-number-and-enable-group-call-pickup-for-a-user"></a>为用户分配组号码并启用组呼叫应答

1.  使用管理员权限登录到安装了 SEFAUtil 工具的计算机。

2.  在命令行中运行：
    
        SEFAUtil.exe sip:<sip address of user> /server:<pool FQDN> /enablegrouppickup:<group number>
    
    例如，若要将组号199分配给用户，请执行以下操作：
    
        SEFAUtil.exe katarina@contoso.com /server:pool01.contoso.com /enablegrouppickup:199 

</div>

<div>

## <a name="see-also"></a>另请参阅


[在 Lync Server 2013 中为用户禁用组呼叫装货](lync-server-2013-disable-group-call-pickup-for-users.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


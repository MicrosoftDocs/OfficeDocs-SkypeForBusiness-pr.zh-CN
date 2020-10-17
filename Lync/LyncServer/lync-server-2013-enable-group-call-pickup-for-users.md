---
title: Lync Server 2013：为用户启用组呼叫装货
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enable Group Call Pickup for users
ms:assetid: 20ec5f41-6ba2-4156-82ed-b91d05b62a6d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945620(v=OCS.15)
ms:contentKeyID: 51541457
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 89d512eea147039a5766193f9ec2a20cf45caaa0
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48528719"
---
# <a name="enable-group-call-pickup-for-users-in-lync-server-2013"></a>在 Lync Server 2013 中为用户启用组呼叫装货

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2013-01-30_

使用 SEFAUtil 资源工具包工具为用户启用组呼叫挑选。 必须在呼叫寄存通道表中为用户分配一个类型为 "GroupPickup" 的组编号，以便启用组呼叫装货。 在运行 SEFAUtil.exe 时，可以通过使用/enablegrouppickup 参数来分配呼叫应答组号码并同时启用组呼叫应答。

<div>

## <a name="to-enable-group-call-pickup-for-a-user"></a>为用户启用组呼叫应答

1.  使用管理员权限登录到安装了 SEFAUtil 工具的计算机。

2.  在命令行中运行：
    
        SEFAUtil.exe sip:<sip address of user> /server:<pool FQDN> /enablegrouppickup:<group number>
    
    例如：
    
        SEFAUtil.exe katarina@contoso.com /server:pool01.contoso.com /enablegrouppickup:199

</div>

<div>

## <a name="see-also"></a>请参阅


[在 Lync Server 2013 中向用户分配组呼叫装货号码](lync-server-2013-assign-group-call-pickup-numbers-to-users.md)  
[在 Lync Server 2013 中为用户禁用组呼叫装货](lync-server-2013-disable-group-call-pickup-for-users.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


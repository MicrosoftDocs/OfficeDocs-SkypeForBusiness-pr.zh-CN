---
title: Lync Server 2013：删除组呼叫装货号码范围
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delete a Group Call Pickup number range
ms:assetid: 521891f3-7a5d-45de-92dc-d57025453159
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945629(v=OCS.15)
ms:contentKeyID: 51541475
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 179bde8b8e23cc21fb95fa93e3c6cbeb7f381630
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/14/2020
ms.locfileid: "42006328"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="delete-a-group-call-pickup-number-range-in-lync-server-2013"></a>在 Lync Server 2013 中删除组呼叫装货号码范围

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2013-01-30_

使用以下过程可删除组内呼叫装货号码范围。

<div>

## <a name="to-delete-a-call-pickup-group-number-range"></a>删除呼叫应答组号码范围

1.  登录到安装了 Lync Server 命令行管理程序的计算机，作为 RTCUniversalServerAdmins 组的成员或具有必要的用户权限（如在[Lync Server 2013 中委派安装权限](lync-server-2013-delegate-setup-permissions.md)中所述）。

2.  启动 Lync Server 命令行管理程序：依次单击“开始”****、“所有程序”****、“Microsoft Lync Server 2013”**** 和“Lync Server 命令行管理程序”****。

3.  在命令行中键入：
    
        Remove-CsCallParkOrbit -Identity "<group number range name>" 
    
    例如：
    
        Remove-CsCallParkOrbit -Identity "Redmond call pickup"
    
    <div>
    

    > [!NOTE]  
    > 有关更多选项的详细信息，请参阅<A href="https://docs.microsoft.com/powershell/module/skype/Remove-CsCallParkOrbit">CsCallParkOrbit</A>。

    
    </div>

</div>

<div>

## <a name="see-also"></a>另请参阅


[在 Lync Server 2013 中创建或修改呼叫寄存通道范围](lync-server-2013-create-or-modify-a-call-park-orbit-range.md)  


[CsCallParkOrbit](https://docs.microsoft.com/powershell/module/skype/Remove-CsCallParkOrbit)  
[CsCallParkOrbit](https://docs.microsoft.com/powershell/module/skype/Get-CsCallParkOrbit)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


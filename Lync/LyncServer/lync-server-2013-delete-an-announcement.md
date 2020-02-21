---
title: Lync Server 2013：删除通知
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delete an announcement
ms:assetid: 26ea7149-4470-4c22-9bab-8a4065aca44e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687998(v=OCS.15)
ms:contentKeyID: 49733588
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3e907a8f0c31555763f6563622c4f3916e4a54ae
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42202768"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="delete-an-announcement-in-lync-server-2013"></a>在 Lync Server 2013 中删除通知

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-11-01_

使用以下过程可删除用于呼叫未分配号码的通知。

<div>

## <a name="to-delete-an-announcement"></a>删除通知

1.  登录到安装了 Lync Server 命令行管理程序的计算机，作为 RTCUniversalServerAdmins 组的成员或具有必要的用户权限（如在[Lync Server 2013 中委派安装权限](lync-server-2013-delegate-setup-permissions.md)中所述）。

2.  启动 Lync Server 命令行管理程序：依次单击“开始”****、“所有程序”****、“Microsoft Lync Server 2013”**** 和“Lync Server 命令行管理程序”****。

3.  列出组织中的所有通知。在命令行运行：
    
        Get-CsAnnouncement

4.  在结果列表中，找到要删除的通知，并复制 GUID。然后，在命令行运行：
    
        Remove-CsAnnouncement -Identity "<Service:service ID/guid>" 
    
    例如：
    
        Remove-CsAnnouncement -Identity "ApplicationServer:Redmond.contoso.com/1951f734-c80f-4fb2-965d-51807c792b90"
    
    <div>
    

    > [!NOTE]  
    > 有关更多选项的详细信息，请参阅<A href="https://docs.microsoft.com/powershell/module/skype/Get-CsAnnouncement">CsAnnouncement</A>和<A href="https://docs.microsoft.com/powershell/module/skype/Remove-CsAnnouncement">Remove-CsAnnouncement</A>。

    
    </div>

</div>

<div>

## <a name="see-also"></a>另请参阅


[在 Lync Server 2013 中创建通知](lync-server-2013-create-an-announcement.md)  


[CsAnnouncement](https://docs.microsoft.com/powershell/module/skype/Remove-CsAnnouncement)  
[CsAnnouncement](https://docs.microsoft.com/powershell/module/skype/Get-CsAnnouncement)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


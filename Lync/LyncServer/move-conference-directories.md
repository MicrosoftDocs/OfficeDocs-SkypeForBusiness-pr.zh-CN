---
title: 移动会议目录
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Move conference directories
ms:assetid: 71a28308-1f3b-4717-b535-2f4bfe3499a1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204994(v=OCS.15)
ms:contentKeyID: 48184463
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f2f4897df817c4392779169c535199579ac04d9e
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42034648"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="move-conference-directories"></a>移动会议目录

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-10-04_

在取消池的授权之前，您需要为 Office 通信服务器 2007 R2 池中的每个会议目录执行以下过程。

<div>

## <a name="to-move-a-conference-directory-to-lync-server-2013"></a>将会议目录移动到 Lync Server 2013

1.  打开 Lync Server 命令行管理程序。

2.  若要获取组织中会议目录的标识，请运行以下命令：
    
        Get-CsConferenceDirectory
    
    因为此 cmdlet 返回组织中的所有会议目录，所以您可能希望将结果限制为仅要停用的池。例如，如果要停用具有完全限定域名 (FQDN) pool01.contoso.net 的池：
    
        Get-CsConferenceDirectory | Where-Object {$_.ServiceID -match "pool01.contoso.net"}
    
    此 cmdlet 返回其中服务 ID 包含 FQDN pool01.contoso.net 的所有会议目录。

3.  若要移动会议目录，请对池中的每个会议目录运行以下命令：
    
        Move-CsConferenceDirectory -Identity <Numeric identity of conference directory> -TargetPool <FQDN of pool where ownership is to be transitioned>
    
    例如：
    
        Move-CsConferenceDirectory -Identity 3 -TargetPool pool02.contoso.net

<div>


> [!NOTE]  
> 您可能会遇到以下错误： Lync Server 命令行管理程序需要从 Active Directory 中更新一组权限导致的错误。 若要解决此错误，请关闭当前窗口并打开新的 Lync Server 命令行管理程序，然后再次运行该命令。



</div>

![移动-New-csconferencedirectory 错误输出](images/JJ204994.4748b9e8-9651-4527-afe1-cbdc6d5ce4a8(OCS.15).jpg "移动-New-csconferencedirectory 错误输出")

</div>

</div>

<span> </span>

</div>

</div>

</div>


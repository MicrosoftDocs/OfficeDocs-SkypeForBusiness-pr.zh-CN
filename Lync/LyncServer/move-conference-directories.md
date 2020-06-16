---
title: 移动会议目录
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Move conference directories
ms:assetid: 71a28308-1f3b-4717-b535-2f4bfe3499a1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204994(v=OCS.15)
ms:contentKeyID: 48184463
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2de2b588d880600a4a7d8365f20423d3faf2653e
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/16/2020
ms.locfileid: "44756621"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

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
    
    Because this cmdlet returns all the conference directories in your organization, you may want to limit the results to only the pool you want to decommission. For example, if you want to decommission a pool with the fully qualified domain name (FQDN) pool01.contoso.net:
    
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


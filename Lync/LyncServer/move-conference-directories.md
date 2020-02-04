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
ms.openlocfilehash: 1ae7633d638571410c93cfefe87d9e333731a4bb
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41727582"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="move-conference-directories"></a>移动会议目录

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2012-10-04_

在取消池之前，你需要针对 Office 通信服务器 2007 R2 池中的每个会议目录执行以下过程。

<div>

## <a name="to-move-a-conference-directory-to-lync-server-2013"></a>将会议目录移动到 Lync Server 2013

1.  打开 Lync Server 命令行管理程序。

2.  若要获取组织中的会议目录的标识，请运行以下命令：
    
        Get-CsConferenceDirectory
    
    由于此 cmdlet 返回你的组织中的所有会议目录，你可能希望将结果限制为仅限于你希望解除授权的池。 例如，如果要使用完全限定的域名（FQDN） pool01.contoso.net 解除池的授权，请执行以下操作：
    
        Get-CsConferenceDirectory | Where-Object {$_.ServiceID -match "pool01.contoso.net"}
    
    此 cmdlet 返回服务 ID 包含 FQDN pool01.contoso.net 的所有会议目录。

3.  若要移动会议目录，请对池中的每个会议目录运行以下操作：
    
        Move-CsConferenceDirectory -Identity <Numeric identity of conference directory> -TargetPool <FQDN of pool where ownership is to be transitioned>
    
    例如：
    
        Move-CsConferenceDirectory -Identity 3 -TargetPool pool02.contoso.net

<div>


> [!NOTE]  
> 你可能会遇到如下所示的错误，该错误由 Lync Server 管理外壳要求从 Active Directory 中更新的权限集导致的。 若要解决此错误，请关闭当前窗口并打开新的 Lync Server 命令行管理程序，然后再次运行该命令。



</div>

![移动-CsConferenceDirectory 错误输出](images/JJ204994.4748b9e8-9651-4527-afe1-cbdc6d5ce4a8(OCS.15).jpg "移动-CsConferenceDirectory 错误输出")

</div>

</div>

<span> </span>

</div>

</div>

</div>


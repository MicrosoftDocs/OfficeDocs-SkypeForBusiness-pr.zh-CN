---
title: Lync Server 2013：删除公共的区域电话联系人对象
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delete a common area phone Contact object
ms:assetid: f4c139dc-f07c-4c75-9345-e291aea41173
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994087(v=OCS.15)
ms:contentKeyID: 51803999
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2a3088150c882a5ebca99318f7c85ddbddddc333
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41741012"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="delete-a-common-area-phone-contact-object-in-lync-server-2013"></a>在 Lync Server 2013 中删除公用的 "区域电话联系人" 对象

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2013-02-20_

您可能希望删除与普通的区域电话相关联的联系人对象。 例如，如果您从员工的工作人员那里删除手机，则无需具有与该电话关联的 contact 对象。 **CsCommonAreaPhone** cmdlet 提供了一种删除公共区域电话帐户的方法。 当你运行此 cmdlet 时，将从**CsCommonAreaPhone**返回的常用区域电话列表中删除手机。 此外，还会从 Active Directory 域服务中删除与该电话相关联的联系人对象。

使用 "**删除-CsCommonAreaPhone** " 删除一个通用区域电话或所有具有公共元素（如显示名称或国家/地区代码）的通用区域电话。 你可以从 Lync Server 2013 命令行管理程序或 Windows PowerShell 的远程会话运行此 cmdlet。 有关使用远程 Windows PowerShell 连接到 Lync Server 的详细信息，请参阅 Lync Server Windows PowerShell 博客文章 "快速入门：使用远程 PowerShell 管理 Microsoft Lync Server 2010" [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)。

<div>


<div>

## <a name="removing-a-specified-common-area-phone"></a>删除指定的公共区域电话

  - 以下命令将删除带有 SIP 地址 sip:mainlobby@litwareinc.com 的公共区域电话：
    
        Remove-CsCommonAreaPhone -Identity "sip:mainlobby@litwareinc.com"

</div>

<div>

## <a name="removing-common-area-phones-based-on-their-display-name"></a>根据其显示名称删除公共的区域电话

  - 此命令将删除显示名称包括字符串值 "建筑物 14" 的所有公共区域电话：
    
        Get-CsCommonAreaPhone | Where-Object {$_.DisplayName -match "Building 14"} | Remove-CsCommonAreaPhone

</div>

<div>

## <a name="removing-common-area-phones-based-on-their-country-and-area-codes"></a>根据国家和地区代码删除公共的区域电话

  - 此命令将删除美国的所有通用区域电话（国家码1）和区号425：
    
        Get-CsCommonAreaPhone | Where-Object {$_.LineUri  -match "^tel:\+1425"} | Remove-CsCommonAreaPhone

</div>

有关详细信息，请参阅[CsCommonAreaPhone](https://docs.microsoft.com/powershell/module/skype/Remove-CsCommonAreaPhone) Cmdlet 的帮助主题。

</div>

<div>

## <a name="see-also"></a>另请参阅


[Get-CsCommonAreaPhone](https://docs.microsoft.com/powershell/module/skype/Get-CsCommonAreaPhone)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


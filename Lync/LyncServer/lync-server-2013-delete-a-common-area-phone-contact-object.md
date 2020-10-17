---
title: Lync Server 2013：删除公用区域电话联系人对象
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
ms.openlocfilehash: 38126f54e02738b1f48b42022a9061055e271d18
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48525719"
---
# <a name="delete-a-common-area-phone-contact-object-in-lync-server-2013"></a>在 Lync Server 2013 中删除公用区域电话联系人对象

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2013-02-20_

您可能想要删除与公用区域电话相关联的 contact 对象。 例如，如果您从员工的工作方式中删除了电话，则无需具有与该电话关联的 contact 对象。 **CsCommonAreaPhone** cmdlet 提供了一种删除公用区域电话帐户的方法。 运行此 cmdlet 时，将从 **CsCommonAreaPhone**返回的常见区域电话列表中删除手机。 此外，还会从 Active Directory 域服务中删除与该手机相关联的 contact 对象。

使用 **CsCommonAreaPhone** 删除包含通用元素（如显示名称、国家/地区代码和区号）的一个公用区域电话或所有公用区域电话。 您可以从 Lync Server 2013 命令行管理程序或从 Windows PowerShell 的远程会话中运行此 cmdlet。 有关使用远程 Windows PowerShell 连接到 Lync Server 的详细信息，请参阅在上的 Lync Server Windows PowerShell 博客文章 "快速入门：使用远程 PowerShell 管理 Microsoft Lync Server 2010" [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) 。

<div>


<div>

## <a name="removing-a-specified-common-area-phone"></a>删除指定的公共区域电话

  - 以下命令将删除带有 SIP 地址 sip:mainlobby@litwareinc.com 的公用区域电话：
    
        Remove-CsCommonAreaPhone -Identity "sip:mainlobby@litwareinc.com"

</div>

<div>

## <a name="removing-common-area-phones-based-on-their-display-name"></a>根据其显示名称删除公用区域电话

  - 此命令将删除显示名称包含字符串值 "建筑物 14" 的所有公用区域电话：
    
        Get-CsCommonAreaPhone | Where-Object {$_.DisplayName -match "Building 14"} | Remove-CsCommonAreaPhone

</div>

<div>

## <a name="removing-common-area-phones-based-on-their-country-and-area-codes"></a>根据国家/地区代码和区号删除公用区域电话

  - 此命令将删除美国的所有常见地区电话 (国家/地区代码 1) 和区号425：
    
        Get-CsCommonAreaPhone | Where-Object {$_.LineUri  -match "^tel:\+1425"} | Remove-CsCommonAreaPhone

</div>

有关详细信息，请参阅 [CsCommonAreaPhone](https://docs.microsoft.com/powershell/module/skype/Remove-CsCommonAreaPhone) Cmdlet 的帮助主题。

</div>

<div>

## <a name="see-also"></a>另请参阅


[CsCommonAreaPhone](https://docs.microsoft.com/powershell/module/skype/Get-CsCommonAreaPhone)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


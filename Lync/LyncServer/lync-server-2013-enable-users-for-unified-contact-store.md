---
title: Lync Server 2013：为用户启用统一联系人存储
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Enable users for unified contact store
ms:assetid: 7b46a01f-beb5-4a33-adb0-35f0502b168d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205024(v=OCS.15)
ms:contentKeyID: 48184599
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b1ece699d8c5b43e09323708c075687bfe81146e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34830266"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enable-users-for-unified-contact-store-in-lync-server-2013"></a>在 Lync Server 2013 中为用户启用统一联系人存储

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2012-10-07_

当你部署 Lync Server 2013 并发布拓扑时, 默认情况下为所有用户启用 "统一联系人存储"。 部署 Lync Server 2013 后, 无需执行任何其他操作即可启用统一联系人存储。 但是，可以使用 **Set-CsUserServicesPolicy** cmdlet 自定义哪些用户可以使用统一联系人存储。 可以全局启用此功能，或者按站点、租户、个人或个人组启用此功能。

<div>

## <a name="to-enable-users-for-unified-contact-store"></a>为用户启用统一联系人存储

1.  启动 Lync Server 命令行管理程序: 依次单击 "**开始**"、"**所有程序**"、" **Microsoft Lync server 2013**", 然后单击 " **Lync server Management shell**"。

2.  请执行以下任一操作：
    
      - 若要为所有 Lync Server 用户全局启用统一联系人存储, 请在命令行中键入:
        
            Set-CsUserServicesPolicy -Identity global -UcsAllowed $True
    
      - 若要为特定网站上的用户启用统一联系人存储区, 请在命令行键入:
        
            New-CsUserServicesPolicy -Identity site:<site name> -UcsAllowed $True
        
        例如：
        
            New-CsUserServicesPolicy -Identity site:Redmond -UcsAllowed $True
    
      - 若要通过租户启用统一联系人存储, 请在命令行中键入:
        
            Set-CsUserServicesPolicy -Tenant <tenantId> -UcsAllowed $True
        
        例如：
        
            Set-CsUserServicesPolicy -Tenant "38aad667-af54-4397-aaa7-e94c79ec2308" -UcsAllowed $True
    
      - 若要为特定用户启用统一联系人存储, 请在命令行键入:
        
            New-CsUserServicesPolicy -Identity "<policy name>" -UcsAllowed $True
            Grant-CsUserServicesPolicy -Identity "<user display name>" -PolicyName <"policy name">
        
        <div>
        

        > [!NOTE]  
        > 还可以使用用户别名或 SIP URI 代替用户显示名称。

        
        </div>
        
        例如：
        
            New-CsUserServicesPolicy -Identity "UCS Enabled Users" -UcsAllowed $True
            Grant-CsUserServicesPolicy -Identity "Ken Myer" -PolicyName "UCS Enabled Users"
        
        <div>
        

        > [!NOTE]  
        > 在上面的示例中，第一个命令创建一个名为“<EM>启用 UCS 的用户</EM>”的新每用户策略，并将 UcsAllowed 标记设置为 True。第二个命令将该策略分配给显示名称为 Ken Myer 的用户，这意味着现在已为 Ken Myer 启用统一的联系人存储库。

        
        </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>


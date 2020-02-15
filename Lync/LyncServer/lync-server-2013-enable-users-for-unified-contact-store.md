---
title: Lync Server 2013：为用户启用统一联系人存储
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enable users for unified contact store
ms:assetid: 7b46a01f-beb5-4a33-adb0-35f0502b168d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205024(v=OCS.15)
ms:contentKeyID: 48184599
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b99fd96b16d19305ea5bb63ea9f84096ef6117c7
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42046645"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enable-users-for-unified-contact-store-in-lync-server-2013"></a>在 Lync Server 2013 中为用户启用统一联系人存储

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-10-07_

当您部署 Lync Server 2013 并发布拓扑时，默认情况下会为所有用户启用统一联系人存储。 部署 Lync Server 2013 后，无需执行任何其他操作即可启用统一的联系人存储。 但是，可以使用 **Set-CsUserServicesPolicy** cmdlet 自定义哪些用户可以使用统一的联系人存储库。 可以全局启用此功能，或者按站点、租户、个人或个人组启用此功能。

<div>

## <a name="to-enable-users-for-unified-contact-store"></a>为用户启用统一的联系人存储库

1.  启动 Lync Server 命令行管理程序：依次单击“开始”****、“所有程序”****、“Microsoft Lync Server 2013”**** 和“Lync Server 命令行管理程序”****。

2.  执行下列任意操作：
    
      - 若要为所有 Lync Server 用户全局启用统一联系人存储，请在命令行中键入：
        
            Set-CsUserServicesPolicy -Identity global -UcsAllowed $True
    
      - 若要为特定站点的用户启用统一的联系人存储库，请在命令行中键入：
        
            New-CsUserServicesPolicy -Identity site:<site name> -UcsAllowed $True
        
        例如：
        
            New-CsUserServicesPolicy -Identity site:Redmond -UcsAllowed $True
    
      - 若要按租户启用统一的联系人存储库，请在命令行中键入：
        
            Set-CsUserServicesPolicy -Tenant <tenantId> -UcsAllowed $True
        
        例如：
        
            Set-CsUserServicesPolicy -Tenant "38aad667-af54-4397-aaa7-e94c79ec2308" -UcsAllowed $True
    
      - 若要为特定用户启用统一的联系人存储库，请在命令行中键入：
        
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
        > 在上面的示例中，第一个命令创建一个名为“启用 UCS 的用户”<EM></EM>的新每用户策略，并将 UcsAllowed 标记设置为 True。第二个命令将该策略分配给显示名称为 Ken Myer 的用户，这意味着现在已为 Ken Myer 启用统一的联系人存储库。

        
        </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>


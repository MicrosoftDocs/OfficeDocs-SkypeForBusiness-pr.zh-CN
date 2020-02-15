---
title: Lync Server 2013：回滚已迁移用户
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Roll back migrated users
ms:assetid: bfabaf0b-9a42-4057-b729-a7ab9eee8c72
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205224(v=OCS.15)
ms:contentKeyID: 48185286
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7398e69e5a02924025d63fc48096244d67c49aeb
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42051466"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="roll-back-migrated-users-in-lync-server-2013"></a>在 Lync Server 2013 中回滚已迁移的用户

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-10-07_

如果需要回滚统一联系人存储功能，请仅在将用户移回 Exchange 2010 或 Lync Server 2010 时才回滚联系人。 要进行回滚，请针对用户禁用该策略，然后运行 **Invoke-CsUcsRollback** cmdlet。 只是单独运行 **Invoke-CsUcsRollback** 并不足以确保永久回滚，因为如果未禁用该策略，统一联系人存储迁移将再次发生。 例如，如果由于 Exchange 2013 回滚到 Exchange 2010 而回滚用户，然后将用户的邮箱移动到 Exchange 2013，则在回滚之后的七天内将再次启动统一联系人存储迁移（只要是统一联系人存储）。在用户服务策略中仍为用户启用。

<div>


> [!IMPORTANT]  
> 在下列情况下，Get-csuser cmdlet 会自动<STRONG>将</STRONG>用户的联系人存储从 Exchange 2013 回滚到 Lync Server 2013： 
> <UL>
> <LI>
> <P>将用户从 Lync Server 2013 移动到 Lync Server 2010 时。</P>
> <LI>
> <P>当用户迁移到跨界时，例如，在本地将用户从 Lync Online 移到 Lync Server 2013 时，或者相反。</P></LI></UL>



</div>

<div>


> [!IMPORTANT]  
> 如果统一联系人存储模式在导出和导入之间发生更改，则从备份数据库中导入统一联系人存储数据，可能导致统一联系人存储数据和用户数据发生损坏。例如： 
> <UL>
> <LI>
> <P>如果在将用户的联系人迁移到 Exchange 2013 之前导出联系人列表，然后在迁移后导入相同的数据，则统一联系人存储数据和联系人列表将损坏。</P>
> <LI>
> <P>如果你在将用户迁移到 Exchange 2013 之后导出 userdata，请回滚迁移，然后，由于某些原因，在迁移后导入数据，统一联系人存储数据和联系人列表将损坏。</P></LI></UL>



</div>

<div>


> [!IMPORTANT]  
> 在将 Exchange 邮箱从 Exchange 2013 移动到 Exchange 2010 之前，Exchange 管理员必须确保 Lync server 管理员首先将 Lync Server 用户联系人从 Exchange 2013 回滚到 Lync Server。 若要将统一联系人存储联系人回滚到 Lync Server，请参阅本节后面的过程 "将统一联系人存储联系人从 Exchange 2013 回滚到 Lync Server 2013"。



</div>

以下过程介绍如何回滚用户联系人。 如果使用**get-csuser** Cmdlet 在 lync server 2013 和 lync server 2010 之间移动用户，则可以跳过这些步骤，因为**get-csuser** cmdlet 会在将用户从 Lync Server 2013 移动到 lync server 2010 时自动回退 unifed 联系人存储库。 **Get-csuser**不会禁用统一联系人存储策略，因此如果用户移回到 Lync Server 2013 中，则迁移到统一联系人存储将会重现。

<div>

## <a name="to-roll-back-user-contacts-from-lync-server-2013-to-lync-server-2010"></a>将 Lync Server 2013 中的用户联系人回退到 Lync Server 2010

1.  启动 Lync Server 命令行管理程序：依次单击“开始”****、“所有程序”****、“Microsoft Lync Server 2013”**** 和“Lync Server 命令行管理程序”****。

2.  为要回滚的用户禁用统一联系人存储，使其不会在回滚后重新迁移。（只有您想要确保用户将来不会迁移时，才执行此步骤。）要为单个用户禁用统一联系人存储，请在命令行中键入：
    
        Set-CsUserServicesPolicy -Identity "<policy name>" -UcsAllowed $False
    
    例如：
    
        Set-CsUserServicesPolicy -Identity "UCS Enabled Users" -UcsAllowed $False

3.  在将用户从 Lync Server 2013 移动到 Lync Server 2010 之前，请为 Lync Server 上的指定用户回滚好友列表。
    
    <div>
    

    > [!IMPORTANT]  
    > 如果省略此步骤，则将丢失“好友列表”。

    
    </div>

4.  回滚指定用户。在命令行中键入：
    
        Invoke-CsUcsRollback -Identity "<user display name>"
    
    例如：
    
        Invoke-CsUcsRollback -Identity "Ken Myer"
    
    <div>
    

    > [!IMPORTANT]  
    > 建议不要使用 –Force 选项来强制回滚。如果使用此选项，则将会丢失用户的联系人。

    
    </div>

</div>

<div>

## <a name="to-roll-back-unified-contact-store-contacts-from-exchange-2013-to-lync-server-2013"></a>将统一联系人存储联系人从 Exchange 2013 回退到 Lync Server 2013

1.  启动 Lync Server 命令行管理程序：依次单击“开始”****、“所有程序”****、“Microsoft Lync Server 2013”**** 和“Lync Server 命令行管理程序”****。

2.  为要回滚的用户禁用统一联系人存储，使其不会在回滚后重新迁移。要为单个用户禁用统一联系人存储，请在命令行中键入：
    
        Set-CsUserServicesPolicy -Identity "<policy name>" -UcsAllowed $False
    
    例如：
    
        Set-CsUserServicesPolicy -Identity "UCS Enabled Users" -UcsAllowed $False

3.  回滚指定用户。在命令行中键入：
    
        Invoke-CsUcsRollback -Identity "<user display name>"
    
    例如：
    
        Invoke-CsUcsRollback -Identity "Ken Myer"
    
    <div>
    

    > [!IMPORTANT]  
    > 必须先回滚 Lync Server 用户，然后再移动 Exchange 2013 邮箱。 在 Lync Server 回滚完成之前，阻止 Exchange 管理员回滚 Exchange。 建议不要使用 –Force 选项来强制回滚。 如果使用此选项，则将会丢失用户的联系人。

    
    </div>

4.  将用户回滚到 Lync Server 后，Exchange 管理员可以将 exchange 用户从 Exchange 2013 回退到 Exchange 2010。

</div>

</div>

<span> </span>

</div>

</div>

</div>


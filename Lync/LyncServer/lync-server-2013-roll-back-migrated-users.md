---
title: Lync Server 2013：回滚已迁移用户
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Roll back migrated users
ms:assetid: bfabaf0b-9a42-4057-b729-a7ab9eee8c72
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205224(v=OCS.15)
ms:contentKeyID: 48185286
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 57462cee6c4996f0beb51290f8382a1736d3e635
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34822438"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="roll-back-migrated-users-in-lync-server-2013"></a>在 Lync Server 2013 中回滚已迁移用户

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2012-10-07_

如果需要回滚 "统一联系人存储" 功能, 请仅在将用户移回 Exchange 2010 或 Lync Server 2010 时, 才返回联系人。 要进行回滚，请针对用户禁用该策略，然后运行 **Invoke-CsUcsRollback** cmdlet。 只是单独运行 **Invoke-CsUcsRollback** 并不足以确保永久回滚，因为如果未禁用该策略，统一联系人存储迁移将再次发生。 例如, 如果由于 Exchange 2013 回退到 Exchange 2010 而回滚用户, 然后将用户的邮箱移动到 Exchange 2013, 则在回滚后的七天内将再次启动统一联系人存储迁移, 只要有统一联系人存储在用户服务策略中仍为用户启用。

<div>


> [!IMPORTANT]  
> 在以下情况下, <STRONG>move-csuser</STRONG> cmdlet 会自动将用户的联系人存储从 Exchange 2013 回退到 Lync Server 2013: 
> <UL>
> <LI>
> <P>当用户从 Lync Server 2013 移动到 Lync Server 2010 时。</P>
> <LI>
> <P>当用户在本地迁移时, 例如当用户从 Lync Online 移动到本地 Lync Server 2013 时, 反之亦然。</P></LI></UL>



</div>

<div>


> [!IMPORTANT]  
> 如果统一联系人存储模式在导出和导入之间发生更改，则从备份数据库中导入统一联系人存储数据，可能导致统一联系人存储数据和用户数据发生损坏。例如： 
> <UL>
> <LI>
> <P>如果在将用户联系人迁移到 Exchange 2013 之前导出联系人列表, 然后在迁移后导入相同的数据, 则统一联系人存储数据和联系人列表将损坏。</P>
> <LI>
> <P>如果你在将用户迁移到 Exchange 2013 后导出了 userdata, 请回退迁移, 然后出于某些原因, 在迁移后导入数据, 统一联系人存储数据和联系人列表将损坏。</P></LI></UL>



</div>

<div>


> [!IMPORTANT]  
> 在将 Exchange 邮箱从 Exchange 2013 移动到 Exchange 2010 之前, Exchange 管理员必须确保 Lync server 管理员首先将 Lync Server 用户联系人从 Exchange 2013 回退到 Lync Server。 若要将统一联系人存储联系人回滚到 Lync Server, 请参阅本部分后面的过程 "将统一联系人存储源联系人从 Exchange 2013 回滚到 Lync Server 2013"。



</div>

以下过程介绍如何回滚用户联系人。 如果使用**move-csuser** Cmdlet 在 lync server 2013 和 Lync server 2010 之间移动用户, 则可以跳过这些步骤, 因为**move-csuser** cmdlet 会在将用户从 Lync Server 2013 移动到 lync 时自动回退 unifed 联系人存储服务器2010。 **Move-move-csuser**不会禁用 "统一联系人存储" 策略, 因此如果用户移回 Lync Server 2013, 则迁移到 "统一联系人存储" 将会重现。

<div>

## <a name="to-roll-back-user-contacts-from-lync-server-2013-to-lync-server-2010"></a>将 Lync Server 2013 中的用户联系人回退到 Lync Server 2010

1.  启动 Lync Server 命令行管理程序: 依次单击 "**开始**"、"**所有程序**"、" **Microsoft Lync server 2013**", 然后单击 " **Lync server Management shell**"。

2.  禁用 "统一联系人存储" 以使用户能够回滚, 以便它们在回滚后不会 remigrated。 (仅当您希望确保用户以后不再 remigrate 时, 才执行此步骤。)若要为单个用户禁用统一联系人存储, 请在命令行中键入:
    
        Set-CsUserServicesPolicy -Identity "<policy name>" -UcsAllowed $False
    
    例如：
    
        Set-CsUserServicesPolicy -Identity "UCS Enabled Users" -UcsAllowed $False

3.  将用户从 Lync Server 2013 移动到 Lync Server 2010 之前, 请回退 Lync Server 上指定用户的好友列表。
    
    <div>
    

    > [!IMPORTANT]  
    > 如果此步骤被忽略, 好友列表将丢失。

    
    </div>

4.  回滚指定的用户。 在命令行中键入：
    
        Invoke-CsUcsRollback -Identity "<user display name>"
    
    例如：
    
        Invoke-CsUcsRollback -Identity "Ken Myer"
    
    <div>
    

    > [!IMPORTANT]  
    > 我们不建议使用-Force 选项强制执行回退。 如果使用此选项, 用户的联系人将丢失。

    
    </div>

</div>

<div>

## <a name="to-roll-back-unified-contact-store-contacts-from-exchange-2013-to-lync-server-2013"></a>将来自 Exchange 2013 的统一联系人存储联系人回滚到 Lync Server 2013

1.  启动 Lync Server 命令行管理程序: 依次单击 "**开始**"、"**所有程序**"、" **Microsoft Lync server 2013**", 然后单击 " **Lync server Management shell**"。

2.  禁用 "统一联系人存储" 以使用户能够回滚, 以便它们在回滚后不会 remigrated。 若要为单个用户禁用统一联系人存储, 请在命令行中键入:
    
        Set-CsUserServicesPolicy -Identity "<policy name>" -UcsAllowed $False
    
    例如：
    
        Set-CsUserServicesPolicy -Identity "UCS Enabled Users" -UcsAllowed $False

3.  回滚指定的用户。 在命令行中键入：
    
        Invoke-CsUcsRollback -Identity "<user display name>"
    
    例如：
    
        Invoke-CsUcsRollback -Identity "Ken Myer"
    
    <div>
    

    > [!IMPORTANT]  
    > 必须先回滚 Lync 服务器用户, 然后再移动 Exchange 2013 邮箱。 在 Lync Server 回退完成之前, 阻止 Exchange 管理员回退 Exchange。 我们不建议使用-Force 选项强制执行回退。 如果使用此选项, 用户的联系人将丢失。

    
    </div>

4.  将用户回退到 Lync Server 后, Exchange 管理员可以将 exchange 用户从 Exchange 2013 回退到 Exchange 2010。

</div>

</div>

<span> </span>

</div>

</div>

</div>


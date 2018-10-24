---
title: Lync Server 2013：回滚已迁移用户
TOCTitle: 回滚已迁移用户
ms:assetid: bfabaf0b-9a42-4057-b729-a7ab9eee8c72
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ205224(v=OCS.15)
ms:contentKeyID: 49314114
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 在 Lync Server 2013 中回滚已迁移用户

 

_**上一次修改主题：** 2012-10-07_

如果您需要回滚统一联系人存储功能，则只有在将用户移回至 Exchange 2010 或 Lync Server 2010 时才能回滚联系人。要进行回滚，请针对用户禁用该策略，然后运行 **Invoke-CsUcsRollback** cmdlet。只是单独运行 **Invoke-CsUcsRollback** 并不足以确保永久回滚，因为如果未禁用该策略，统一联系人存储迁移将再次发生。例如，如果用户回滚是因 Exchange 2013 回滚到 Exchange 2010 产生的，且用户邮箱移动到 Exchange 2013，则只要统一联系人存储对于用户服务策略中的用户而言仍处于启用状态，统一联系人存储迁移就会回滚后的七天内再次发生。

> [!IMPORTANT]  
> 在以下情况下， <strong>Move-CsUser</strong> cmdlet 会将用户的联系人存储从 Exchange 2013 自动回滚到 Lync Server 2013：
> <ul>
> <li><p>当用户从 Lync Server 2013 移动到 Lync Server 2010 时。</p></li>
> <li><p>当用户交叉迁移时，如用户在内部从 Skype for Business Online 移动到 Lync Server 2013（反之亦然）时。</p></li>
> </ul>

> [!IMPORTANT]  
> 如果统一联系人存储模式在导出和导入之间发生更改，则从备份数据库中导入统一联系人存储数据，可能导致统一联系人存储数据和用户数据发生损坏。例如：
> <ul>
> <li><p>如果您在用户的联系人迁移到 Exchange 2013 之前导出联系人列表，然后在迁移之后再导入相同的数据，则统一联系人存储数据和联系人列表将发生损坏。</p></li>
> <li><p>如果您在将用户迁移到 Exchange 2013 之后导出用户数据，回滚迁移，然后由于某种原因在迁移之后再导入该数据，则统一联系人存储数据和联系人列表将发生损坏。</p></li>
> </ul>

> [!IMPORTANT]
> 在将 Exchange 邮箱从 Exchange 2013 移动到 Exchange 2010 之前， Exchange 管理员必须确保 Lync Server 管理员已先将 Lync Server 用户联系人从 Exchange 2013 回滚到 Lync Server。要将统一联系人存储联系人回滚到 Lync Server，请参阅本节后面的“将统一联系人存储联系人从 Exchange 2013 回滚到 Lync Server 2013”。


以下过程介绍如何回滚用户联系人。如果您使用 **Move-CsUser** cmdlet 在 Lync Server 2013 与 Lync Server 2010 之间移动用户，则可以跳过这些步骤，因为在 **Move-CsUser** cmdlet 将用户从 Lync Server 2013 移动到 Lync Server 2010 时，会自动回滚统一联系人存储。 **Move-CsUser** 不会禁用统一联系人存储策略，因此如果用户移回 Lync Server 2013，将会再次发生统一联系人存储迁移。

## 将用户联系人从 Lync Server 2013 回滚到 Lync Server 2010

1.  启动 Lync Server 命令行管理程序：依次单击“开始”、“所有程序”和“Microsoft Lync Server 2013”，然后单击“Lync Server 命令行管理程序”。

2.  为要回滚的用户禁用统一联系人存储，使其不会在回滚后重新迁移。（只有您想要确保用户将来不会迁移时，才执行此步骤。）要为单个用户禁用统一联系人存储，请在命令行中键入：
    
        Set-CsUserServicesPolicy -Identity "<policy name>" -UcsAllowed $False
    
    例如：
    
        Set-CsUserServicesPolicy -Identity "UCS Enabled Users" -UcsAllowed $False

3.  在将用户从 Lync Server 2013 移动到 Lync Server 2010 之前，回滚 Lync Server 上指定用户的“好友列表”。
    
    > [!IMPORTANT]
    > 如果省略此步骤，则将丢失“好友列表”。


4.  回滚指定用户。在命令行中键入：
    
        Invoke-CsUcsRollback -Identity "<user display name>"
    
    例如：
    
        Invoke-CsUcsRollback -Identity "Ken Myer"
    
    > [!IMPORTANT]
    > 建议不要使用 –Force 选项来强制回滚。如果使用此选项，则将会丢失用户的联系人。


## 将统一联系人存储联系人从 Exchange 2013 回滚到 Lync Server 2013

1.  启动 Lync Server 命令行管理程序：依次单击“开始”、“所有程序”和“Microsoft Lync Server 2013”，然后单击“Lync Server 命令行管理程序”。

2.  为要回滚的用户禁用统一联系人存储，使其不会在回滚后重新迁移。要为单个用户禁用统一联系人存储，请在命令行中键入：
    
        Set-CsUserServicesPolicy -Identity "<policy name>" -UcsAllowed $False
    
    例如：
    
        Set-CsUserServicesPolicy -Identity "UCS Enabled Users" -UcsAllowed $False

3.  回滚指定用户。在命令行中键入：
    
        Invoke-CsUcsRollback -Identity "<user display name>"
    
    例如：
    
        Invoke-CsUcsRollback -Identity "Ken Myer"
    
    > [!IMPORTANT]
    > 必须先回滚 Lync Server 用户，然后移动 Exchange 2013 邮箱。在完成 Lync Server 回滚之前阻止 Exchange 管理员回滚 Exchange。建议不要使用 –Force 选项来强制回滚。如果使用此选项，则将会丢失用户的联系人。


4.  在将用户回滚到 Lync Server 之后，Exchange 管理员可将 Exchange 用户从 Exchange 2013 回滚到 Exchange 2010。


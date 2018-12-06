---
title: Lync Server 2013：为用户启用统一联系人存储
TOCTitle: 为用户启用统一联系人存储
ms:assetid: 7b46a01f-beb5-4a33-adb0-35f0502b168d
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ205024(v=OCS.15)
ms:contentKeyID: 49313340
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 在 Lync Server 2013 中为用户启用统一联系人存储

 

_**上一次修改主题：** 2012-10-07_

在部署 Lync Server 2013 并发布拓扑时，默认情况下会为所有用户启用统一的联系人存储库。在部署 Lync Server 2013 后，无需执行任何其他操作就能启用统一的联系人存储库。但是，可以使用 **Set-CsUserServicesPolicy** cmdlet 自定义哪些用户可以使用统一的联系人存储库。可以全局启用此功能，或者按站点、租户、个人或个人组启用此功能。

## 为用户启用统一的联系人存储库

1.  启动 Lync Server 命令行管理程序：依次单击“开始”、“所有程序”和“Microsoft Lync Server 2013”，然后单击“Lync Server 命令行管理程序”。

2.  执行下列任意操作：
    
      - 若要在全局为所有 Lync Server 用户启用统一的联系人存储库，请在命令行中键入：
        
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
        
        > [!NOTE]  
		> 还可以使用用户别名或 SIP URI 代替用户显示名称。
        
        
        例如：
        
            New-CsUserServicesPolicy -Identity "UCS Enabled Users" -UcsAllowed $True
            Grant-CsUserServicesPolicy -Identity "Ken Myer" -PolicyName "UCS Enabled Users"
        
        > [!NOTE]  
		> 在上面的示例中，第一个命令创建一个名为“<em>启用 UCS 的用户</em>”的新每用户策略，并将 UcsAllowed 标记设置为 True。第二个命令将该策略分配给显示名称为 Ken Myer 的用户，这意味着现在已为 Ken Myer 启用统一的联系人存储库。
        


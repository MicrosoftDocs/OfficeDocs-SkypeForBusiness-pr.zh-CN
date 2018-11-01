---
title: 分配每用户位置策略
TOCTitle: 分配每用户位置策略
ms:assetid: 343f2de3-a0ae-4403-8456-6e520b579d32
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg520974(v=OCS.15)
ms:contentKeyID: 49312455
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 分配每用户位置策略

 

_**上一次修改主题：** 2013-02-22_

位置策略是可以在 Lync Server 控制面板中配置的用户帐户的各项设置之一。

部署一个或多个每用户位置策略是可选的。还可以只部署一个全局级别的位置策略或子网级别的位置策略。如果要部署每用户策略，则必须将其明确分配给用户、组或联系对象。未分配特定的子网级别或每用户策略时，会自动默认使用全局级别位置策略中定义的增强型 9-1-1 (E9-1-1) 设置。

创建至少一个每用户位置策略之后，请使用本主题中的过程分配策略，该策略指定您希望服务器应用于特定用户发出的紧急呼叫的设置。

有关所有可用位置策略设置的列表，请参阅[为 Lync Server 2013 定义位置策略](lync-server-2013-defining-the-location-policy.md)。

有关创建位置策略的详细信息，请参阅[在 Lync Server 2013 中创建位置策略](lync-server-2013-create-location-policies.md)。

## 分配每用户位置策略

1.  使用分配给 CsUserAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。

2.  打开浏览器窗口，然后输入管理 URL 以打开 Lync Server 控制面板。有关可以用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅[打开 Lync Server 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左侧导航栏中，单击“用户”。

4.  使用下列方法之一查找用户：
    
      - 在“搜索用户”框中，键入用户帐户的显示名称、名字、姓氏、安全帐户管理器 (SAM) 帐户名、SIP 地址或线路统一资源标识符 (URI) 的全部或第一部分，然后单击“查找”。
    
      - 如果具有保存的查询，请单击“打开查询”图标，使用“打开”对话框来检索该查询（.usf 文件），然后单击“查找”。

5.  （可选）指定附加搜索条件以缩小结果的范围：
    
    1.  单击“添加筛选器”。
    
    2.  通过键入用户属性，或单击下拉列表中的箭头选择属性来输入用户属性。
    
    3.  在“等于”下拉列表中，单击运算符（例如“等于”或“不等于”）。
    
    4.  根据所选的用户属性，通过键入条件或单击下拉列表中的箭头输入用于筛选搜索结果的条件。
        
        > [!TIP]  
        > 要向查询中添加附加搜索子句，请单击“添加筛选器”。
    
    5.  单击“查找”。

6.  在搜索结果中单击某个用户，再单击“操作”，然后单击“分配策略”。
    
    > [!TIP]
    > 如果您希望将相同的每用户位置策略应用于多个用户，请在搜索结果中选择多个用户，单击“操作”，然后单击“分配策略”。


7.  在“分配策略”中的“位置策略”下，执行下列操作之一：
    
    > [!NOTE]  
    > 有多个策略可以使用“分配策略”对话框进行配置，因此默认情况下，将为对话框中的每个策略选中“&lt;保留原样&gt;”。如果不对此设置进行任何更改，则将继续使用先前分配给用户的策略。
    
    
      - 允许 Lync Server 2013 自动选择全局级别的策略或子网级别的策略（如果已定义）。
    
      - 单击先前通过运行 **New-CsLocationPolicy** cmdlet 定义的每用户位置策略的名称。
        
        > [!TIP]  
        > 为帮助您确定要分配的策略，请在单击策略名称后单击“查看”以查看策略中定义的用户权限。


8.  完成后，单击“确定”。

## 使用 Lync Server 命令行管理程序分配每用户位置策略

您可以使用 Grant-CsLocationPolicy cmdlet 分配每用户位置策略。可以从 Lync Server 2013 命令行管理程序或从 Windows PowerShell 的远程会话中运行此 cmdlet。有关使用远程 Windows PowerShell 连接到 Lync Server 的详细信息，请参阅 Lync Server Windows PowerShell 博客文章“快速入门：使用远程 PowerShell 管理 Microsoft Lync Server 2010”，网址为 [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)。

## 将每用户位置策略分配给单个用户

  - 以下命令将每用户位置策略 RedmondLocationPolicy 分配给用户 Ken Myer。
    
        Grant-CsLocationPolicy -Identity "Ken Myer" -PolicyName "RedmondLocationPolicy"

## 将每用户位置策略分配给多个用户

  - 此命令将每用户位置策略 AccountingDepartmentLocationPolicy 分配给就职于 Accounting 部门的所有用户。有关此命令中使用的 LdapFilter 参数的详细信息，请参阅 [Get-CsUser](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsUser) cmdlet 的文档。
    
        Get-CsUser -LdapFilter "Department=Accounting" | Grant-CsLocationPolicy -PolicyName "AccountingDepartmentLocationPolicy"

## 取消分配每用户位置策略

  - 以下命令取消分配之前分配给 Ken Myer 的所有每用户位置策略。取消分配每用户策略后，将使用全局策略或其本地站点策略（如果存在）自动管理 Ken Myer。站点策略优先于全局策略。
    
        Grant-CsLocationPolicy -Identity "Ken Myer" -PolicyName $Null

有关详细信息，请参阅 [Grant-CsLocationPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Grant-CsLocationPolicy) cmdlet 的帮助主题。


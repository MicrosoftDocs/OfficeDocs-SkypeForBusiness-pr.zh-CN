---
title: 分配每用户移动策略
TOCTitle: 分配每用户移动策略
ms:assetid: d8bf997f-4bc7-48d3-973b-323505f55e9d
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ721902(v=OCS.15)
ms:contentKeyID: 49888635
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 分配每用户移动策略

 

_**上一次修改主题：** 2013-02-22_

移动策略是您可以在 Lync Server 控制面板或 Lync Server 命令行管理程序中配置的用户帐户的各个设置之一。

## 在 Lync Server 控制面板中分配每用户移动策略

1.  使用分配给 CsUserAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。

2.  打开浏览器窗口，然后输入管理 URL 以打开 Lync Server 控制面板。有关可以用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅[打开 Lync Server 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左侧导航栏中，单击“用户”。

4.  使用以下方法之一找到用户：
    
      - 在“搜索用户”框中，键入用户帐户的显示名称、名、姓、安全帐户管理器 (SAM) 帐户名称、SIP 地址或线路统一资源标识符 (URI) 的全部或前面部分，然后单击“查找”。
    
      - 如果有已保存的查询，请单击“打开查询”图标，使用“打开”对话框检索查询（一个 .usf 文件），然后单击“查找”。

5.  （可选）指定附加搜索条件以缩小结果的范围：
    
    1.  单击“添加筛选器”。
    
    2.  通过键入用户属性，或单击下拉列表中的箭头选择用户属性来输入用户属性。
    
    3.  在“等于”下拉列表中，单击运算符（例如，“等于”或“不等于”）。
    
    4.  根据所选用户属性，通过键入条件或单击下拉列表中的箭头输入用于筛选搜索结果的条件。
        
        > [!TIP]  
        > 要向查询中添加附加搜索子句，请单击“添加筛选器”。
    
    5.  单击“查找”。

6.  在搜索结果中单击某个用户，再单击“操作”，然后单击“分配策略”。
    
    > [!TIP]
    > 如果您希望将相同的每用户移动策略应用于多个用户，请在搜索结果中选择多个用户，单击“操作”，然后单击“分配策略”。


7.  在“分配策略”中的“移动策略”下，执行以下操作之一：
    
    > [!NOTE]  
    > 由于在“分配策略”中可配置多种策略，对话框中的每种策略默认选择“&lt;保持原样&gt;”。对此设置不做更改则继续使用之前分配给该用户的策略。
    
    
      - 选择“\<自动\>”可允许 Lync Server 2013 自动选择全局级别策略或站点级别策略（如果已定义）。
    
      - 单击之前在“移动策略”页上定义的每用户移动策略的名称。
        
        > [!TIP]  
        > 为帮助您确定要分配的策略，请在单击策略名称后单击“查看”以查看策略中定义的用户权限。


8.  完成后，单击“确定”。

## 使用 Lync Server 命令行管理程序 Cmdlet 分配每用户移动策略

可以使用 Lync Server 命令行管理程序和 **Grant-CsMobilityPolicy** cmdlet 分配每用户移动策略。可以从Lync Server 2013 命令行管理程序或从 Windows PowerShell 的远程会话中运行此 cmdlet。有关使用远程 Windows PowerShell 连接到 Lync Server 的详细信息，请参阅 Lync Server Windows PowerShell 博客文章“快速入门：使用远程 PowerShell 管理 Microsoft Lync Server 2010”，网址为 [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)。

## 为单个用户分配每用户移动策略

  - 以下命令为用户 Ken Myer 分配每用户移动策略 RedmondMobilityPolicy。
    
        Grant-CsMobilityPolicy -Identity "Ken Myer" -PolicyName "RedmondMobilityPolicy"

## 为多个用户分配每用户移动策略

  - 以下命令为当前已分配策略 NorthAmericaMobilityPolicy 的所有用户分配每用户移动策略 RedmondMobilityPolicy。有关此命令中使用的 Filter 参数的详细信息，请参阅 [Get-CsUser](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsUser)。
    
        Get-CsUser -Filter {MobilityPolicy -eq "NorthAmericaMobilityPolicy"} | Grant-CsMobilityPolicy -PolicyName "RedmondMobilityPolicy"

## 取消分配每用户移动策略

  - 以下命令取消分配之前分配给 Ken Myer 的任何每用户移动策略。取消分配每用户策略后，将自动使用全局策略或本地站点策略（如果存在）管理 Ken Myer。站点策略优先于全局策略。
    
        Grant-CsMobilityPolicy -Identity "Ken Myer" -PolicyName $Null

有关详细信息，请参阅 [Grant-CsMobilityPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Grant-CsMobilityPolicy)。

## 另请参阅

#### 任务

[在 Lync Server 2013 中配置移动策略](lync-server-2013-configuring-mobility-policy.md)


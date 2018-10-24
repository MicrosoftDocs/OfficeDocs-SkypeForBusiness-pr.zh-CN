---
title: 分配每用户持久聊天策略
TOCTitle: 分配每用户持久聊天策略
ms:assetid: e22168f2-fde1-4f0a-b194-1fc881436822
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ721908(v=OCS.15)
ms:contentKeyID: 49888647
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 分配每用户持久聊天策略

 

_**上一次修改主题：** 2013-02-22_

您可以在 Lync Server 2013 控制面板或 Lync Server 2013 命令行管理程序中分配每用户持久聊天策略。有关创建持久聊天服务器的用户策略的信息，请参阅[在 Lync Server 2013 中为持久聊天创建用户策略](lync-server-2013-create-a-user-policy-for-persistent-chat.md)。

## 在 Lync Server 控制面板中分配每用户持久聊天策略

1.  使用分配给 CsUserAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。

2.  打开浏览器窗口，然后输入管理 URL 以打开 Lync Server 控制面板。有关可以用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅[打开 Lync Server 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左侧导航栏中，单击“用户”。

4.  使用下列其中的一个方法查找用户：
    
      - 在“搜索用户”框中，键入显示名称、名字、姓氏、安全帐户管理器 (SAM) 帐户名称、SIP 地址或用户帐户的线路统一资源标识符 (URI) 的全部或第一部分，然后单击“查找”。
    
      - 如果您有一个保存的查询，请单击“打开查询”图标，使用“打开”对话框检索该查询（.usf 文件），然后单击“查找”。

5.  （可选）指定附加搜索条件以缩小结果的范围：
    
    1.  单击“添加筛选器”。
    
    2.  通过键入用户属性或单击下拉列表中的箭头来选择该属性从而输入该用户属性。
    
    3.  在“等于”下拉列表中，单击运算符（例如，“等于”或“不等于”）。
    
    4.  根据您选择的用户属性，输入您要用于筛选搜索结果的条件，方法是键入该条件或通过单击下拉列表中的箭头。
        
        > [!TIP]  
        > 要将其他搜索子句添加到您的查询，请单击“添加筛选器”。
    
    5.  单击“查找”。

6.  在搜索结果中单击某个用户，再单击“操作”，然后单击“分配策略”。
    
    > [!TIP]
    > 如果要将相同的每用户持久聊天策略适用于多个用户，请在搜索结果中选择多个用户，然后单击“操作”，再单击“分配策略”。


7.  在“分配策略”的“持久聊天策略”下，执行下列操作之一：
    
    > [!NOTE]  
    > 有多个策略可以使用“分配策略”对话框进行配置，因此默认情况下，将为对话框中的每个策略选中“&lt;保留原样&gt;”。如果不对此设置进行任何更改，则将继续使用先前分配给用户的策略。
    
    
      - 选择“\<自动\>”以允许 Lync Server 2013 自动选择全局级别的策略或站点级别的策略（如果已定义）。
    
      - 单击先前您在“持久聊天策略”页面上定义的每用户持久聊天策略的名称。
        
        > [!TIP]  
        > 为帮助您确定要分配的策略，请在单击策略名称后单击“查看”以查看策略中定义的用户权限。


8.  操作完成后，单击“确定”。

## 通过使用 Lync Server PowerShell Cmdlet 分配每用户持久聊天策略

还可以使用 Lync Server PowerShell 和 Grant-CsPersistentChatPolicy cmdlet 分配每用户持久聊天策略。可从 Lync Server 2013 命令行管理程序或从 Windows PowerShell 的远程会话运行此 cmdlet。有关使用远程 Windows PowerShell 连接到 Lync Server 的详细信息，请参阅 Lync Server Windows PowerShell 博客文章“快速入门：使用远程 PowerShell 管理 Microsoft Lync Server 2010”，网址为 [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)。

## 将每用户持久聊天策略分配到单个用户

  - 下列命令可用于将每用户持久聊天策略 RedmondPersistentChatPolicy 分配到用户 Ken Myer。
    
        Grant-CsPersistentChatPolicy -Identity "Ken Myer" -PolicyName "RedmondPersistentChatPolicy"

## 将每用户持久聊天策略分配到多个用户

  - 此命令可用于将每用户持久聊天策略 RedmondUsersPersistentChatPolicy 分配到为 IT 部门服务的所有用户。有关此命令中使用的 LdapFilter 参数的更多信息，请参阅 [Get-CsUser](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsUser) cmdlet 的文档。
    
        Get-CsUser -LdapFilter "Department=IT" | Grant-CsPersistentChatPolicy -PolicyName "RedmondUsersPersistentChatPolicy"

## 取消分配每用户持久聊天策略

  - 下列命令可用于取消先前分配到 Ken Myer 的任何每用户持久聊天策略。取消分配每用户策略后，将自动使用全局策略或其本地站点策略（如果存在该策略）自动管理 Ken Myer。站点策略优先于全局策略。
    
        Grant-CsPersistentChatPolicy -Identity "Ken Myer" -PolicyName $Null

有关更多信息，请参阅[Grant-CsPersistentChatPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Grant-CsPersistentChatPolicy) cmdlet 的帮助主题。

## 另请参阅

#### 概念

[在 Lync Server 2013 中为持久聊天创建用户策略](lync-server-2013-create-a-user-policy-for-persistent-chat.md)


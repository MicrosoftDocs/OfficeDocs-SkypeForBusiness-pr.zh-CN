---
title: 锁定或解锁用户 PIN
TOCTitle: 锁定或解锁用户 PIN
ms:assetid: 3d293a8a-e182-4547-8b06-2603c3c77329
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ688028(v=OCS.15)
ms:contentKeyID: 49888386
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 锁定或解锁用户 PIN

 

_**上一次修改主题：** 2013-02-23_

您可以从 Lync Server 2013 控制面板的“用户”部分锁定或解锁用户 PIN。

## 在 Lync Server 控制面板中锁定用户 PIN

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
    
    6.  单击用户，再单击“操作”，然后单击“锁定 PIN”。

## 在 Lync Server 控制面板中解锁用户 PIN

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
    
    6.  单击用户，再单击“操作”，然后单击“解锁 PIN”。

## 使用 Lync Server 命令行管理程序 cmdlet 锁定和解锁 PIN

还可以使用 Windows PowerShell 以及 Lock-CsClientPin 和 Unlock-CsClientPin cmdlet 来锁定和解锁用户 PIN。可以从 Lync Server 2013 命令行管理程序或从 Windows PowerShell 的远程会话中运行这些 cmdlet。有关使用远程 Windows PowerShell 连接到 Lync Server 的详细信息，请参阅 Lync Server Windows PowerShell 博客文章“快速入门：使用远程 PowerShell 管理 Microsoft Lync Server 2010”，网址为 [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)。

## 锁定用户 PIN

  - 若要锁定用户 PIN，请使用 Lock-CsClientPin cmdlet。例如：
    
        Lock-CsClientPin -Identity "Ken Myer"

## 解锁用户 PIN

  - 若要解锁用户 PIN，请使用 Unlock-CsClientPin cmdlet。例如：
    
        Unlock-CsClientPin -Identity "Ken Myer"

有关详细信息，请参阅 [Lock-CsClientPin](https://docs.microsoft.com/en-us/powershell/module/skype/Lock-CsClientPin) 和 [Unlock-CsClientPin](https://docs.microsoft.com/en-us/powershell/module/skype/Unlock-CsClientPin) cmdlet 的帮助主题。


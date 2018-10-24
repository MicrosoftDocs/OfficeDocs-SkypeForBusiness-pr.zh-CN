---
title: 搜索 Lync Server 用户
TOCTitle: 搜索 Lync Server 用户
ms:assetid: 3b9f6f55-d7a9-46ae-8e10-f221ba0d3bb5
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg429701(v=OCS.15)
ms:contentKeyID: 49312560
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 搜索 Lync Server 用户

 

_**上一次修改主题：** 2014-05-14_

可以使用搜索查询的结果来配置 Lync Server 2013 用户。可以按照显示名称、名字、姓氏、安全帐户管理器 (SAM) 帐户名、SIP 地址或线路统一资源标识符 (URI) 搜索用户。

可以使用 Lync Server 控制面板或 Active Directory 用户和计算机管理单元来搜索用户。下面的过程介绍了如何使用 Lync Server 控制面板搜索用户。

> [!NOTE]  
> 在包括中央林拓扑的环境中，按照用户的电子邮件地址搜索用户时，搜索结果可能不准确。可以改为通过指定 SIP 地址前缀（例如，sip:name）来搜索用户，然后添加搜索筛选器并选择包含部分电子邮件地址的 SIP 地址，或使用 <strong>Get-CSUser</strong> cmdlet。



## 搜索一个或多个用户

1.  使用分配给 CsUserAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。

2.  打开浏览器窗口，然后输入管理 URL 以打开 Lync Server 控制面板。有关可以用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅[打开 Lync Server 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左导航栏中，单击“用户”。

4.  在“搜索用户”框中，键入要搜索的用户帐户的显示名称、名字、姓氏、SAM 帐户名称、SIP 地址或线路 URI 的完整或第一部分，然后单击“查找”。

5.  （可选）指定附加搜索条件以缩小结果的范围：
    
    1.  单击 “搜索结果”上方屏幕右上角的展开箭头按钮，然后单击“添加筛选器”。
    
    2.  通过键入用户属性，或单击下拉列表中的箭头选择用户属性来输入用户属性。
    
    3.  在“等于” 列表中，单击“等于”或“不等于”。
    
    4.  在文本框中，输入要用于筛选搜索结果的搜索条件，然后单击“查找”。

6.  搜索结果将显示在“搜索结果”下。可以选择列表中的任何或全部用户，并对选择的用户执行配置任务。

## 另请参阅

#### 其他资源

[查看为 Lync Server 2013 启用的用户帐户的信息](lync-server-2013-viewing-information-about-user-accounts-enabled-for-lync-server.md)  
[启用和禁用 Lync Server 2013 的用户](lync-server-2013-enabling-and-disabling-users-for-lync-server.md)


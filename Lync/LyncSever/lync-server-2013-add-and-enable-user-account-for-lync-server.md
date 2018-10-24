---
title: 向 Lync Server 2010 添加和启用用户帐户
TOCTitle: 向 Lync Server 2010 添加和启用用户帐户
ms:assetid: 1edd1c1c-307d-450b-abea-33aaf56bdf13
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg520961(v=OCS.15)
ms:contentKeyID: 49312204
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 向 Lync Server 2010 添加和启用用户帐户

 

_**上一次修改主题：** 2012-11-02_

在 Active Directory 用户和计算机中启用用户帐户后，可以使用 Lync Server 控制面板，通过向 Lync Server 中添加 Active Directory 用户来创建和启用新的 Lync Server 2013 用户帐户。

## 添加和启用新的 Lync Server 用户

1.  使用分配给 CsUserAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。

2.  打开浏览器窗口，然后输入管理 URL 以打开 Lync Server 控制面板。有关可以用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅[打开 Lync Server 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左侧导航栏中，单击“用户”。

4.  单击“启用用户”。

5.  在“新建 Lync Server 用户”对话框中，单击“添加”。

6.  在“搜索用户”框中，键入所需 Active Directory 用户帐户的完整的名称、显示名称、名字、姓氏、安全帐户管理器 (SAM) 帐户名、电子邮件地址、用户主体名称 (UPN) 或电话号码，或这些内容的第一部分，然后单击“查找”。

7.  在表中，选择要添加到 Lync Server 中的帐户，然后单击“确定”。

8.  将该用户分配给某个池，指定其他任何详细信息，并向所需用户分配策略，然后单击“启用”。

## 另请参阅

#### 任务

[禁用或重新启用 Lync Server 的用户帐户](lync-server-2013-disable-or-re-enable-user-account-for-lync-server.md)  
[从 Lync Server 删除用户帐户](lync-server-2013-remove-a-user-account-from-lync-server.md)  

#### 其他资源

[启用和禁用 Lync Server 2013 的用户](lync-server-2013-enabling-and-disabling-users-for-lync-server.md)


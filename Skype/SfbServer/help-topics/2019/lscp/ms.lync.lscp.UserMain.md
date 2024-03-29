---
title: 控制面板 - 已更新用户搜索
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
  - ms.lync.lscp.UserMain
ms.prod: skype-for-business-itpro
f1.keywords:
  - CSH
ms.localizationpriority: medium
ms.assetid: 50feb75f-92a1-4916-b92e-c039e1290c52
ROBOTS: 'NOINDEX, NOFOLLOW'
description: 您可以使用搜索查询的结果为用户配置Skype for Business Server。 可以按照显示名称、名字、姓氏、安全帐户管理器 (SAM) 帐户名、SIP 地址或线路统一资源标识符 (URI) 搜索用户。 您还可以使用 Lync Server 控制面板或 Active Directory 用户和计算机管理单元搜索用户。
---

# <a name="control-panel---updated-user-search"></a>控制面板 - 已更新：用户搜索

您可以使用搜索查询的结果为用户配置Skype for Business Server。 可以按照显示名称、名字、姓氏、安全帐户管理器 (SAM) 帐户名、SIP 地址或线路统一资源标识符 (URI) 搜索用户。 您还可以使用 Lync Server 控制面板或 Active Directory 用户和计算机管理单元搜索用户。

## <a name="tasks-you-can-perform"></a>可执行的任务

您可以在"用户搜索控制面板" **页上执行以下** 任务：

- [搜索用户](/previous-versions/office/lync-server-2013/lync-server-2013-search-for-lync-server-users)

- [启用或禁用用户](/previous-versions/office/lync-server-2013/lync-server-2013-disable-or-re-enable-user-account-for-lync-server)

- [移动用户](ms.lync.lscp.UserMove.md)

- [移动所有用户](ms.lync.lscp.UserMoveAll.md)

- [向用户分配策略](/previous-versions/office/lync-server-2013/lync-server-2013-assigning-per-user-policies)

- [为用户启用企业语音Skype for Business Server](../../../deploy/deploy-enterprise-voice/enable-users-for-enterprise-voice.md)

- [为用户配置联盟、远程用户访问和公共 IM 连接](/previous-versions/office/lync-server-2013/lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user)

- [为用户配置电话](/previous-versions/office/lync-server-2013/lync-server-2013-configure-telephony-for-a-user)



## <a name="ui-reference"></a>用户界面参考

以下列表描述了"用户搜索"页上的菜单、命令 **、字段和** 属性。

### <a name="user-search"></a>用户搜索

- **搜索** 按用户帐户的域名、名字显示名称姓氏、SAM 帐户名、SIP 地址或线路 URI 的第一部分搜索用户。

- **LDAP 搜索** 通过键入 LDAP 表达式搜索用户。

- **"搜索用户"框** 键入要搜索的用户数据或 LDAP 表达式。

- **查找** 单击以显示与在"搜索用户和"框中输入的 **搜索值匹配的** 用户。

- **打开查询** 单击以打开保存的搜索查询。

- **保存查询** 单击以保存搜索查询。

- **+ 添加筛选器** 单击可添加其他搜索条件。

- **搜索筛选器字段** 选择要筛选搜索结果的字段，选择查询的运算符，然后键入要搜索的字符串。

- **要显示的最大用户数** 键入要显示的搜索结果数，或使用向上和向下箭头指定数量。

根据需要添加其他描述性文本。

### <a name="search-results-menus"></a>搜索结果菜单

- **启用用户** 单击以打开"[用户： 新建 Lync Server](ms.lync.lscp.UserNew.md) 用户"对话框，可在其中添加新Skype for Business Server。

    若要添加新联系人，请单击向下箭头，然后选择"启用 **联系人** "以打开"用户 [： 新建联系人对象"](ms.lync.lscp.UserNewContact.md) 对话框。

- **编辑** 单击 **"** 编辑"，然后单击"显示详细信息"以显示所选用户的详细信息，或单击"选择所有搜索结果"以选择结果表中显示的所有用户。

- **操作****单击"** 操作"，然后在搜索结果中选择要为所选用户执行的操作。 提供了以下选项：

  - **重新启用 Lync Server** 在临时禁用所选用户帐户后启用该帐户。

  - **暂时禁用 Lync Server** 在重新启用Skype for Business Server之前禁用用户帐户，而不删除用户帐户。

  - **分配策略** 打开 ["用户： 分配策略](ms.lync.lscp.UserAssignPolicy.md) "对话框，可在其中配置分配给用户的策略。

  - **查看 PIN 状态** 打开" [用户： 查看 PIN 状态](ms.lync.lscp.UserViewPin.md) "对话框，其中显示所选用户的 PIN 数据。

  - **设置 PIN** 打开 ["设置 PIN](ms.lync.lscp.UserSetPin.md) "对话框，可在其中为所选用户设置 PIN。

  - **锁定 PIN** 锁定用户的 PIN。

  - **解锁 PIN** 删除用户 PIN 上的锁定。

  - **从 Lync Server 中删除** 从帐户中删除Skype for Business Server。 不会从 Active Directory 中删除用户。

  - **删除用户证书** 删除授予用户的所有证书。

  - **将所选用户移动到池** 打开 ["移动用户](ms.lync.lscp.UserMove.md) "对话框，可在其中选择要将所选用户移动到的池。

  - **将所有用户移动到池** 打开 ["移动用户](ms.lync.lscp.UserMove.md) "对话框，您可以在其中选择要将所有选定用户移动到的池。
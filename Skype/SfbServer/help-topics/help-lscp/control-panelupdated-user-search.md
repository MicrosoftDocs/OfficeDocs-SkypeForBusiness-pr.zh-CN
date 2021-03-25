---
title: 控制面板 - 已更新用户搜索
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 5/21/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.lscp.UserMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 50feb75f-92a1-4916-b92e-c039e1290c52
description: 您可以使用搜索查询的结果为 Skype for Business Server 配置用户。 可以按照显示名称、名字、姓氏、安全帐户管理器 (SAM) 帐户名、SIP 地址或线路统一资源标识符 (URI) 搜索用户。 您还可以使用 Lync Server 控制面板或 Active Directory 用户和计算机管理单元搜索用户。
ms.openlocfilehash: 117f1c6a5a697cb1cf9e8e1f5c6cbf8363c517bf
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51119931"
---
# <a name="control-panel---updated-user-search"></a>控制面板 - 已更新：用户搜索

您可以使用搜索查询的结果为 Skype for Business Server 配置用户。 可以按照显示名称、名字、姓氏、安全帐户管理器 (SAM) 帐户名、SIP 地址或线路统一资源标识符 (URI) 搜索用户。 您还可以使用 Lync Server 控制面板或 Active Directory 用户和计算机管理单元搜索用户。

## <a name="tasks-you-can-perform"></a>可执行的任务

您可以在"用户搜索控制面板" **页上执行以下** 任务：

- [搜索 Lync Server 2010 用户](/previous-versions/office/lync-server-2013/lync-server-2013-search-for-lync-server-users)

- [为 Lync Server 2010 启用或禁用用户](/previous-versions/office/lync-server-2013/lync-server-2013-disable-or-re-enable-user-account-for-lync-server)

- [移动用户](move-user.md)

- [移动所有用户](move-all-users.md)

- [向用户分配策略](/previous-versions/office/lync-server-2013/lync-server-2013-assigning-per-user-policies)

- [在 Skype for Business Server 2015 企业语音用户进行登录](../../deploy/deploy-enterprise-voice/enable-users-for-enterprise-voice.md)

- [为用户配置联盟、远程用户访问和公共 IM 连接](/previous-versions/office/lync-server-2013/lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user)

- [为用户配置电话](/previous-versions/office/lync-server-2013/lync-server-2013-configure-telephony-for-a-user)

有关可以使用 Skype for Business Server 控制面板执行的不同过程的详细信息，请参阅[管理 Skype for Business Server 2015。](../../manage/manage.md)

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

- **启用用户** 单击以打开" [用户： 新建 Lync Server](users-new-lync-server-user.md) 用户"对话框，可在其中向 Skype for Business Server 添加新用户。

    若要添加新联系人，请单击向下箭头，然后选择"启用 **联系人** "以打开"用户： [新建联系人对象"](users-new-contact-objects.md) 对话框。

- **编辑** 单击 **"** 编辑"，然后单击"显示详细信息"以显示所选用户的详细信息，或单击"选择所有搜索结果"以选择结果表中显示的所有用户。

- **操作** 单击 **"** 操作"，然后在搜索结果中选择要为所选用户执行的操作。 可以使用以下操作：

  - **重新启用 Lync Server** 在临时禁用所选用户帐户后启用该帐户。

  - **暂时禁用 Lync Server** 在重新启用之前禁用 Skype for Business Server 中的用户帐户，而不删除用户帐户。

  - **分配策略** 打开 ["用户： 分配策略](users-assign-policies.md) "对话框，可在其中配置分配给用户的策略。

  - **查看 PIN 状态** 打开" [用户： 查看 PIN 状态](users-view-pin-status.md) "对话框，其中显示所选用户的 PIN 数据。

  - **设置 PIN** 打开 ["设置 PIN"](set-pin.md) 对话框，可在其中为所选用户设置 PIN。

  - **锁定 PIN** 锁定用户的 PIN。

  - **解锁 PIN** 删除用户 PIN 上的锁定。

  - **从 Lync Server 中删除** 从 Skype for Business Server 中删除用户帐户。 不会从 Active Directory 中删除用户。

  - **删除用户证书** 删除授予用户的所有证书。

  - **将所选用户移动到池** 打开 ["移动用户](move-user.md) "对话框，可在其中选择要将所选用户移动到的池。

  - **将所有用户移动到池** 打开 ["移动用户](move-user.md) "对话框，可在其中选择要将所有选定用户移动到的池。
---
title: 控制面板 - 更新的用户搜索
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
ms.openlocfilehash: 699f0a4eeb07eb1ac056cdf4777853b163fdb1c0
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49800362"
---
# <a name="control-panel---updated-user-search"></a>控制面板 - 已更新：用户搜索

您可以使用搜索查询的结果为 Skype for Business Server 配置用户。 可以按照显示名称、名字、姓氏、安全帐户管理器 (SAM) 帐户名、SIP 地址或线路统一资源标识符 (URI) 搜索用户。 您还可以使用 Lync Server 控制面板或 Active Directory 用户和计算机管理单元搜索用户。

## <a name="tasks-you-can-perform"></a>可执行的任务

您可以在"用户搜索控制面板" **页上执行以下** 任务：

- [搜索 Lync Server 2010 用户](https://technet.microsoft.com/library/3b9f6f55-d7a9-46ae-8e10-f221ba0d3bb5.aspx)

- [为 Lync Server 2010 启用或禁用用户](https://technet.microsoft.com/library/12497d00-f665-4a97-be68-854c5a8be4fc.aspx)

- [移动用户](move-user.md)

- [移动所有用户](move-all-users.md)

- [向用户分配策略](https://technet.microsoft.com/library/a4ed0120-d9e5-4eb2-acfd-8de2cb503652.aspx)

- [在 Skype for Business Server 2015 中企业语音用户登录](../../deploy/deploy-enterprise-voice/enable-users-for-enterprise-voice.md)

- [为用户配置联盟、远程用户访问和公共 IM 连接](https://technet.microsoft.com/library/736fcaad-9f95-4896-b767-e199d86a00a4.aspx)

- [为用户配置电话](https://technet.microsoft.com/library/4546432e-c839-4517-a2c5-bc0d4d8c6a03.aspx)

有关可以使用 Skype for Business Server 控制面板执行的不同过程的详细信息，请参阅["管理 Skype for Business Server 2015"。](../../manage/manage.md)

## <a name="ui-reference"></a>用户界面参考

以下列表描述了"用户搜索"页上的菜单、命令、字段 **和** 属性。

### <a name="user-search"></a>用户搜索

- **搜索** 按用户帐户的 显示名称、名字、姓氏、SAM 帐户名、SIP 地址或线路 URI 的第一部分搜索用户。

- **LDAP 搜索** 通过键入 LDAP 表达式来搜索用户。

- **"搜索用户"框** 键入要搜索的用户数据或 LDAP 表达式。

- **查找** Click to display the users that match the search values you entered in the **Search users** and box.

- **打开查询** 单击以打开保存的搜索查询。

- **保存查询** 单击以保存搜索查询。

- **+ 添加筛选器** 单击以添加其他搜索条件。

- **搜索筛选器字段** 选择要筛选搜索结果的字段，为查询选择一个运算符，然后键入要搜索的字符串。

- **要显示的最大用户数** 键入要显示的搜索结果数，或使用向上和向下箭头指定数量。

根据需要添加其他描述性文本。

### <a name="search-results-menus"></a>搜索结果菜单

- **启用用户** 单击以打开 ["用户： 新建 Lync Server 用户](users-new-lync-server-user.md) "对话框，可在其中向 Skype for Business Server 添加新用户。

    若要添加新联系人，请单击向下箭头，然后选择"启用 **联系人** "以打开"用户： [新建联系人对象"](users-new-contact-objects.md) 对话框。

- **编辑** 单击 **"** 编辑"，然后单击"显示详细信息"以显示所选用户的详细信息，或单击"选择所有搜索结果"以选择结果表中显示的所有用户。

- **操作** 单击 **"** 操作"，然后在搜索结果中选择要为所选用户执行的操作。 可以使用以下操作：

  - **重新启用 Lync Server** 在暂时禁用所选用户帐户后启用它。

  - **暂时禁用 Lync Server** 在重新启用用户帐户之前，禁用 Skype for Business Server 中的用户帐户，而不删除用户帐户。

  - **分配策略** 打开 ["用户： 分配策略](users-assign-policies.md) "对话框，可在其中配置分配给用户的策略。

  - **查看 PIN 状态** 打开 ["用户： 查看 PIN 状态](users-view-pin-status.md) "对话框，该对话框显示所选用户的 PIN 数据。

  - **设置 PIN** 打开 ["设置 PIN"](set-pin.md) 对话框，可在其中为所选用户设置 PIN。

  - **锁定 PIN** 锁定用户的 PIN。

  - **解锁 PIN** 删除用户 PIN 上的锁定。

  - **从 Lync Server 中删除** 从 Skype for Business Server 中删除用户帐户。 不会从 Active Directory 中删除用户。

  - **删除用户证书** 删除授予用户的所有证书。

  - **将所选用户移动到池** 打开 ["移动用户](move-user.md) "对话框，您可以在其中选择要将所选用户移动到的池。

  - **将所有用户移动到池** 打开 ["移动用户](move-user.md) "对话框，您可以在其中选择要将所有用户移动到的池。



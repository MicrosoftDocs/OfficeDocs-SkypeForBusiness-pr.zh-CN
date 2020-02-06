---
title: 控制面板-更新的用户搜索
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: 你可以使用搜索查询的结果为 Skype for Business 服务器配置用户。 可以按照显示名称、名字、姓氏、安全帐户管理器 (SAM) 帐户名、SIP 地址或线路统一资源标识符 (URI) 搜索用户。 还可以使用 Lync Server 控制面板或 Active Directory 用户和计算机管理单元搜索用户。
ms.openlocfilehash: 4d0fc01a5843408effa69aceb5c95a74c875213a
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41822935"
---
# <a name="control-panel---updated-user-search"></a>控制面板 - 已更新：用户搜索

你可以使用搜索查询的结果为 Skype for Business 服务器配置用户。 可以按照显示名称、名字、姓氏、安全帐户管理器 (SAM) 帐户名、SIP 地址或线路统一资源标识符 (URI) 搜索用户。 还可以使用 Lync Server 控制面板或 Active Directory 用户和计算机管理单元搜索用户。

## <a name="tasks-you-can-perform"></a>可执行的任务

您可以在“**用户搜索**”控制面板页上执行以下任务：

- [Search for Lync Server 2010 Users](https://technet.microsoft.com/library/3b9f6f55-d7a9-46ae-8e10-f221ba0d3bb5.aspx)

- [Enable or Disable Users for Lync Server 2010](https://technet.microsoft.com/library/12497d00-f665-4a97-be68-854c5a8be4fc.aspx)

- [移动用户](move-user.md)

- [移动所有用户](move-all-users.md)

- [Assign Policies to Users](https://technet.microsoft.com/library/a4ed0120-d9e5-4eb2-acfd-8de2cb503652.aspx)

- [Enable users for Enterprise Voice in Skype for Business Server 2015](../../deploy/deploy-enterprise-voice/enable-users-for-enterprise-voice.md)

- [Configure Federation, Remote User Access, and Public IM Connectivity for Users](https://technet.microsoft.com/library/736fcaad-9f95-4896-b767-e199d86a00a4.aspx)

- [Configure Telephony for Users](https://technet.microsoft.com/library/4546432e-c839-4517-a2c5-bc0d4d8c6a03.aspx)

有关可通过使用 Skype for Business 服务器控制面板执行的不同过程的详细信息，请参阅[管理 skype for Business server 2015](../../manage/manage.md)。

## <a name="ui-reference"></a>用户界面参考

下表介绍了“**用户搜索**”页上的菜单、命令、字段和属性。

### <a name="user-search"></a>用户搜索

- **搜索**按显示名称、名字、姓氏、SAM 帐户名、SIP 地址或用户帐户的行 URI 的第一部分搜索用户。

- **LDAP 搜索**通过键入 LDAP 表达式来搜索用户。

- **"搜索用户" 框**键入要搜索的用户数据或 LDAP 表达式。

- **查找**单击以显示与您在 "**搜索用户**和" 框中输入的搜索值相匹配的用户。

- **打开查询**单击以打开已保存的搜索查询。

- **保存查询**单击以保存搜索查询。

- **+ 添加筛选器**单击以添加其他搜索条件。

- **搜索筛选字段**选择要筛选搜索结果的字段，选择查询的运算符，然后键入要搜索的字符串。

- **要显示的最大用户**数键入要显示的搜索结果数，或使用向上键和向下键指定数字。

添加附加描述性文本，视情况而定。

### <a name="search-results-menus"></a>搜索结果菜单

- **启用用户**单击以打开 "[用户：新建 Lync Server 用户](users-new-lync-server-user.md)" 对话框，您可以在其中将新用户添加到 Skype For business 服务器。

    若要添加新的联系人，请单击向下箭头并选择“**启用联系人**”以打开[Users: New Contact Objects](users-new-contact-objects.md)对话框。

- **编辑**单击 "**编辑**"，然后单击 "**显示详细信息**" 以显示所选用户的详细信息，或单击 "**选择所有搜索结果**" 以选择结果表中显示的所有用户。

- **操作**单击 "**操作**"，然后在搜索结果中选择要为所选用户执行的操作。 以下操作可用：

  - **为 Lync Server 重新启用**选中的用户帐户被暂时禁用后启用。

  - **为 Lync Server 暂时禁用**在 Skype for Business 服务器中禁用用户帐户，直到重新启用它，而不删除用户帐户。

  - **分配策略**打开 "[用户：分配策略](users-assign-policies.md)" 对话框，您可以在其中配置分配给用户的策略。

  - **查看 PIN 状态**打开 "[用户：查看引脚状态](users-view-pin-status.md)" 对话框，其中显示所选用户的固定数据。

  - **设置 PIN**打开 "[设置 PIN](set-pin.md) " 对话框，您可以在其中设置所选用户的 PIN。

  - **锁定引脚**锁定用户的 PIN。

  - **解锁 PIN 码**删除用户的 PIN 锁。

  - **从 Lync Server 中删除**从 Skype for Business 服务器中删除用户帐户。 用户未从 Active Directory 中删除。

  - **删除用户证书**删除授予用户的所有证书。

  - **将所选用户移动到池中**打开 "[移动用户](move-user.md)" 对话框，您可以在其中选择要将所选用户移动到的池。

  - **将所有用户移到池中**打开 "[移动用户](move-user.md)" 对话框，您可以在其中选择要将所有选定的用户移动到的池。



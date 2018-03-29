---
title: 控制面板-更新用户搜索
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 5/21/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.UserMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 50feb75f-92a1-4916-b92e-c039e1290c52
description: 搜索查询的结果可以用于配置用户的 Skype 业务服务器。 可以按照显示名称、名字、姓氏、安全帐户管理器 (SAM) 帐户名、SIP 地址或线路统一资源标识符 (URI) 搜索用户。 还可以使用 Lync Server 控制面板或 Active Directory 用户和计算机管理单元搜索用户。
ms.openlocfilehash: 9cf6384d10cc4b6d2931fb21c75fd09da873d383
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="control-panel---updated-user-search"></a>控制面板 - 已更新：用户搜索
 
搜索查询的结果可以用于配置用户的 Skype 业务服务器。 可以按照显示名称、名字、姓氏、安全帐户管理器 (SAM) 帐户名、SIP 地址或线路统一资源标识符 (URI) 搜索用户。 还可以使用 Lync Server 控制面板或 Active Directory 用户和计算机管理单元搜索用户。
  
## <a name="tasks-you-can-perform"></a>可执行的任务

您可以在“**用户搜索**”控制面板页上执行以下任务：
  
- [Lync Server 2010 用户搜索](http://technet.microsoft.com/library/3b9f6f55-d7a9-46ae-8e10-f221ba0d3bb5.aspx)
    
- [启用或禁用 Lync Server 2010 中的用户](http://technet.microsoft.com/library/12497d00-f665-4a97-be68-854c5a8be4fc.aspx)
    
- [移动用户](move-user.md)
    
- [移动所有用户](move-all-users.md)
    
- [将策略分配到的用户](http://technet.microsoft.com/library/a4ed0120-d9e5-4eb2-acfd-8de2cb503652.aspx)
    
- [启用用户的 Skype 在企业语音的业务服务器 2015](../../deploy/deploy-enterprise-voice/enable-users-for-enterprise-voice.md)
    
- [为用户配置联盟、 远程用户访问和公用 IM 连接](http://technet.microsoft.com/library/736fcaad-9f95-4896-b767-e199d86a00a4.aspx)
    
- [为用户配置电话服务](http://technet.microsoft.com/library/4546432e-c839-4517-a2c5-bc0d4d8c6a03.aspx)
    
您还可以通过 Skype 业务服务器控件面板的不同过程的详细信息，请参阅[管理的业务服务器 2015年的 Skype](../../manage/manage.md)。
  
## <a name="ui-reference"></a>用户界面参考

下表介绍了“**用户搜索**”页上的菜单、命令、字段和属性。
  
### <a name="user-search"></a>用户搜索

- **搜索**显示名称、 名字、 姓氏、 SAM 帐户名、 SIP 地址的第一部分通过搜索用户或行 URI 的用户帐户。
    
- **LDAP 搜索**通过键入表达式 LDAP 搜索用户。
    
- **搜索用户框**键入要搜索的 LDAP 表达式或用户数据。
    
- **查找**单击此处，显示与您在**搜索用户**和框中输入搜索值匹配的用户。
    
- **打开查询**单击此处，打开一个已保存的搜索查询。
    
- **保存查询**单击此处，保存搜索查询。
    
- **+ 添加筛选器**单击要添加其他搜索条件。
    
- **搜索筛选器字段**选择要筛选搜索结果，选择一个运算符用于查询，，然后键入您要搜索的字符串的字段。
    
- **若要显示的最多用户**键入您想要显示，或使用向上键和向下箭头，以指定数量的搜索结果数。
    
添加附加描述性文本，视情况而定。
  
### <a name="search-results-menus"></a>搜索结果菜单

- **启用用户**单击以打开[用户： 新 Lync Server 用户](users-new-lync-server-user.md)对话框，在其中您可以添加一个新用户 Skype 业务服务器。
    
    若要添加新联系人，单击向下箭头，然后选择**启用联系人**以打开[用户： 新的联系对象](users-new-contact-objects.md)对话框。
    
- **编辑**单击**编辑**，然后单击**显示详细信息**以显示所选用户的详细信息，或单击**选择所有搜索结果**来都选择显示在结果表中的所有用户。
    
- **操作**单击**操作**，然后选择您想要在搜索结果中的所选用户执行的操作。 下列操作有：
    
  - **Lync 服务器重新启用**使选定的用户帐户后暂时被禁用。
    
  - **暂时禁用 Lync 服务器**业务服务器禁用在 Skype 的用户帐户，直到您重新启用它，而不删除用户帐户。
    
  - **分配策略**打开[用户： 分配策略](users-assign-policies.md)对话框，您可以将配置分配给用户的策略。
    
  - **查看针状态**打开[用户： 查看针状态](users-view-pin-status.md)对话框，其中显示所选用户的 PIN 数据。
    
  - **设置旋转中心点**打开[设置 PIN](set-pin.md)对话框，您可以为所选用户设置 PIN。
    
  - **锁针**锁定用户的 PIN。
    
  - **PIN 解锁**删除该用户的 PIN 的锁定。
    
  - **从 Lync 服务器中删除**删除业务服务器从 Skype 的用户帐户。 无法从 Active Directory 中删除用户。
    
  - **删除用户证书**删除授予用户的所有证书。
    
  - **移动所选的用户到池**打开[移动用户](move-user.md)对话框，您可以在其中选择要移动到所选的用户的池。
    
  - **移动到池中的所有用户**打开[移动用户](move-user.md)对话框，可以在其中选择一个池移动到所有选定的用户。
    


---
title: 控制面板-更新用户搜索
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.UserMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 50feb75f-92a1-4916-b92e-c039e1290c52
description: 搜索查询的结果可用于配置用户的 Skype 业务服务器。 可以按照显示名称、名字、姓氏、安全帐户管理器 (SAM) 帐户名、SIP 地址或线路统一资源标识符 (URI) 搜索用户。 还可以使用 Lync Server 控制面板或 Active Directory 用户和计算机管理单元搜索用户。
ms.openlocfilehash: eb123d3fcbf13b75687f40d7311d8d9af8cb8fda
ms.sourcegitcommit: 9c5c67eb50006f84c425456dfb3ecfcf4638d5fc
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/28/2018
ms.locfileid: "20088544"
---
# <a name="control-panel---updated-user-search"></a>控制面板 - 已更新：用户搜索
 
搜索查询的结果可用于配置用户的 Skype 业务服务器。 可以按照显示名称、名字、姓氏、安全帐户管理器 (SAM) 帐户名、SIP 地址或线路统一资源标识符 (URI) 搜索用户。 还可以使用 Lync Server 控制面板或 Active Directory 用户和计算机管理单元搜索用户。
  
## <a name="tasks-you-can-perform"></a>可执行的任务

您可以在“**用户搜索**”控制面板页上执行以下任务：
  
- [搜索用户](http://technet.microsoft.com/library/3b9f6f55-d7a9-46ae-8e10-f221ba0d3bb5.aspx)
    
- [启用或禁用用户](http://technet.microsoft.com/library/12497d00-f665-4a97-be68-854c5a8be4fc.aspx)
    
- [移动用户](ms.lync.lscp.UserMove.md)
    
- [移动所有用户](ms.lync.lscp.UserMoveAll.md)
    
- [将策略分配给用户](http://technet.microsoft.com/library/a4ed0120-d9e5-4eb2-acfd-8de2cb503652.aspx)
    
- [Skype 中的企业语音的用户启用企业服务器](../../../deploy/deploy-enterprise-voice/enable-users-for-enterprise-voice.md)
    
- [为用户配置联盟、 远程用户访问和公共 IM 连接](http://technet.microsoft.com/library/736fcaad-9f95-4896-b767-e199d86a00a4.aspx)
    
- [为用户配置电话](http://technet.microsoft.com/library/4546432e-c839-4517-a2c5-bc0d4d8c6a03.aspx)
    
 
  
## <a name="ui-reference"></a>用户界面参考

下表介绍了“**用户搜索**”页上的菜单、命令、字段和属性。
  
### <a name="user-search"></a>用户搜索

- **搜索**按显示名称、 名字、 姓氏、 SAM 帐户名、 SIP 地址的第一部分搜索用户或线路 URI 的用户帐户。
    
- **LDAP 搜索**通过键入 LDAP 表达式搜索用户。
    
- **搜索用户框**键入的用户数据或您要搜索的 LDAP 表达式。
    
- **查找**单击以显示与您在**搜索用户**框中输入的搜索值匹配的用户。
    
- **打开查询**单击可打开已保存的搜索查询。
    
- **保存查询**单击可保存搜索查询。
    
- **+ 添加筛选器**单击可添加附加搜索条件。
    
- **搜索筛选器字段**选择您要在其筛选搜索结果，选择一个运算符对于查询，然后键入您想要搜索的字符串的字段。
    
- **若要显示的最大用户**键入您想要显示，或使用向上和向下箭头指定数量的搜索结果数。
    
添加附加描述性文本，视情况而定。
  
### <a name="search-results-menus"></a>搜索结果菜单

- **启用用户**单击可打开[用户： 新建 Lync Server 用户](ms.lync.lscp.UserNew.md)对话框中，其中您可将新用户添加到 Skype 业务服务器。
    
    若要添加新的联系人，单击向下箭头，然后选择**启用联系人**以打开[用户： New Contact Objects](ms.lync.lscp.UserNewContact.md)对话框。
    
- **编辑**单击**编辑**，然后单击**显示详细信息**以显示所选用户的详细信息，或单击**选择所有搜索结果**以都选择结果表中显示的所有用户。
    
- **操作**单击**操作**，然后选择想要在搜索结果中所选用户执行的操作。 以下操作有：
    
  - **为 Lync Server 重新启用**临时禁用了后使选定的用户帐户。
    
  - **暂时禁用 Lync server**禁用的用户帐户的 Skype 业务服务器，直到您重新启用它，而无需删除的用户帐户。
    
  - **将策略分配**打开[用户： 分配策略](ms.lync.lscp.UserAssignPolicy.md)对话框中，您可在其中配置分配给用户的策略。
    
  - **查看 PIN 状态**打开[用户： 查看 PIN 状态](ms.lync.lscp.UserViewPin.md)对话框，可显示所选用户的 PIN 数据。
    
  - **设置 PIN**打开[Set PIN](ms.lync.lscp.UserSetPin.md)对话框，其中所选用户设置 PIN。
    
  - **锁定 PIN**锁定用户的 PIN。
    
  - **解锁 PIN**删除用户的 PIN 的锁定。
    
  - **从 Lync Server 中删除**业务服务器从 Skype 中删除的用户帐户。 用户并未从 Active Directory。
    
  - **删除用户证书**删除授予用户的所有证书。
    
  - **移动所选的用户移动到池**打开[Move User](ms.lync.lscp.UserMove.md)对话框，您可以在其中选择一个池移动到所选的用户。
    
  - **移动所有用户移动到池**打开[Move User](ms.lync.lscp.UserMove.md)对话框，您可以在其中选择一个池移动到的所有选定的用户。
    


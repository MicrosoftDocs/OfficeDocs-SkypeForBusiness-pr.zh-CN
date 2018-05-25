---
title: 客户端版本策略创建新的或编辑现有的
ms.author: laurawi
author: LauraWi
manager: serdars
ms.date: 3/23/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.ClientCVPolicyEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e32c6712-6dc9-4de9-8d74-9fdccf3de1ba
description: 可以指定环境中支持的客户端版本。 当两个不同版本的客户端交互时，其中一个客户端的可用功能会受到另一个客户端的功能的限制。 地利用最大的业务服务器 2015 Skype 中包含的功能和改进的整体用户体验，您可以使用客户端版本筛选器来限制在您的环境中使用的客户端版本。 使用客户端版本筛选器还有助于降低支持多个客户端版本的相关成本。
ms.openlocfilehash: 6c1e895dc03d094013f41a34cb21a12a24928172
ms.sourcegitcommit: e577b4bdf3827fdfaf4482928adde177a64e4406
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/24/2018
---
# <a name="client-version-policy-create-new-or-edit-existing"></a>客户端版本策略：创建新的或编辑现有的
 
可以指定环境中支持的客户端版本。 当两个不同版本的客户端交互时，其中一个客户端的可用功能会受到另一个客户端的功能的限制。 地利用最大的业务服务器 2015 Skype 中包含的功能和改进的整体用户体验，您可以使用客户端版本筛选器来限制在您的环境中使用的客户端版本。 使用客户端版本筛选器还有助于降低支持多个客户端版本的相关成本。
  
> [!IMPORTANT]
> 按优先顺序列出筛选器。例如，如果您具有一个筛选器可允许运行版本 1.5 的客户端进行连接，还有另一个筛选器可阻止运行低于 2.0 版本的客户端，则第一个筛选器优先，允许运行版本 1.5 的客户端进行连接。 
  
## <a name="tasks-you-can-perform"></a>可执行的任务

您可以在“**新建客户端版本策略**”或“**编辑客户端版本策略**”页上执行以下任务：
  
- 添加或修改客户端版本策略的名称或描述。
    
- 添加或修改客户端版本策略的客户端版本规则。
    
## <a name="ui-reference"></a>用户界面参考

下表介绍了该页上的菜单、命令、字段和属性。
  
- **范围**标识客户端版本策略的范围 （站点、 池或用户）。
    
- **名称**您可以添加或修改客户端版本策略的名称。
    
- **说明**您可以添加描述以帮助标识客户端版本策略页上的列表中的策略。
    
- **新**您可以向策略添加新的客户端版本规则。
    
- **显示详细信息**此选项可打开一个对话框，您可以在其中更改客户端版本规则的选项。
    
- **删除**此选项从策略中删除选定的客户端版本规则。
    
- **上下箭头**此选项将选定的客户端版本中的规则向上或向下优先级。 规则中列出的顺序进行处理。
    
有关客户端和客户端版本之间的互操作性的详细信息，请参阅规划文档中的[Client Interoperability in Lync 2013 Preview](http://technet.microsoft.com/library/0f126571-91a2-45d5-855c-1e4ddb45fc04.aspx) 。 有关使用客户端版本策略的详细信息，请参阅操作文档中的[指定 the Client Versions Supported in Your Organization](http://technet.microsoft.com/library/d256a581-9a48-4d1a-82cc-2e1f520d7d2e.aspx) 。


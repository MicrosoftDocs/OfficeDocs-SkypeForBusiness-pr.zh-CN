---
title: 客户端版本规则
ms.author: dianef
author: dianef77
manager: serdars
ms.date: 3/23/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.ClientCVPolicyRuleEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6e7e94c2-1475-4334-b8da-716b24a4c255
description: 客户端版本策略由一组客户端版本规则组成。这些规则定义在用户尝试使用特定客户端和客户端版本登录时应采取的操作。
ms.openlocfilehash: 88316487ccd6f061127f92a762ac2d8c17b6a9c7
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="client-version-rule"></a>客户端版本规则
 
客户端版本策略由一组客户端版本规则组成。这些规则定义在用户尝试使用特定客户端和客户端版本登录时应采取的操作。
  
## <a name="tasks-you-can-perform"></a>可执行的任务

您可以在“**新建客户端版本配置**”或“**编辑客户端版本配置**”页上执行以下任务：
  
- 向客户端版本策略添加新规则。
    
- 修改构成现有客户端版本策略的规则
    
## <a name="ui-reference"></a>用户界面参考

下表介绍了该页上的菜单、命令、字段和属性。
  
- **用户代理**您可以从列表中选择客户端类型。 下表定义了用户代理代码。
    
|**客户端名称**|**用户代理**|
|:-----|:-----|
|Lync 2013，Lync 2010 Office Communicator  <br/> |OC  <br/> |
|Lync Web 应用程序中，Communicator Web 访问  <br/> |CWA  <br/> |
|Lync 电话版 Office Communicator 的电话  <br/> |OCPhone  <br/> |
|Communicator Phone Edition 平台  <br/> |CPE  <br/> |
|统一通信平台  <br/> |UCCP  <br/> |
|Lync 2010 Attendee  <br/> |AOC  <br/> |
|Live Meeting 外接程序  <br/> |LiveMeetingAddins  <br/> |
|Office Live Meeting  <br/> |LMC  <br/> |
|Windows Messenger  <br/> |WM  <br/> |
|实时通信客户端  <br/> |RTC  <br/> |
|IPad 的 Lync 2010  <br/> |iPadLync  <br/> |
|IPhone 的 Lync 2010  <br/> |iPhoneLync  <br/> |
|Windows Phone 的 Lync 2010 年  <br/> |WPLync  <br/> |
|诺基亚的 Lync 2010  <br/> |NokiaLync  <br/> |
|Android 的 Lync 2010  <br/> |AndroidLync  <br/> |
|Mobility Service  <br/> |McxService  <br/> |
   
- **版本号**可以指定以下字段，版本号或使用通配符来表示的客户端版本编号。
    
  - **主要版本**指定对应于主要版本的客户机的数量。
    
  - **次要版本**指定对应于客户端的次要版本数。
    
  - **生成**指定对应于客户端的主要和次要版本的内部版本号。
    
  - **更新**指定给客户机的更新版本相对应的编号。
    
- **比较操作**您可以指定您在前面的步骤中指定的客户端版本匹配的操作。 下面的操作有：
    
  - **相同**
    
  - **不是**
    
  - **更高**
    
  - **更高或相同**
    
  - **更低**
    
  - **更低或相同**
    
- **操作**您可以指定要在前面的步骤中的条件满足时执行的操作。 下列操作有：
    
  - **允许**允许客户端登录。
    
  - **允许和升级**允许客户端登录，接收来自 Microsoft 更新或 Windows 服务器更新服务的更新。 仅当用户代理**OC**处于选中状态时，此操作才可用。
    
    > [!NOTE]
    > 选择此操作会导致出现在用户下次登录到业务的 Skype 的通知。 该通知指出有可用更新，即使更新尚未发布到 Windows Server Update Service 或 Microsoft Update。 为了避免混淆，您只应在更新可用后选择此操作。 
  
  - **允许使用 URL**允许客户端登录并显示一条有关另一个客户端版本的下载位置。 可以在“**URL**”字段中指定 URL。
    
  - **块**可以阻止登录客户端。
    
  - **块和升级**可以阻止客户端登录，并允许客户端能够接收来自 Microsoft 更新或 Windows 服务器更新服务的更新。 仅当用户代理**OC**处于选中状态时，此操作才可用。
    
  - **使用 URL 阻止**   阻止客户端登录并显示有关下载其他客户端版本的位置的消息。可以在“**URL**”字段中指定 URL。
    
在客户端和客户端版本之间的互操作性的详细信息，请参阅规划文档中的[Lync 2013 预览中的客户端互操作性](http://technet.microsoft.com/library/0f126571-91a2-45d5-855c-1e4ddb45fc04.aspx)。 有关使用客户端版本配置的详细信息，请参阅操作文档中[修改客户端未显式支持或受限默认动作](http://technet.microsoft.com/library/548dd0f5-62fe-4c3f-8952-2b9fd4c5fff3.aspx)。


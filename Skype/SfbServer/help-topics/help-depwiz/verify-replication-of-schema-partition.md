---
title: 验证架构分区的复制
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 11/17/2014
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.dep.DeployMainVerifySchemaPrep
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0357f230-6d0c-41f1-942c-e14f76e55d31
description: 要验证的架构扩展已被成功复制 Active Directory 域服务林中，请执行以下操作：
ms.openlocfilehash: a5628e369ffc796affe9984cef8ecb1ba044ec8a
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="verify-replication-of-schema-partition"></a>验证架构分区的复制
 
要验证的架构扩展已被成功复制 Active Directory 域服务林中，请执行以下操作：
  
1. 在 Active Directory 域服务林中，其中架构扩展应用作为企业管理员组的成员登录到域控制器 （而不是充当架构主机角色的域控制器）。
    
2. 打开 ADSI 编辑： 单击**开始**，单击**管理工具**，然后单击**ADSI 编辑**。
    
    > [!TIP]
    > 或者，单击**开始**，然后单击**运行**类型**adsiedit.msc**启动 ADSI 编辑。
  
3. 在 Microsoft 管理控制台 (MMC) 树中，如果它尚未被选中，则单击 ADSI 编辑。
    
4. 在“**操作**”菜单上，单击“**连接到**”。
    
5. 在“**连接设置**”对话框中的“**选择一个已知命名上下文**”下，选择“**架构**”，然后单击“**确定**”。
    
6. 在架构容器中下, 搜索 CN = ms RTC SIP SchemaVersion。 如果该对象存在，并**rangeUpper**属性的值是 1150 **rangeLower**属性的值为 3，然后架构已成功更新和复制。 如果不存在此对象，或**rangeUpper**和**rangeLower**属性的值不是作为指定，然后架构未被修改或尚未复制。
    
> [!NOTE]
> 如果复制架构的签还不会显示成功复制，等待约 15 分钟，然后再次进行检查。 活动目录复制是基于松散一致性模型，可能会出现一些复制滞后时间，基于许多因素中的服务器和基础结构。 
  


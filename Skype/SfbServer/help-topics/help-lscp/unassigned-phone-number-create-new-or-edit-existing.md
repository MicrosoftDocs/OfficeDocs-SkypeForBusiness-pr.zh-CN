---
title: 未指定的电话号码创建新模板或编辑现有的
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 11/17/2014
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.VoiceFeaVacantNumEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 58903e40-6b93-40d6-88f8-1201743cd9be
description: 未分配号码是指对于组织有效但尚未分配给用户或电话的电话号码。未分配号码表标识您希望如何处理对未分配号码的调用。
ms.openlocfilehash: b4cdd3d4efad5299b855c546edf2359698ef6a47
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="unassigned-phone-number-create-new-or-edit-existing"></a>未指定的电话号码： 新建或编辑现有的
 
未分配号码是指对于组织有效但尚未分配给用户或电话的电话号码。未分配号码表标识您希望如何处理对未分配号码的调用。
  
> [!IMPORTANT]
> 当您创建新的未分配编号范围或编辑一个现有完成时，单击**确定**以返回到**未分配数**页列出所有数字的范围。 直到您单击**未分配的数**页上的**全部提交****新编号范围未分配**页或**编辑未分配编号 Rage**页所做的更改未提交到数据库。
  
## <a name="ui-reference"></a>用户界面参考

下表介绍了该页上的各个字段。
  
- **名称**键入一个描述性的名称，用于标识未指定编号范围。 保存区域后，无法更改此名称。
    
- **编号范围**在第一个字段中，键入未分配的编号范围的起始数。 在第二个字段中，键入该范围的结束编号。
    
  - 该范围的起始号码必须小于或等于该范围的结束号码。
    
  - 如果号码范围的起始号码或结束号码包含分机号，那么号码范围的起始号码和结束号码都必须包含分机号，并且起始号码和结束号码的分机号必须相同。
    
  - 数量必须匹配的正则表达式 (tel:) ? (\+) ? [1-9] \d {0,17} (; ext = [1-9] \d {0,9}) ?。 这意味着数可能开始与字符串 tel: （如果不指定该字符串它将会自动为您添加），加号 （+） 和数字 1 到 9。 电话号码最长为 17 位数，并可以后跟分机号，格式为 ;ext= 后跟分机号。
    
- **发布服务**选择**发布**公告应用程序处理传入呼叫或**Exchange UM**让 Exchange UM 自动助理处理传入呼叫。
    
- 如果选择**发布****公告服务**：
    
  - **目标服务器的 FQDN**选择运行发布应用程序将处理传入呼叫此未分配的数字范围的应用程序服务的服务 ID。
    
  - **公告**选择通知播放的这个未分配的数字范围。
    
-  如果您选择了**UM Exchange** **发布**服务：
    
  - **自动助理的电话号码**选择交换 UM 自动助理的电话号码。
    
有关公告的特性和功能的详细信息，请参阅规划文档中[规划业务 2015年的 Skype 的发布应用程序](../../plan-your-deployment/enterprise-voice-solution/announcement.md)。 有关使用未分配的数字范围的详细信息，请参阅操作文档中的[配置路由的未指定的电话号码](http://technet.microsoft.com/library/a0650659-dce7-455f-8977-02454bbfa400.aspx)。
  


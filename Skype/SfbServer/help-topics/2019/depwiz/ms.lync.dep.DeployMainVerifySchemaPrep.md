---
title: 验证架构分区的复制
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.dep.DeployMainVerifySchemaPrep
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0357f230-6d0c-41f1-942c-e14f76e55d31
ROBOTS: NOINDEX, NOFOLLOW
description: 若要验证架构扩展已在 Active Directory 域服务林中成功复制，请执行以下操作：
ms.openlocfilehash: 0837191d63bf3a851d1ff69884a0084c81280e7c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "33893607"
---
# <a name="verify-replication-of-schema-partition"></a>验证架构分区的复制
 
若要验证架构扩展已在 Active Directory 域服务林中成功复制，请执行以下操作：
  
1. 在您的 Active Directory 域服务林，其中的架构扩展已应用的 Enterprise Admins 组成员身份登录到域控制器 （而非保留架构主机角色的域控制器）。
    
2. 打开 ADSI Edit： 单击**开始**，单击**管理工具**，然后单击**ADSI 编辑**。
    
    > [!TIP]
    > 或者，单击**开始**，然后单击**运行**键入**adsiedit.msc**来启动 ADSI Edit。
  
3. 在 Microsoft 管理控制台 (MMC) 树中，如果尚未选择它，则单击 ADSI 编辑。
    
4. 在“**操作**”菜单上，单击“**连接到**”。
    
5. 在“**连接设置**”对话框中的“**选择一个已知命名上下文**”下，选择“**架构**”，然后单击“**确定**”。
    
6. 在架构容器下，搜索“CN=ms-RTC-SIP-SchemaVersion”。 如果此对象存在，并且**rangeUpper**属性的值为 1150年， **rangeLower**属性的值为 3，然后架构已成功更新和复制。 如果此对象不存在，或**rangeUpper**和**rangeLower**属性的值不为指定，然后架构未经过修改或尚未复制。
    
> [!NOTE]
> 如果架构的复制您复选尚未不显示成功复制，等待约为 15 分钟，然后再次检查。 Active Directory 复制是基于松散一致性模型和一些复制延迟可能发生，根据多种因素的服务器和基础结构中。 
  


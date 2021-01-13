---
title: 验证架构分区的复制
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.dep.DeployMainVerifySchemaPrep
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: 0357f230-6d0c-41f1-942c-e14f76e55d31
ROBOTS: NOINDEX, NOFOLLOW
description: 若要验证已在 Active Directory 域服务林中成功复制架构扩展，请执行下列操作：
ms.openlocfilehash: 4e4bfdf4fb50366f831f029d8f331551ba906969
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49801562"
---
# <a name="verify-replication-of-schema-partition"></a>验证架构分区的复制
 
若要验证已在 Active Directory 域服务林中成功复制架构扩展，请执行下列操作：
  
1. 登录到域控制器 (在 Active Directory 域服务林中保留架构主机角色) 的域控制器，其中架构扩展已作为 Enterprise Admins 组的成员应用。
    
2. 打开 ADSI Edit：依次单击“开始”、“管理工具”和“ADSI Edit”。
    
    > [!TIP]
    > 或者，通过单击“开始”，再单击“运行”，然后键入 **adsiedit.msc** 来启动 ADSI Edit。
  
3. 在 Microsoft 管理控制台 (MMC) 树中，单击“ADSI Edit”（如果尚未选中）。
    
4. 在 **“操作”** 菜单上，单击 **“连接到”**。
    
5. 在“连接设置”对话框中的“选择一个已知命名上下文”下，选择“架构”，然后单击“确定”。
    
6. 在架构容器下，搜索“CN=ms-RTC-SIP-SchemaVersion”。如果此对象存在，并且 **rangeUpper** 属性的值为 1150，**rangeLower** 属性的值为 3，则说明架构更新和复制成功。如果此对象不存在，或 **rangeUpper** 和 **rangeLower** 属性的值不是指定的值，则说明架构未经过修改或尚未复制。
    
> [!NOTE]
> 如果检查架构复制时未显示复制成功，请等待大约 15 分钟，然后重新检查。 Active Directory 复制基于松散的一致性模型，并且可能会发生一些复制延迟，这基于服务器和基础结构中的许多因素。 
  


---
title: 验证架构分区的复制
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.dep.DeployMainVerifySchemaPrep
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0357f230-6d0c-41f1-942c-e14f76e55d31
ROBOTS: NOINDEX, NOFOLLOW
description: '若要验证架构扩展是否已成功复制到你的 Active Directory 域服务林中, 请执行下列操作:'
ms.openlocfilehash: c8417d4b1df11536f733ad68b1546fb4cf7de0ce
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34303339"
---
# <a name="verify-replication-of-schema-partition"></a>验证架构分区的复制
 
若要验证架构扩展是否已成功复制到你的 Active Directory 域服务林中, 请执行下列操作:
  
1. 在 Active Directory 域服务林中登录到作为企业管理员组成员应用的架构扩展的域控制器 (不包含架构主机角色的域控制器除外)。
    
2. 打开 "ADSI 编辑": 单击 "**开始**", 单击 "**管理工具**", 然后单击 " **ADSI 编辑**"。
    
    > [!TIP]
    > 或者, 单击 "**开始**", 然后单击 "**运行**", 键入 " **ADSIEDIT** " 以启动 "ADSI 编辑"。
  
3. 在 Microsoft 管理控制台 (MMC) 树中, 如果尚未选中它, 请单击 "ADSI 编辑"。
    
4. 在“**操作**”菜单上，单击“**连接到**”。
    
5. 在“**连接设置**”对话框中的“**选择一个已知命名上下文**”下，选择“**架构**”，然后单击“**确定**”。
    
6. 在架构容器下，搜索“CN=ms-RTC-SIP-SchemaVersion”。 如果此对象存在, 并且**rangeUpper**属性的值为 1150, 并且**rangeLower**属性的值为 3, 则架构已成功更新和复制。 如果此对象不存在, 或者**rangeUpper**和**rangeLower**属性的值不是指定的, 则架构未被修改或未复制。
    
> [!NOTE]
> 如果检查架构的复制尚未显示成功复制, 请等待大约15分钟, 然后再次检查。 Active Directory 复制基于松散一致性模型, 并且可能会发生某些复制延迟, 具体取决于服务器和基础结构中的多种因素。 
  


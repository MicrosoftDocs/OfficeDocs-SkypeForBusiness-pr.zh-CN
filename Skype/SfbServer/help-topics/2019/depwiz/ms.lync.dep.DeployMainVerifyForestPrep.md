---
title: 验证林准备的复制
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.dep.DeployMainVerifyForestPrep
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: 94e87632-7c28-43df-9238-f5a47c1c43c0
ROBOTS: NOINDEX, NOFOLLOW
description: 若要确认在林准备期间成功复制全局编录和创建对象，请执行下列操作：
ms.openlocfilehash: 299b738bbfa14ad13825e5c08e87c03167c9f4cc
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49801592"
---
# <a name="verify-replication-of-forest-preparation"></a>验证林准备的复制
 
若要确认在林准备期间成功复制全局编录和创建对象，请执行下列操作：
  
1. 在域控制器 (最好在其他域控制器) 的远程站点中，在运行林准备的林中，打开 **Active Directory 用户和计算机**。
    
2. 在 **“Active Directory 用户和计算机”** 中，展开林或子域的域名。
    
3. 单击 **左侧窗格** 上的"用户"容器，在右侧窗格中查找通用组 CsAdministrator。 如果 CsAdministrator (以 Cs) 开头的其他八个新通用组，则林准备复制已成功完成。
    
4. 如果未显示这些组，可以强制复制或等待 15 分钟后再刷新右侧窗格。显示组后，表明复制完成。
    
> [!TIP]
> 如果要查看由 Skype for Business Server 部署向导创建的日志文件，可以在运行部署向导的计算机上找到这些文件，位于运行该步骤的 Active Directory 域服务用户的 Users 目录中。 例如，如果用户以域 Contoso.net 域管理员身份登录，则日志文件位于：C：\Users\Administrator.Contoso\AppData\Local\Temp 
  


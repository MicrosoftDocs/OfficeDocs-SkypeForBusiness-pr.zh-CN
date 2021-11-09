---
title: 验证林准备的复制
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 2/8/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.dep.DeployMainVerifyForestPrep
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 94e87632-7c28-43df-9238-f5a47c1c43c0
description: 若要确认在林准备期间已成功复制全局编录和创建对象，请执行下列操作：
ms.openlocfilehash: 2105ff54f44a4e5ab58b2509348126920f0823b5
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/08/2021
ms.locfileid: "60862839"
---
# <a name="verify-replication-of-forest-preparation"></a>验证林准备的复制
 
若要确认在林准备期间已成功复制全局编录和创建对象，请执行下列操作：
  
1. 在域控制器 (最好位于其他域控制器) 的远程站点中，在运行林准备的林中，打开 **"Active Directory 用户和计算机"。**
    
2. 在 **“Active Directory 用户和计算机”** 中，展开林或子域的域名。
    
3. 单击左侧 **窗格** 上的"用户"容器，在右侧窗格中查找通用组 CsAdministrator。 如果 CsAdministrator (以 Cs) 开头的其他八个新通用组之间，则林准备复制已成功完成。
    
4. 如果未显示这些组，可以强制复制或等待 15 分钟后再刷新右侧窗格。显示组后，表明复制完成。
    
> [!TIP]
> 如果要查看 Skype for Business Server 部署向导创建的日志文件，可以在运行部署向导的计算机上找到这些文件，位置为运行该步骤的 Active Directory 域服务用户的 Users 目录。 例如，如果用户以域 Contoso.net 的域管理员身份登录，则日志文件位于：C：\Users\Administrator.Contoso\AppData\Local\Temp 
  


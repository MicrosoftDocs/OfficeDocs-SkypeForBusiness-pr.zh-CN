---
title: 验证复制的目录林的准备
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 2/8/2018
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.dep.DeployMainVerifyForestPrep
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 94e87632-7c28-43df-9238-f5a47c1c43c0
description: 要确认具有全局编录的复制和林准备过程期间创建的对象已成功，请执行以下操作：
ms.openlocfilehash: cfb993a9a80bf4b37e76712a58aa6c1fb0c270c3
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="verify-replication-of-forest-preparation"></a>验证复制的目录林的准备
 
要确认具有全局编录的复制和林准备过程期间创建的对象已成功，请执行以下操作：
  
1. 在运行林准备的林中的域控制器上（最好在其他域控制器的远程站点中），打开“**Active Directory 用户和计算机**”。
    
2. 在“**Active Directory 用户和计算机**”中，展开林或子域的域名。
    
3. 单击左侧窗格中的**用户**容器，寻找在右侧窗格中的通用组 CsAdministrator。 如果 CsAdministrator （还有八个其他新通用组开头 Cs），则林准备过程的复制已成功。
    
4. 如果组尚不存在，您可以强制进行复制或等待 15 分钟和刷新右侧窗格。 显示组后，表明复制完成。
    
> [!TIP]
> 如果您想要查看由 Skype 业务服务器部署向导创建的日志文件，您可以部署向导已运行，运行步骤的 Active Directory 域服务用户的用户目录中的计算机上找到它们。 例如，如果用户作为 Contoso.net 域中的域管理员登录，日志文件位于： C:\Users\Administrator.Contoso\AppData\Local\Temp 
  


---
title: 验证林准备的复制
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.dep.DeployMainVerifyForestPrep
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 94e87632-7c28-43df-9238-f5a47c1c43c0
ROBOTS: NOINDEX, NOFOLLOW
description: 若要确认全局编录复制和林准备期间创建的对象已成功，执行以下操作：
ms.openlocfilehash: b755aeb6d7d9fe79940472b7b5883d1fdacaeee9
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "33893621"
---
# <a name="verify-replication-of-forest-preparation"></a>验证林准备的复制
 
若要确认全局编录复制和林准备期间创建的对象已成功，执行以下操作：
  
1. 在运行林准备的林中的域控制器上（最好在其他域控制器的远程站点中），打开“**Active Directory 用户和计算机**”。
    
2. 在“**Active Directory 用户和计算机**”中，展开林或子域的域名。
    
3. 单击左侧窗格上的**用户**容器，并在右侧窗格中的通用组 CsAdministrator 查找。 如果存在 CsAdministrator （之间八个其他新通用组开头 Cs），林准备的复制已成功。
    
4. 如果组尚不存在，您可以强制执行复制或等待 15 分钟和刷新右侧窗格。 显示组后，表明复制完成。
    
> [!TIP]
> 如果您想要查看日志文件中的业务 Server 部署向导创建的 Skype，您可以在其中运行部署向导中，运行该步骤的 Active Directory 域服务用户的用户目录中的计算机上找到这些。 例如，如果用户登录以域管理员的域 Contoso.net 中，日志文件位于： C:\Users\Administrator.Contoso\AppData\Local\Temp 
  


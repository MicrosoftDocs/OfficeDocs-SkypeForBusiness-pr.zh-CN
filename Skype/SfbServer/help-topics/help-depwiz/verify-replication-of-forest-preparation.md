---
title: 验证林准备的复制
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/8/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.dep.DeployMainVerifyForestPrep
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 94e87632-7c28-43df-9238-f5a47c1c43c0
description: 若要在林准备中确认全局编录和创建对象的复制是否成功，请执行下列操作：
ms.openlocfilehash: 5f02707b8a98ec9869aa2b2b4d867bb45351371b
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41823276"
---
# <a name="verify-replication-of-forest-preparation"></a>验证林准备的复制
 
若要在林准备中确认全局编录和创建对象的复制是否成功，请执行下列操作：
  
1. 在运行林准备的林中的域控制器上（最好在其他域控制器的远程站点中），打开“**Active Directory 用户和计算机**”。
    
2. 在“**Active Directory 用户和计算机**”中，展开林或子域的域名。
    
3. 单击左侧窗格中的 "**用户**" 容器，然后在右侧窗格中查找 "通用组" CsAdministrator。 如果 CsAdministrator （在八个其他以 Cs 开头的新通用组中）存在，则林准备复制已成功。
    
4. 如果组尚不存在，则可以强制执行复制或等待15分钟，并刷新右侧窗格。 显示组后，表明复制完成。
    
> [!TIP]
> 如果您想要查看由 Skype for Business 服务器部署向导创建的日志文件，可以在运行该步骤的 Active Directory 域服务用户的用户目录中的 "部署向导" 计算机上找到它们。 例如，如果用户在域 Contoso.net 中以域管理员身份登录，则日志文件位于： C:\Users\Administrator.Contoso\AppData\Local\Temp 
  


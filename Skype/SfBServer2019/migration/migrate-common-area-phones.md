---
title: 迁移公共区域电话
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 公共区域电话是最常位于共享工作区或公共区域（例如会议厅、厨房或工厂车间）的 IP 电话。 公用区域电话无需连接到计算机，Skype for Business Server UC (功能) 通信。 在将部署迁移到 Skype for Business Server 2019 之后，还必须迁移与旧公用区域部署关联的联系电话。 使用Skype for Business Server命令行管理程序，首先检索与旧版公用区域电话关联的所有联系对象，然后将这些对象移动到 Skype for Business Server 2019 池。
ms.openlocfilehash: 808e874216fac97b01face6efa7aae00e269b74ee0f009b106f872a33a6d6261
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2021
ms.locfileid: "54340428"
---
# <a name="migrate-common-area-phones"></a>迁移公共区域电话

公共区域电话是最常位于共享工作区或公共区域（例如会议厅、厨房或工厂车间）的 IP 电话。 公用区域电话无需连接到计算机，Skype for Business Server UC (功能) 通信。 在将部署迁移到 Skype for Business Server 2019 之后，还必须迁移与旧公用区域部署关联的联系电话。 使用Skype for Business Server命令行管理程序，首先检索与旧版公用区域电话关联的所有联系对象，然后将这些对象移动到 Skype for Business Server 2019 池。
  
### <a name="migrate-common-area-phones"></a>迁移公共区域电话

1. 从 Skype for Business Server 2019 前端服务器中，打开"Skype for Business Server命令行管理程序"。
    
2. 从命令行键入：
    
   ```PowerShell
   Get-CsCommonAreaPhone -Filter {RegistrarPool -eq "pool01.contoso.net"} | Move-CsCommonAreaPhone -Target pool02.contoso.net
   ```

3. 若要验证所有联系对象是否都移至 Skype for Business Server 2019 池，请从命令行Skype for Business Server命令行管理程序键入以下内容：
    
   ```PowerShell
   Get-CsCommonAreaPhone -Filter {RegistrarPool -eq "pool02.contoso.net"}
   ```

    验证所有联系对象现在是否都与 Skype for Business Server 2019 池关联。
    


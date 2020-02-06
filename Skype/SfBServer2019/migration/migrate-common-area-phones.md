---
title: 迁移公共区域电话
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 常见的区域电话是指通常位于共享工作区或通用区域（如大厅、厨房或工厂地板）的 IP 电话。 常用的区域电话无需连接到计算机即可提供 Skype for business 服务器统一通信（UC）功能。 将部署迁移到 Skype for business Server 2019 后，还必须迁移与旧式公共区域电话相关联的联系人对象。 使用 Skype for Business 服务器管理外壳，你将首先检索与旧式公共区域电话相关联的所有联系人对象，然后将这些对象移动到 Skype for Business Server 2019 池。
ms.openlocfilehash: 5110f91788d09f644e20680f91f1cbafe146bdd6
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41813560"
---
# <a name="migrate-common-area-phones"></a>迁移公共区域电话

常见的区域电话是指通常位于共享工作区或通用区域（如大厅、厨房或工厂地板）的 IP 电话。 常用的区域电话无需连接到计算机即可提供 Skype for business 服务器统一通信（UC）功能。 将部署迁移到 Skype for business Server 2019 后，还必须迁移与旧式公共区域电话相关联的联系人对象。 使用 Skype for Business Server 命令行管理程序，将首先检索与旧式公共区域电话相关联的所有联系人对象，然后将这些对象移动到 Skype for business Server 2019 池。
  
### <a name="migrate-common-area-phones"></a>迁移公共区域电话

1. 从 Skype for business 服务器2019前端服务器，打开 Skype for business Server 命令行管理程序。
    
2. 在命令行中，键入以下内容：
    
   ```PowerShell
   Get-CsCommonAreaPhone -Filter {RegistrarPool -eq "pool01.contoso.net"} | Move-CsCommonAreaPhone -Target pool02.contoso.net
   ```

3. 若要验证是否已将所有联系人对象移动到 Skype for business Server 2019 池，请从 Skype for business 服务器管理外壳键入以下内容：
    
   ```PowerShell
   Get-CsCommonAreaPhone -Filter {RegistrarPool -eq "pool02.contoso.net"}
   ```

    验证所有联系人对象现已与 Skype for Business Server 2019 池相关联。
    


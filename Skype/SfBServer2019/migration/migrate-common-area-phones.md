---
title: 迁移公用区域电话
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 公用区域电话是 IP 大多数通常位于共享工作区或公共区域电话如会议室、 厨房或工厂基底。 公用区域电话不需要连接到计算机以提供业务服务器 Skype 统一通信 (UC) 功能。 迁移后部署到 Skype 的业务服务器 2019年，您必须迁移与旧版公用区域电话联系对象。 Skype 用于业务 Server 命令行管理程序将先检索与旧的公用区域电话，关联的所有联系对象，然后将这些对象移动到业务服务器 2019年池的 Skype。
ms.openlocfilehash: 6d5adebd4ab1b4cb79d79f4049c7d7456bb07a29
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/24/2018
ms.locfileid: "25028024"
---
# <a name="migrate-common-area-phones"></a>迁移公用区域电话

公用区域电话是 IP 大多数通常位于共享工作区或公共区域电话如会议室、 厨房或工厂基底。 公用区域电话不需要连接到计算机以提供业务服务器 Skype 统一通信 (UC) 功能。 迁移后部署到 Skype 的业务服务器 2019年，您必须迁移与旧版公用区域电话联系对象。 使用 Skype 业务 Server 命令行管理程序，您将先检索与旧的公用区域电话，关联的所有联系对象，然后将这些对象移动到业务服务器 2019年池 Skype。
  
### <a name="migrate-common-area-phones"></a>迁移公用区域电话

1. 从业务服务器 2019年前端服务器的 Skype，打开业务 Server 命令行管理程序 Skype。
    
2. 从命令行中，键入以下命令：
    
  ```
  Get-CsCommonAreaPhone -Filter {RegistrarPool -eq "pool01.contoso.net"} | Move-CsCommonAreaPhone -Target pool02.contoso.net
  ```

3. 若要验证的所有联系对象已移至 Skype 业务服务器 2019年池，从业务 Server 命令行管理程序 Skype 键入以下命令：
    
  ```
  Get-CsCommonAreaPhone -Filter {RegistrarPool -eq "pool02.contoso.net"}
  ```

    验证所有联系对象现在是否与业务服务器 2019年池 Skype 关联。
    


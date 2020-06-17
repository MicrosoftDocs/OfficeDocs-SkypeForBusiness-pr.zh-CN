---
title: 配置受信任应用程序服务器
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
description: 在混合环境中，如果创建新的受信任应用程序服务器，则必须将下一个跃点池设置为 Skype for Business Server 2019 池。 在混合环境中，旧版池和 Skype for Business Server 2019 池都将显示在下拉列表中。 此环境不支持选择旧池。
ms.openlocfilehash: 1c0aac1efa4f83a81ccf2f3bb5ecbc925ee58839
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/16/2020
ms.locfileid: "44753942"
---
# <a name="configure-trusted-application-servers"></a>配置受信任应用程序服务器

在混合环境中，如果创建新的受信任应用程序服务器，则必须将下一个跃点池设置为 Skype for Business Server 2019 池。 在混合环境中，旧版池和 Skype for Business Server 2019 池都将显示在下拉列表中。 此环境不支持选择旧池。
  
> [!IMPORTANT]
> 如果要迁移受信任的应用程序服务器，还应更新正在使用的 UCMA 的版本。 如果为 Skype for business Server 2019 创建了新的受信任应用程序池，则应将 UCMA 更新为 Skype for Business Server 2019 附带的版本或可用的最新版本。 
  
### <a name="select-skype-for-business-server-2019-as-next-hop-when-creating-a-trusted-application-server"></a>创建受信任的应用程序服务器时，选择 "Skype for Business Server 2019" 作为下一个跃点

1. 打开拓扑生成器。
    
2. 在左窗格中，右键单击 "**受信任的应用程序服务器**"，然后单击 "**新建受信任应用程序池**"。
    
3. 输入受信任的应用程序池的**池 FQDN** ，并选择是单服务器还是多服务器。 
    
4. 单击“**下一步**”。
    
5. 在 "**选择下一个跃点**" 页上的列表中，选择 "Skype For business Server 2019 前端池"。 
    
6. 单击“完成”****。
    
7. 选择顶部节点**Skype For Business Server**，并从 "**操作**" 菜单中选择 "**发布**"。
    
    验证是否已成功创建**受信任的应用程序池**，并将其与正确的前端池关联。 
    


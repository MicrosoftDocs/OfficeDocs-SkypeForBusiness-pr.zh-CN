---
title: 配置受信任应用程序服务器
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 在混合环境中，如果您创建一个新的受信任应用程序服务器，必须设置为 Skype 业务服务器 2019年池的下一个跃点池。 在混合环境中，旧池和业务服务器 2019年池 Skype 显示在下拉列表。 不支持选择旧池。
ms.openlocfilehash: 79f4de527008d2d9bf295fcb82eee433d04a1691
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/27/2019
ms.locfileid: "30890886"
---
# <a name="configure-trusted-application-servers"></a>配置受信任应用程序服务器

在混合环境中，如果您创建一个新的受信任应用程序服务器，必须设置为 Skype 业务服务器 2019年池的下一个跃点池。 在混合环境中，旧池和业务服务器 2019年池 Skype 显示在下拉列表中。 不支持选择旧池。
  
> [!IMPORTANT]
> 如果您要迁移的受信任应用程序服务器，则还应该更新的 UCMA 您使用的版本。 如果您在为业务服务器 2019年的 Skype 创建一个新的受信任应用程序池，您应更新到附带的业务服务器 2019 Skype 的版本或最新版本的 UCMA。 
  
### <a name="select-skype-for-business-server-2019-as-next-hop-when-creating-a-trusted-application-server"></a>Skype 的业务服务器 2019年时选择作为下一个跃点创建受信任应用程序服务器

1. 打开拓扑生成器。
    
2. 在左窗格中，右键单击**受信任应用程序服务器**，然后单击**新建受信任应用程序池**。
    
3. 输入受信任应用程序池的**池 FQDN** ，并选择该池是单服务器还是多服务器。 
    
4. 单击" **下一步**"。
    
5. 在**选择下一个跃点**页上，从列表中，选择 Business Server 2019 前端池的 Skype。 
    
6. 单击“**完成**”。
    
7. 选择顶层节点**Skype 业务服务器**，并从**操作**菜单中，选择**发布**。
    
    验证**受信任应用程序池**已成功创建且与正确的前端池关联。 
    


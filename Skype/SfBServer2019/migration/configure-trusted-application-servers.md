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
ms.localizationpriority: medium
description: 在混合环境中，如果创建新的受信任应用程序服务器，则必须将下一个跃点池设置为 2019 Skype for Business Server池。 在混合环境中，旧池和 Skype for Business Server 2019 池都显示在下拉列表中。 此环境不支持选择旧池。
ms.openlocfilehash: 9965af757a570cfd787bb482a932d2817fd07ab0
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/26/2021
ms.locfileid: "58584466"
---
# <a name="configure-trusted-application-servers"></a>配置受信任应用程序服务器

在混合环境中，如果创建新的受信任应用程序服务器，则必须将下一个跃点池设置为 2019 Skype for Business Server池。 在混合环境中，旧池和 Skype for Business Server 2019 池都显示在下拉列表中。 此环境不支持选择旧池。
  
> [!IMPORTANT]
> 如果要迁移受信任应用程序服务器，还应更新使用的 UCMA 版本。 如果为 Skype for Business Server 2019 创建新的受信任应用程序池，您应将 UCMA 更新为 Skype for Business Server 2019 中包含的版本或可用的最新版本。 
  
### <a name="select-skype-for-business-server-2019-as-next-hop-when-creating-a-trusted-application-server"></a>在创建受Skype for Business Server应用程序服务器时，选择"2019 Skype for Business Server 2019"作为下一个跃点

1. 打开拓扑生成器。
    
2. 在左窗格中，右键单击"**受信任的应用程序服务器**"，然后单击"**新建受信任应用程序池"。**
    
3. 输入 **受信任服务器的池 FQDN** 应用程序池并选择它是单服务器还是多服务器。 
    
4. 单击“**下一步**”。
    
5. 在"**选择下一个跃** 点"页上，从列表中选择"Skype for Business Server 2019 前端池"。 
    
6. 单击“完成”。
    
7. Select the top node **Skype for Business Server**， and from the **Action** menu select **Publish**.
    
    确认已成功 **创建受** 信任应用程序池，并且与正确的前端池关联。 
    


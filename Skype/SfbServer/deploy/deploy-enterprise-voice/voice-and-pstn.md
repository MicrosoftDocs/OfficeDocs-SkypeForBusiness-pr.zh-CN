---
title: 在呼叫中配置语音策略、PSTN 用法记录和Skype for Business
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 1e5a15f9-6f42-4dc6-baaa-24daf54afc4d
description: 摘要：了解如何在部署中配置语音策略、PSTN 用法记录和Skype for Business Server。
ms.openlocfilehash: 62fcd557a0cdbaf8064e49f7c1c695f0f6f31880
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/04/2021
ms.locfileid: "60759054"
---
# <a name="configure-voice-policies-pstn-usage-records-and-voice-routes-in-skype-for-business"></a>在呼叫中配置语音策略、PSTN 用法记录和Skype for Business
 
**摘要：** 了解如何在客户端部署中配置语音策略、PSTN 用法记录和Skype for Business Server。
  
语音策略、PSTN 用法记录和语音路由是一个有机整体。可以通过选择一组呼叫功能，然后为策略分配一组 PSTN 用法记录来配置语音策略，这些记录指定为分配了语音策略的用户或组授予哪些权限。系统还向语音路由分配 PSTN 用法记录，这些记录用于将路由与有权使用它们的用户进行匹配。也就是说，用户只能发出使用用户对于其有匹配的 PSTN 用法记录的路由的呼叫。
  
通过配置包含相应的 PSTN 用法记录的语音策略来启动新企业语音部署的建议工作流，然后将相应的路由关联到每个 PSTN 用法记录。 
  
> [!NOTE]
> 您还可以创建具有  *用户作用域的*  语音策略，并将其分配给单个用户或组。
  
有关执行上述各项任务的详细步骤，请参阅本节中的过程。
  
## <a name="in-this-section"></a>本节内容

- [创建或修改语音策略，并配置 PSTN 用法Skype for Business](voice-policy-and-pstn-usage-records.md)
    
- [配置语音邮件转义Skype for Business](configure-voice-mail-escape.md)
    
- [查看 PSTN 用法记录Skype for Business](view-pstn-usage-records.md)
    
- [Create or modify a voice route in Skype for Business](create-or-modify-a-voice-route.md)
    
- [导出或导入语音路由配置文件Skype for Business](voice-route-configuration-import-export.md)
    
- [在语音路由配置中发布待处理Skype for Business](voice-route-config-changes.md)
    


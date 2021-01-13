---
title: 在 Skype for Business 中配置语音策略、PSTN 用法记录和语音路由
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 1e5a15f9-6f42-4dc6-baaa-24daf54afc4d
description: 摘要：了解如何在 Skype for Business Server 中配置语音策略、PSTN 用法记录和语音路由。
ms.openlocfilehash: f8c9f75f24a06b210a1c17ed11a1485ab5158f3d
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49830442"
---
# <a name="configure-voice-policies-pstn-usage-records-and-voice-routes-in-skype-for-business"></a>在 Skype for Business 中配置语音策略、PSTN 用法记录和语音路由
 
**摘要：** 了解如何在 Skype for Business Server 中配置语音策略、PSTN 用法记录和语音路由。
  
语音策略、PSTN 用法记录和语音路由是一个有机整体。可以通过选择一组呼叫功能，然后为策略分配一组 PSTN 用法记录来配置语音策略，这些记录指定为分配了语音策略的用户或组授予哪些权限。系统还向语音路由分配 PSTN 用法记录，这些记录用于将路由与有权使用它们的用户进行匹配。也就是说，用户只能发出使用用户对于其有匹配的 PSTN 用法记录的路由的呼叫。
  
通过配置包含相应的 PSTN 用法记录的语音策略来启动新企业语音部署的建议工作流，然后将相应的路由关联到每个 PSTN 用法记录。 
  
> [!NOTE]
> 您还可以创建具有  *用户作用域的*  语音策略，并将其分配给单个用户或组。
  
有关执行上述各项任务的详细步骤，请参阅本节中的过程。
  
## <a name="in-this-section"></a>本节内容

- [在 Skype for Business 中创建或修改语音策略和配置 PSTN 用法记录](voice-policy-and-pstn-usage-records.md)
    
- [在 Skype for Business 中配置语音邮件转义](configure-voice-mail-escape.md)
    
- [在 Skype for Business 中查看 PSTN 用法记录](view-pstn-usage-records.md)
    
- [在 Skype for Business 中创建或修改语音路由](create-or-modify-a-voice-route.md)
    
- [在 Skype for Business 中导出或导入语音路由配置文件](voice-route-configuration-import-export.md)
    
- [在 Skype for Business 中发布对语音路由配置的挂起更改](voice-route-config-changes.md)
    


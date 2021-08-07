---
title: 在部署中配置辅助位置信息Skype for Business Server
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
ms.assetid: 083ffbc6-7c18-4141-85f9-8825b62c3d10
description: 在) 中为 E9-1-1 (SLS Skype for Business Server 企业语音辅助位置源。
ms.openlocfilehash: 9fe548c30dd7f90f854143a9d3e8261214f9c837a692a0afe07173ac98a730b4
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2021
ms.locfileid: "54305894"
---
# <a name="configure-a-secondary-location-information-service-in-skype-for-business-server"></a>在部署中配置辅助位置信息Skype for Business Server
 
在) 中为 E9-1-1 (SLS Skype for Business Server 企业语音辅助位置源。 
  
Skype for Business Server提供了一个 Web 服务接口，可用于将位置信息服务指向 SLS 数据库 (辅助) 源。 连接到 SLS 数据库的 Web 服务接口必须符合位置信息服务 WSDL。 如果同时配置了位置数据库和辅助位置数据库，则位置信息服务将首先查询位置数据库，如果未找到匹配项，则从客户端向 SLS 数据库发送位置请求。 如果位置存在于 SLS 中，则位置信息服务会向客户端发送回该位置。 
  
### <a name="to-configure-a-secondary-location-database"></a>配置辅助位置数据库

1. 启动命令行Skype for Business Server：单击"开始"，单击"所有程序"，单击 **"Skype for Business 2015"，** 然后单击"Skype for Business Server **命令行管理程序"。**
    
2. 运行以下 cmdlet 为辅助位置数据库位置配置 URL。 
    
   ```powershell
   Set-CsWebServiceConfiguration -SecondaryLocationSourceURL "<web service url>" 
   ```

## <a name="see-also"></a>另请参阅

[Set-CsWebServiceConfiguration](/powershell/module/skype/set-cswebserviceconfiguration?view=skype-ps)
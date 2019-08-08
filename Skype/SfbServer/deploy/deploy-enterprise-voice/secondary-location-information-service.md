---
title: 在 Skype for Business 服务器中配置辅助位置信息服务
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 083ffbc6-7c18-4141-85f9-8825b62c3d10
description: 在 Skype for business Server Enterprise Voice 中为 E9 配置辅助位置源 (SLS) 数据库。
ms.openlocfilehash: 47dd4015cde79536323cee3edc04ed546459a3f0
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/07/2019
ms.locfileid: "36240163"
---
# <a name="configure-a-secondary-location-information-service-in-skype-for-business-server"></a>在 Skype for Business 服务器中配置辅助位置信息服务
 
在 Skype for business Server Enterprise Voice 中为 E9 配置辅助位置源 (SLS) 数据库。 
  
Skype for Business 服务器提供可用于将位置信息服务指向辅助位置源 (SLS) 数据库的 web 服务界面。 连接到 SLS 数据库的 web 服务接口必须符合 Location 信息服务 WSDL。 如果同时配置了位置数据库和辅助位置数据库, 则位置信息服务首先查询位置数据库, 如果未找到匹配项, 则将位置请求从客户端发送到 SLS 数据库。 如果该位置存在于 SLS 中, 则位置信息服务随后会将该位置发送回客户端。 
  
### <a name="to-configure-a-secondary-location-database"></a>配置辅助位置数据库

1. 启动 Skype for Business Server 命令行管理程序：依次单击“开始”****、“所有程序”**** 和“Skype for Business 2015”****，然后单击“Skype for Business Server 命令行管理程序”****。
    
2. 运行以下 cmdlet 为辅助位置数据库位置配置 URL。 
    
   ```
   Set-CsWebServiceConfiguration -SecondaryLocationSourceURL "<web service url>" 
   ```

## <a name="see-also"></a>另请参阅

[Set-CsWebServiceConfiguration](https://docs.microsoft.com/powershell/module/skype/set-cswebserviceconfiguration?view=skype-ps)


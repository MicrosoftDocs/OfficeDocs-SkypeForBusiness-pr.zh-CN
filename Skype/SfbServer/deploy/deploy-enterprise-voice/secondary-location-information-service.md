---
title: 在 Skype for Business Server 2015 中配置辅助位置信息服务
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 8/17/2015
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: 083ffbc6-7c18-4141-85f9-8825b62c3d10
description: 为业务服务器企业语音 E9-1-1 在 Skype 的配置辅助位置源 (SLS) 数据库。
ms.openlocfilehash: 03de4369b8473142e7a76e3698bb9fe7f129d546
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="configure-a-secondary-location-information-service-in-skype-for-business-server-2015"></a>在 Skype for Business Server 2015 中配置辅助位置信息服务
 
为业务服务器企业语音 E9-1-1 在 Skype 的配置辅助位置源 (SLS) 数据库。 
  
Skype 业务服务器提供 web 服务接口，您可以使用指向辅助位置源 (SLS) 数据库的位置信息服务。 对 SLS 数据库连接的 web 服务接口必须符合位置信息服务 WSDL。 如果配置了一个位置数据库和辅助位置数据库，位置信息服务首先查询位置数据库，并如果不找到任何匹配项，则请从客户端发送位置请求，对 SLS 数据库。 如果该位置位于 SLS，位置信息服务然后将位置发送回客户端。 
  
### <a name="to-configure-a-secondary-location-database"></a>配置辅助位置数据库

1. 启动 Skype for Business Server 命令行管理程序：依次单击“**开始**”、“**所有程序**”和“**Skype for Business 2015**”，然后单击“**Skype for Business Server 命令行管理程序**”。
    
2. 运行以下 cmdlet 为辅助位置数据库位置配置 URL。 
    
   ```
   Set-CsWebServiceConfiguration -SecondaryLocationSourceURL "<web service url>" 
   ```

## <a name="see-also"></a>另请参阅

#### 

[一组 CsWebServiceConfiguration](https://docs.microsoft.com/powershell/module/skype/set-cswebserviceconfiguration?view=skype-ps)


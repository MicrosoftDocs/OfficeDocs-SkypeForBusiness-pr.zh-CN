---
title: 在 Skype for Business Server 2015 中配置辅助位置信息服务
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 8/17/2015
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 083ffbc6-7c18-4141-85f9-8825b62c3d10
description: 为业务 Server 企业语音的 E9-1-1 在 Skype 配置辅助位置源 （另外） 数据库。
ms.openlocfilehash: 4eaab1b6dfaae9b1298cce3544d89f8b6724733e
ms.sourcegitcommit: fa61d0b380a6ee559ad78e06bba85bc28d1045a6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/03/2018
---
# <a name="configure-a-secondary-location-information-service-in-skype-for-business-server-2015"></a>在 Skype for Business Server 2015 中配置辅助位置信息服务
 
为业务 Server 企业语音的 E9-1-1 在 Skype 配置辅助位置源 （另外） 数据库。 
  
Skype 业务服务器提供了可用于指向辅助位置源 （另外） 数据库的位置信息服务的 web 服务接口。 连接到另外数据库的 web 服务界面必须符合位置信息服务 WSDL。 如果配置位置数据库和辅助位置数据库，位置信息服务将首先查询位置数据库，并如果未找到匹配，请从客户端发送位置请求，另外数据库。 如果位置存在于另外，位置信息服务然后向客户端发送位置。 
  
### <a name="to-configure-a-secondary-location-database"></a>配置辅助位置数据库

1. 启动 Skype for Business Server 命令行管理程序：依次单击“**开始**”、“**所有程序**”和“**Skype for Business 2015**”，然后单击“**Skype for Business Server 命令行管理程序**”。
    
2. 运行以下 cmdlet 为辅助位置数据库位置配置 URL。 
    
   ```
   Set-CsWebServiceConfiguration -SecondaryLocationSourceURL "<web service url>" 
   ```

## <a name="see-also"></a>另请参阅

#### 

[通过 Set-cswebserviceconfiguration](https://docs.microsoft.com/powershell/module/skype/set-cswebserviceconfiguration?view=skype-ps)


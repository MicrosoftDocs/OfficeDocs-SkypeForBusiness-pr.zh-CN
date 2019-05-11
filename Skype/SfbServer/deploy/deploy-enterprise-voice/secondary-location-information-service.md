---
title: 在 Skype for Business Server 中配置的辅助位置信息服务
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 083ffbc6-7c18-4141-85f9-8825b62c3d10
description: 为业务 Server 企业语音的 E9-1-1 在 Skype 配置辅助位置源 （另外） 数据库。
ms.openlocfilehash: 047fd1a7dca0c4c2b76d01fd0c5d67230246441e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "33892291"
---
# <a name="configure-a-secondary-location-information-service-in-skype-for-business-server"></a>在 Skype for Business Server 中配置的辅助位置信息服务
 
为业务 Server 企业语音的 E9-1-1 在 Skype 配置辅助位置源 （另外） 数据库。 
  
Skype 业务服务器提供了可用于指向辅助位置源 （另外） 数据库的位置信息服务的 web 服务接口。 连接到另外数据库的 web 服务界面必须符合位置信息服务 WSDL。 如果配置位置数据库和辅助位置数据库，位置信息服务将首先查询位置数据库，并如果未找到匹配，请从客户端发送位置请求，另外数据库。 如果位置存在于另外，位置信息服务然后向客户端发送位置。 
  
### <a name="to-configure-a-secondary-location-database"></a>配置辅助位置数据库

1. 启动 Skype for Business Server 命令行管理程序：依次单击“开始”****、“所有程序”**** 和“Skype for Business 2015”****，然后单击“Skype for Business Server 命令行管理程序”****。
    
2. 运行以下 cmdlet 为辅助位置数据库位置配置 URL。 
    
   ```
   Set-CsWebServiceConfiguration -SecondaryLocationSourceURL "<web service url>" 
   ```

## <a name="see-also"></a>另请参阅

[通过 Set-cswebserviceconfiguration](https://docs.microsoft.com/powershell/module/skype/set-cswebserviceconfiguration?view=skype-ps)


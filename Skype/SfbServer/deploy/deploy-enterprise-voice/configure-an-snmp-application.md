---
title: 在 Skype for Business Server 中配置 SNMP 应用程序
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: c4b4a736-3b2e-45b9-a965-19d22161ad57
description: 配置 SNMP 应用程序以使用 E9-1-1 在 Skype 业务 Server 企业语音。
ms.openlocfilehash: f45666708b2f5bb3065631bbb4ab38ee88082517
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/27/2019
ms.locfileid: "30898597"
---
# <a name="configure-an-snmp-application-in-skype-for-business-server"></a>在 Skype for Business Server 中配置 SNMP 应用程序
 
配置 SNMP 应用程序以使用 E9-1-1 在 Skype 业务 Server 企业语音。 
  
Skype 业务服务器包括可用于连接到简单网络管理协议 (SNMP) 应用程序匹配 MAC 地址与端口和交换机信息的位置信息服务的标准 web 服务接口。 
  
如果安装 SNMP 应用程序和位置信息服务未能找到匹配项的位置数据库中，位置信息服务自动使用客户端提供的 MAC 地址查询应用程序。 位置信息服务然后使用 SNMP 应用程序返回的端口和交换机信息重新查询位置数据库。
  
> [!NOTE]
> MAC 地址不在运行 Windows 8 的计算机上可用。 
  
### <a name="to-configure-the-snmp-application-url"></a>配置 SNMP 应用程序 URL

1.  启动 Skype for Business Server 命令行管理程序：依次单击“开始”****、“所有程序”**** 和“Skype for Business 2015”****，然后单击“Skype for Business Server 命令行管理程序”****。
    
2. 运行以下 cmdlet 为 SNMP 应用程序配置 URL。 
    
   ```
   Set-CsWebServiceConfiguration -MACResolverUrl "<SNMP application url>" 
   ```

## <a name="see-also"></a>另请参阅

[通过 Set-cswebserviceconfiguration](https://docs.microsoft.com/powershell/module/skype/set-cswebserviceconfiguration?view=skype-ps)


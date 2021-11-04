---
title: 在服务器中配置 SNMP Skype for Business Server
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
ms.assetid: c4b4a736-3b2e-45b9-a965-19d22161ad57
description: 将 SNMP 应用程序配置为在 Skype for Business Server 企业语音 中与 E9-1-1 一Skype for Business Server 企业语音。
ms.openlocfilehash: b033a25d16e5f9ffae47111dbd0929441a735796
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/04/2021
ms.locfileid: "60741448"
---
# <a name="configure-an-snmp-application-in-skype-for-business-server"></a>在服务器中配置 SNMP Skype for Business Server
 
将 SNMP 应用程序配置为在 Skype for Business Server 企业语音 中与 E9-1-1 一Skype for Business Server 企业语音。 
  
Skype for Business Server包括一个标准的 Web 服务接口，可用于将位置信息服务连接到与 MAC 地址与端口和交换机信息匹配的简单网络管理协议 (SNMP) 应用程序。 
  
如果安装了 SNMP 应用程序，而位置信息服务在位置数据库中找不到匹配项，则位置信息服务将自动使用客户端提供的 MAC 地址查询该应用程序。 然后，位置信息服务使用 SNMP 应用程序返回的端口和交换机信息再次查询位置数据库。
  
> [!NOTE]
> MAC 地址在运行 MAC 地址的计算机上Windows 8。 
  
### <a name="to-configure-the-snmp-application-url"></a>配置 SNMP 应用程序 URL

1.  启动命令行Skype for Business Server：单击"开始"，单击"所有程序"，单击 **"Skype for Business 2015"，** 然后单击"Skype for Business Server **命令行管理程序"。**
    
2. 运行以下 cmdlet 为 SNMP 应用程序配置 URL。 
    
   ```powershell
   Set-CsWebServiceConfiguration -MACResolverUrl "<SNMP application url>" 
   ```

## <a name="see-also"></a>另请参阅

[Set-CsWebServiceConfiguration](/powershell/module/skype/set-cswebserviceconfiguration?view=skype-ps)
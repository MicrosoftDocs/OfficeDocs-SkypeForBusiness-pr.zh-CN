---
title: 在 Skype for Business Server 中配置 SNMP 应用程序
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
ms.assetid: c4b4a736-3b2e-45b9-a965-19d22161ad57
description: 将 SNMP 应用程序配置为与 Skype for Business Server 企业语音 中的 E9-1-1 一企业语音。
ms.openlocfilehash: eb1947f24968dccc6f45b6d8ea3a7df42282a58f
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49804152"
---
# <a name="configure-an-snmp-application-in-skype-for-business-server"></a>在 Skype for Business Server 中配置 SNMP 应用程序
 
将 SNMP 应用程序配置为与 Skype for Business Server 企业语音 中的 E9-1-1 一企业语音。 
  
Skype for Business Server 包括一个标准 Web 服务接口，可用于将位置信息服务连接到与 MAC 地址与端口和交换机信息匹配的简单网络管理协议 (SNMP) 应用程序。 
  
如果安装了 SNMP 应用程序，而位置信息服务在位置数据库中找不到匹配项，则位置信息服务将自动使用客户端提供的 MAC 地址查询该应用程序。 然后，位置信息服务使用 SNMP 应用程序返回的端口和交换机信息再次查询位置数据库。
  
> [!NOTE]
> MAC 地址在运行 Windows 8 的计算机上不可用。 
  
### <a name="to-configure-the-snmp-application-url"></a>配置 SNMP 应用程序 URL

1.  启动 Skype for Business Server命令行管理程序：单击"开始"，**单击"所有** 程序"，再单击 **"Skype for Business 2015"，** 然后单击 **"Skype for Business Server 命令行管理程序"。**
    
2. 运行以下 cmdlet 为 SNMP 应用程序配置 URL。 
    
   ```powershell
   Set-CsWebServiceConfiguration -MACResolverUrl "<SNMP application url>" 
   ```

## <a name="see-also"></a>另请参阅

[Set-CsWebServiceConfiguration](https://docs.microsoft.com/powershell/module/skype/set-cswebserviceconfiguration?view=skype-ps)


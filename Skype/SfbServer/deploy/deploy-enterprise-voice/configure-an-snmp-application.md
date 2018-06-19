---
title: 在 Skype for Business Server 2015 中配置 SNMP 应用程序
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
ms.assetid: c4b4a736-3b2e-45b9-a965-19d22161ad57
description: 配置 SNMP 应用程序以使用 E9-1-1 在 Skype 业务 Server 企业语音。
ms.openlocfilehash: 6024119042bede23f6b38f07c6ccdffa86a76db7
ms.sourcegitcommit: b14cfca231b618ec28cf9f4efe11cb3e8aceb34b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/19/2018
ms.locfileid: "19500415"
---
# <a name="configure-an-snmp-application-in-skype-for-business-server-2015"></a>在 Skype for Business Server 2015 中配置 SNMP 应用程序
 
配置 SNMP 应用程序以使用 E9-1-1 在 Skype 业务 Server 企业语音。 
  
Skype 业务服务器包括可用于连接到简单网络管理协议 (SNMP) 应用程序匹配 MAC 地址与端口和交换机信息的位置信息服务的标准 web 服务接口。 
  
如果安装 SNMP 应用程序和位置信息服务未能找到匹配项的位置数据库中，位置信息服务自动使用客户端提供的 MAC 地址查询应用程序。 位置信息服务然后使用 SNMP 应用程序返回的端口和交换机信息重新查询位置数据库。
  
> [!NOTE]
> MAC 地址不在运行 Windows 8 的计算机上可用。 
  
### <a name="to-configure-the-snmp-application-url"></a>配置 SNMP 应用程序 URL

1.  启动 Skype for Business Server 命令行管理程序：依次单击“**开始**”、“**所有程序**”和“**Skype for Business 2015**”，然后单击“**Skype for Business Server 命令行管理程序**”。
    
2. 运行以下 cmdlet 为 SNMP 应用程序配置 URL。 
    
   ```
   Set-CsWebServiceConfiguration -MACResolverUrl "<SNMP application url>" 
   ```

## <a name="see-also"></a>另请参阅

[通过 Set-cswebserviceconfiguration](https://docs.microsoft.com/powershell/module/skype/set-cswebserviceconfiguration?view=skype-ps)


---
title: 在 Skype for Business 服务器中配置 SNMP 应用程序
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: 在 Skype for business Server Enterprise Voice 中配置 SNMP 应用程序以使用 E9-1。
ms.openlocfilehash: fd8db117f590343d3e2f5a0194a0f6d8c3bcfb39
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41768135"
---
# <a name="configure-an-snmp-application-in-skype-for-business-server"></a>在 Skype for Business 服务器中配置 SNMP 应用程序
 
在 Skype for business Server Enterprise Voice 中配置 SNMP 应用程序以使用 E9-1。 
  
Skype for Business 服务器包括一个标准的 web 服务接口，可用于将 Location 信息服务连接到与端口和交换机信息相匹配的 MAC 地址的简单网络管理协议（SNMP）应用程序。 
  
如果已安装 SNMP 应用程序，并且位置信息服务无法在位置数据库中找到匹配项，则位置信息服务将使用客户端提供的 MAC 地址自动查询应用程序。 然后，位置信息服务使用 SNMP 应用程序返回的端口和交换信息再次查询位置数据库。
  
> [!NOTE]
> MAC 地址在运行 Windows 8 的计算机上不可用。 
  
### <a name="to-configure-the-snmp-application-url"></a>配置 SNMP 应用程序 URL

1.  启动 Skype for Business Server 命令行管理程序：依次单击“开始”****、“所有程序”**** 和“Skype for Business 2015”****，然后单击“Skype for Business Server 命令行管理程序”****。
    
2. 运行以下 cmdlet 为 SNMP 应用程序配置 URL。 
    
   ```powershell
   Set-CsWebServiceConfiguration -MACResolverUrl "<SNMP application url>" 
   ```

## <a name="see-also"></a>另请参阅

[Set-CsWebServiceConfiguration](https://docs.microsoft.com/powershell/module/skype/set-cswebserviceconfiguration?view=skype-ps)


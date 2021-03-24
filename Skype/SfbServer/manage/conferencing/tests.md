---
title: 在 Skype for Business Server 中测试电话拨入式会议
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: f4ccbfd4-6075-466f-b459-20561318803d
description: 摘要：了解如何在 Skype for Business Server 中测试电话拨入式会议。
ms.openlocfilehash: be1cf5bba5a5bec2076f78880343582be19eda70
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51096728"
---
# <a name="test-dial-in-conferencing-in-skype-for-business-server"></a>在 Skype for Business Server 中测试电话拨入式会议
 
**摘要：** 了解如何在 Skype for Business Server 中测试电话拨入式会议。
  
作为电话拨入式会议配置的最终验证，可以搜索电话拨入式会议区域未由任何访问号码使用的拨号计划，以及尚未指定电话拨入式会议区域的访问号码。 还应验证"电话拨入式会议设置"网页和拨入访问号码是否正常工作。
  
## <a name="find-dial-plans-with-a-dial-in-conferencing-region-that-is-not-used-by-an-access-number"></a>查找具有访问号码未使用的电话拨入式会议区域拨号计划

1. 以 RTCUniversalServerAdmins 组成员或者 Cs-ServerAdministrator 或 CsAdministrator 角色成员的身份登录计算机。
    
2. 启动 Skype for Business Server命令行管理程序：单击"开始"，单击"所有程序"，单击 **"Skype for Business 2015"，** 然后单击 **"Skype for Business Server 命令行管理程序"。**
    
3. 在命令提示符下，运行以下内容：
    
   ```PowerShell
   Get-CsDialinConferencingAccessNumber -EmptyRegion
   ```

    此 cmdlet 返回具有访问号码未使用的电话拨入式会议区域的所有拨号计划。
    
有关详细信息，请参阅 [Get-CsDialInConferencingAccessNumber](/powershell/module/skype/get-csdialinconferencingaccessnumber?view=skype-ps)。
  
## <a name="find-access-numbers-without-assigned-regions"></a>查找没有分配区域的访问号码

1. 以 RTCUniversalServerAdmins 组成员或者 Cs-ServerAdministrator 或 CsAdministrator 角色成员的身份登录计算机。
    
2. 启动 Skype for Business Server命令行管理程序：单击"开始"，单击"所有程序"，单击 **"Skype for Business 2015"，** 然后单击 **"Skype for Business Server 命令行管理程序"。**
    
3. 在命令提示符下，运行以下内容：
    
   ```PowerShell
   Get-CsDialinConferencingAccessNumber -Region NULL
   ```

    此 cmdlet 返回未与区域关联的所有电话拨入式会议访问号码。
    
有关详细信息，请参阅 [Get-CsDialInConferencingAccessNumber](/powershell/module/skype/get-csdialinconferencingaccessnumber?view=skype-ps)。
  
## <a name="test-webpage-and-access-numbers"></a>测试网页和访问号码

要验证“电话拨入式会议设置”网页和拨入访问号码是否工作正常，您需要执行以下操作：
  
- 通过登录简单 URL 来测试“电话拨入式会议设置”网页。
    
- 通过运行本主题后面的脚本来测试该访问号码在特定池中是否工作正常。此脚本模拟对访问号码的呼叫。要使用此脚本，需要提供该特定池承载的一个统一通信 (UC) 客户端的 SIP 地址和凭据。
    
### <a name="to-test-access-numbers-for-a-specific-pool"></a>测试特定池的访问号码

1. 以 RTCUniversalServerAdmins 组成员或者 Cs-ServerAdministrator 或 CsAdministrator 角色成员的身份登录计算机。
    
2. 启动 Skype for Business Server命令行管理程序：单击"开始"，单击"所有程序"，单击 **"Skype for Business 2015"，** 然后单击 **"Skype for Business Server 命令行管理程序"。**
    
3. 在命令提示符下，运行以下内容：
    
   ```PowerShell
   $credentials = Get-Credential
   User name:  testuser1@contoso.com
   Password:  ********
   Test-CsDialInConferencing -UserSipAddress sip:testuser1@contoso.com -UserCredential $credentials -TargetFqdn <serverName>.<domainName>.com -Verbose
   ```

    得出的报告将显示 Success 或 Failure，以及具体的诊断信息。 -Verbose 标志提供有关找到的访问号码数量及其详细信息的更多详细信息。
    
有关详细信息，请参阅 [Test-CsDialInConferencing](/powershell/module/skype/test-csdialinconferencing?view=skype-ps)。

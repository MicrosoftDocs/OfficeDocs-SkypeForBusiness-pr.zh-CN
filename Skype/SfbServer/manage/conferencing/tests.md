---
title: 在 Skype for Business Server 2015 中测试电话拨入式会议
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: f4ccbfd4-6075-466f-b459-20561318803d
description: 摘要： 了解如何为业务服务器 2015年在 Skype 测试电话拨入式会议。
ms.openlocfilehash: 7e6e53d5d4ee3e3e28beadc54ca86a79c6118637
ms.sourcegitcommit: a79668bb45b73a63bea5c249d76a4c4c2530a096
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/05/2018
ms.locfileid: "19569269"
---
# <a name="test-dial-in-conferencing-in-skype-for-business-server-2015"></a>在 Skype for Business Server 2015 中测试电话拨入式会议
 
**摘要：** 了解如何为业务服务器 2015年在 Skype 测试电话拨入式会议。
  
最终验证电话拨入式会议配置后，你可以搜索具有尚未被任何访问号码使用的电话拨入式会议区域的拨号计划，还可以搜索未指定电话拨入式会议区域的访问号码。 你还应验证电话拨入式会议设置网页和拨入访问号码是否可以正常使用。
  
## <a name="find-dial-plans-with-a-dial-in-conferencing-region-that-is-not-used-by-an-access-number"></a>查找具有尚未被访问号码使用的电话拨入式会议区域的拨号计划

1. 以  RTCUniversalServerAdmins  组成员或者  Cs-ServerAdministrator  或  CsAdministrator  角色成员的身份登录计算机。
    
2. 启动 Skype for Business Server 命令行管理程序：依次单击“**开始**”、“**所有程序**”和“**Skype for Business 2015**”，然后单击“**Skype for Business Server 命令行管理程序**”。
    
3. 在命令提示符下，运行以下内容：
    
  ```
  Get-CsDialinConferencingAccessNumber -EmptyRegion
  ```

    此 cmdlet 返回具有尚未被访问号码使用的电话拨入式会议区域的所有拨号计划。
    
有关详细信息，请参阅[Get-csdialinconferencingaccessnumber](https://docs.microsoft.com/powershell/module/skype/get-csdialinconferencingaccessnumber?view=skype-ps)。
  
## <a name="find-access-numbers-without-assigned-regions"></a>查找未分配区域的访问号码

1. 以  RTCUniversalServerAdmins  组成员或者  Cs-ServerAdministrator  或  CsAdministrator  角色成员的身份登录计算机。
    
2. 启动 Skype for Business Server 命令行管理程序：依次单击“**开始**”、“**所有程序**”和“**Skype for Business 2015**”，然后单击“**Skype for Business Server 命令行管理程序**”。
    
3. 在命令提示符下，运行以下内容：
    
  ```
  Get-CsDialinConferencingAccessNumber -Region NULL
  ```

    此 cmdlet 返回尚未与区域关联的所有电话拨入式会议访问号码。
    
有关详细信息，请参阅[Get-csdialinconferencingaccessnumber](https://docs.microsoft.com/powershell/module/skype/get-csdialinconferencingaccessnumber?view=skype-ps)。
  
## <a name="test-webpage-and-access-numbers"></a>测试网页和访问号码

要验证“电话拨入式会议设置”网页和拨入访问号码是否工作正常，您需要执行以下操作：
  
- 通过登录简单 URL 来测试“电话拨入式会议设置”网页。
    
- 通过运行本主题后面的脚本来测试该访问号码在特定池中是否工作正常。此脚本模拟对访问号码的呼叫。要使用此脚本，需要提供该特定池承载的一个统一通信 (UC) 客户端的 SIP 地址和凭据。
    
### <a name="to-test-access-numbers-for-a-specific-pool"></a>测试特定池的访问号码

1. 以  RTCUniversalServerAdmins  组成员或者  Cs-ServerAdministrator  或  CsAdministrator  角色成员的身份登录计算机。
    
2. 启动 Skype for Business Server 命令行管理程序：依次单击“**开始**”、“**所有程序**”和“**Skype for Business 2015**”，然后单击“**Skype for Business Server 命令行管理程序**”。
    
3. 在命令提示符下，运行以下内容：
    
  ```
  $credentials = Get-Credential
   User name:  testuser1@contoso.com
   Password:  ********
Test-CsDialInConferencing -UserSipAddress sip:testuser1@contoso.com -UserCredential $credentials -TargetFqdn <serverName>.<domainName>.com -Verbose
  ```

    得出的报告将显示 Success 或 Failure，以及具体的诊断信息。 -Verbose 标志提供更多详细信息多少访问找到编号和详细信息。
    
有关详细信息，请参阅[Test-csdialinconferencing](https://docs.microsoft.com/powershell/module/skype/test-csdialinconferencing?view=skype-ps)。
  


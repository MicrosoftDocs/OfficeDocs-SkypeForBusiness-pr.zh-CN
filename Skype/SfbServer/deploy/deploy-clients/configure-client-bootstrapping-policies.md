---
title: 配置客户端引导策略
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
ms.assetid: 45042eca-b845-4207-b12f-b8b7f5d44bdf
description: 摘要：如何管理组策略。
ms.openlocfilehash: 8bf4d1eb07f2386d07c3cc9e4d529b06a392631ba5cea2d66cf02cc7742ed1f5
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2021
ms.locfileid: "54294939"
---
# <a name="configure-client-bootstrapping-policies"></a>配置客户端引导策略
 
**摘要：** 如何管理组策略。
  
组策略管理控制台 (GPMC) 和组策略对象编辑器是可用于管理组策略的工具。 Office 组策略管理模板包含 lync16.admx (ADMX) 和 .adml (ADML) 管理模板，其中包含为域中的组策略对象配置的 Skype for Business 的基于注册表的策略设置。 ADML 文件是 ADMX 文件的特定语言补充。 每个 ADMX 和 ADML 文件都包含单个应用程序策略Office设置。 可以从 Microsoft 下载中心Office [ADMX/ADML (ADML) 2016](https://www.microsoft.com/download/details.aspx?id=49030)管理模板文件。
  
对于Skype for Business客户端，在用户首次登录到服务器之前，应考虑配置几个客户端引导策略。 例如，客户端在登录完成之前应该使用的默认服务器和安全模式。 在用户登录并开始从服务器接收带内设置之前，可以使用组策略在用户的计算机注册表中建立这些设置。 下表列出了可供用户Skype for Business。
  
**适用于设置组策略Skype for Business**

|组策略设置|说明|
|:-----|:-----|
|指定 Server (ConfigurationMode)   <br/> | 指定Skype for Business标识登录期间使用的传输和服务器。 在此设置中，指定以下内容： <br/>  ServerAddressExternal：指定客户端和联盟联系人在从外部防火墙外部连接时所使用的服务器名称或 IP 地址。 <br/>  ServerAddressInternal：指定客户端从组织防火墙内部连接时所使用的服务器名称或 IP 地址。 <br/>  Transport：指定传输控制协议 (TCP) 或传输层安全性 (TLS) 。 <br/> |
|ConfiguredServerCheckValues (支持的其他服务器)   <br/> |指定服务器版本名称的列表，除了默认支持的服务器版本之外，Skype for Business Server将登录到的服务器版本名称。  <br/> |
|禁用 DisableAutomaticSendTracing (登录失败日志的自动)   <br/> |自动将登录失败日志上载到Skype for Business Server进行分析。 如果登录成功，则不会自动上载任何日志。 如果未配置此策略，将发生以下情况：  <br/> For Skype for Business Online users： Sign-in failure logs are automatically uploaded. For Skype for Business on-premises users： A confirmation dialog box is shown to the user before upload. 禁用此设置后，登录日志将自动上载到 Skype for Business Server 本地用户Skype for Business联机Skype for Business登录日志。 启用此设置后，绝不会自动上载登录日志。  <br/> |
|禁用 SIP 连接的 HTTP 回退 (DisableHttpConnect)   <br/> |阻止Skype for Business Server TLS 或 TCP 不可用时尝试使用 HTTP 连接到服务器。 默认情况下，Skype for Business先尝试使用 TLS 或 TCP 连接到服务器，如果这两种传输方法均不成功，Skype for Business尝试使用 HTTP 进行连接。 使用此策略可禁止回退 HTTP 连接尝试。  <br/> |
|DisableNTCredentials (需要登录)   <br/> |要求用户在登录 SIP 服务器期间Skype for Business登录凭据，Windows自动使用登录凭据。  <br/> |
|DisableServerCheck (禁用服务器版本)   <br/> |如果此策略设置为 1，Skype for Business登录之前检查服务器名称和版本。 默认情况下，Skype for Business登录之前进行这些检查。  <br/> |
|Enable using BITS to download Address Book Service files (EnableBitsForGalDownload)   <br/> |使Skype for Business可以使用后台智能传输服务 (BITS) 下载通讯簿服务文件。  <br/> |
|Configure SIP security mode (EnableSIPHighSecurityMode)   <br/> |使Skype for Business可以更安全地发送和接收即时消息。 此策略对 Windows .NET 或 Microsoft Exchange Server 服务不起作用。  <br/> 如果未配置此策略设置，Skype for Business任何传输。 但是，如果它不使用 TLS，并且服务器对用户进行身份验证，Skype for Business必须使用 NTLM 或 Kerberos 身份验证。  <br/> |
|Global Address Book Download Initial Delay (GalDownloadInitialDelay)   <br/> |指定在 GAL 中下载全局地址列表 (的) 时间段。 默认值为 60 分钟，这意味着服务器将 GAL 文件的下载延迟 0 到 60 分钟之间的随机时间。  <br/> |
|阻止用户运行 Skype for Business (PreventRun)   <br/> |阻止用户运行Skype for Business。 可在“计算机配置”和“用户配置”中同时配置此策略设置，但“计算机配置”中的策略设置优先。  <br/> |
|允许存储 SavePassword (用户)   <br/> |允许Skype for Business存储密码。  <br/> |
|配置 SipCompression (SIP 压缩)   <br/> |指定何时打开 SIP 压缩。 默认情况下，根据适配器速度启用 SIP 压缩。 请注意，设置此策略可能会导致登录时间延长。  <br/> |
|TrustModelData (受信任的域)   <br/> |列出与客户 SIP 域的前缀不匹配的受信任域。  <br/> |
   
服务器上所配置的策略优先于用户所配置的组策略设置和客户端选项。下表汇总了在发生冲突时各个设置的优先顺序。
  
**组策略优先级**

|**Precedence**|**设置的位置或方法**|
|:-----|:-----|
|1  <br/> |Skype for Business Server带内设置  <br/> |
|2  <br/> |HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Office\16.0\Lync  <br/> |
|3  <br/> |HKEY_CURRENT_USER\SOFTWARE\Policies\Microsoft\Office\16.0\Lync  <br/> |
|4   <br/> |"选项"对话框Skype for Business  <br/> |
   
### <a name="to-define-group-policy-settings-by-using-the-skype-for-business-administrative-template-files"></a>使用管理模板文件定义Skype for Business策略设置

1. 创建一个根级别文件夹以包含所有中性语言 ADMX 文件。 例如，可在域控制器上的以下位置创建中央存储的根文件夹：
    
     `%systemroot%\sysvol\domain\policies\PolicyDefinitions`
    
    > [!NOTE]
    > 此过程假定您希望管理域中的多个计算机。 在这种情况下，将模板存储在主域控制器上 Sysvol 文件夹中的中央存储中。 这为域管理模板提供了中央存储位置的副本。 
  
2. 为将使用的每种语言创建子文件夹。 这些子文件夹将包含特定语言的 ADML 资源文件。 例如，在此位置为美国英语 (EN-US) 子文件夹：
    
     `%systemroot%\sysvol\domain\policies\PolicyDefinitions\EN-US`
    


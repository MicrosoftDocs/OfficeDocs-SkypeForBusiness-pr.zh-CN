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
ms.openlocfilehash: 5d5a2d3a7939f34bb42995bb69280fb7891736ad
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49805982"
---
# <a name="configure-client-bootstrapping-policies"></a>配置客户端引导策略
 
**摘要：** 如何管理组策略。
  
组策略管理控制台 (GPMC) 和组策略对象编辑器是可用于管理组策略的工具。 Office 组策略管理模板包含 lync16.admx (ADMX) 和 .adml (ADML) 管理模板，其中包含为域中的组策略对象配置的基于注册表的 Skype for Business 策略设置。 ADML 文件是 ADMX 文件的特定语言补充。 每个 ADMX 和 ADML 文件都包含单个 Office 应用程序的策略设置。 可以从 Microsoft 下载中心 ([ADMX/ADML) Office 2016 ](https://www.microsoft.com/download/details.aspx?id=49030) 管理模板文件。
  
对于 Skype for Business 客户端，在用户首次登录服务器之前，应考虑配置多个客户端引导策略。 例如，客户端应在登录完成之前使用的默认服务器和安全模式。 在用户登录并开始从服务器接收带内设置之前，可以使用组策略在用户的计算机注册表中建立这些设置。 下表列出了可用于 Skype for Business 的组策略设置。
  
**适用于 Skype for Business 的组策略设置**

|组策略设置|说明|
|:-----|:-----|
|指定 Server (ConfigurationMode)   <br/> | 指定 Skype for Business 如何标识登录期间使用的传输和服务器。 在此设置中，指定以下内容： <br/>  ServerAddressExternal：指定客户端和联盟联系人在从外部防火墙外部连接时所使用的服务器名称或 IP 地址。 <br/>  ServerAddressInternal：指定客户端从组织防火墙内部连接时所使用的服务器名称或 IP 地址。 <br/>  传输：指定传输控制协议 (TCP) 传输层安全性 (TLS) 。 <br/> |
|ConfiguredServerCheckValues (支持的其他服务器)   <br/> |指定除默认支持的服务器版本外，以分号分隔的 Skype for Business Server 将登录的服务器版本名称列表。  <br/> |
|禁用 DisableAutomaticSendTracing (登录失败日志的自动)   <br/> |自动将登录失败日志上载到 Skype for Business Server 进行分析。 如果登录成功，则不会自动上载任何日志。 如果未配置此策略，将发生以下情况：  <br/> 对于 Skype for Business Online 用户：将自动上载登录失败日志。 对于 Skype for Business 本地用户：在上传前向用户显示确认对话框。 禁用此设置后，登录日志将自动上载到 Skype for Business Server，以便本地 Skype for Business 和 Skype for Business Online 用户都使用。 启用此设置后，登录日志永远不会自动上载。  <br/> |
|禁用 SIP 连接的 HTTP 回退 (DisableHttpConnect)   <br/> |如果 TLS 或 TCP 不可用，则阻止 Skype for Business Server 尝试使用 HTTP 连接到服务器。 默认情况下，Skype for Business 首先尝试使用 TLS 或 TCP 连接到服务器，如果两种传输方法均不成功，Skype for Business 会尝试使用 HTTP 进行连接。 使用此策略可禁止回退 HTTP 连接尝试。  <br/> |
|DisableNTCredentials (需要登录)   <br/> |要求用户为 Skype for Business 提供登录凭据，而不是在登录 SIP 服务器期间自动使用 Windows 凭据。  <br/> |
|禁用服务器版本检查 (DisableServerCheck)   <br/> |如果此策略设置为 1，则阻止 Skype for Business 在登录之前检查服务器名称和版本。 默认情况下，Skype for Business 在登录之前进行这些检查。  <br/> |
|Enable using BITS to download Address Book Service files (EnableBitsForGalDownload)   <br/> |允许 Skype for Business 使用后台智能传输服务 (BITS) 下载通讯簿服务文件。  <br/> |
|配置 SIP 安全模式 (EnableSIPHighSecurityMode)   <br/> |使 Skype for Business 可以更安全地发送和接收即时消息。 此策略对 Windows .NET 或 Microsoft Exchange Server 服务不起作用。  <br/> 如果未配置此策略设置，Skype for Business 可以使用任何传输。 但是，如果它不使用 TLS，并且服务器对用户进行身份验证，Skype for Business 必须使用 NTLM 或 Kerberos 身份验证。  <br/> |
|全局通讯簿下载初始延迟 (GalDownloadInitialDelay)   <br/> |指定在 GAL 中下载全局地址列表 (的) 时间段。 默认值为 60 分钟，这意味着服务器将 GAL 文件的下载延迟 0 到 60 分钟之间的随机时间。  <br/> |
|阻止用户运行 Skype for Business (PreventRun)   <br/> |阻止用户运行 Skype for Business。 可在“计算机配置”和“用户配置”中同时配置此策略设置，但“计算机配置”中的策略设置优先。  <br/> |
|允许将用户密码 (SavePassword)   <br/> |允许 Skype for Business 存储密码。  <br/> |
|配置 SIP 压缩模式 (SipCompression)   <br/> |指定何时打开 SIP 压缩。 默认情况下，根据适配器速度启用 SIP 压缩。 请注意，设置此策略可能会导致登录时间延长。  <br/> |
|TrustModelData (受信任的域)   <br/> |列出与客户 SIP 域前缀不匹配的受信任域。  <br/> |
   
服务器上所配置的策略优先于用户所配置的组策略设置和客户端选项。下表汇总了在发生冲突时各个设置的优先顺序。
  
**组策略优先级**

|**Precedence**|**设置的位置或方法**|
|:-----|:-----|
|1   <br/> |Skype for Business Server 带内设置  <br/> |
|2   <br/> |HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Office\16.0\Lync  <br/> |
|3   <br/> |HKEY_CURRENT_USER\SOFTWARE\Policies\Microsoft\Office\16.0\Lync  <br/> |
|4   <br/> |Skype for Business 中的"选项"对话框  <br/> |
   
### <a name="to-define-group-policy-settings-by-using-the-skype-for-business-administrative-template-files"></a>使用 Skype for Business 管理模板文件定义组策略设置

1. 创建根级别文件夹以包含所有中性语言的 ADMX 文件。 例如，可在域控制器上的以下位置创建中央存储的根文件夹：
    
     `%systemroot%\sysvol\domain\policies\PolicyDefinitions`
    
    > [!NOTE]
    > 此过程假定要管理域中的多个计算机。 在这种情况下，将模板存储在主域控制器上 Sysvol 文件夹中的中央存储中。 这为域管理模板提供了中央存储位置的副本。 
  
2. 为将使用的每种语言创建一个子文件夹。 这些子文件夹将包含特定语言的 ADML 资源文件。 例如，在此位置为 EN-US (创建) 文件夹：
    
     `%systemroot%\sysvol\domain\policies\PolicyDefinitions\EN-US`
    


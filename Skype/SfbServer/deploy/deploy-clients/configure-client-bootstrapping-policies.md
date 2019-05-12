---
title: 配置客户端引导策略
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 45042eca-b845-4207-b12f-b8b7f5d44bdf
description: 摘要： 如何管理组策略。
ms.openlocfilehash: 050040ae6de828e20aadf75bc4d8accfa782fc7c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "33895368"
---
# <a name="configure-client-bootstrapping-policies"></a>配置客户端引导策略
 
**摘要：** 如何管理组策略。
  
组策略管理控制台 (GPMC) 和组策略对象编辑器是用于管理组策略的工具。 Office 组策略管理模板包括 lync16.admx (ADMX) 和 (ADML).adml 管理模板，其中包含 for Business 内的域中的组策略对象配置 Skype 的基于注册表的策略设置。 ADML 文件是针对 ADMX 文件的特定语言的补充。 每个 ADMX 和 ADML 文件均包含单个 Office 应用程序的策略设置。 您可以从 Microsoft 下载中心免费[下载 Office 2016 管理模板文件 (ADMX/ADML)](https://www.microsoft.com/en-us/download/details.aspx?id=49030) 。
  
对于业务客户端的 Skype，有多个客户端引导策略配置用户登录到服务器首次之前应考虑的。 例如，客户端在登录完成之前应使用的默认服务器和安全模式。 您可以使用组策略之前他们登录并开始带内设置接收来自服务器建立在用户计算机注册表中的这些设置。 下表列出了可供 for Business 的 Skype 的组策略设置。
  
**业务 Skype 的的组策略设置**

|组策略设置|描述|
|:-----|:-----|
|指定服务器 (ConfigurationMode)  <br/> | 指定 for Business 的 Skype 识别传输类型和服务器登录过程中使用的方式。 在此设置中，可以指定： <br/>  ServerAddressExternal：指定在从外部防火墙之外连接时由客户端和联盟联系人使用的服务器名称或 IP 地址。 <br/>  ServerAddressInternal： 指定服务器名称或客户端从组织的防火墙内部连接时使用的 IP 地址。 <br/>  Transport：指定传输控制协议 (TCP) 或传输层安全性 (TLS)。 <br/> |
|支持的其他服务器版本 (ConfiguredServerCheckValues)  <br/> |指定用 Skype 业务服务器将登录到，除了默认支持的服务器版本的分号分隔的服务器版本名称列表。  <br/> |
|禁止自动上载登录失败日志 (DisableAutomaticSendTracing)  <br/> |自动上载登录失败日志到 Skype 业务服务器进行分析。 如果登录成功，则不会自动上载任何日志。 如果未配置此策略，则会出现下列情况：  <br/> 为业务 Online 用户的 Skype： 自动上载登录失败日志。 有关 for Business 的 Skype 本地用户： 上载之前将为用户显示一个确认对话框。 禁用此设置时，登录日志自动上载到 Skype 业务服务器 Skype 业务本地和 Skype 的业务联机用户。 如果启用此设置，则绝不会自动上载登录日志。  <br/> |
|禁用 HTTP 回退对 SIP 连接 (回滚 DisableHttpConnect)  <br/> |防止 Skype 业务服务器尝试 TLS 或 TCP 不可用时使用 HTTP，连接到服务器。 默认情况下，for Business 的 Skype 首先尝试使用 TLS 或 TCP 连接到服务器，并且，如果这些传输方法都不成功，尝试使用 HTTP 连接 for Business 的 Skype。 使用此策略可禁止回滚 HTTP 连接尝试。  <br/> |
|需要登录凭据 (DisableNTCredentials)  <br/> |要求用户提供 Skype 业务，而无需使用登录过程中向 SIP 服务器的 Windows 凭据自动登录凭据。  <br/> |
|禁用服务器版本检查 (DisableServerCheck)  <br/> |如果此策略设置为 1 时，可以防止 for Business 的 Skype 在登录之前检查的服务器名称和版本。 默认情况下，for Business 的 Skype 使这些登录之前检查。  <br/> |
|允许使用 BITS 下载通讯簿服务文件 (EnableBitsForGalDownload)  <br/> |允许 Skype for Business 使用后台智能传输服务 (BITS) 下载通讯簿服务文件。  <br/> |
|配置 SIP 安全模式 (EnableSIPHighSecurityMode)  <br/> |允许 Skype for Business 发送和接收即时消息更安全地。 此策略对 Windows .NET 或 Microsoft Exchange Server 服务不起作用。  <br/> 如果不配置此策略设置，for Business 的 Skype 可以使用任何传输。 但是，如果不使用 TLS 和 for Business 的 Skype 如果服务器对用户进行身份验证，必须使用 NTLM 或 Kerberos 身份验证。  <br/> |
|全局通讯簿下载初始延迟 (GalDownloadInitialDelay)  <br/> |指定全局地址列表 (GAL) 下载发生之前的时间。默认值为 60 分钟，这表示服务器可将 GAL 文件的下载延迟 0 到 60 分钟之间的任意时间。  <br/> |
|禁止用户运行 Skype for Business (PreventRun)  <br/> |禁止用户运行 for Business 的 Skype。 可在“计算机配置”和“用户配置”中同时配置此策略设置，但“计算机配置”中的策略设置优先。  <br/> |
|允许存储用户密码 (SavePassword)  <br/> |允许 Skype for Business 存储密码。  <br/> |
|配置 SIP 压缩模式 (SipCompression)  <br/> |指定何时打开 SIP 压缩。默认情况下，根据适配器速度启用 SIP 压缩。请注意，设置此策略可能会导致登录时间延长。  <br/> |
|受信任的域列表 (TrustModelData)  <br/> |列出与客户 SIP 域的前缀不匹配的受信任域。  <br/> |
   
服务器上所配置的策略优先于用户所配置的组策略设置和客户端选项。下表汇总了在发生冲突时各个设置的优先顺序。
  
**组策略优先级**

|**优先级**|**设置的位置或方法**|
|:-----|:-----|
|1  <br/> |Skype 的业务服务器带内设置  <br/> |
|2  <br/> |HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Office\16.0\Lync  <br/> |
|3  <br/> |HKEY_CURRENT_USER\SOFTWARE\Policies\Microsoft\Office\16.0\Lync  <br/> |
|4  <br/> |Skype for Business 中的选项对话框  <br/> |
   
### <a name="to-define-group-policy-settings-by-using-the-skype-for-business-administrative-template-files"></a>若要使用 Skype 业务管理模板文件定义组策略设置

1. 创建根级别文件夹以包含所有与语言无关的 ADMX 文件。例如，在位于以下位置的域控制器上创建中央存储的根文件夹：
    
     `%systemroot%\sysvol\domain\policies\PolicyDefinitions`
    
    > [!NOTE]
    > 此过程假定您需要管理域中的多台计算机。在此情况下，您将模板存储在主域控制器上的 Sysvol 文件夹中的中央存储中。这将为域管理模板提供复制的中央存储位置。 
  
2. 创建将使用的每种语言的子文件夹。 这些子文件夹将包含特定语言的 ADML 资源文件。 例如，在以下位置为美国英语 (EN-US) 创建一个子文件夹：
    
     `%systemroot%\sysvol\domain\policies\PolicyDefinitions\EN-US`
    


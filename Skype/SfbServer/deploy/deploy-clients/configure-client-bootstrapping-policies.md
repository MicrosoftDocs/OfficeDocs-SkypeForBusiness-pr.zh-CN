---
title: 在 Skype for Business Server 2015 中配置客户端引导策略
ms.author: chucked
author: chuckedmonson
manager: serdars
ms.date: 10/20/2017
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 45042eca-b845-4207-b12f-b8b7f5d44bdf
description: 摘要： 如何为 Skype 业务管理组策略。
ms.openlocfilehash: b2e2f9787dd54b783b0f24ce9a6bb152ea4a69d7
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="configure-client-bootstrapping-policies-in-skype-for-business-server-2015"></a>在 Skype for Business Server 2015 中配置客户端引导策略
 
**摘要：**如何为 Skype 业务管理组策略。
  
组策略管理控制台 (GPMC) 和组策略对象编辑器是用于管理组策略的工具。 办公室的组策略管理模板包括 lync16.admx (ADMX) 和.adml (ADML) 管理模板，其中包含您为域中的组策略对象配置的业务的 Skype 的基于注册表的策略设置。 ADML 文件是针对 ADMX 文件的特定语言的补充。 每个 ADMX 和 ADML 文件均包含单个 Office 应用程序的策略设置。 您可以免费从 Microsoft 下载中心[下载 Office 2016 管理模板文件 (ADMX/ADML)](https://www.microsoft.com/en-us/download/details.aspx?id=49030) 。
  
对于业务的 Skype，有几个客户端启动的策略，则应该考虑配置之前，用户在登录到服务器第一次。 例如，客户端在登录完成之前应使用的默认服务器和安全模式。 您可以使用组策略来登录并开始接收来自服务器的带内配置设置之前建立这些设置在用户的计算机的注册表中。 下表列出了可用于业务的 Skype 的组策略设置。
  
**业务 Skype 的的组策略设置**

|**组策略设置**|**说明**|
|:-----|:-----|
|指定服务器 (ConfigurationMode)  <br/> | 指定为业务 Skype 将传输和服务器以在登录过程中使用的标识。 在此设置中，可以指定： <br/>  ServerAddressExternal：指定在从外部防火墙之外连接时由客户端和联盟联系人使用的服务器名称或 IP 地址。 <br/>  ServerAddressInternal： 指定的服务器名或 IP 地址从位于组织的防火墙内的客户端连接时使用。 <br/>  Transport：指定传输控制协议 (TCP) 或传输层安全性 (TLS)。 <br/> |
|支持附加的服务器版本 (ConfiguredServerCheckValues)  <br/> |指定的服务器版本名称，Skype 的业务服务器 2015年将登录到，除了默认支持的服务器版本与中的以分号分隔的列表。  <br/> |
|禁止自动上载登录失败日志 (DisableAutomaticSendTracing)  <br/> |自动上载登录失败日志到 Skype 的业务服务器 2015年进行分析。 如果登录成功，则不会自动上载任何日志。 如果未配置此策略，则会出现下列情况：  <br/> 为业务联机用户的 Skype： 登录失败日志将自动上载。 对 Skype 为企业内部的用户： 用户上载前显示确认对话框。 禁用此设置后，登录日志自动上载到 Skype 业务服务器的 Skype 的业务部署和业务联机用户的 Skype。 如果启用此设置，则绝不会自动上载登录日志。  <br/> |
|禁用 HTTP 回退 SIP 连接 (DisableHttpConnect)  <br/> |可防止 Skype 业务服务器试图连接到服务器使用 HTTP，如果 TLS 或 TCP 将不可用。 默认情况下，Skype 业务的第一次尝试使用 TLS 或 TCP 连接到服务器，如果这些传输方法均未成功，Skype 为企业试图通过 HTTP 连接。 使用此策略可禁止回滚 HTTP 连接尝试。  <br/> |
|需要登录凭据 (DisableNTCredentials)  <br/> |要求用户提供登录凭据的 Skype 业务，而不是自动登录到 SIP 服务器过程中使用的 Windows 凭据。  <br/> |
|禁用服务器版本检查 (DisableServerCheck)  <br/> |如果将此策略设置为 1，可以防止业务的 Skype 登录前检查服务器的名称和版本。 默认情况下，通过 Skype 业务使得之前签入这些检查。  <br/> |
|启用使用 BITS 下载通讯簿服务文件 (EnableBitsForGalDownload)  <br/> |使企业可以使用后台智能传输服务 (BITS) 下载通讯簿服务文件的 Skype。  <br/> |
|配置 SIP 安全模式 (EnableSIPHighSecurityMode)  <br/> |使业务能够发送和接收即时消息更安全地为 Skype。 此策略对 Windows .NET 或 Microsoft Exchange Server 服务不起作用。  <br/> 如果您不配置此策略设置，Skype 为企业可以使用任何传输。 但是，如果它不使用 TLS 服务器对用户进行身份验证，如果 Skype 业务必须使用 NTLM 或 Kerberos 身份验证。  <br/> |
|全球通讯簿下载初始延迟 (GalDownloadInitialDelay)  <br/> |指定全局地址列表 (GAL) 下载发生之前的时间。默认值为 60 分钟，这表示服务器可将 GAL 文件的下载延迟 0 到 60 分钟之间的任意时间。  <br/> |
|禁止用户使用 Skype 业务 (PreventRun)  <br/> |防止用户运行业务的 Skype。 可在“计算机配置”和“用户配置”中同时配置此策略设置，但“计算机配置”中的策略设置优先。  <br/> |
|允许存储用户密码 (SavePassword)  <br/> |使业务要存储密码的 Skype。  <br/> |
|配置 SIP 压缩模式 (SipCompression)  <br/> |指定何时打开 SIP 压缩。默认情况下，根据适配器速度启用 SIP 压缩。请注意，设置此策略可能会导致登录时间延长。  <br/> |
|受信的域列表 (TrustModelData)  <br/> |列出与客户 SIP 域的前缀不匹配的受信任域。  <br/> |
   
服务器上所配置的策略优先于用户所配置的组策略设置和客户端选项。下表汇总了在发生冲突时各个设置的优先顺序。
  
**组策略优先级**

|**优先级**|**位置或设置的方法**|
|:-----|:-----|
|1  <br/> |Skype 的业务服务器 2015年带内配置  <br/> |
|2  <br/> |HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Office\16.0\Lync  <br/> |
|3  <br/> |HKEY_CURRENT_USER\SOFTWARE\Policies\Microsoft\Office\16.0\Lync  <br/> |
|4  <br/> |Skype 为企业中的选项对话框  <br/> |
   
### <a name="to-define-group-policy-settings-by-using-the-skype-for-business-administrative-template-files"></a>通过 Skype 业务管理模板文件定义组策略设置

1. 创建根级别文件夹以包含所有与语言无关的 ADMX 文件。例如，在位于以下位置的域控制器上创建中央存储的根文件夹：
    
     `%systemroot%\sysvol\domain\policies\PolicyDefinitions`
    
    > [!NOTE]
    > 此过程假定您需要管理域中的多台计算机。在此情况下，您将模板存储在主域控制器上的 Sysvol 文件夹中的中央存储中。这将为域管理模板提供复制的中央存储位置。 
  
2. 创建一个子文件夹，您将使用的每种语言。 这些子文件夹将包含特定语言的 ADML 资源文件。 例如，在以下位置为美国英语 (EN-US) 创建一个子文件夹：
    
     `%systemroot%\sysvol\domain\policies\PolicyDefinitions\EN-US`
    


---
title: "解决管理员的 Skype for Business Online 登录错误"
ms.author: tonysmit
author: tonysmit
manager: scotv
ms.date: 11/17/2017
ms.audience: Admin
ms.topic: troubleshooting
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: cdd4801a-2fe1-4aab-bbb6-db5f95f972d1
description: "Learn common causes for Skype for Business Online sign-errors and Work through troubleshooting these problems. "
---

# 解决管理员的 Skype for Business Online 登录错误

> [!IMPORTANT]
> 本文是由机器翻译的，请参阅[免责声明]。
  
若要解决Skype for Business Online登录错误，首先消除登录时遇到困难的最常见的原因。如有必要，则可以按照特定分辨率根据错误类型的步骤。如果用户仍然无法登录，收集的其他信息，然后再寻求其他帮助。
  
## 您要做什么？
<a name="__top"> </a>

> [检查Skype for Business Online登录错误的常见原因](cdd4801a-2fe1-4aab-bbb6-db5f95f972d1.md#__toc323194094)
    
> [执行特定错误的解决步骤（仅限企业版）](cdd4801a-2fe1-4aab-bbb6-db5f95f972d1.md#__toc325626440)
    
> [请将 msoidsvc.exe 的防火墙项添加到代理服务器](cdd4801a-2fe1-4aab-bbb6-db5f95f972d1.md#__add_a_firewall)
    
> [更新 DNS 设置](cdd4801a-2fe1-4aab-bbb6-db5f95f972d1.md#__update_dns_service)
    
> [在 ADFS 服务器上安装第三方 SSL 证书](cdd4801a-2fe1-4aab-bbb6-db5f95f972d1.md#__verify_upn_and)
    
> [更新安全凭据](cdd4801a-2fe1-4aab-bbb6-db5f95f972d1.md#__update_security_credentials_1)
    
> [修改 TrustModelData 注册表项](cdd4801a-2fe1-4aab-bbb6-db5f95f972d1.md#__modify_trustmodeldata_registry)
    
> [更新 Active Directory 中的用户设置](cdd4801a-2fe1-4aab-bbb6-db5f95f972d1.md#__update_user_settings_1)
    
> [使用 Microsoft 支持疑难解答指南](cdd4801a-2fe1-4aab-bbb6-db5f95f972d1.md#__toc325626447)
    
> [收集更多信息并寻求其他帮助](cdd4801a-2fe1-4aab-bbb6-db5f95f972d1.md#__collect_more_information_1)
    
## 检查Skype for Business Online登录错误的常见原因
<a name="__toc323194094"> </a>

可归少数几个原因，大多数登录问题，其中的许多易于更正。 下表列出了登录错误的一些常见原因和您或多个用户可以采取以解决这些问题的一些步骤。
  
|**可能的原因**|**解决方法**|
|:-----|:-----|
|在登录，会出现一个对话框，其中包含以下短语： **无法验证服务器是您的登录地址是否信任。连接吗？** <br/> |请验证该对话框中的域名是否为组织中的受信任服务器，例如 **domainName.contoso.com**。让用户选中" **始终信任此服务器** "复选框，然后单击" **连接** "。 <br/> 企业客户可以通过修改每个用户的计算机上的 Windows 注册表，阻止在用户首次登录时显示此消息。有关详细信息，请参阅[修改 TrustModelData 注册表项](cdd4801a-2fe1-4aab-bbb6-db5f95f972d1.md#__modify_trustmodeldata_registry)。  <br/> |
|输入了错误的登录地址、用户名或密码  <br/> | 确认用户的登录名称和密码正确。 <br/>  验证用户的登录名称格式是否如下所示： **bobk@contoso.com**。这可能不同于您用于登录到组织的网络中的格式。  <br/>  让用户再次尝试登录。 <br/> |
|忘记密码  <br/> |重置用户密码，并通知他或她新的临时密码。  <br/> |
|未授权使用Skype for Business Online  <br/> |确认用户的已注册为Skype for Business Online用户。如果没有，则注册用户，并询问他或她重新登录。  <br/> |
|Skype for Business Online安装的版本不正确  <br/> |此问题通常与包含以下短语的错误消息相关联： **身份验证服务可能与此版本的程序不兼容**。  <br/> 要求用户卸载并重新安装Skype for Business Online从 Office 365 门户。  <br/> |
|获得登录所需的个人证书时出现问题  <br/> |如果已最近更改用户的登录地址，它们可能需要删除缓存的登录数据。让用户注销，请单击的删除我的登录信息的链接在登录屏幕上，然后再试。  <br/> |
|您设置了自定义域名，而所做更改可能未在系统内完成传播。  <br/> |首先，确保您已修改以反映更改的域名服务 (DNS) 记录。  <br/> 如果您已经做了必要的 DNS 更改，请建议用户以后尝试登录。DNS 更改最多需要 72 个小时才会在整个系统中反映出来。  <br/> |
|系统时钟与服务器时钟不同步  <br/> |确保您的网络域控制器与可靠的外部时间源保持同步。 有关详细信息，请参阅 Microsoft 知识库文章 816042 [如何在 Windows Server 中配置权威时间服务器](http://go.microsoft.com/fwlink/?linkid=3052&amp;kbid=816042)。  <br/> |
   
[本文是由机器翻译的，请参阅免责声明。请在 此处https://support.office.com/en-us/article/cdd4801a-2fe1-4aab-bbb6-db5f95f972d1 中查找本文的英文版本以便参考。 若要解决Skype for Business Online登录错误，首先消除登录时遇到困难的最常见的原因。如有必要，则可以按照特定分辨率根据错误类型的步骤。如果用户仍然无法登录，收集的其他信息，然后再寻求其他帮助。](cdd4801a-2fe1-4aab-bbb6-db5f95f972d1.md#__top)
  
## 执行特定错误的解决步骤（仅限企业版）
<a name="__toc325626440"> </a>

> [!IMPORTANT]
> 这些说明主要用于 Microsoft Office 365 Plan E 客户。如果您是 Office 365 计划 P 客户，请继续下面的部分，[收集更多信息并寻求其他帮助](cdd4801a-2fe1-4aab-bbb6-db5f95f972d1.md#__collect_more_information_1)。 
  
如果在您尝试了前一节中的建议之后用户仍然无法登录，您可以基于错误类型执行其他疑难解答。 下表列出了最常见的错误消息和可能的原因。表后面提供了解决各个问题的详细过程。
  
|**错误消息**|**可能的原因**|**解决方法**|
|:-----|:-----|:-----|
|找不到登录地址  <br/> |Microsoft Online Services 登录助手 (msoidsvc.exe) 发出的登录请求未通过外部防火墙或代理服务器。  <br/> |[请将 msoidsvc.exe 的防火墙项添加到代理服务器](cdd4801a-2fe1-4aab-bbb6-db5f95f972d1.md#__add_a_firewall) <br/> |
|服务器暂时不可用  <br/> |如果您的组织具有自定义域，则必要的域名系统 (DNS) 设置可能缺少或不正确。  <br/> |[更新 DNS 设置](cdd4801a-2fe1-4aab-bbb6-db5f95f972d1.md#__update_dns_service) <br/> |
|服务器暂时不可用  <br/> |如果您的组织正在使用单一登录和 Active Directory 联合身份验证服务 (ADFS)，那么您可能使用了自签名的安全套接字层 (SSL) 证书，而不是来自第三方证书颁发机构的证书。  <br/> |[在 ADFS 服务器上安装第三方 SSL 证书](cdd4801a-2fe1-4aab-bbb6-db5f95f972d1.md#__verify_upn_and) <br/> |
|获得登录所需的个人证书时出现问题  <br/> |如果你已经删除了缓存的服务器数据用于登录并继续显示错误，、 用户的安全凭据可能已损坏，或用户的计算机上的 RSA 文件夹可能会阻止身份验证。  <br/> |[更新安全凭据](cdd4801a-2fe1-4aab-bbb6-db5f95f972d1.md#__update_security_credentials_1) <br/> |
|当用户首次登录时，出现证书信任对话框。  <br/> |如果Skype for Business服务器未列在 **TrustModelData**注册表项中，将显示此对话框。  <br/> |[修改 TrustModelData 注册表项](cdd4801a-2fe1-4aab-bbb6-db5f95f972d1.md#__modify_trustmodeldata_registry) <br/> |
|用户未启用 SIP。  <br/> |如果您的组织以前安装了 Microsoft Office Communications Server 或 Microsoft Lync Server 2010，则在取消服务器之前，您可能尚未从服务器中删除您的用户。因此， **msRTCSIP-UserEnabled** 属性在 Active Directory 域服务中仍设置为 **FALSE**。  <br/> |[更新 Active Directory 中的用户设置](cdd4801a-2fe1-4aab-bbb6-db5f95f972d1.md#__update_user_settings_1) <br/> |
   
### 请将 msoidsvc.exe 的防火墙项添加到代理服务器
<a name="__add_a_firewall"> </a>

此过程是以下错误消息的可能修复方法： **找不到登录地址**。
  
 **注意** ：下列步骤假定您使用的是 Microsoft Forefront Threat Management Gateway (TMG) 2010。如果您具有不同的 Web 网关解决方案，请使用下面的步骤 4 中介绍的设置。
  
要在 Forefront TMG 2010 中为 Msoidsvc.exe 创建应用程序项目，请按照下列步骤操作：
  
1. 在 Forefront 左窗格中，单击" **网络**"。
    
2. 单击" **网络**"选项卡。在右窗格中的" **任务**"选项卡下方，单击" **配置 Forefront TMG 客户端设置**"。
    
3. 在" **Forefront TMG 客户端设置**"对话框中，单击 **"新建"**。
    
4. 在" **应用程序项目设置**"对话框中，配置以下规则：
    
|****应用程序****|****键****|****值****|
|:-----|:-----|:-----|
|**msoidsvc** <br/> |Disable  <br/> |0  <br/> |
|**msoidsvc** <br/> |DisableEx  <br/> |0  <br/> |
   
有关详细信息，请参阅 Microsoft 知识库文章 2409256，[您无法连接到 Skype for Business Online，因为本地防火墙阻止连接](http://go.microsoft.com/fwlink/?linkid=3052&amp;kbid=2409256)。
  
### 更新 DNS 设置
<a name="__update_dns_service"> </a>

如果您的组织具有自定义域，此过程是以下错误消息的可能修复方法： **服务器暂时不可用** 。
  
- 有关如何将下列 CNAME 记录添加到域的信息，请联系您的域名注册机构：
    
  - **DNS 记录类型**：CNAME
    
  - **名称**：sip
    
  - **值/目标**：sipdir.online.microsoft.com
    
有关详细信息，请参阅 Microsoft 知识库文章 2566790、 [Office 365 中的业务 Online DNS 配置问题疑难解答 Skype](http://go.microsoft.com/fwlink/?linkid=3052&amp;kbid=2566790)，并确保您的网络可与 Skype Office 365 Wiki 文章[for Business (Lync) Online](https://go.microsoft.com/fwlink/?linkid=231156)。
  
### 在 ADFS 服务器上安装第三方 SSL 证书
<a name="__verify_upn_and"> </a>

要在 Active Directory 联合身份验证服务 (ADFS) 服务器上安装第三方 SSL 证书，请按照下列步骤操作：
  
1. 从第三方证书颁发机构（如 VeriSign 或 Thawte）获得 SSL 证书。
    
2. 在 ADFS 服务器上安装证书，使用 ADFS 管理控制台。
    
### 更新安全凭据
<a name="__update_security_credentials_1"> </a>

此过程是以下错误消息的可能修复方法： **获取登录所需的个人证书时出现问题**。
  
要消除可能的证书或凭据问题，请首先在 Windows 证书管理器中续订用户的证书。为此，请按照下列步骤操作：
  
1. 打开 Windows 证书管理器。要执行此操作，请单击" **开始**"、" **运行**"，键入 **certmgr.msc**，然后单击" **确定**"。
    
2. 双击" **个人**"，然后双击" **证书**"。
    
3. 按" **颁发者**"列排序，然后查找由通信服务器颁发的证书。
    
4. 右键单击证书，然后单击" **删除**"。
    
接下来，如果用户正在运行 Windows 7，请删除 Windows 凭据管理器中存储的凭据。为此，请按照下列步骤操作：
  
1. 单击" **开始**"，单击" **控制面板**"，然后单击" **凭据管理器**"。
    
2. 找到用于连接到联机Skype for Business的一组凭据。
    
3. 展开一组凭据，然后单击" **从保管库中删除**"。
    
4. 再次登录并重新输入用户的凭据。
    
最后，如果在您更新凭据后用户仍然无法登录，请尝试在用户的计算机上删除 RSA 文件夹，因为它可能阻止用户身份验证过程完成：
  
1. 使用管理员帐户登录用户的计算机。
    
2. 如有必要，打开 **显示隐藏的文件**文件夹视图选项。
    
3. 在文件管理器的地址栏中键入以下内容： **C:\\Documents and Settings\\UserName\\Application Data\\Microsoft\\Crypto\\RSA**，其中， *UserName* **是您的 Windows 登录名称** 。
    
4. 删除名称为 **S-1-5-21-** 且后面跟有一串数字的任何文件夹。
    
### 修改 TrustModelData 注册表项
<a name="__modify_trustmodeldata_registry"> </a>

当用户首次登录时，它们可能会收到一个对话框，包含以下类似： **无法验证服务器是您的登录地址是否信任。连接吗？**这是一个安全功能，而不是错误。但是，您可以防止使用组策略对象 (GPO) 之前登录第一次更新与您的域名的用户的计算机显示对话框。为此，请执行下列操作：
  
- 创建和部署Skype for Business域名 GPO  例如，domainName.contoso.comto HKEY_LOCAL_MACHINE\\Software\\Policies\\Microsoft\\Communicator\\TrustModelData 的当前值。
    
> [!IMPORTANT]
> 必须将域名 *附加*  到现有值，而不只是替换它。
  
有关详细信息，请参阅 Microsoft 知识库文章 2531068 [Skype for Business (Lync) 无法验证服务器是否信任你的登录地址](http://go.microsoft.com/fwlink/?linkid=3052&amp;kbid=2531068)。
  
### 更新 Active Directory 中的用户设置
<a name="__update_user_settings_1"> </a>

如果您的组织以前安装了 Microsoft Office Communications Server 或 Microsoft Lync Server 2010，则在取消服务器之前，您可能尚未从服务器中删除您的用户。因此， **msRTCSIP-UserEnabled** 属性在 Active Directory 域服务中仍设置为 **FALSE**。
  
若要解决此问题，请执行以下步骤：
  
1. 将所有受影响用户的 **msRTCSIP-UserEnabled** 属性更新为 **TRUE**。
    
2. 重新运行 Microsoft Online Services 目录同步工具 (DirSync)。有关详细信息，请参阅[与 Azure Active Directory AIntegrate 您的本地目录](https://technet.microsoft.com/en-us/library/hh967642.aspx)。
    
[本文是由机器翻译的，请参阅免责声明。请在 此处https://support.office.com/en-us/article/cdd4801a-2fe1-4aab-bbb6-db5f95f972d1 中查找本文的英文版本以便参考。 若要解决Skype for Business Online登录错误，首先消除登录时遇到困难的最常见的原因。如有必要，则可以按照特定分辨率根据错误类型的步骤。如果用户仍然无法登录，收集的其他信息，然后再寻求其他帮助。](cdd4801a-2fe1-4aab-bbb6-db5f95f972d1.md#__top)
  
## 使用 Microsoft 支持疑难解答指南
<a name="__toc325626447"> </a>

如果仍无法解决用户的登录问题，请查看 Microsoft 知识库文章 2541980，[如何登录 Skype for Business Online 中的问题进行故障排除](http://go.microsoft.com/fwlink/?linkid=3052&amp;kbid=2541980)中的建议。
  
## 收集更多信息并寻求其他帮助
<a name="__collect_more_information_1"> </a>

如果您已经按照上面的指南，并仍无法解决登录问题，必须收集更多信息并联系技术支持。若要执行此操作，请按照下列步骤：
  
1. 从用户的计算机中获得的日志文件和 Windows 事件日志详细信息。分步说明，请参阅[关于 Lync 中的日志记录](https://support.office.com/article/eaf6602b-95e0-4c27-869f-36017475806c)最终用户帮助主题。
    
2. 将关于错误的日志文件和详细信息发送给 Microsoft 技术支持人员。
    
您可能被要求通过在受影响用户的机器上安装 Microsoft Online Services 诊断和日志记录 (MOSDAL) 支持工具包来提供更多诊断所需信息。有关详细信息，请参阅[使用 MOSDAL 支持工具包](https://support.office.com/article/ddf1f52f-24a1-4675-abe0-141052c88b72)。
  
[本文是由机器翻译的，请参阅免责声明。请在 此处https://support.office.com/en-us/article/cdd4801a-2fe1-4aab-bbb6-db5f95f972d1 中查找本文的英文版本以便参考。 若要解决Skype for Business Online登录错误，首先消除登录时遇到困难的最常见的原因。如有必要，则可以按照特定分辨率根据错误类型的步骤。如果用户仍然无法登录，收集的其他信息，然后再寻求其他帮助。](cdd4801a-2fe1-4aab-bbb6-db5f95f972d1.md#__top)
  
## 
<a name="MT_Footer"> </a>

> [!NOTE]
> **机器翻译免责声明**：本文是由无人工介入的计算机系统翻译的。Microsoft 提供机器翻译是为了帮助非英语国家/地区用户方便阅读有关 Microsoft 产品、服务和技术的内容。由于机器翻译的原因，本文可能包含词汇、语法或文法方面的错误。 
  


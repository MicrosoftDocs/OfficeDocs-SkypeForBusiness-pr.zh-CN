---
title: "管理员 Skype 业务联机登录错误疑难解答"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 01/22/2018
ms.topic: article
ms.assetid: cdd4801a-2fe1-4aab-bbb6-db5f95f972d1
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- Setup
description: "了解常见原因为 Skype 的在线业务的符号错误和工作通过解决这些问题。 "
ms.openlocfilehash: a30375b54db5ef02756253e9419c2cb54f8f2f8b
ms.sourcegitcommit: 371a699df0c13f44d2cb6511ba7eaafe047be92c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/27/2018
---
# <a name="troubleshooting-skype-for-business-online-sign-in-errors-for-administrators"></a>管理员 Skype 业务联机登录错误疑难解答

为了解决 Skype 业务联机登录错误，请首先消除登录困难的最常见原因。 如有必要，您可以按照特定的分辨率根据错误类型的步骤。 如果用户仍然不能登录，收集的其他信息，然后再寻求更多帮助。 
  
## <a name="what-do-you-want-to-do"></a>你要做什么？
<a name="top"> </a>

> [检查的 Skype 业务联机登录错误的常见原因](troubleshooting-sign-in-errors-for-admins.md#toc323194094)
    
> [按照一个特定的错误 （仅适用于企业） 的解决方法步骤](troubleshooting-sign-in-errors-for-admins.md#toc325626440)
    
> [将 msoidsvc.exe 防火墙项添加到您的代理服务器](troubleshooting-sign-in-errors-for-admins.md#add-a-firewall)
    
> [更新 DNS 设置](troubleshooting-sign-in-errors-for-admins.md#update-dns-service)
    
> [ADFS 在服务器上安装一个第三方的 SSL 证书](troubleshooting-sign-in-errors-for-admins.md#verify-upn-and)
    
> [更新的安全凭据](troubleshooting-sign-in-errors-for-admins.md#update-security-credentials)
    
> [修改 TrustModelData 注册表项](troubleshooting-sign-in-errors-for-admins.md#modify-trustmodeldata-registry)
    
> [更新在 Active Directory 中的用户设置](troubleshooting-sign-in-errors-for-admins.md#update-user-settings)
    
> [使用 Microsoft 支持故障排除指南](troubleshooting-sign-in-errors-for-admins.md#toc325626447)
    
> [收集的详细信息，并寻求额外的帮助](troubleshooting-sign-in-errors-for-admins.md#collect-more-information)
    
## <a name="check-for-common-causes-of-skype-for-business-online-sign-in-errors"></a>检查的 Skype 业务联机登录错误的常见原因
<a name="toc323194094"> </a>

符号中的大多数问题可以归因为对数目较少的原因，和许多种可以很容易地更正。 下表列出了登录错误的某些常见原因和一些您或用户可以采取的措施来解决这些问题。
  
|**可能的原因**|**解析**|
|:-----|:-----|
|在签入期间会出现一个对话框，其中包含下列文字：**不能验证服务器是否信任您的登录地址。是否仍要连接？** <br/> |验证是否在对话框中的域名是您的组织中受信任的服务器 — — 例如， **domainName.contoso.com**。要求用户选中**始终信任此服务器**复选框，然后单击**连接**。 <br/> 企业客户可以防止用户签署第一次通过修改每个用户的计算机上的 Windows 注册表时出现此消息。 有关详细信息，请参阅[修改 TrustModelData 注册表项](troubleshooting-sign-in-errors-for-admins.md#modify-trustmodeldata-registry)。<br/> |
|键入登录地址、 用户名或密码  <br/> | 确认用户的登录名和密码正确。 <br/>  验证用户的登录名的格式如下： **bobk@contoso.com**。这可能不同于您用于登录到您的组织的网络的格式。  <br/>  要求用户再次尝试登录。 <br/> |
|忘记的密码  <br/> |重置用户的密码并通知他 （或她） 的新的临时密码。  <br/> |
|未被授权用于 Skype 在线业务  <br/> |请确认该用户被视为业务在线用户的 Skype。 如果不是，注册用户，并询问他或她再次登录。  <br/> |
|Skype 业务在线安装的版本不正确  <br/> |此问题是通常与错误消息包含下面的短语：**可能是身份验证服务与程序的当前版本不兼容**。  <br/> 要求用户卸载并重新安装 Office 365 门户在线业务的 Skype。  <br/> |
|获得个人证书所需登录问题  <br/> |如果最近更改了用户的登录地址，它们可能需要删除缓存的登录数据。 询问用户注销，请单击的删除我的登录信息链接在登录屏幕上，并再试一次。  <br/> |
|设置自定义的域名，并不可能传播通过系统完成所做的更改。  <br/> |首先，确保您已修改了域名服务 (DNS) 记录以反映此更改。  <br/> 如果您已进行必要的 DNS 更改，建议用户尝试登录以后。 DNS 更改可能需要 72 小时可以反映整个系统。  <br/> |
|系统同步的服务器时钟的时钟  <br/> |确保您网络的域控制器与可靠的外部时间源同步。 有关详细信息，请参阅 Microsoft 知识库文章 816042，[如何配置 Windows 服务器的权威时间服务器](http://go.microsoft.com/fwlink/?linkid=3052&amp;kbid=816042)。<br/> |
   
为了解决 Skype 业务联机登录错误，请首先消除登录困难的最常见原因。 如有必要，您可以按照特定的分辨率根据错误类型的步骤。 如果用户仍然不能登录，收集的其他信息，然后再寻求更多帮助。 
  
## <a name="follow-resolution-steps-for-a-specific-error-enterprise-only"></a>按照一个特定的错误 （仅适用于企业） 的解决方法步骤
<a name="toc325626440"> </a>

> [!IMPORTANT]
>  这些说明是主要适用于 Microsoft Office 365 计划电子客户。 如果您是 Office 365 计划 P 客户，继续下一节，[收集更多的信息，并寻求额外的帮助](troubleshooting-sign-in-errors-for-admins.md#collect-more-information)。 
  
如果您已经尝试了上一节中的建议之后，用户无法登录，则可以执行根据错误类型的其它故障诊断。 下表列出了最常见的错误消息和可能的原因。 下表是以解决每个问题的详细的过程。
  
|**错误消息**|**可能的原因**|**解析**|
|:-----|:-----|:-----|
|找不到的登录地址  <br/> |从 Microsoft 联机服务登录助手 (msoidsvc.exe) 的登录请求将不会通过外部的防火墙或代理服务器。  <br/> |[将 msoidsvc.exe 防火墙项添加到您的代理服务器](troubleshooting-sign-in-errors-for-admins.md#add-a-firewall) <br/> |
|服务器当前不可用  <br/> |如果您的组织自定义的域，则必要的域名系统 (DNS) 设置可能会丢失或不正确。  <br/> |[更新 DNS 设置](troubleshooting-sign-in-errors-for-admins.md#update-dns-service) <br/> |
|服务器当前不可用  <br/> |如果您的组织与活动目录联合身份验证服务 (ADF) 使用单一登录，您可能使用的是自签名的安全套接字层 (SSL) 证书，而不是从第三方证书颁发机构。  <br/> |[ADFS 在服务器上安装一个第三方的 SSL 证书](troubleshooting-sign-in-errors-for-admins.md#verify-upn-and) <br/> |
|获得个人证书所需登录问题  <br/> |如果您已经删除了已缓存的服务器数据用于登录错误继续出现，可能损坏用户的安全凭据，或 RSA 文件夹在用户的计算机上可能会阻止身份验证。  <br/> |[更新的安全凭据](troubleshooting-sign-in-errors-for-admins.md#update-security-credentials) <br/> |
|当用户首次登录时，会出现证书信任对话框。  <br/> |如果您 Skype 业务服务器未列出的**TrustModelData**注册表项中，将出现此对话框。 <br/> |[修改 TrustModelData 注册表项](troubleshooting-sign-in-errors-for-admins.md#modify-trustmodeldata-registry) <br/> |
|不启用了 SIP 用户。  <br/> |如果您的组织具有以前安装的 Microsoft Office 通信服务器或 Microsoft Lync Server 2010 中，您可能不具有您的用户从服务器上删除在停止使用它之前。 因此， **msRTCSIP UserEnabled**属性仍设置为**FALSE**在 Active Directory 域服务。 <br/> |[更新在 Active Directory 中的用户设置](troubleshooting-sign-in-errors-for-admins.md#update-user-settings)<br/> |
   
### <a name="add-a-firewall-entry-for-msoidsvcexe-to-your-proxy-server"></a>将 msoidsvc.exe 防火墙项添加到您的代理服务器
<a name="add-a-firewall"> </a>

此过程是下面的错误消息的可能解决方法：**找不到的登录地址**。
  
 **注意**： 以下步骤假定您使用的 Microsoft 最前沿威胁管理网关 (TMG) 2010年。 如果您有另一个站点的网关解决方案，使用下面的步骤 4 中所述的设置。
  
要为在前沿 TMG 2010 Msoidsvc.exe 创建一个应用程序项目，请执行以下步骤：
  
1. 在最前沿的左窗格中，单击**网络**。
    
2. 单击**网络**选项卡。在右窗格中的**任务**选项卡上，单击**配置 Forefront TMG 客户端设置**。
    
3. 在**最前沿 TMG 客户端设置**对话框中，单击**新建**。
    
4. 在**应用程序项目设置**对话框中，配置以下规则：
    
|**应用程序**|**密钥**|**值**|
|:-----|:-----|:-----|
|**msoidsvc** <br/> |禁用  <br/> |0  <br/> |
|**msoidsvc** <br/> |DisableEx  <br/> |0  <br/> |
   
有关详细信息，请参阅 Microsoft 知识库文章 2409256，[由于内部防火墙会阻止该连接无法连接到 Skype 的在线业务](http://go.microsoft.com/fwlink/?linkid=3052&amp;kbid=2409256)。
  
### <a name="update-dns-settings"></a>更新 DNS 设置
<a name="update-dns-service"> </a>

如果您的组织自定义的域，此过程是下面的错误消息的可能解决方法：**服务器当前不可用**。
  
- 有关如何将以下的 CNAME 记录添加到您的域的信息联系您的域名称注册：
    
  - **DNS 记录类型**： CNAME 
    
  - **名称**： sip
    
  - **值/目标**： sipdir.online.microsoft.com
    
有关详细信息，请参阅 Microsoft 知识库文章 2566790， [Office 365 中的业务在线 DNS 配置问题的故障排除 Skype](http://go.microsoft.com/fwlink/?linkid=3052&amp;kbid=2566790)。
  
### <a name="install-a-third-party-ssl-certificate-on-your-adfs-server"></a>ADFS 在服务器上安装一个第三方的 SSL 证书
<a name="verify-upn-and"> </a>

以活动域联合身份验证服务 (ADF) 在服务器上安装一个第三方的 SSL 证书，请执行以下步骤：
  
1. 从第三方证书颁发机构如 VeriSign 或 Thawte 获取 SSL 证书。
    
2. 使用 ADFS 管理控制台在 ADFS 服务器上安装证书。 
    
### <a name="update-security-credentials"></a>更新的安全凭据
<a name="update-security-credentials"> </a>

此过程是可能的修复**问题获得个人证书登录所需**的错误消息。
  
若要消除可能的证书或凭据问题，第一次续订的证书用户的 Windows 证书管理器中。 若要执行此操作，请执行以下步骤：
  
1. 打开 Windows 证书管理器。 若要执行此操作，单击**开始**，单击**运行**，键入**certmgr.msc**，然后单击**确定**。 
    
2. 双击**个人**，然后双击**证书**。 
    
3. 通信服务器颁发的证书，然后查找与**颁发者**列进行排序。
    
4. 用鼠标右键单击证书，然后单击**删除**。 
    
接下来，如果用户在运行 Windows 7，删除它们存储的凭据 Windows 凭据管理器中。 若要执行此操作，请执行以下步骤：
  
1. 单击**开始**，单击**控制面板**，然后单击**凭据管理器**。 
    
2. 找到一的组凭据用来连接到 Skype 的在线业务。 
    
3. 展开的一组凭据，，然后单击**删除存储库中**。 
    
4. 重新登录并重新输入用户凭据。
    
最后，如果用户仍然不能登录后您已经更新其凭据，请尝试删除 RSA 文件夹在用户的计算机上，因为它可能会阻止用户身份验证过程的完成：
  
1. 登录到用户的计算机使用的是管理员帐户。
    
2. 如果有必要，请打开**显示隐藏的文件**文件夹视图选项。 
    
3. 到地址栏的文件资源管理器中键入以下内容： **c:\\文档和设置\\用户名\\应用程序数据\\Microsoft\\加密\\RSA**，其中***用户名***是您的 Windows 登录名。
    
4. 删除名称开头的任何文件夹**S-1-5-21-**跟的一串数字。
    
### <a name="modify-trustmodeldata-registry-keys"></a>修改 TrustModelData 注册表项
<a name="modify-trustmodeldata-registry"> </a>

当第一次登录的用户时，他们可能会收到一个对话框，其中包含类似下面的内容：**不能验证服务器是否信任您的登录地址。是否仍要连接？** 这是一种安全功能，而不是错误。 但是，可以防止对话框中显示通过使用组策略对象 (GPO) 前他们第一次登录与您的域名更新用户的计算机。 若要完成此任务，请执行以下操作：
  
- 创建和部署 GPO 附加您的 Skype 的业务域的名称 — — 例如，domainName.contoso.com—to 置此变量的当前值\\软件\\策略\\Microsoft\\Communicator\\TrustModelData。
    
> [!IMPORTANT]
>  必须*追加*的现有值与您的域名，不是简单地将其替换。
  
有关详细信息，请参阅 Microsoft 知识库文章 2531068， [Skype 业务 (Lync) 无法验证服务器信任您的登录地址](http://go.microsoft.com/fwlink/?linkid=3052&amp;kbid=2531068)。
  
### <a name="update-user-settings-in-active-directory"></a>更新 Active Directory 中的用户设置
<a name="update-user-settings"> </a>

如果您的组织具有以前安装的 Microsoft Office 通信服务器或 Microsoft Lync Server 2010 中，您可能不具有您的用户从服务器上删除在停止使用它之前。 因此， **msRTCSIP UserEnabled**属性仍设置为**FALSE**在 Active Directory 域服务。
  
若要解决此问题，请执行以下步骤：
  
1. 更新所有受影响的用户的**msRTCSIP UserEnabled**属性设**为 TRUE**。
    
2. 重新运行 Microsoft Online Services 目录同步工具 （目录同步）。 有关详细信息，请参阅[使用 Azure 活动目录的 AIntegrate 您的内部目录](https://technet.microsoft.com/en-us/library/hh967642.aspx)。 
    
为了解决 Skype 业务联机登录错误，请首先消除登录困难的最常见原因。 如有必要，您可以按照特定的分辨率根据错误类型的步骤。 如果用户仍然不能登录，收集的其他信息，然后再寻求更多帮助。 
## <a name="use-the-microsoft-support-troubleshooting-guide"></a>使用 Microsoft 支持故障排除指南
<a name="toc325626447"> </a>

如果你仍然不能解决用户的登录问题，查看 Microsoft 知识库文章 2541980，[如何解决登录问题在 Skype 的在线业务](http://go.microsoft.com/fwlink/?linkid=3052&amp;kbid=2541980)中的建议。
  
## <a name="collect-more-information-and-seek-additional-help"></a>收集的详细信息，并寻求额外的帮助
<a name="collect-more-information"> </a>

如果按照上述指南，仍不能解决登录问题，必须收集的其他信息，请联系技术支持。 若要执行此操作，请执行以下步骤： 
  
1. 从用户的计算机中获取日志文件和 Windows 事件日志的详细信息。 有关分步说明，请参阅[打开错误日志中 Lync](http://support.office.com/article/eaf6602b-95e0-4c27-869f-36017475806c)最终用户帮助主题。
    
2. 将日志文件和错误的详细的信息发送到 Microsoft 技术支持部门。
    
您可能需要通过受影响的用户的计算机上安装的 Microsoft Online Services 诊断和日志记录 (MOSDAL) 支持 Toolkit 提供更多的诊断信息。 有关详细信息，请参阅[使用 MOSDAL 支持 Toolkit](http://support.office.com/article/ddf1f52f-24a1-4675-abe0-141052c88b72)。
  
为了解决 Skype 业务联机登录错误，请首先消除登录困难的最常见原因。 如有必要，您可以按照特定的分辨率根据错误类型的步骤。 如果用户仍然不能登录，收集的其他信息，然后再寻求更多帮助。 
  
## <a name="related-topics"></a>相关主题
[设置 Skype for Business Online](set-up-skype-for-business-online.md)

[允许 Skype for Business 用户添加 Skype 联系人](let-skype-for-business-users-add-skype-contacts.md)

## <a name="feedback"></a>反馈意见？
提供产品反馈意见或让我们知道我们所执行的信息，请参阅[Skype 业务反馈](https://www.skypefeedback.com)。
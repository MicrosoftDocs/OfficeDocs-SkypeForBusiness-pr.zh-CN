---
title: 管理员 Skype 业务 Online 登录错误疑难解答
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: cdd4801a-2fe1-4aab-bbb6-db5f95f972d1
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- Setup
description: '了解常见原因的 Skype 业务 Online 登录错误和工作通过解决这些问题。 '
ms.openlocfilehash: df34252281bebe429a85fb1a778b6d28023eb9d4
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25371146"
---
# <a name="troubleshooting-skype-for-business-online-sign-in-errors-for-administrators"></a>管理员 Skype 业务 Online 登录错误疑难解答

若要解决的业务 Online 登录错误 Skype，启动通过消除登录难度的最常见原因。 如有必要，则可以按照步骤基于类型的错误的特定解决方案。 如果用户仍然不能登录，收集的其他信息，然后 seek 获取其他帮助。

## <a name="what-do-you-want-to-do"></a>你要做什么？
<a name="top"> </a>

> [检查的 Skype 业务 Online 登录错误的常见原因](troubleshooting-sign-in-errors-for-admins.md#toc323194094)
> 
> [按照相应解决步骤特定错误 （仅适用于企业）](troubleshooting-sign-in-errors-for-admins.md#toc325626440)
> 
> [将 msoidsvc.exe 防火墙条目添加到您的代理服务器](troubleshooting-sign-in-errors-for-admins.md#add-a-firewall)
> 
> [更新 DNS 设置](troubleshooting-sign-in-errors-for-admins.md#update-dns-service)
> 
> [在您的 ADFS 服务器上安装第三方 SSL 证书](troubleshooting-sign-in-errors-for-admins.md#verify-upn-and)
> 
> [更新安全凭据](troubleshooting-sign-in-errors-for-admins.md#update-security-credentials)
> 
> [修改 TrustModelData 注册表项](troubleshooting-sign-in-errors-for-admins.md#modify-trustmodeldata-registry)
> 
> [更新 Active Directory 中的用户设置](troubleshooting-sign-in-errors-for-admins.md#update-user-settings)
> 
> [使用故障排除指南的 Microsoft 支持](troubleshooting-sign-in-errors-for-admins.md#toc325626447)
> 
> [收集的详细信息和 seek 获取其他帮助](troubleshooting-sign-in-errors-for-admins.md#collect-more-information)

## <a name="check-for-common-causes-of-skype-for-business-online-sign-in-errors"></a>检查的 Skype 业务 Online 登录错误的常见原因
<a name="toc323194094"> </a>

大多数登录问题可以追溯到少量的原因，以及其中的许多易于更正。 下表列出了一些常见登录错误的原因和一些您或用户可以采取的步骤来解决这些问题。


| **可能的原因**                                                                                                                                                    | **解决方案**                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 |
|:----------------------------------------------------------------------------------------------------------------------------------------------------------------------|:-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 登录过程中，出现一个对话框，其中包含以下短语：**无法验证服务器是否为您的登录地址受信任。仍然连接？** <br/> | 确认对话框中的域名称是您组织中的受信任的服务器 — 例如， **domainName.contoso.com**。 让用户选择**始终信任此服务器**复选框，然后单击**连接**。 <br/> 企业客户可以阻止此消息显示当用户登录首次通过修改每个用户的计算机上的 Windows 注册表。 有关详细信息，请参阅[修改 TrustModelData 注册表项](troubleshooting-sign-in-errors-for-admins.md#modify-trustmodeldata-registry)。<br/> |
| 键入错误登录地址、 用户名或密码  <br/>                                                                                                               | 确认用户的登录名和密码正确。 <br/>  验证用户的登录名格式，如下所示： <strong>bobk@contoso.com</strong>。 这可能不同于您用于登录到贵组织的网络的格式。  <br/>  询问用户尝试再次登录。 <br/>                                                                                                                                                                                                                             |
| 忘记的密码  <br/>                                                                                                                                             | 重置用户的密码并通知他或她的新的临时密码。  <br/>                                                                                                                                                                                                                                                                                                                                                                                                                                                          |
| 没有为业务 Online 使用 Skype 授权  <br/>                                                                                                                  | 确认用户注册为 Skype 业务联机用户。 如果没有，注册用户，并询问他或她再次登录。  <br/>                                                                                                                                                                                                                                                                                                                                                                                           |
| Skype 业务 online 安装的版本不正确  <br/>                                                                                                           | 此问题是通常与包含以下错误消息：**身份验证服务可能与此版本的程序不兼容**。  <br/> 要求用户要卸载并重新 Skype 安装从 Office 365 门户业务 online。  <br/>                                                                                                                                                                                                                                                    |
| 获取个人证书所需登录问题  <br/>                                                                                           | 如果最近已更改用户的登录地址，它们可能需要删除缓存登录数据。 要求用户注销，请单击的删除我的登录信息链接上的登录屏幕中，然后再试。  <br/>                                                                                                                                                                                                                                                                                                                                |
| 设置自定义域名，并不可能通过系统传播完成所做的更改。  <br/>                                                         | 首先，确保您已修改的域服务 (DNS) 记录，以反映的更改。  <br/> 如果您已指定的所需的 DNS 更改，告知用户尝试登录更高版本。 DNS 更改可能需要 72 小时才能反映在整个系统。  <br/>                                                                                                                                                                                                                                                        |
| 与服务器时钟不同步的系统时钟  <br/>                                                                                                                     | 确保您的网络域控制器与可靠的外部时间源同步。 有关详细信息，请参阅 Microsoft 知识库文章 816042，[如何配置在 Windows Server 权威时间服务器](https://go.microsoft.com/fwlink/?linkid=3052&amp;kbid=816042)。<br/>                                                                                                                                                                                                                                          |

若要解决的业务 Online 登录错误 Skype，启动通过消除登录难度的最常见原因。 如有必要，则可以按照步骤基于类型的错误的特定解决方案。 如果用户仍然不能登录，收集的其他信息，然后 seek 获取其他帮助。

## <a name="follow-resolution-steps-for-a-specific-error-enterprise-only"></a>按照相应解决步骤特定错误 （仅适用于企业）
<a name="toc325626440"> </a>

> [!IMPORTANT]
>  这些说明是主要适用于 Microsoft Office 365 计划 E 客户。 如果您是 Office 365 计划 P 客户，继续下一节，[收集的详细信息和 seek 获取其他帮助](troubleshooting-sign-in-errors-for-admins.md#collect-more-information)。

如果您试图在未在上一节中的建议后，用户不能登录，您可以执行基于错误类型的其他故障排除。 下表列出的最常见的错误消息和可能的原因。 下表是为了解决每个问题的详细的过程。

|**错误消息**|**可能的原因**|**解决方案**|
|:-----|:-----|:-----|
|找不到的登录地址  <br/> |通过外部防火墙或代理服务器，将不会从 Microsoft Online Services 登录助手 (msoidsvc.exe) 登录请求。  <br/> |[将 msoidsvc.exe 防火墙条目添加到您的代理服务器](troubleshooting-sign-in-errors-for-admins.md#add-a-firewall) <br/> |
|服务器是暂时不可用  <br/> |如果贵组织拥有的自定义域名，缺失或错误可能是必要的域名系统 (DNS) 设置。  <br/> |[更新 DNS 设置](troubleshooting-sign-in-errors-for-admins.md#update-dns-service) <br/> |
|服务器是暂时不可用  <br/> |如果您的组织使用单一登录与 Active Directory 联合身份验证服务 (ADFS)，您可能使用的是自签名的安全套接字层 (SSL) 证书，而不是从第三方证书颁发机构。  <br/> |[在您的 ADFS 服务器上安装第三方 SSL 证书](troubleshooting-sign-in-errors-for-admins.md#verify-upn-and) <br/> |
|获取个人证书所需登录问题  <br/> |如果已删除缓存的服务器数据用于登录和继续出现错误，、 用户的安全凭据可能已损坏，或可能阻止身份验证的用户的计算机上的 RSA 文件夹。  <br/> |[更新安全凭据](troubleshooting-sign-in-errors-for-admins.md#update-security-credentials) <br/> |
|用户首次登录时，将出现一个证书信任对话框。  <br/> |如果您的业务服务器 Skype 未列出**TrustModelData**注册表项中，将显示此对话框。 <br/> |[修改 TrustModelData 注册表项](troubleshooting-sign-in-errors-for-admins.md#modify-trustmodeldata-registry) <br/> |
|用户不是启用 SIP  <br/> |如果您的组织具有以前安装的 Microsoft Office Communications Server 或 Microsoft Lync Server 2010，您可能不删除用户从服务器之前停用它。 因此， **Msrtcsip-userenabled**属性仍然设置为**FALSE** Active Directory 域服务中。 <br/> |[更新 Active Directory 中的用户设置](troubleshooting-sign-in-errors-for-admins.md#update-user-settings)<br/> |

### <a name="add-a-firewall-entry-for-msoidsvcexe-to-your-proxy-server"></a>将 msoidsvc.exe 防火墙条目添加到您的代理服务器
<a name="add-a-firewall"> </a>

此过程是可能的修复程序的以下错误消息：**未找到的登录地址**。

> [!NOTE]
> 下面的步骤假定您使用 Microsoft Forefront Threat Management Gateway (TMG) 2010年。 如果您具有不同的 web 网关解决方案，使用下面的步骤 4 中所述的设置。


要为 Msoidsvc.exe 在 Forefront TMG 2010 中创建的应用程序条目，请按照下列步骤：

1. 在 Forefront 的左窗格中，单击**网络**。

2. 单击**网络**选项卡。在右窗格中的**任务**选项卡上，单击**配置 Forefront TMG 客户端设置**。

3. 在**Forefront TMG 客户端设置**对话框中，单击**新建**。

4. 在**应用程序项目设置**对话框中，配置以下规则：

|**应用程序**|**关键字**|**值**|
|:-----|:-----|:-----|
|**msoidsvc** <br/> |禁用  <br/> |0  <br/> |
|**msoidsvc** <br/> |DisableEx  <br/> |0  <br/> |

有关详细信息，请参阅 Microsoft 知识库文章 2409256，[因为本地防火墙阻止连接，无法连接到业务 online Skype](https://go.microsoft.com/fwlink/?linkid=3052&amp;kbid=2409256)。

### <a name="update-dns-settings"></a>更新 DNS 设置
<a name="update-dns-service"> </a>

如果您的组织具有自定义域，此过程是以下错误消息可能修复：**服务器是暂时不可用**。

- 有关如何将下面的 CNAME 记录添加到您的域的信息，请联系您域名注册机构：

  - **DNS 记录类型**： CNAME

  - **名称**： sip

  - **值/目的地**： sipdir.online.microsoft.com

有关详细信息，请参阅 Microsoft 知识库文章 2566790， [Office 365 中的业务联机 DNS 配置问题的疑难解答 Skype](https://go.microsoft.com/fwlink/?linkid=3052&amp;kbid=2566790)。

### <a name="install-a-third-party-ssl-certificate-on-your-adfs-server"></a>在您的 ADFS 服务器上安装第三方 SSL 证书
<a name="verify-upn-and"> </a>

若要在您的活动域联合身份验证服务 (ADFS) 服务器上安装第三方 SSL 证书，请按照下列步骤：

1. 从如 VeriSign 或 Thawte 第三方证书颁发机构获取 SSL 证书。

2. 使用 ADFS 管理控制台中，在您的 ADFS 服务器上安装证书。

### <a name="update-security-credentials"></a>更新安全凭据
<a name="update-security-credentials"> </a>

此过程是可能的修复**问题获取个人证书需要登录**的错误消息。

若要消除可能的证书或凭据问题，请首先续订 Windows 证书管理器中的用户的证书。 若要执行此操作，请按照以下步骤：

1. 打开 Windows 证书管理器。 若要执行此操作，单击**开始**，单击**运行**，键入**certmgr.msc**，，然后单击**确定**。

2. 双击**个人**，然后双击**证书**。

3. 排序依据的**颁发者**列和 Communications server 颁发的证书，然后外观。

4. 右键单击该证书，，然后单击**删除**。

接下来，如果用户正在运行 Windows 7，删除其存储的凭据 Windows 凭据管理器中。 若要执行此操作，请按照以下步骤：

1. 单击**开始**，单击**控制面板**，，然后单击**凭据管理器**。

2. 找到用于连接到 Skype 业务 online 凭据集。

3. 展开的一组凭据，，，然后单击**存储库中删除**。

4. 再次登录，然后重新键入用户的凭据。

最后，如果用户仍然不能登录已更新其凭据后，请尝试删除用户的计算机上的 RSA 文件夹因为可能会阻止用户身份验证过程完成：

1. 登录到使用管理员帐户的用户的计算机。

2. 如有必要，打开**显示隐藏的文件**文件夹视图选项。

3. 键入以下内容到在地址栏中的文件资源管理器： **c:\\Documents and Settings\\UserName\\应用程序数据\\Microsoft\\加密\\RSA**，其中***UserName***是您 Windows 登录名。

4. 删除名称开头的任何文件夹**S-1-5-21-** 跟包含数字的字符串。

### <a name="modify-trustmodeldata-registry-keys"></a>修改 TrustModelData 注册表项
<a name="modify-trustmodeldata-registry"> </a>

当用户首次使用登录时，它们可能会收到一个对话框，包含与下面类似：**无法验证服务器是否为您的登录地址受信任。仍然连接？** 这是一项安全功能，而不是错误。 但是，可以阻止对话框中显示通过使用组策略对象 (GPO) 之前用户首次登录您的域名与更新用户的计算机。 若要实现此目的，执行以下操作：

- 创建和部署附加业务域名您 Skype GPO — 例如，domainName.contoso.com—to HKEY_LOCAL_MACHINE 的当前值\\软件\\策略\\Microsoft\\Communicator\\TrustModelData。

> [!IMPORTANT]
>  您必须*追加*到现有的值您的域名，不是简单地将其替换。

有关详细信息，请参阅 Microsoft 知识库文章 2531068， [Skype for Business (Lync) 无法验证服务器为您的登录地址受信任](https://go.microsoft.com/fwlink/?linkid=3052&amp;kbid=2531068)。

### <a name="update-user-settings-in-active-directory"></a>更新 Active Directory 中的用户设置
<a name="update-user-settings"> </a>

如果您的组织具有以前安装的 Microsoft Office Communications Server 或 Microsoft Lync Server 2010，您可能不删除用户从服务器之前停用它。 因此， **Msrtcsip-userenabled**属性仍然设置为**FALSE** Active Directory 域服务中。

若要解决此问题，请按照下列步骤：

1. 更新所有受影响的用户的**Msrtcsip-userenabled**属性为**TRUE**。

2. 重新运行 Microsoft Online Services 目录同步工具 (DirSync)。 有关详细信息，请参阅[Azure Active Directory AIntegrate 本地目录](https://technet.microsoft.com/en-us/library/hh967642.aspx)。

若要解决的业务 Online 登录错误 Skype，启动通过消除登录难度的最常见原因。 如有必要，则可以按照步骤基于类型的错误的特定解决方案。 如果用户仍然不能登录，收集的其他信息，然后 seek 获取其他帮助。
## <a name="use-the-microsoft-support-troubleshooting-guide"></a>使用故障排除指南的 Microsoft 支持
<a name="toc325626447"> </a>

如果仍无法解决用户的登录问题，请查看 Microsoft 知识库文章 2541980，[如何解决登录问题中 Skype 业务 online](https://go.microsoft.com/fwlink/?linkid=3052&amp;kbid=2541980)中的建议。

## <a name="collect-more-information-and-seek-additional-help"></a>收集的详细信息和 seek 获取其他帮助
<a name="collect-more-information"> </a>

如果您已关注上面的指南并仍无法解决登录问题，您必须收集的其他信息并与技术支持联系。 若要执行此操作，请按照以下步骤：

1. 从用户的计算机中获取的日志文件和 Windows 事件日志的详细信息。 有关分步说明，请参阅[启用 Lync 中的错误日志](https://support.office.com/article/eaf6602b-95e0-4c27-869f-36017475806c)最终用户帮助主题。

2. 将日志文件和有关错误的详细的信息发送到 Microsoft 技术支持。

可能要求您通过受影响的用户的计算机上安装 Microsoft Online Services 诊断和日志记录 (MOSDAL) 支持工具包提供附加诊断信息。 有关详细信息，请参阅[使用 MOSDAL 支持工具包](https://support.office.com/article/ddf1f52f-24a1-4675-abe0-141052c88b72)。

若要解决的业务 Online 登录错误 Skype，启动通过消除登录难度的最常见原因。 如有必要，则可以按照步骤基于类型的错误的特定解决方案。 如果用户仍然不能登录，收集的其他信息，然后 seek 获取其他帮助。

## <a name="related-topics"></a>相关主题
[设置 Skype for Business Online](set-up-skype-for-business-online.md)

[允许 Skype for Business 用户添加 Skype 联系人](let-skype-for-business-users-add-skype-contacts.md)



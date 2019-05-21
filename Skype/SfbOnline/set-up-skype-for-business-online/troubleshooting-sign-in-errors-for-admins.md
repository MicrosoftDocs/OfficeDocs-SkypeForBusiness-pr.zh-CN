---
title: 针对管理员的 Skype for Business Online 登录错误进行故障排除
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: cdd4801a-2fe1-4aab-bbb6-db5f95f972d1
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
localization_priority: Priority
f1keywords: None
ms.custom:
- Setup
description: '了解 Skype for Business Online 登录错误的常见原因, 并解决这些问题。 '
ms.openlocfilehash: 25f6c08392823c35e4bb5d53ac523c1efeddf958
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34285031"
---
# <a name="troubleshooting-skype-for-business-online-sign-in-errors-for-administrators"></a>针对管理员的 Skype for Business Online 登录错误进行故障排除

要解答 Skype for Business Online 登录错误疑难问题，首先应消除登录困难的最常见原因。 如有必要, 可以根据错误类型执行特定的解决步骤。 如果用户仍然无法登录, 请收集其他信息, 然后寻求进一步帮助。

## <a name="what-do-you-want-to-do"></a>要执行什么操作？
<a name="top"> </a>

> [检查 Skype for Business Online 登录错误的常见原因](troubleshooting-sign-in-errors-for-admins.md#toc323194094)
> 
> [执行特定错误的解决步骤（仅限企业版）](troubleshooting-sign-in-errors-for-admins.md#toc325626440)
> 
> [将 msoidsvc.exe 的防火墙项添加到代理服务器](troubleshooting-sign-in-errors-for-admins.md#add-a-firewall)
> 
> [更新 DNS 设置](troubleshooting-sign-in-errors-for-admins.md#update-dns-service)
> 
> [在 ADFS 服务器上安装第三方 SSL 证书](troubleshooting-sign-in-errors-for-admins.md#verify-upn-and)
> 
> [更新安全凭据](troubleshooting-sign-in-errors-for-admins.md#update-security-credentials)
> 
> [修改 TrustModelData 注册表项](troubleshooting-sign-in-errors-for-admins.md#modify-trustmodeldata-registry)
> 
> [更新 Active Directory 中的用户设置](troubleshooting-sign-in-errors-for-admins.md#update-user-settings)
> 
> [使用 Microsoft Support 疑难解答指南](troubleshooting-sign-in-errors-for-admins.md#toc325626447)
> 
> [收集更多信息并寻求进一步帮助](troubleshooting-sign-in-errors-for-admins.md#collect-more-information)

## <a name="check-for-common-causes-of-skype-for-business-online-sign-in-errors"></a>检查 Skype for Business Online 登录错误的常见原因
<a name="toc323194094"> </a>

大多数登录问题可以追溯到少数原因, 其中许多原因很容易纠正。 下表列出了登录错误的一些常见原因以及你或用户可以执行以解决这些错误的一些步骤。


| **可能的原因**                                                                                                                                                    | **解决方案**                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 |
|:----------------------------------------------------------------------------------------------------------------------------------------------------------------------|:-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 在登录过程中，会出现一个包含以下短语的对话框： ** 无法验证服务器是否是可信任的登录地址。 是否仍要连接？** <br/> | 验证该对话框中的域名是否为贵公司的可信任服务器，例如 **domainName.contoso.com**。 让用户选中**始终信任此服务器**复选框，然后单击**连接**。 <br/> 企业客户可以通过修改每个用户的计算机上的 Windows 注册表，阻止在用户首次登录时显示此消息。 有关详细信息，请参阅[修改 TrustModelData 注册表项](troubleshooting-sign-in-errors-for-admins.md#modify-trustmodeldata-registry)。<br/> |
| 输入了错误的登录地址、用户名或密码  <br/>                                                                                                               | 确认用户的登录名和密码正确。 <br/>  验证用户的登录名格式是否如下所示： <strong>bobk@contoso.com</strong>。 这可能不同于你用于登录到组织的网络中的格式。  <br/>  让用户再次尝试登录。   <br/>                                                                                                                                                                                                                             |
| 忘记密码  <br/>                                                                                                                                             | 重置用户密码，并通知他或她新的临时密码。  <br/>                                                                                                                                                                                                                                                                                                                                                                                                                                                          |
| 未授权使用 Skype for Business Online  <br/>                                                                                                                  | 确认用户已注册为 Skype for Business Online 用户。 如果尚未注册，请注册该用户，然后让他或她再次登录。  <br/>                                                                                                                                                                                                                                                                                                                                                                                           |
| 安装的 Skype for Business Online 版本错误  <br/>                                                                                                           | 此问题通常与包含以下短语的错误消息相关联：**身份验证服务可能与此版本的程序不兼容**。  <br/> 让用户卸载并重新安装 Office 365 Portal 中的 Skype for Business Online。  <br/>                                                                                                                                                                                                                                                    |
| 获得登录所需的个人证书时出现问题  <br/>                                                                                           | 如果用户的登录地址最近已发生更改，他们可能需要删除缓存的登录数据。 若要求用户注销，请在登录屏幕上单击“删除我的登录信息”链接，然后重试。  <br/>                                                                                                                                                                                                                                                                                                                                |
| 你设置了自定义域名，而所做更改可能未在系统内完成传播。  <br/>                                                         | 首先，确保修改了域名服务 (DNS) 记录以反映更改。  <br/> 如果已经做了必要的 DNS 更改，请建议用户尝试稍后登录。 DNS 更改最多需要 72 个小时才会在整个系统中反映出来。  <br/>                                                                                                                                                                                                                                                        |
| 系统时钟与服务器时钟不同步  <br/>                                                                                                                     | 确保网络域名控制器与可靠的外部时间源保持同步。 有关详细信息，请参阅 Microsoft 知识库文章 816042 [如何在 Windows Server 中配置权威时间服务器](https://go.microsoft.com/fwlink/?linkid=3052&amp;kbid=816042)。<br/>                                                                                                                                                                                                                                          |

要解答 Skype for Business Online 登录错误疑难问题，首先应消除登录困难的最常见原因。 如有必要, 可以根据错误类型执行特定的解决步骤。 如果用户仍然无法登录, 请收集其他信息, 然后寻求进一步帮助。

## <a name="follow-resolution-steps-for-a-specific-error-enterprise-only"></a>执行特定错误的解决步骤（仅限企业版）
<a name="toc325626440"> </a>

> [!IMPORTANT]
>  这些说明主要适用于 Microsoft Office 365 Plan E 客户。 如果你是 Office 365 Plan P 客户，请继续下面的部分， [收集更多信息并寻求进一步帮助 ](troubleshooting-sign-in-errors-for-admins.md#collect-more-information)。

如果尝试了前一节中的建议之后用户仍然无法登录，可以基于错误类型执行其他疑难解答。 下表列出了最常见的错误消息和可能的原因。 表后面提供了解决各个问题的详细过程。

|**错误消息**|**可能的原因**|**解决方案**|
|:-----|:-----|:-----|
|找不到登录地址  <br/> |Microsoft Online Services 登录助手 (msoidsvc.exe) 发出的登录请求未通过外部防火墙或代理服务器。  <br/> |[将 msoidsvc.exe 的防火墙项添加到代理服务器](troubleshooting-sign-in-errors-for-admins.md#add-a-firewall) <br/> |
|服务器暂时不可用  <br/> |如果贵公司有自定义域名，则必要的域名系统 (DNS) 设置可能缺少或不正确。  <br/> |[更新 DNS 设置](troubleshooting-sign-in-errors-for-admins.md#update-dns-service) <br/> |
|服务器暂时不可用  <br/> |如果贵公司使用单一登录和 Active Directory Federation Services (ADFS)，那么你可能使用了自签的 Secure Socket Layer (SSL) 证书，而不是来自第三方证书颁发机构的证书。  <br/> |[在 ADFS 服务器上安装第三方 SSL 证书](troubleshooting-sign-in-errors-for-admins.md#verify-upn-and) <br/> |
|获得登录所需的个人证书时出现问题  <br/> |如果已经删除了用于登录的缓存服务器数据, 并且错误继续出现, 则用户的安全凭据可能已损坏, 或者用户计算机上的 RSA 文件夹可能会阻止身份验证。  <br/> |[更新安全凭据](troubleshooting-sign-in-errors-for-admins.md#update-security-credentials) <br/> |
|当用户首次登录时，出现证书信任对话框。  <br/> |如果 Skype for Business 服务器尚未在 **TrustModelData** 注册表项中列出, 则会出现此对话框。 <br/> |[修改 TrustModelData 注册表项](troubleshooting-sign-in-errors-for-admins.md#modify-trustmodeldata-registry) <br/> |
|用户未启用 SIP。  <br/> |如果贵公司以前安装了 Microsoft Office Communications Server 或 Microsoft Lync Server 2010，则在取消服务器之前，你可能尚未从服务器中删除你的用户。 因此, **msRTCSIP-UserEnabled** 属性在 Active Directory Domain Services 中仍设置为 **FALSE**。 <br/> |[更新 Active Directory 中的用户设置](troubleshooting-sign-in-errors-for-admins.md#update-user-settings)<br/> |

### <a name="add-a-firewall-entry-for-msoidsvcexe-to-your-proxy-server"></a>将 msoidsvc.exe 的防火墙项添加到代理服务器
<a name="add-a-firewall"> </a>

此过程可能修复以下错误消息: **找不到登录地址**。

> [!NOTE]
> 下列步骤假定你使用的是 Microsoft Forefront Threat Management Gateway (TMG) 2010。 如果你有不同的 Web 网关解决方案，请使用下面的步骤 4 中介绍的设置。


要在 Forefront TMG 2010 中为 Msoidsvc.exe 创建应用程序项目，请按照下列步骤操作：

1. 在 Forefront 左窗格中，单击 **Networking**。

2. 单击 **Network** 选项卡。在右窗格中的 **Tasks** 选项卡下, 单击 **Configure Forefront TMG Client Settings**。

3. 在 **Forefront TMG Client Settings** 对话框中，单击 **New**。

4. 在 **Application Entry Setting** 对话框中，配置以下规则：

|**Application**|**Key**|**Value**|
|:-----|:-----|:-----|
|**msoidsvc** <br/> |禁用  <br/> |0  <br/> |
|**msoidsvc** <br/> |DisableEx  <br/> |0  <br/> |

有关详细信息，请参阅 Microsoft 知识库文章 2409256 [无法连接到 Skype for Business Online，因为企业内防火墙阻止连接](https://go.microsoft.com/fwlink/?linkid=3052&amp;kbid=2409256)。

### <a name="update-dns-settings"></a>更新 DNS 设置
<a name="update-dns-service"> </a>

如果贵公司有自定义域名，此过程可能修复以下错误消息： **服务器暂时不可用**。

- 有关如何将下列 CNAME 记录添加到域名的信息，请联系域名注册机构：

  - **DNS 记录类型**：CNAME

  - **名称**：sip

  - **Value/Destination**: sipdir.online.lync.com

有关详细信息, 请参阅 Microsoft 知识库文章 2566790, [Office 365 中的 Skype for business Online DNS 配置问题疑难解答](https://go.microsoft.com/fwlink/?linkid=3052&amp;kbid=2566790)。

### <a name="install-a-third-party-ssl-certificate-on-your-adfs-server"></a>在 ADFS 服务器上安装第三方 SSL 证书
<a name="verify-upn-and"> </a>

要在 Active Domain Federation Services (ADFS) 服务器上安装第三方 SSL 证书，请按照下列步骤操作：

1. 从第三方证书颁发机构（如 VeriSign 或 Thawte）获得 SSL 证书。

2. 使用 ADFS 管理控制台在 ADFS 服务器上安装证书。

### <a name="update-security-credentials"></a>更新安全凭据
<a name="update-security-credentials"> </a>

此过程可能修复以下错误消息： **获取登录所需的个人证书时出现问题**。

要消除可能的证书或凭据问题，请首先在 Windows 证书管理器中续订用户的证书。 为此，请按照下列步骤操作：

1. 打开 Windows 证书管理器。 要执行此操作，请单击**开始**、**运行**，键入 **certmgr.msc**，然后单击**确定**。

2. 双击**个人**，然后双击**证书**。

3. 按**颁发者** 列排序，然后查找由通信服务器颁发的证书。

4. 右键单击证书，然后单击**删除**。

接下来，如果用户运行 Windows 7，请删除 Windows 凭据管理器中存储的凭据。 为此，请按照下列步骤操作：

1. 单击**开始**，单击**控制面板**，然后单击**凭据管理器**。

2. 找到用于连接到 Skype for Business Online 的一组凭据。

3. 展开一组凭据，然后单击**从保管库中删除**。

4. 再次登录，并重新输入用户的凭据。

最后，如果在更新凭据后用户仍然无法登录，请尝试在用户的计算机上删除 RSA 文件夹，因为它可能阻止用户身份验证过程完成：

1. 使用管理员帐户登录用户的计算机。

2. 如有必要，请启用文件夹视图选项**显示隐藏的文件**。

3. 在文件管理器的地址栏中键入以下内容：**C:\\Documents and Settings\\UserName\\Application Data\\Microsoft\\Crypto\\RSA**， 其中，***UserName*** 是你的 Windows 登录名。

4. 删除名为 **S-1-5-21-** 且后面跟有一串数字的任何文件夹。

### <a name="modify-trustmodeldata-registry-keys"></a>修改 TrustModelData 注册表项
<a name="modify-trustmodeldata-registry"> </a>

当用户首次登录时，他们可能收到包含以下语句的对话框： **无法验证你的登录地址是否是可信任服务器。仍然连接？** 这是一项安全功能，而非错误。 但是，你可以阻止显示此对话框，方法是在用户首次登录之前通过组策略对象 (GPO) 使用你的域名更新用户的机器。 若要完成此任务，请执行以下操作：

- 创建并部署将 Skype for Business 域名（例如 domainName.contoso.com）附加到 HKEY_LOCAL_MACHINE\\Software\\Policies\\Microsoft\\Communicator\\TrustModelData 的当前值的 GPO。

> [!IMPORTANT]
>  必须将域名*附加*到现有值，而不只是替换它。

有关详细信息，请参阅 Microsoft 知识库文章 2531068 [Skype for Business (Lync) 无法验证你的登录地址是否是可信任服务器](https://go.microsoft.com/fwlink/?linkid=3052&amp;kbid=2531068)。

### <a name="update-user-settings-in-active-directory"></a>更新 Active Directory 中的用户设置
<a name="update-user-settings"> </a>

如果贵公司以前安装了 Microsoft Office Communications Server 或 Microsoft Lync Server 2010，则在取消服务器之前，你可能尚未从服务器中删除你的用户。 因此, **msRTCSIP-UserEnabled** 属性在 Active Directory Domain Services 中仍设置为 **FALSE**。

若要解决此问题，请执行以下步骤：

1. 将所有受影响用户的 **msRTCSIP-UserEnabled** 属性更新为 **TRUE**。

2. 重新运行 Microsoft Online Services 目录同步工具 (DirSync)。 有关详细信息, 请参阅[将本地目录与 Azure Active Directory 集成](https://technet.microsoft.com/zh-CN/library/hh967642.aspx)。

要解答 Skype for Business Online 登录错误疑难问题，首先应消除登录困难的最常见原因。 如有必要, 可以根据错误类型执行特定的解决步骤。 如果用户仍然无法登录, 请收集其他信息, 然后寻求进一步帮助。
## <a name="use-the-microsoft-support-troubleshooting-guide"></a>使用 Microsoft 支持疑难解答指南
<a name="toc325626447"> </a>

如果你仍然无法解决用户的登录问题, 请查看 Microsoft 知识库文章2541980中的建议, 即[如何解决 Skype for Business Online 中的登录问题](https://go.microsoft.com/fwlink/?linkid=3052&amp;kbid=2541980)。

## <a name="collect-more-information-and-seek-additional-help"></a>收集更多信息并寻求进一步帮助
<a name="collect-more-information"> </a>

如果按照上述指导进行了操作，但是仍然无法解决登录问题，则必须收集其他信息，并与技术支持人员联系。 为此，请按照下列步骤操作：

1. 从用户的机器获取日志文件和 Windows 事件日志详细信息。 有关分步说明, 请参阅终端用户帮助主题[在 Lync 中打开错误日志](https://support.office.com/article/eaf6602b-95e0-4c27-869f-36017475806c)。

2. 将关于错误的日志文件和详细信息发送给 Microsoft 技术支持人员。

你可能会被要求通过在受影响的用户的计算机上安装 Microsoft 联机服务诊断和日志记录 (MOSDAL) 支持工具包来提供其他诊断信息。 有关详细信息，请参阅[使用 MOSDAL 支持工具包](https://support.office.com/article/ddf1f52f-24a1-4675-abe0-141052c88b72)。

要解答 Skype for Business Online 登录错误疑难问题，首先应消除登录困难的最常见原因。 如有必要, 可以根据错误类型执行特定的解决步骤。 如果用户仍然无法登录, 请收集其他信息, 然后寻求进一步帮助。

## <a name="related-topics"></a>相关主题
[设置 Skype for Business Online](set-up-skype-for-business-online.md)

[允许 Skype for Business 用户添加 Skype 联系人](let-skype-for-business-users-add-skype-contacts.md)



---
title: Skype 业务 Online 和 Exchange 服务器之间的集成
ms.reviewer: cbland
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 4/2/2019
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: ffe4c3ba-7bab-49f1-b229-5142a87f94e6
description: 配置 OAuth 业务 online 本地 Exchange 和 Skype 之间的身份验证使 Skype 功能支持中所述的业务和 Exchange 集成功能。
ms.openlocfilehash: 976aae8287c1d9f209975d53ebc64ac80033c591
ms.sourcegitcommit: 42666cf15b37279244d205715016a10e01fc752e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/02/2019
ms.locfileid: "31040014"
---
# <a name="configure-integration-between-skype-for-business-online-or-microsoft-teams-and-exchange-server"></a>配置 Skype for Business 联机或 Microsoft 团队和 Exchange 服务器之间的集成 

配置 Exchange server 和 Skype 之间业务 online 的集成允许 Skype[功能支持](../../plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md#feature_support)中所述的业务和 Exchange 集成功能。

本主题适用于通过 2019年与 Exchange Server 2013 的集成。

## <a name="what-do-you-need-to-know-before-you-begin"></a>开始之前你需要了解哪些信息？

- 完成此任务的估计时间：15 分钟

-  在可以执行此过程或其他过程之前，你需要被分配适当的权限。 若要查看所需的权限，请参阅[and Shell infrastructure permissions](https://go.microsoft.com/fwlink/p/?LinkId=746511)主题。

- 有关可能适用于此主题中的过程的键盘快捷方式的信息，请参阅[Exchange 管理中心中的键盘快捷方式]( https://go.microsoft.com/fwlink/p/?LinkId=746512)。

## <a name="configure-integration-between-exchange-server-and-o365"></a>配置 Exchange Server 和 O365 之间的集成

### <a name="step-1-configure-oauth-authentication-between-exchange-server-and-o365"></a>步骤 1： 配置 Exchange Server 和 O365 之间的 OAuth 身份验证

执行以下文章中的步骤：

[配置 Exchange 和 Exchange Online 组织之间的 OAuth 身份验证](https://docs.microsoft.com/en-us/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help)

### <a name="step-2-create-a-new-mail-user-account-for-the-skype-for-business-online-or-teams-partner-application"></a>步骤 2： 业务联机或团队合作伙伴应用程序为 Skype 创建新邮件用户帐户

Exchange 服务器上完成此步骤。 它将创建一个邮件用户并为其分配合适的管理角色权限。 随后此用户将用于下一步骤。

指定为 Exchange 组织已验证的域。 此域应为同一个域用作用于内部部署 Exchange 帐户的主 SMTP 域。 此域称作\<验证域\>在下面的过程。 此外， \<DomainControllerFQDN\>应域控制器的 FQDN。

``` Powershell
$user = New-MailUser -Name O365-ApplicationAccount -ExternalEmailAddress O365-ApplicationAccount@<your Verified Domain> -DomainController <DomainControllerFQDN>
```

此命令将在地址列表中隐藏新的邮件用户。

``` Powershell
Set-MailUser -Identity $user.Identity -HiddenFromAddressListsEnabled $True -DomainController <DomainControllerFQDN>
```

接下来的两个命令将为这个新帐户分配 UserApplication 和 ArchiveApplication 管理角色。

``` Powershell
New-ManagementRoleAssignment -Role UserApplication -User $user.Identity -DomainController <DomainControllerFQDN>
```

``` Powershell
New-ManagementRoleAssignment -Role ArchiveApplication -User $user.Identity -DomainController <DomainControllerFQDN>
```

### <a name="step-3-create-and-enable-a-partner-application-for-skype-for-business-online-or-teams"></a>步骤 3： 创建和启用合作伙伴应用程序的 Skype 业务联机或团队

创建新的合作伙伴应用程序，并且将使用你刚刚创建的帐户。 运行以下命令在 Exchange PowerShell 中，在您的内部部署 Exchange 组织。

``` Powershell
New-PartnerApplication -Name SfBOnline -ApplicationIdentifier 00000004-0000-0ff1-ce00-000000000000 -Enabled $True -LinkedAccount $user.Identity
```

### <a name="verify-your-success"></a>验证是否成功

验证配置通过验证成功工作的一些功能正确。 

1. 确认 Outlook 日历委派的工作方式与 Exchange Server 2016 或 2019年邮箱介于这两个两个团队用户。

2. 确认在 Outlook 对话历史记录文件夹中的移动客户端的对话历史记录可见。

另外，查看您的通信。 OAuth 握手流量是真正独特 （和看起来像基本身份验证），尤其是在领域，开始将看到如下所示的颁发者流量: 00000004-0000-0ff1-ce00-000000000000 @ (有时与 / 之前@ 符号)，正在传递令牌中。 您将看用户名和密码，即点的 OAuth。 但您将看到 Office 颁发者 –"4"在这种情况下是 Skype 商业 – 和您的订阅的领域。

如果希望以确保您成功使用 OAuth，请确保您知道要预期并知道流量应如下所示。 [下面是收获](https://tools.ietf.org/html/draft-ietf-oauth-v2-23#page-34)是这样，下面是一个非常标准[的 Microsoft 应用程序中的 OAuth 流量示例](https://download.microsoft.com/download/8/5/8/858F2155-D48D-4C68-9205-29460FD7698F/[MS-SPS2SAUTH].pdf)（真正有用读取，但它不使用刷新令牌），并且有可以让您看到到您 OAuth JWT (JSON 的 Fiddler 扩展Web 令牌）。

下面是[一个设置的示例](https://blogs.msdn.microsoft.com/kaevans/2015/03/30/updated-fiddler-oauth-inspector/)中，但您可以使用任何要执行此过程的网络跟踪工具。

## <a name="related-topics"></a>相关主题

[配置 Exchange 和 Exchange Online 组织之间的 OAuth 身份验证](https://docs.microsoft.com/en-us/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help)

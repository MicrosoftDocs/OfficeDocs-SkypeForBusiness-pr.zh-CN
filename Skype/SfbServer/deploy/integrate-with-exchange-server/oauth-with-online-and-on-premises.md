---
title: Skype for Business Online 和 Exchange server 之间的集成
ms.reviewer: cbland
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 4/2/2019
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: ffe4c3ba-7bab-49f1-b229-5142a87f94e6
description: 在 Exchange Online 和 Skype for business Online 之间配置 OAuth 身份验证可启用功能支持中所述的 Skype for Business 和 Exchange 集成功能。
ms.openlocfilehash: be1fd4ae0c1a1046a8da1d9a30550ac238a4034a
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34278124"
---
# <a name="configure-integration-between-skype-for-business-online-or-microsoft-teams-and-exchange-server"></a>配置 Skype for Business Online 或 Microsoft 团队和 Exchange Server 之间的集成 

配置 Exchange server 和 Skype for business Online 之间的集成可启用[功能支持](../../plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md#feature_support)中所述的 Skype for Business 和 Exchange 集成功能。

本主题适用于与 Exchange Server 2013 到2019的集成。

## <a name="what-do-you-need-to-know-before-you-begin"></a>开始之前你需要了解哪些信息？

- 完成此任务的估计时间：15 分钟

-  在可以执行此过程或其他过程之前，你需要被分配适当的权限。 若要查看所需的权限, 请参阅[Exchange 和 Shell 基础结构权限](https://go.microsoft.com/fwlink/p/?LinkId=746511)主题。

- 有关可适用于本主题中的过程的键盘快捷方式的信息, 请参阅[Exchange 管理中心中的键盘快捷方式]( https://go.microsoft.com/fwlink/p/?LinkId=746512)。

## <a name="configure-integration-between-exchange-server-and-o365"></a>配置 Exchange Server 和 O365 之间的集成

### <a name="step-1-configure-oauth-authentication-between-exchange-server-and-o365"></a>步骤 1: 在 Exchange Server 和 O365 之间配置 OAuth 身份验证

执行以下文章中的步骤:

[在 Exchange 和 Exchange Online 组织之间配置 OAuth 身份验证](https://docs.microsoft.com/en-us/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help)

### <a name="step-2-create-a-new-mail-user-account-for-the-skype-for-business-online-or-teams-partner-application"></a>步骤 2: 为 Skype for Business Online 或团队合作伙伴应用程序创建新的邮件用户帐户

此步骤在 Exchange 服务器上执行。 它将创建一个邮件用户并为其分配合适的管理角色权限。 随后此用户将用于下一步骤。

为您的 Exchange 组织指定经验证的域。 此域应该是用作本地 Exchange 帐户使用的主 SMTP 域的相同域。 此域在以下过程\<中称为 "\>已验证域"。 此外, \<DomainControllerFQDN\>应该是域控制器的 FQDN。

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

### <a name="step-3-create-and-enable-a-partner-application-for-skype-for-business-online-or-teams"></a>步骤 3: 为 Skype for Business Online 或团队创建和启用合作伙伴应用程序

创建新的合作伙伴应用程序，并且将使用你刚刚创建的帐户。 在您的本地 Exchange 组织中的 Exchange PowerShell 中运行以下命令。

``` Powershell
New-PartnerApplication -Name SfBOnline -ApplicationIdentifier 00000004-0000-0ff1-ce00-000000000000 -Enabled $True -LinkedAccount $user.Identity
```

### <a name="verify-your-success"></a>验证是否成功

通过验证某些功能是否已成功运行, 验证配置是否正确。 

1. 确认 Outlook 日历委派工作 betweeen 两个团队用户使用 Exchange Server 2016 或2019邮箱。

2. 确认移动客户的对话历史记录在 "Outlook 对话历史记录" 文件夹中可见。

或者, 查看您的流量。 OAuth 握手中的流量非常特殊 (并且看起来不像基本身份验证), 特别是在领域内, 你将开始查看如下所示的颁发者流量: 00000004-0000-0ff1-ce00-000000000000 @ (有时有@ 符号), 位于正在传递的令牌中。 您将看不到用户名或密码, 这是 OAuth 的点。 但是, 你将看到 "Office" 颁发者-在本例中, "4" 是 Skype for Business-以及你的订阅领域。

如果你想要确保你成功使用了 OAuth, 请确定你知道所需的内容, 并了解流量应类似的内容。 因此[](https://tools.ietf.org/html/draft-ietf-oauth-v2-23#page-34), 下面是[Microsoft 应用程序中的 OAuth 流量](https://download.microsoft.com/download/8/5/8/858F2155-D48D-4C68-9205-29460FD7698F/[MS-SPS2SAUTH].pdf)的非常标准示例 (虽然它不使用刷新令牌, 但仍很有帮助, 虽然它不使用刷新令牌), 并且将允许你查看 OAuth JWT (JSON) 的 Fiddler 扩展。Web 令牌)。

下面是[一个设置的示例](https://blogs.msdn.microsoft.com/kaevans/2015/03/30/updated-fiddler-oauth-inspector/), 但你可以使用任何你喜欢的网络跟踪工具来执行此过程。

## <a name="related-topics"></a>相关主题

[在 Exchange 和 Exchange Online 组织之间配置 OAuth 身份验证](https://docs.microsoft.com/en-us/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help)

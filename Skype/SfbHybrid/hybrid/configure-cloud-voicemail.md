---
title: 为本地用户配置云语音邮件服务
ms.reviewer: ''
ms.author: dstrome
author: dstrome
manager: serdars
ms.date: 2/11/2019
audience: ITPro
f1.keywords:
- NOCSH
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: ''
description: 有关为驻留在 Skype for business Server 上的用户实施基于云的语音邮件的说明。
ms.openlocfilehash: 4542207beb3ccd090c1215a8832f53b3ab08ed97
ms.sourcegitcommit: 152eb7daacd0a36f42aa441633c12c7037a0969a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/27/2020
ms.locfileid: "42288710"
---
# <a name="configure-cloud-voicemail-service-for-on-premises-users"></a>为本地用户配置云语音邮件服务

## <a name="overview"></a>概述 
本文介绍如何为您的 Skype for business 本地用户配置 Microsoft 云语音邮件服务。  

本文假定您已在受支持的拓扑中部署了 Skype for Business 服务器，并且您已满足设置混合连接的先决条件。

有关实施云语音邮件的优势、规划注意事项和要求的详细信息，请参阅[Plan 云语音邮件服务](plan-cloud-voicemail.md)。




配置云语音邮件涉及以下任务：

1.  确保您符合[Plan 云语音邮件服务](plan-cloud-voicemail.md)中所述的先决条件。

2.  确保已按照[规划混合连接](plan-hybrid-connectivity.md)和[配置混合连接](configure-hybrid-connectivity.md)中所述设置了混合连接。 

3.  [将云语音邮件配置为边缘服务器上的承载提供程序](#configure-cloud-voicemail-as-the-hosting-provider)，如本文中所述。

4.  [配置托管的语音邮件策略](#configure-a-hosted-voicemail-policy)，如本文中所述。

5.  按照本文所述，[分配一个托管的语音邮件策略](#assign-a-hosted-voicemail-policy)。

6.  为[用户启用云语音邮件](#enable-a-user-for-cloud-voicemail)，如本文中所述。


## <a name="configure-cloud-voicemail-as-the-hosting-provider"></a>将云语音邮件配置为承载提供程序 

您可以使用 CsHostingProvider cmdlet 和以下参数将云语音邮件配置为前端服务器上的托管提供程序：

- **Identity**为您要创建的托管提供程序指定一个唯一的字符串值标识符;例如，云语音邮件。 

- **Enabled** 指示您的域与承载服务提供商之间的网络连接是否已启用。 此参数必须设置为 True。

- **EnabledSharedAddressSpace** 指示是否要在共享 SIP 地址空间方案中使用承载服务提供商。 此参数必须设置为 True。

- **HostsOCSUsers**指示是否使用托管提供程序来承载 Skype For business Server 帐户。 此参数必须设置为 False。

- **ProxyFQDN**指定承载提供程序所使用的代理服务器的完全限定域名（FQDN）;例如，proxyserver.contoso.com。 有关此信息，请与承载服务提供商联系。 不能修改此值。 如果托管提供程序更改其代理服务器，则需要删除并重新创建该提供程序的条目。

- **IsLocal**指示托管提供程序使用的代理服务器是否包含在您的 Skype For business server 拓扑中。 此参数必须设置为 False。

例如，在 Skype for Business 命令行管理程序中，以下 cmdlet 将云语音邮件配置为承载提供程序：


```PowerShell
New-CsHostingProvider -Identity "Exchange Online" -Enabled $True -EnabledSharedAddressSpace $True -HostsOCSUsers $False -ProxyFqdn "exap.um.outlook.com" -IsLocal $False -VerificationLevel UseSourceVerification
```

## <a name="configure-a-hosted-voicemail-policy"></a>配置托管的语音邮件策略

为了确保将组织的语音邮件路由到云语音邮件服务，您必须为您的组织配置托管的语音邮件策略。 在许多情况下，只需要一个托管的语音邮件策略，您可以修改全局策略以满足您的所有需求。 如果您的组织需要多个托管的语音邮件策略，则可以使用 cshostedvoicemailpolicy cmdlet 添加策略。

若要修改全局策略，请在更新组织和 TenantID 之后在 Skype for Business Server 命令行管理程序中运行以下命令：

```PowerShell
Set-CsHostedVoicemailPolicy -Identity Global -Description "Global Cloud Voicemail Policy" -Destination exap.um.outlook.com -Organization YourDefaultDomain.onmicrosoft.com
```

- **Destination**指定托管云语音邮件服务的完全限定域名（FQDN）。 此值应设置为**exap.um.outlook.com**。

- "**组织**" 是分配给租户的默认域。 您可以通过让租户管理员登录到 office.com，单击 "管理中心" 应用程序，导航到左侧的 "**安装**"，然后单击 "**域**" 来检索此信息。 例如： mytenant.onmicrosoft.com。

    组织名称也是 Office 365 中的默认域名。

若要确保已成功创建托管的语音邮件策略，请运行以下命令：

```PowerShell
Get-CsHostedVoicemailPolicy
```

## <a name="assign-a-hosted-voicemail-policy"></a>分配托管语音邮件策略

默认情况下，将全局托管的语音邮件策略分配给所有用户。 如果使用其他策略，则在为用户启用托管语音邮件之前，必须首先使用[CSHostedVoicemailPolicy](https://docs.microsoft.com/powershell/module/skype/grant-cshostedvoicemailpolicy?view=skype-ps) cmdlet 向用户授予所需的托管语音邮件策略。

例如，以下命令可向用户分配非全局托管的语音邮件策略：


```PowerShell
Get-CsUser -Identity "User1" | Grant-CsHostedVoicemailPolicy -Identity "Tag:CloudVoiceMailUsers" 
```

## <a name="enable-a-user-for-cloud-voicemail"></a>为用户启用云语音邮件

若要使用户的语音邮件呼叫能够路由到云语音邮件，请使用[get-csuser](https://docs.microsoft.com/powershell/module/skype/set-csuser?view=skype-ps) Cmdlet 和 HostedVoiceMail 参数。 

例如，以下命令将为云语音邮件启用用户帐户： 

```powershell
Set-CsUser -Identity "User1" -HostedVoiceMail $True
```

Cmdlet 验证云语音邮件策略--在全局、站点或用户级别--适用于此用户。 如果没有适用的策略，该 cmdlet 将失败。  

下一个示例为云语音邮件禁用用户帐户：

```powershell
Set-CsUser -Identity "User1" -HostedVoiceMail $False
```

此 cmdlet 在全局、站点或用户级别验证没有托管的语音邮件策略--适用于此用户。 如果有适用的策略，该 cmdlet 将失败。

> [!NOTE]
>  用户必须是已启用企业语音的用户才能使用 Microsoft 云语音邮件服务。

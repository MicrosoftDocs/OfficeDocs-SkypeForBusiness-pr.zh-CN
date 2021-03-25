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
description: 为托管在 Skype for Business Server 上的用户实施基于云的语音邮件的说明。
ms.openlocfilehash: a9c308189a5dc70c85382f638f30f52c0ac69bdb
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51118981"
---
# <a name="configure-cloud-voicemail-service-for-on-premises-users"></a>为本地用户配置云语音邮件服务

## <a name="overview"></a>概述 
本文介绍如何为 Skype for Business 本地用户配置 Microsoft 云语音邮件服务。  

本文假定你已在支持的拓扑中部署了 Skype for Business Server，并且你已满足设置混合连接的先决条件。

有关实施云语音邮件的好处、规划注意事项和要求详细信息，请参阅规划 [云语音邮件服务](plan-cloud-voicemail.md)。




配置云语音邮件涉及以下任务：

1.  确保你已满足 Plan Cloud Voicemail [service](plan-cloud-voicemail.md)中所述的先决条件。

2.  确保已设置混合连接，如规划混合连接和[](plan-hybrid-connectivity.md)[配置混合连接中所述](configure-hybrid-connectivity.md)。 

3.  [将云语音邮件配置为](#configure-cloud-voicemail-as-the-hosting-provider) 前端服务器的托管提供商，如本文所述。

4.  [配置托管语音邮件策略](#configure-a-hosted-voicemail-policy) ，如本文所述。

5.  [分配托管语音邮件策略](#assign-a-hosted-voicemail-policy) ，如本文所述。

6.  [为用户启用云语音邮件](#enable-a-user-for-cloud-voicemail) ，如本文所述。


## <a name="configure-cloud-voicemail-as-the-hosting-provider"></a>将云语音邮件配置为托管提供商 

通过具有以下参数的 New-CsHostingProvider cmdlet，可以将云语音邮件配置为前端服务器的托管提供商：

- **Identity** 指定要创建的宿主提供商的唯一字符串值标识符;例如，云语音邮件。 

- **Enabled** 指示您的域与承载服务提供商之间的网络连接是否已启用。 此参数必须设置为 True。

- **EnabledSharedAddressSpace** 指示是否要在共享 SIP 地址空间方案中使用承载服务提供商。 此参数必须设置为 True。

- **HostsOCSUsers** 指示宿主提供商是否用于托管 Skype for Business Server 帐户。 此参数必须设置为 False。

- **ProxyFQDN** 指定托管 (使用的) 的完全限定域名和 FQDN 名称;例如，proxyserver.contoso.com。 有关此信息，请与承载服务提供商联系。 不能修改此值。 如果宿主提供商更改其代理服务器，则需要删除该条目，然后重新创建该提供商的条目。

- **IsLocal** 指示宿主提供商使用的代理服务器是否包含在 Skype for Business Server 拓扑中。 此参数必须设置为 False。

例如，在 Skype for Business 命令行管理程序中，以下 cmdlet 将云语音邮件配置为托管提供商：


```PowerShell
New-CsHostingProvider -Identity "Exchange Online" -Enabled $True -EnabledSharedAddressSpace $True -HostsOCSUsers $False -ProxyFqdn "exap.um.outlook.com" -IsLocal $False -VerificationLevel UseSourceVerification
```

## <a name="configure-a-hosted-voicemail-policy"></a>配置托管语音邮件策略

若要确保组织的语音邮件路由到云语音邮件服务，必须为组织配置托管语音邮件策略。 在许多情况下，只需要一个托管语音邮件策略，您可以修改全局策略来满足所有需求。 如果组织需要多个托管语音邮件策略，可以使用 new-cshostedvoicemailpolicy cmdlet 添加策略。

若要修改全局策略，在更新组织和 TenantID 后，在 Skype for Business Server 命令行管理程序中运行以下命令：

```PowerShell
Set-CsHostedVoicemailPolicy -Identity Global -Description "Global Cloud Voicemail Policy" -Destination exap.um.outlook.com -Organization YourDefaultDomain.onmicrosoft.com
```

- **Destination** 指定托管云语音邮件 (FQDN) 的完全限定域名。 此值应设置为 **exap.um.outlook.com**。

- **组织** 是分配给租户的默认域。 可以通过让租户管理员登录帐户来检索此信息 office.com 单击管理中心应用，导航到左侧的"设置"，然后单击"域 **"。** 例如：mytenant.onmicrosoft.com。

    组织名称也是 Microsoft 365 或 Office 365 中的默认域名。

若要确保已成功创建托管语音邮件策略，请运行以下命令：

```PowerShell
Get-CsHostedVoicemailPolicy
```

## <a name="assign-a-hosted-voicemail-policy"></a>分配托管语音邮件策略

默认情况下，全局托管语音邮件策略分配给所有用户。 如果您使用其他策略，则必须先使用 [Grant-CSHostedVoicemailPolicy](/powershell/module/skype/grant-cshostedvoicemailpolicy?view=skype-ps) cmdlet 向用户授予所需的托管语音邮件策略，然后才能为用户启用托管语音邮件。

例如，以下命令将非全局托管语音邮件策略分配给用户：


```PowerShell
Get-CsUser -Identity "User1" | Grant-CsHostedVoicemailPolicy -PolicyName "Tag:CloudVoiceMailUsers" 
```

## <a name="enable-a-user-for-cloud-voicemail"></a>为用户启用云语音邮件

若要使用户的语音邮件呼叫可以路由到云语音邮件，请使用 [Set-CsUser](/powershell/module/skype/set-csuser?view=skype-ps) cmdlet 和 HostedVoiceMail 参数。 

例如，以下命令为用户帐户启用云语音邮件： 

```powershell
Set-CsUser -Identity "User1" -HostedVoiceMail $True
```

此 cmdlet 验证云语音邮件策略（全局、站点或用户级别）是否适用于此用户。 如果没有适用的策略，该 cmdlet 将失败。  

下一个示例禁用云语音邮件的用户帐户：

```powershell
Set-CsUser -Identity "User1" -HostedVoiceMail $False
```

此 cmdlet 验证在全局、站点或用户级别托管语音邮件策略是否适用于此用户。 如果有适用的策略，该 cmdlet 将失败。

> [!NOTE]
>  用户必须启用企业语音，以便使用 Microsoft 云语音邮件服务。
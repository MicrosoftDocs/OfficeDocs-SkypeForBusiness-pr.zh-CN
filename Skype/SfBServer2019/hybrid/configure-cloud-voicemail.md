---
title: 配置语音邮件云服务
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 5/9/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: ''
description: 业务服务器驻留在 Skype 中实施的基于云的语音邮件的用户的说明。
ms.openlocfilehash: 9cc990cbaecfea74b269809d9e31588d61eee93c
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/24/2018
ms.locfileid: "25027814"
---
# <a name="configure-cloud-voicemail-service"></a>配置语音邮件云服务


[!INCLUDE [disclaimer](../disclaimer.md)]

## <a name="overview"></a>概述 
本文介绍如何配置您的业务内部部署用户的 Skype 的 Microsoft 云语音邮件服务。  

本文假定您已有 Skype 业务服务器部署中支持的拓扑，并且您已满足的先决条件设置混合连接性。

有关好处的详细信息，规划注意事项以及要求实现云语音邮件，请参阅[规划语音邮件云服务](plan-cloud-voicemail.md)。




配置语音邮件云涉及以下任务：

1.  确保您已满足先决条件[规划云语音邮件服务](plan-cloud-voicemail.md)中所述。

2.  确保您已设置混合连接性[计划混合连接](plan-hybrid-connectivity.md)和[配置混合连接](configure-hybrid-connectivity.md)中所述。 

3.  [为边缘服务器上的宿主提供商配置云语音邮件](#configure-cloud-voicemail-as-the-hosting-provider-on-the-edge-server)这篇文章中所述。

4.  [配置托管语音邮件策略](#configure-a-hosted-voicemail-policy)这篇文章中所述。

5.  本文中所述，[分配托管语音邮件策略](#assign-a-hosted-voicemail-policy)。

6.  本文中所述，[云语音邮件为用户启用](#enable-a-user-for-cloud-voicemail)。


## <a name="configure-cloud-voicemail-as-the-hosting-provider-on-the-edge-server"></a>将云语音邮件配置为边缘服务器上的宿主提供商 

通过使用带下列参数的 New-cshostingprovider cmdlet 可将云语音邮件配置为边缘服务器上的宿主提供商中：

- **Identity**为正在创建; 的宿主提供商指定唯一的字符串值标识符例如，云语音邮件。 

- **Enabled ** 指示您的域与承载服务提供商之间的网络连接是否已启用。 此参数必须设置为 True。

- **EnabledSharedAddressSpace**指示是否将共享 SIP 地址空间方案中使用的宿主提供商。 此参数必须设置为 True。

- **HostsOCSUsers**指示承载服务提供商是否用于承载 Skype Business Server 帐户。 此参数必须设置为 False。

- **ProxyFQDN**指定宿主提供商; 使用的代理服务器的完全限定的域名 (FQDN)例如，proxyserver.contoso.com。 有关此信息，请与您宿主提供商联系。 不能修改此值。 如果宿主提供商更改其代理服务器，您将需要删除，然后重新创建该提供程序条目。

- **IsLocal**指示承载服务提供商使用的代理服务器是否包含您 Skype 企业服务器拓扑中。 此参数必须设置为 False。

例如，业务命令行管理程序的 Skype 中, 以下 cmdlet 为宿主提供商配置云语音邮件：


```
New-CsHostingProvider -Identity "Exchange Online" -Enabled $True -EnabledSharedAddressSpace $True -HostsOCSUsers $False -ProxyFqdn "exap.um.outlook.com" -IsLocal $False -VerificationLevel UseSourceVerification
```

## <a name="configure-a-hosted-voicemail-policy"></a>配置托管语音邮件策略

若要确保您的组织的语音邮件被路由到云语音邮件服务，您必须为您的组织配置托管语音邮件策略。 在许多情况下，只有一个托管语音邮件策略是必需的并可以修改全局策略以满足您的需求。 如果您的组织需要多个托管语音邮件策略，您可以通过使用新 cshostedvoicemailpolicy cmdlet 添加策略。

要修改全局策略，请运行以下命令在 Skype 业务服务器命令行管理程序更新您的组织和 TenantID 之后：

```
Set-CsHostedVoicemailPolicy -Identity Global -Description "Global Cloud Voicemail Policy" -Destination exap.um.outlook.com -Organization YourDefaultDomain.onmicrosoft.com -TenantID “11111111-1111-1111-1111-111111111111”
```

- **目标**指定承载的语音邮件云服务的完全限定的域名 (FQDN)。 此值应设置为**exap.um.outlook.com**。

- **组织**是分配给您的租户的默认域。 您可以通过租户管理员登录到 office.com 管理中心应用程序的左侧，导航到**安装程序**和，单击**域**检索此信息。 例如： mytenant.onmicrosoft.com。

    组织名称也是在 Office 365 中的默认域名。

- **TenantID**用于标识您在 Office 365 中的租户。 有关详细信息，请参阅[查找您的 Office 365 租户 ID](https://support.office.com/en-us/article/find-your-office-365-tenant-id-6891b561-a52d-4ade-9f39-b492285e2c9b)。

若要确保已成功创建托管语音邮件策略，请运行以下命令：

```
Get-CsHostedVoicemailPolicy
```

## <a name="assign-a-hosted-voicemail-policy"></a>分配托管语音邮件策略

默认情况下，全局承载语音邮件策略分配给所有用户。 如果您使用不同的策略，在启用托管语音邮件的用户之前，您必须首先授予用户所需的托管语音邮件策略使用[授予 CSHostedVoicemailPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/grant-cshostedvoicemailpolicy?view=skype-ps) cmdlet。

例如，以下命令将非全局托管语音邮件策略分配给用户：


```
Get-CsUser -Identity "User1" | Grant-CsHostedVoicemailPolicy -Identity "Tag:CloudVoiceMailUsers" 
```

## <a name="enable-a-user-for-cloud-voicemail"></a>为用户启用云语音邮件

若要启用用户的语音邮件的呼叫路由到云语音邮件，您可以与 HostedVoiceMail 参数中使用[Set-csuser](https://docs.microsoft.com/en-us/powershell/module/skype/set-csuser?view=skype-ps) cmdlet。 

例如，以下命令可使云语音邮件的用户帐户： 

```Set-CsUser -Identity "User1" -HostedVoiceMail $True```

此 cmdlet 会验证云语音邮件策略-全局、 站点或用户级别--适用于此用户。 如果没有策略应用，此 cmdlet 将失败。  

下一个示例禁用云语音邮件的用户帐户：

```Set-CsUser -Identity "User1" -HostedVoiceMail $False```

Cmdlet 验证的任何托管语音邮件策略-全局、 站点或用户级别--适用于此用户。 如果策略不适用于，cmdlet 将失败。

> [!NOTE]
>  用户必须是企业语音启用用于 Microsoft 云语音邮件服务。
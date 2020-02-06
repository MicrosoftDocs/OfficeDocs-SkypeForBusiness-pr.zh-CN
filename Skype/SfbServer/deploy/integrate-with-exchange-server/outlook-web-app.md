---
title: 配置本地 Skype for business 服务器和 Outlook Web App 之间的集成
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/7/2016
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 95a20117-2064-43c4-94fe-cac892cadb6f
description: 摘要：集成 Skype for Business 服务器和 Outlook Web App。
ms.openlocfilehash: 2496cc7c2f357c4e1afa73dea18f304c6a7f9607
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41797033"
---
# <a name="configure-integration-between-on-premises-skype-for-business-server-and-outlook-web-app"></a>配置本地 Skype for business 服务器和 Outlook Web App 之间的集成

**摘要：** 集成 Skype for Business 服务器和 Outlook Web App。

使用本地 Skype for Business 服务器部署的客户可以在混合部署模式下，在 Microsoft Exchange Online 中配置与 Microsoft Outlook Web App 的互操作性。 互操作性功能包括单一登录和即时消息 (IM) 以及与 Outlook Web App 接口的状态集成。 若要启用此集成，必须通过完成以下任务在本地 Skype for Business 服务器部署中配置 Edge 服务器：

- 配置共享的 SIP 地址空间

- 在边缘服务器上配置托管提供商

- 验证更新的中央管理存储的复制

## <a name="configure-a-shared-sip-address-space"></a>配置共享的 SIP 地址空间

若要将本地 Skype for Business 服务器与 Exchange Online 集成，必须配置共享 SIP 地址空间。 Skype for Business 服务器和 Exchange Online 服务均支持相同的 SIP 域地址空间。

使用 Skype for Business Server Management Shell，使用以下示例中显示的参数运行**CSAccessEdgeConfiguration** cmdlet 来配置联盟的边缘服务器：

```powershell
Set-CsAccessEdgeConfiguration -AllowFederatedUsers $True
```

- **AllowFederatedUsers** 参数指定是否允许内部用户与联盟域中的用户进行通信。 此属性还确定内部用户是否可以使用 Skype for Business Server 和 Exchange Online 与共享 SIP 地址空间方案中的用户进行通信。

有关使用 Skype for Business Server 命令行管理程序的详细信息，请参阅[skype for Business Server 命令行管理程序](../../manage/management-shell.md)。

## <a name="configure-a-hosting-provider-on-the-edge-server"></a>在边缘服务器上配置宿主提供程序

通过使用以下示例中的参数运行**CsHostingProvider** cmdlet，使用 Skype For Business Server Management Shell 在 Edge 服务器上配置托管提供商：

```powershell
New-CsHostingProvider -Identity "Exchange Online" -Enabled $True -EnabledSharedAddressSpace $True -HostsOCSUsers $False -ProxyFqdn "exap.um.outlook.com" -IsLocal $False -VerificationLevel UseSourceVerification
```

> [!NOTE]
> 如果您在中国使用 21Vianet 运营的 Office 365，请将此示例中 ProxyFqdn 参数的值（“exap.um.outlook.com”）替换为 21Vianet 运营的服务的 FQDN：“exap.um.partner.outlook.cn”。 如果您使用的是 Office 365 GCC 高版，请将此示例（"exap.um.outlook.com"）中的 ProxyFqdn 参数的值替换为 GCC High 的 FQDN： "exap.um.office365.us"。

- **Identity** 将为您创建的宿主提供程序指定一个唯一的字符串值标识符（例如“Exchange Online”）。 包含空格的值必须用双引号括起来。

- **Enabled ** 指示您的域与承载服务提供商之间的网络连接是否已启用。 必须将其设置为 True。

- **EnabledSharedAddressSpace** 指示是否将在共享的 SIP 地址空间方案中使用托管提供程序。 必须将其设置为 True。

- **HostsOCSUsers**指示托管提供商是否用于托管 Office 通信服务器或 Skype For business 服务器。 必须将其设置为 False。

- **ProxyFQDN** 指定宿主提供程序所使用的代理服务器的完全限定域名 (FQDN)。 对于 Exchange Online，FQDN 为 exap.um.outlook.com。

- **IsLocal**指示托管提供商使用的代理服务器是否包含在您的 Skype For business 服务器拓扑中。 必须将其设置为 False。

- **VerificationLevel**指示对托管提供程序发送和接收的消息所允许的验证级别。 指定 **UseSourceVerification**，它依赖于从宿主提供程序发送的邮件中包含的验证级别。 如果未指定此级别，邮件将因无法验证而被拒绝。

## <a name="verify-replication-of-the-updated-central-management-store"></a>确保复制更新后的中央管理存储

通过使用上述部分中的 cmdlet 所做的更改将自动应用到边缘服务器，并且通常需要的时间不超过一分钟才能进行复制。 你可以验证复制状态，然后通过使用以下 cmdlet 确认是否已将更改应用到 Edge 服务器。

若要验证复制更新，请在 Skype for business Server 部署内部的服务器上运行以下 cmdlet：

```powershell
Get-CsManagementStoreReplicationStatus
```
检查 UpToDate 值是否为所有副本显示 TRUE。

若要确认已应用所做的更改，请在边缘服务器上运行以下 cmdlet：

```powershell
Get-CsHostingProvider -LocalStore
```
请仔细检查所显示的信息是否与前面步骤中提交的更改相匹配。

## <a name="see-also"></a>另请参阅

[在托管 Exchange UM 上提供 Skype for business 服务器用户语音邮件](https://technet.microsoft.com/library/306d3fb5-231b-4f0b-b8d8-0d9083b5ed77.aspx)

[Skype for Business 服务器中的托管 Exchange 统一消息集成](https://technet.microsoft.com/library/f4de0165-da3b-499e-98fc-28ddd0db02d5.aspx)

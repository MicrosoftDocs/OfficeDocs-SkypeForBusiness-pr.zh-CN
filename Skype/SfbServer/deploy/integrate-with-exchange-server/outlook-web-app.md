---
title: 配置本地部署和Skype for Business Server之间的Outlook Web App
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/7/2016
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: 95a20117-2064-43c4-94fe-cac892cadb6f
description: 摘要：集成Skype for Business Server和Outlook Web App。
ms.openlocfilehash: 9edbd804347cd8eba8db609c73066b9030c73ba7
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/26/2021
ms.locfileid: "58621754"
---
# <a name="configure-integration-between-on-premises-skype-for-business-server-and-outlook-web-app"></a>配置本地部署和Skype for Business Server之间的Outlook Web App

**摘要：** 集成Skype for Business Server和Outlook Web App。

使用本地部署部署Skype for Business Server可以在混合部署Microsoft Outlook Web App Microsoft Exchange Online配置与本地部署中的客户端的互操作性。 互操作性功能包括单一登录和即时消息 (IM) 以及状态与 Outlook Web App 接口集成。 若要启用此集成，必须通过完成以下任务在内部部署Skype for Business Server配置边缘服务器：

- 配置共享 SIP 地址空间

- 在边缘服务器上配置宿主提供商

- 验证更新的中央管理存储的复制

## <a name="configure-a-shared-sip-address-space"></a>配置共享 SIP 地址空间

若要将内部部署Skype for Business Server与Exchange Online集成，必须配置共享 SIP 地址空间。 同一 SIP 域地址空间受 Skype for Business Server 和 Exchange Online 服务支持。

使用 Skype for Business Server 命令行管理程序，使用以下示例中显示的参数运行 **Set-CSAccessEdgeConfiguration** cmdlet，为联盟配置边缘服务器：

```powershell
Set-CsAccessEdgeConfiguration -AllowFederatedUsers $True
```

- **AllowFederatedUsers** 参数指定是否允许内部用户与联盟域中的用户通信。 此属性还确定内部用户是否可以与共享 SIP 地址空间方案中的用户进行通信，Skype for Business Server Exchange Online。

有关使用命令行管理程序Skype for Business Server，请参阅Skype for Business Server[命令行管理程序。](../../manage/management-shell.md)

## <a name="configure-a-hosting-provider-on-the-edge-server"></a>在边缘服务器上配置宿主提供商

使用 Skype for Business Server命令行管理程序，使用以下示例中的参数运行 **New-CsHostingProvider** cmdlet，在边缘服务器上配置宿主提供商：

```powershell
New-CsHostingProvider -Identity "Exchange Online" -Enabled $True -EnabledSharedAddressSpace $True -HostsOCSUsers $False -ProxyFqdn "exap.um.outlook.com" -IsLocal $False -VerificationLevel UseSourceVerification
```

> [!NOTE]
> 如果使用的是由世纪Microsoft 365或 Office 365 在中国运营的 Microsoft 365 或 Office 365，请将此示例中 ProxyFqdn 参数的值替换为由世纪 ("exap.um.outlook.com") 运营的服务的 FQDN："exap.um.partner.outlook.cn"。 如果使用的是 Microsoft 365 或 Office 365 GCC High，请将此示例中 ProxyFqdn 参数的值 ("exap.um.outlook.com") 替换为 GCC High 的 FQDN："exap.um.office365.us"。

- **Identity** 为要创建的宿主提供商指定唯一的字符串值标识符 (例如，"Exchange Online") 。 包含空格的值必须用双引号括起来。

- **Enabled** 指示您的域与承载服务提供商之间的网络连接是否已启用。 必须设置为 True。

- **EnabledSharedAddressSpace** 指示是否要在共享 SIP 地址空间方案中使用承载服务提供商。 必须设置为 True。

- **HostsOCSUsers** 指示是使用宿主提供商在 Communications Server Office还是Skype for Business Server。 这必须设置为 False。

- **ProxyFQDN** 指定托管服务提供商使用的代理服务器的完全限定的域名 (FQDN)。 例如Exchange Online，则 FQDN exap.um.outlook.com。

- **IsLocal** 指示宿主提供商使用的代理服务器是否包含在您的Skype for Business Server拓扑中。 这必须设置为 False。

- **VerificationLevel** 指示向托管提供程序发送和发送的消息所允许的验证级别。 指定 **UseSourceVerification**，它依赖于从宿主提供程序发送的邮件中包含的验证级别。 如果未指定此级别，邮件将因不可验证而被拒绝。

## <a name="verify-replication-of-the-updated-central-management-store"></a>验证更新的中央管理存储的复制

使用上述各节中的 cmdlet 所做的更改将自动应用于边缘服务器，复制通常不到一分钟。 您可以验证复制状态，然后通过以下 cmdlet 确认更改已应用到边缘服务器。

若要验证复制更新，在部署中内部Skype for Business Server运行以下 cmdlet：

```powershell
Get-CsManagementStoreReplicationStatus
```
检查 UpToDate 值是否显示所有副本的 TRUE。

若要确认已应用更改，在边缘服务器上运行以下 cmdlet：

```powershell
Get-CsHostingProvider -LocalStore
```
仔细检查显示的信息是否与前面步骤中提交的更改匹配。

## <a name="see-also"></a>另请参阅

[在Skype for Business Server UM 上为用户提供Exchange语音邮件](/previous-versions/office/lync-server-2013/lync-server-2013-providing-lync-server-users-voice-mail-on-hosted-exchange-um)

[托管Exchange统一消息集成Skype for Business Server](/previous-versions/office/lync-server-2013/lync-server-2013-hosted-exchange-unified-messaging-integration)
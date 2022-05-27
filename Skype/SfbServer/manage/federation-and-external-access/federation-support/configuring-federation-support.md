---
title: 为 Skype for Business Online 客户配置联合身份验证支持
ms.reviewer: ''
ms:assetid: e5f7f38d-ede5-4af3-88c2-026e8a78df12
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202193(v=OCS.15)
ms:contentKeyID: 48185669
mtps_version: v=OCS.15
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: '如果在组织中部署Skype for Business，则可以与一个或多个 Skype for Business Online 客户的域联合。 '
ms.openlocfilehash: d180de014c0a7479eb5dc7a6fb60e00e5b136f24
ms.sourcegitcommit: 296862e02b548f0212c9c70504e65b467d459cc3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/25/2022
ms.locfileid: "65676224"
---
# <a name="configuring-federation-support-for-a-skype-for-business-online-customer-in-skype-for-business-server"></a>在 Skype for Business Server 中为 Skype for Business Online 客户配置联合身份验证支持

可以通过以下任一方式为组织中的用户提供通信服务：

- 在组织中部署Skype for Business Server (称为 *本地服务*) 并在组织中设置Skype for Business用户帐户。
- 使用托管提供商设置 Microsoft Skype for Business Online 客户帐户，并使用托管提供商 (（称为 *联机服务)*）设置用户帐户。

如果在组织中部署Skype for Business，则可以与一个或多个 Skype for Business Online 客户的域联合。 若要在本地Skype for Business部署用户与 Skype for Business Online 客户的用户之间启用联合，必须配置对域和 Skype for Business Online 客户用户的支持。

[!INCLUDE [sfbo-retirement-skype](../../../../Hub/includes/sfbo-retirement.md)]

> [!NOTE]  
> 本文档仅介绍将组织配置为支持与 Skype for Business Online 客户联合的过程。 本文档未介绍将 Skype for Business Online 客户配置为支持联合身份验证的过程。

## <a name="prerequisites-for-federating-with-a-skype-for-business-online-customer"></a>与 Skype for Business Online 客户联合的先决条件

若要与 Skype for Business Online 客户联合，应已完成组织中Skype for Business Server的初始部署和配置。 其中包括：

- 在组织中部署至少一个Standard Edition服务器或一个Enterprise Edition前端池。
- 为Skype for Business Server启用内部用户帐户。
- 部署至少一个 Edge Server 和其他支持外部用户访问所需的组件。 有关详细信息，请参阅[管理联合身份验证和对Skype for Business Server的外部访问](../managing-federation-and-external-access.md)。
- 在您的组织中启用联盟支持并配置适当的方法来控制联合域进行的访问。 有关详细信息，请参阅 [为组织启用或禁用远程用户访问](../access-edge/enable-or-disable-remote-user-access.md) 和管理 [SIP 联合提供商](../sip-providers/manage-sip-federated-providers-for-your-organization.md)。
- 为您的组织中的用户启用外部用户访问。 有关详细信息，请参阅[将外部用户访问策略分配给已启用Skype for Business用户](../external-access-policies/assign-an-external-user-access-policy.md)。

## <a name="configure-federation-support-for-a-skype-for-business-online-domain"></a>配置对 Skype for Business Online 域的联合身份验证支持

与 Skype for Business Online 客户联合需要完成以下步骤：

- 配置对 Skype for Business Online 2010 客户 (域的支持，例如 contoso.onmicrosoft.com) 。 如与 [Skype for Business Online 客户联合的先决条件](#prerequisites-for-federating-with-a-skype-for-business-online-customer)中所述，你应该已经为组织启用了联合身份验证。 启用联盟要求指定联盟的域用于控制访问的方法。 如果将组织配置为使用发现，则可以选择将域添加到组织的允许列表。 如果未启用域发现，则必须将 Skype for Business Online 客户的域名添加到允许的域列表中。 可以通过使用Skype for Business Server 控制面板或运行 **New-CSAllowedDomain** cmdlet 来添加域名。 有关使用Skype for Business Server 控制面板（包括启用域发现）的详细信息，请参阅[Skype for Business Server中管理组织的 SIP 联合提供商](../sip-providers/manage-sip-federated-providers-for-your-organization.md)。 有关使用 **New-CSAllowedDomain** cmdlet 添加域的详细信息，请参阅 [New-CsAllowedDomain](/powershell/module/skype/New-CsAllowedDomain)。

  > [!NOTE]  
  > Skype for Business联机客户可以具有多个域。 若要与多个域联合，必须为要支持联合的每个单个域配置支持，并且 Skype for Business Online 客户的管理员必须为要联合的每个域启用联合身份验证。

- 配置对要与之联合的 Skype for Business Online 客户域的托管提供程序的支持。 请使用本节中的步骤配置托管服务提供商支持。

  > [!NOTE]  
  > 此步骤仅适用于与 Skype for Business Online 客户的域联合，而不是与部署在联合合作伙伴位置的本地的任何域联合。

### <a name="to-configure-support-for-a-hosting-provider"></a>要从前端服务器

1. 从前端服务器"开始"菜单Skype for Business Server管理外壳：单击 **"开始"菜单**，单击 **“所有程序**”，单击 **Skype for Business Server**，然后单击 **Skype for Business Server Management Shell**。

2. 运行 **New-CsHostingProvider** cmdlet 以创建和配置托管服务提供商。 例如，运行：

    ```powershell
    New-CsHostingProvider -Identity LyncOnline -ProxyFqdn "sipfed.online.lync.com" -VerificationLevel UseSourceVerification -Enabled $True -EnabledSharedAddressSpace $False -HostsOCSUsers $False -IsLocal $False
    ```

    前一个示例将设置以下参数：

    - **Identity** 为您创建的托管服务提供商指定唯一的字符串值标识符。请注意，如果已使用该 Identity 对现有的提供商进行配置，该命令将无法运行。

    - **ProxyFQDN** 指定托管服务提供商使用的代理服务器的完全限定的域名 (FQDN)。该值不能修改。如果托管服务提供商更改了其代理服务器，则需要为该提供商删除并重新创建项目。

    - **VerificationLevel** 指定如何（或是否）验证邮件是从托管服务提供商发送，以确保这些邮件是从该提供商发送。

    - **Enabled** 指示是否已启用您的域和托管服务提供商之间的网络连接。只有将该值设置为 **True**，才能在这两个组织之间交换邮件。

    - **EnabledSharedAddressSpace** 指示是否在共享 SIP 地址空间（拆分域）方案中使用此承载服务提供商。

    - **HostsOCSUsers** 指示托管提供程序是否用于托管Skype for Business Server帐户。 如果设置为 **False**，则提供商承载其他帐户类型，例如 Microsoft Exchange 帐户。

    - **IsLocal** 指示托管提供程序使用的代理服务器是否包含在Skype for Business Server拓扑中。

    有关使用此 cmdlet 的详细信息，请参阅 [New-CsHostingProvider](/powershell/module/skype/New-CsHostingProvider)。

## <a name="configure-user-access-for-federation-with-a-skype-for-business-online-customer"></a>配置用户访问权限以与 Skype for Business Online 客户联合

您必须对组织中所有用户的用户帐户进行配置，以便其能够与联盟伙伴进行通信。 此配置适用于所有联合合作伙伴，包括任何支持联合身份验证的 Microsoft Skype for Business Online 客户域。 有关为用户帐户配置联合身份验证支持的详细信息，请参阅[配置策略以控制联合用户访问权限](../external-access-policies/configure-policies-to-control-federated-user-access.md)，并将[外部用户访问策略分配给已启用Skype for Business用户](../external-access-policies/assign-an-external-user-access-policy.md)。

## <a name="verify-communications-with-a-skype-for-business-online-customer-in-skype-for-business-server"></a>在 Skype for Business Server 中验证与 Skype for Business Online 客户的通信

若要使组织中的Skype for Business用户能够与 Skype for Business Online 客户的用户通信，必须已完成以下步骤：

- 满足所有先决条件。 这包括部署内部和边缘服务器，为组织实现联盟支持以及设置用户帐户。 有关详细信息，请参阅[与 Skype for Business Online 客户联合的先决条件](#prerequisites-for-federating-with-a-skype-for-business-online-customer)。
- 配置内部部署中的域访问支持。 这包括创建主机提供程序条目，并将部署配置为允许从 Skype for Business Online 客户的域进行访问。 有关详细信息，请参阅[配置 Skype for Business Online 域的联合身份验证支持](#configure-federation-support-for-a-skype-for-business-online-domain)。
- 将用户帐户配置为支持联盟。 有关详细信息，请参阅[为与 Skype for Business Online 客户联合配置用户访问权限](#configure-user-access-for-federation-with-a-skype-for-business-online-customer)。

完成所有这些步骤后，Skype for Business Online 客户的管理员完成其联机服务的所有配置，以支持与组织联合，通过测试组织中的内部用户与 Skype for Business Online 客户用户之间的通信来验证通信。 如果通信不成功，请使用边缘服务器中的日志记录工具捕获日志和跟踪文件，以排查问题。

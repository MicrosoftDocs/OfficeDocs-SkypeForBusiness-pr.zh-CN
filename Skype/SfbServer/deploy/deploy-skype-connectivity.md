---
title: 在 Skype for Business Server 中部署 Skype 连接
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: fb51860b-6f46-4b71-b8c8-682d0982d36d
description: 摘要：了解如何将 Skype for Business Server 与 Skype 消费者连接。 也称为 Skype 连接。
ms.openlocfilehash: 2cf124c340218a352f55fa1c09302a0d0f1d972a
ms.sourcegitcommit: ea54990240fcdde1fb061489468aadd02fb4afc7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/22/2020
ms.locfileid: "43780061"
---
# <a name="deploy-skype-connectivity-in-skype-for-business-server"></a>在 Skype for Business Server 中部署 Skype 连接

**摘要：** 了解如何将 Skype for Business Server 与 Skype 消费者连接。 也称为 Skype 连接。
  
本文逐步介绍了如何部署 Skype 连接。
  
## <a name="skype-connectivity-overview-for-it-professionals"></a>IT 专业人员的 Skype 连接概述

Skype 连接为 Skype for business 用户提供搜索和添加 Skype 用户的功能。 Skype 连接是 Skype for Business 的一项功能，允许你启用与 Skype 用户的联盟和目录搜索。 启用 Skype 连接后，你的 Skype for Business 用户将能够搜索和添加 Skype 用户。
  
## <a name="skype-directory-search"></a>Skype 目录搜索

Skype 目录搜索功能为 Skype for Business 用户提供了搜索 Skype 联系人的功能。 使用搜索功能，用户可以使用以下内容进行搜索：
  
- **按显示名称进行搜索，例如 "John Doe"** -这可能会返回许多结果，因此您可能无法找到要查找的内容。
    
- **按显示名称加位置搜索，示例 "John Doe Of 巴塞罗纳"** -这将大大缩小搜索结果的范围。
    
- **通过电子邮件进行搜索，示例 "johndoe@outlook.com"** -这在大多数情况下应返回一个结果;与指定的电子邮件完全匹配的一个。 但是，如果同一个电子邮件与多个帐户相关联，则可能返回多个结果。
    
- **按电话号码进行搜索，例如 "123-123-1234"** -这在大多数情况下应返回一个结果;与指定电话完全匹配的一个。 电话号码必须包含国家/地区代码（例如，zzzz）。 如果同一个电话号码与多个帐户相关联，则可能返回多个结果。
    
- **按 Skype 名称搜索，示例 "JohnDoe1456"** -如果找到了完全匹配项，它将作为第一个结果返回。 可能会返回其他可能的 "名称" 匹配项。
    
    > [!NOTE]
    > Skype 目录搜索必须能够与端口443上的以下 IP 地址进行通信：104.40.75.246、23.101.135.34 和40.113.86.19。 
  
## <a name="supported-deployment-matrix-for-skype-directory-search"></a>Skype 目录搜索支持的部署矩阵

下表概述了对 Skype 目录搜索的支持。
  

||**Skype for Business Server 前端**|**Lync Server 2013 （或更早版本）前端**|**Comments**|
|:-----|:-----|:-----|:-----|
|Skype for Business Server Edge  <br/> |支持  <br/> |不支持  <br/> |Skype for business Server 和 Edge 是 Skype 目录搜索的先决条件  <br/> |
|Skype for Business Server Edge + Lync Server 2013 Edge 并行部署  <br/> |支持  <br/> |不支持  <br/> |Skype 目录搜索流量通过 Skype for Business Server 边缘服务器流动。 联盟流量通过由管理员配置的边缘进行。 例如，管理员可以选择继续通过不支持 Skype 目录搜索的 Lync Server 2013 边缘服务器发送联盟流量。  <br/> |
|Lync Server 2013 （或更早版本）边缘  <br/> |不支持  <br/> |不支持  <br/> ||
   
> [!NOTE]
> 在 Skype for Business Server 前端运行的 Addressbook 服务通过边缘服务器中存在的 Skype 搜索端口4443查找边缘。 
  
> [!NOTE]
> 如果客户在其本地部署中有多个站点，并且他们仅部署了一个 Skype for Business Server Edge 服务器/池，则所有站点的搜索流量将通过单个可用的边缘服务器。 管理员需要确保所有站点的池都能访问已部署的 Skype for Business Server Edge 服务器/池。 
  
> [!NOTE]
> 如果请求速率超过15个请求/秒，则 Skype graph 服务将限制来自任何内部部署或 Microsoft 365 或 Office 365 客户的搜索请求。 
  
> [!NOTE]
> 对于大型企业内部部署客户，需要使用 Skype search service 对域进行白名单，以允许更高的请求速率。 
  
> [!NOTE]
> 如果队列中的挂起请求过多，Skype for Business Server 将限制传入的请求。 
  
## <a name="deploying-skype-connectivity-for-skype-for-business-online-in-office-365"></a>在 Office 365 中为 Skype for business Online 部署 Skype 连接

Skype 连接也是 Skype for business Online 的一项功能，它是 Office 365 的一部分。 您可以从 Microsoft 365 管理中心内的 Skype for Business 管理中心启用 Skype 连接功能。
  
对于 Office 365 中型企业版、Office 365 企业版、Office 365 教育版和 Office 365 for 政府版：登录 Microsoft 365 管理中心并导航到 Skype for Business 管理中心。 转到 "外部通信"。 在 "公共 IM 服务提供商" 下，单击 "启用"。 如果要控制各个用户对 Skype 连接的访问权限，您可以通过编辑单个用户的外部通信设置来执行此操作。
  
对于 Office 365 小型企业高级版：登录到 Office 365，然后转到 " \>管理服务\>设置即时消息、会议和会议"。 打开外部通信。 外部通信交换机可同时启用 Skype 连接和与使用 Skype for Business 的其他组织的通信。
  
有关 Skype for business Online 管理的详细信息，请参阅：
  
- [允许用户连接外部 Skype for Business 用户](../../SfbOnline/set-up-skype-for-business-online/allow-users-to-contact-external-skype-for-business-users.md)

- [无法对 Skype for business 或 Skype 外部联系人进行 IM 通信时应尝试的操作](https://support.office.com/article/What-to-try-if-you-cant-IM-Skype-for-Business-Lync-or-Skype-external-contacts-87f6d5d7-3b8c-4196-9c8c-1dabb75f54b8?ui=en-US&amp;rs=en-US&amp;ad=US)
    
- [在 Skype for Business 中添加联系人](https://support.office.com/article/Add-a-contact-in-Skype-for-Business-89338023-2adf-4f5c-90b6-f8b6f72fadd1)
  
- [管理员：为单个用户配置 Skype for Business 设置](../../SfbOnline/set-up-skype-for-business-online/configure-skype-for-business-settings-for-individual-users.md)
    
## <a name="deploying-skype-connectivity-for-skype-for-business-server"></a>为 Skype for business Server 部署 Skype 连接

Skype for Business Server 使用联合身份验证访问体系结构支持与 Skype 的连接。 此连接使 Skype for business Server 用户能够添加 Skype。 Skype 客户端也可以将 Skype for Business 用户添加到其联系人列表中。 根据在 Skype for Business Server 中进行管理设置的策略，用户将能够使用即时消息进行通信、查看彼此的状态以及启动音频和视频呼叫。 Skype 连接也是 Skype for business Online 的一项功能，可在 Microsoft 365 管理中心内的 Skype for business 管理中心中为 Skype for business Online 客户启用此功能。
  
> [!NOTE]
> 如果 Skype for Business Server 已配置为使用公共即时消息连接（PIC）与 Windows Messenger 进行连接，则您的部署已配置了 Skype 连接。 您可能需要考虑的唯一更改是将现有的 Messenger PIC 条目重命名为 Skype。 
  
### <a name="the-skype-for-business-server-public-im-connectivity-provisioning-site-is-no-longer-available"></a>Skype for Business Server 公共 IM 连接设置网站不再可用

以前用于在 Skype for Business 本地部署和 Skype 之间手动设置联合的网站不再是必需的，将在8/15/2019 上关闭。 与 Skype 联合身份验证现在利用了联合合作伙伴发现，这与与 Skype for business Online 联盟所需的机制相同。

在任何本地 Skype for Business 部署和 Skype 用户之间通过现有公共 IM 基础结构进行通信现在需要本地边缘服务器配置与 Skype for Business Online 兼容。

> [!NOTE]
> 大多数客户都不需要执行任何操作，包括与 Skype for Business Online 联盟的所有部署。
  
需要本地部署才能为其承载的每个域发布联合 DNS SRV 记录。 指南在[DNS 规划](../plan-your-deployment/edge-server-deployments/edge-environmental-requirements.md#dns-planning)中可用。 每个域必须由 DNS SRV 查询解析为满足域的顶级后缀匹配的边缘服务器 FQDN。 例如，请考虑域 "contoso.com"：

|**有效 Fqdn**|**Comment**|
|:-----|:-----|
|sip.contoso.com   ||
|sipfed.contoso.com   |在每种情况下，确切的 FQDN 都必须存在于安装在边缘服务器上的外部证书的 SN 或 SAN 中。   |
|access.contoso.com   ||
|**Fqdn 无效**|**原因**|
|sip.contoso-edge.com   |后缀不匹配。  |
|sip.it.contoso.com   |不是最高级别的后缀匹配项。   |

有关外部证书的进一步指导可在[证书规划](../plan-your-deployment/edge-server-deployments/edge-environmental-requirements.md#certificate-planning)中找到。

#### <a name="faqs"></a>常见问题解答

**为什么要关闭预配网站？**
在2006中部署的公共 IM （PIC）设置机制（pic.lync.com）将不再可维修，并将在8/15/2019 上关闭。 相反，公用 IM 联合将假定 Skype for Business Online 使用的联盟模型（称为 "合作伙伴发现"），从而使本地部署可通过其联合 DNS SRV 记录公开发现。

**此更改是否意味着即将弃用公共 IM 联合身份验证？**
不正确。 公共 IM 联盟将继续支持许多年，可能一直等到 Skype for Business 本地产品达到寿命结束的情况。

**我们的公司有与 Skype for Business Online 的混合关系（共享地址空间），我们受到影响？**
否，由于你已与 Skype for Business Online 联盟，因此此更改不会影响你。
 
**此更改是否意味着我们的公司必须启用与 Skype for Business Online 的联盟？**
不正确。 如果你的边缘服务器代理设置未启用与 Skype for Business Online 托管提供商（sipfed.online.lync.com）的联盟，则此更改不会影响。 但是，应用于与 Skype for Business Online 联盟的相同 DNS 和证书要求现在也适用于与 Skype 用户进行联盟。
 
**我们的公司规模较大，不能更改其边缘配置，因为遵守管理法规/合规性或等原因 .。。我们可以做什么？**
无法更改其边缘服务器配置的任何内部部署组织应尽早进入产品支持。

### <a name="enabling-federation-and-public-im-connectivity-pic"></a>启用联盟和公共 IM 连接（PIC）

现在将重点放在 Skype for Business Server 环境和配置 Skype 连接所需的管理任务上。 在本节中，我们假定管理员已部署 Skype for Business Server 并配置了外部访问（也称为边缘服务器）。 
  
启用联盟和 PIC 需要执行三个主要步骤。 分别是：
  
1. 配置联盟和 PIC
    
2. 至少配置一个用于支持联合用户访问的策略
    
3. 配置 Skype PIC 提供程序设置
    
#### <a name="1-configure-federation-and-pic"></a>1. 配置联盟和 PIC

若要使 Skype 用户能够与组织中的 Skype for Business 用户通信，需要联合身份验证。 公共即时消息连接（PIC）是一种联盟类，必须将其配置为使您的 Skype for Business 用户能够与 Skype 用户进行通信。 联盟和 PIC 是使用 Skype for Business Server 控制面板配置的。
  
> [!NOTE]
> Lync Server 2010 （Live Communication Server、Office 通信服务器）之前的产品版本不再支持 PIC 联盟。 PIC 联盟的受支持平台包括 Skype for Business Server、Lync Server 2013 和 Lync Server 2010。 
  
若要使 Skype 用户能够与组织中的 Skype for Business 用户通信，需要联合身份验证。 公共即时消息连接（PIC）是联合的一类，必须将其配置为使 Skype for Business Server 用户能够与 Skype 用户进行通信。 联盟和 PIC 是使用 Skype for Business Server 控制面板的 "边缘配置" 对话框配置的，如图所示。
  
![定义新的边缘池](../media/32d7f255-c6ad-426d-96c2-2ef4d81f3b51.png)
  
> [!NOTE]
> 在公共提供程序设置（请参阅后面的说明）中，EnableSkypeIdRouting 和 EnableSkypeDirectorySearch 属性需要设置为 true，才能使搜索正常工作。 
  
这将完成必须在服务器上执行的管理任务。 您现在已设置 Skype 连接。
  
#### <a name="2-configure-at-least-one-policy-to-support-federated-user-access"></a>2. 至少配置一个策略以支持联合用户访问

通过使用 Skype for Business Server 控制面板，管理员必须配置一个或多个外部用户访问策略，以控制 Skype 用户是否可以与内部 Skype for Business Server 用户进行协作。
  
#### <a name="3-configure-the-skype-pic-provider-setting"></a>3. 配置 Skype PIC 提供程序设置

通过使用 Skype for Business Server 命令行管理程序，管理员必须配置 Skype for Business 客户端策略，以将 Skype 显示为其他 PIC 提供程序。 
  
> [!NOTE]
> 公共即时消息连接（PIC）服务提供程序的用户无法在您的组织中加入 IM 或会议，除非您还配置了至少一个策略（此过程中前面的步骤2），以支持公用 IM 连接。 
  
对于新的安装，您可以通过使用 Skype for business Server 控制面板启用 Skype 公共提供商来配置 Skype 连接，如图所示。
  
![SIP 联盟提供商](../media/8fc7b566-72b5-4c43-961c-9249fdf7e575.png)
  
> [!NOTE]
> 若要在升级到 Skype for business Server 时配置 Skype 连接，必须删除并重新添加现有 Skype 公共提供商。 
  
也可以仅使用 PowerShell 完成配置 Skype 连接。 使用 PowerShell 配置 Skype 连接：
  
1. 从 Skype for business Server 前端服务器，打开 Skype for Business Server 命令行管理程序。
    
2. 运行以下两个命令：
    
   ```powershell
    Remove-CsPublicProvider -Identity <identity-name>
   ```

    > [!NOTE]
    > 如果您的环境中尚未安装 PIC 提供程序，并且要创建新的 PIC 提供程序，则无需运行 CsPublicProvider cmdlet。 
  
   ```powershell
   New-CsPublicProvider -Identity Skype -ProxyFqdn federation.messenger.msn.com -IconUrl https://images.edge.messenger.live.com/Messenger_16x16.png -NameDecorationRoutingDomain msn.com -NameDecorationExcludedDomainList "msn.com,outlook.com,live.com,hotmail.com" -Enabled $true -EnableSkypeIdRouting $true -EnableSkypeDirectorySearch $true
   ```

    不太明显的参数有什么作用？
    
   - ProxyFqdn： Skype 联盟边缘的位置（由 Microsoft 拥有/维护）
    
   - IconURL： Lync &amp; Skype for business 客户端用来直观标识 Skype 联系人的图标
    
   - NameDecorationRoutingDomain 和 NameDecorationExcludedDomainList：设置这些设置使用户可以输入 Skype 用户的 Msa，而无需了解有关 "修饰" 非 Microsoft 域的 "msn.com"。 这样就无需为 ExcludedDomainList 中不的所有域键入 "user （contoso .com） @msn"。 如果域不在排除列表中，则 SfB 客户端将自动设置 MSA 的格式。 我们已将最常见的 Microsoft 帐户域添加到了排除列表中。
    
     > [!NOTE]
     > 如果进行了更改，则必须删除公共提供程序并添加新的提供程序。 不允许就地更改。 
  
     > [!NOTE]
     > 在 Lync Server 2013 CU5 &amp; lync desktop Client in OFFICE 2013 SP1 中，NameDecorationRoutingDomain 和 NameDecorationExcludedDomainList 改进了 Lync 用户在其中添加需要 "装饰" 非 Microsoft 域的 skype 联系人以标识并将其路由到 Skype （格式为： user （contoso） @msn .com）的情况。 如果在 NameDecorationExcludedDomainList 中不包含域（我们当前可以支持 msn.com、live.com、Hotmail.com、outlook.com），则这些新设置将允许使用 NameDecorationRoutingDomain （应设置为 msn.com）的 "添加 Skype 联系人" 对话框中的地址用户输入自动设置格式。 
  
3. 从 Skype for Business 客户端，用户现在可以搜索和添加 Skype 用户。
    
## <a name="clients-and-interoperability-matrix"></a>客户端和互操作性矩阵

下表概述了 Skype 消费者的最新版本和最新版本的 Skype for Business 之间的互操作性状态。
  

|**Skype 客户端**|**添加联系人、即时消息、状态、音频和视频呼叫**|**Comment**|
|:-----|:-----|:-----|
|Skype Windows 桌面  <br/> |7.6 或更高版本、Windows XP 及更高版本  <br/> |**NEW**：为 windows XP 和 windows Vista 上运行的 windows Skype 客户端添加的支持 **（需要最新的客户端版本7.26 或更高版本）** <br/> |
|Skype Mobile-Android 手机和平板电脑  <br/> |6.19 或更高版本，运行 Android OS 版本4.0.3 或更高版本  <br/> |低规范设备可能不支持视频呼叫  <br/> |
|Skype Mobile-iOS  <br/> |IOS 7 或更高版本上的6.11 或更高版本  <br/> |不支持的是 iPhone 4 及更早版本、iPod 第4代及更早版本、iPad 第一代  <br/> |
|Skype Mac  <br/> |7.19 或更高版本，在 Mac OS X 10.9 （Mavericks）或更高版本上  <br/> |需要 Mac OSX 10.9 或更高版本  <br/> |
|Skype 通用 Windows 应用（Windows 10）桌面和移动设备  <br/> |Windows 10 （Redstone 1 更新或更高版本）  <br/> |Windows 通用应用程序将在秋季2016中接收更新。添加互操作性支持  <br/> |
   
下表概述了最新版本的 Skype for business 与最新版本的 Skype 使用者之间的互操作性状态。 
  
|**客户端**|**Skype 目录搜索和添加联系人**|**Skype A/V、IM 互操作性**|
|:-----|:-----|:-----|
|Skype for Business  <br/> |是  <br/> |是  <br/> |
|Mac 版 Skype for Business  <br/> |可以添加（无搜索）  <br/> |是  <br/> |
|Lync 桌面2013  <br/> |可以添加（无搜索）  <br/> |是  <br/> |
|Lync Web App-联机和本地  <br/> |不适用  <br/> |不适用  <br/> |
|Lync Mobile-Windows Phone  <br/> |即将推出  <br/> |是  <br/> |
|Lync Mobile-Android  <br/> |即将推出  <br/> |是  <br/> |
|Lync 移动-iOS  <br/> |即将推出  <br/> |是  <br/> |
|Lync 会议室系统  <br/> |即将推出  <br/> |是  <br/> |
|Lync 新式应用（Win 8.1）  <br/> |是  <br/> |是  <br/> |
|Lync Mac 2011  <br/> |可以添加（无搜索）  <br/> |是  <br/> |
|Lync 桌面2010  <br/> |可以添加（无搜索）  <br/> |是  <br/> |
|Lync Phone Edition  <br/> |不适用  <br/> |不适用  <br/> |
|Lync 助理  <br/> |不适用  <br/> |不适用  <br/> |
   


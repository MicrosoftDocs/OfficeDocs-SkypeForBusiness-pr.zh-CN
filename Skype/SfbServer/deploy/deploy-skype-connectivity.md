---
title: 在Skype for Business Server中部署Skype连接
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: fb51860b-6f46-4b71-b8c8-682d0982d36d
description: 摘要：了解如何将Skype for Business Server与Skype使用者连接。 也称为Skype连接。
ms.openlocfilehash: 6e569a52569e72d2fe67bdde786b752834452069
ms.sourcegitcommit: c53c22069b1babce7a2364de631057ff501ca1c0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/25/2022
ms.locfileid: "65671678"
---
# <a name="deploy-skype-connectivity-in-skype-for-business-server"></a>在Skype for Business Server中部署Skype连接

**总结：** 了解如何将Skype for Business Server与Skype使用者连接。 也称为Skype连接。
  
本文介绍Skype连接的部署。
  
## <a name="skype-connectivity-overview-for-it-professionals"></a>SKYPE IT 专业人员的连接性概述

Skype连接为Skype for Business用户提供了搜索和添加Skype用户的能力。 Skype连接是Skype for Business的一项功能，可用于启用与Skype用户的联合身份验证和目录搜索。 启用Skype连接后，Skype for Business用户将能够搜索和添加Skype用户。
  
## <a name="skype-directory-search"></a>Skype目录搜索

Skype目录搜索功能为Skype for Business用户提供了搜索Skype联系人的功能。 使用搜索功能，用户可以使用以下内容进行搜索：
  
- **按显示名称搜索，例如“John Doe”** - 这可能会返回许多结果，因此你可能找不到要查找的内容。
    
- **按显示名称和位置（例如“巴塞罗那的 John Doe”）进行搜索** - 这会大大缩小搜索结果的范围。
    
- **通过电子邮件搜索，示例“johndoe@outlook.com”** - 这应在大多数情况下返回一个结果;与指定的电子邮件完全匹配的邮件。 但是，如果同一封电子邮件与多个帐户相关联，则可能会返回多个结果。
    
- **按电话号码搜索，例如“123-123-1234”** - 在大多数情况下，这应返回一个结果：与指定手机完全匹配的手机。 电话编号必须包含国家/地区代码 (，即 1-xxx-yyy-zzzz) 。 如果同一电话号码与多个帐户相关联，则可能会返回多个结果。
    
- **按名称Skype搜索，例如“JohnDoe1456”** - 如果找到完全匹配项，它将作为第一个结果返回。 可能会返回其他可能的“名称”匹配项。
    
    > [!NOTE]
    > Skype目录搜索必须能够在端口 443：104.40.75.246、23.101.135.34 和 40.113.86.19 上与以下 IP 地址通信。 
  
## <a name="supported-deployment-matrix-for-skype-directory-search"></a>Skype目录搜索支持的部署矩阵

下表概述了对Skype目录搜索的支持。
  

|&nbsp;|Skype for Business Server前端|Lync Server 2013 (或更早) 前端|备注|
|:-----|:-----|:-----|:-----|
|Skype for Business Server Edge   |支持   |不支持   |Skype for Business Server和边缘是Skype目录搜索的先决条件   |
|Skype for Business Server Edge + Lync Server 2013 Edge 并行部署   |支持   |不支持   |Skype目录搜索流量流经 Skype for Business Server Edge 服务器。 联合流量通过管理员配置的边缘进行。 例如，管理员可以选择通过 Lync Server 2013 Edge 服务器继续发送联合身份验证流量，这些服务器不支持Skype目录搜索。   |
|Lync Server 2013 (或更早) Edge   |不支持   |不支持   ||
   
> [!NOTE]
> Skype for Business Server前端上运行的通讯簿服务通过在 Edge 服务器中存在Skype搜索端口 4443 来查找 Edge。 
  
> [!NOTE]
> 如果客户的本地部署中有多个站点，并且仅部署了一个 Skype for Business Server Edge 服务器/池，则来自所有站点的搜索流量将通过单个可用的 Edge 服务器。 管理员需要确保来自所有站点的池可以访问部署的 Skype for Business Server Edge 服务器/池。 
  
> [!NOTE]
> 如果请求速率超过 15 个请求/秒，Skype图形服务将限制来自任何本地或Microsoft 365或Office 365客户的搜索请求。 
  
> [!NOTE]
> 对于大型企业本地客户，需要使用Skype搜索服务将域添加到允许列表，以允许更高的请求率。
  
> [!NOTE]
> 如果队列中存在过多的挂起请求，Skype for Business Server将限制传入请求。 
  
## <a name="deploying-skype-connectivity-for-skype-for-business-online"></a>为联机Skype for Business部署Skype连接

Skype连接也是Skype for Business联机的一项功能，它是Microsoft 365和Office 365的一部分。 可以从Microsoft 365 管理中心内的Skype for Business管理中心启用Skype连接功能。
  
对于Microsoft 365中型企业、Office 365 企业版、Microsoft 365 教育版和Office 365：登录到Microsoft 365 管理中心并导航到Skype for Business管理中心。 转到外部通信。 在“公共 IM 服务提供程序”下，单击“启用”。 如果要控制单个用户对Skype连接的访问权限，可以通过编辑单个用户的外部通信设置来实现此操作。
  
有关Office 365 小型企业高级版：登录到Office 365，然后转到管理员\>服务设置\>即时消息、会议和会议。 启用外部通信。 外部通信交换机打开Skype连接以及与其他使用Skype for Business的组织通信。
  
有关Skype for Business联机管理的详细信息，请参阅：
  
- [允许用户连接外部 Skype for Business 用户](../../SfbOnline/set-up-skype-for-business-online/allow-users-to-contact-external-skype-for-business-users.md)

- [如果无法在外部联系人Skype for Business或Skype IM，请尝试什么](https://support.office.com/article/What-to-try-if-you-cant-IM-Skype-for-Business-Lync-or-Skype-external-contacts-87f6d5d7-3b8c-4196-9c8c-1dabb75f54b8?ui=en-US&amp;rs=en-US&amp;ad=US)
    
- [在Skype for Business中添加联系人](https://support.office.com/article/Add-a-contact-in-Skype-for-Business-89338023-2adf-4f5c-90b6-f8b6f72fadd1)
  
- [管理员：为单个用户配置Skype for Business设置](../../SfbOnline/set-up-skype-for-business-online/configure-skype-for-business-settings-for-individual-users.md)
    
## <a name="deploying-skype-connectivity-for-skype-for-business-server"></a>为Skype for Business Server部署Skype连接

Skype for Business Server使用联合身份验证访问体系结构来支持与Skype的连接。 此连接使Skype for Business Server用户能够添加Skype。 Skype客户端还可以将Skype for Business用户添加到其联系人列表。 根据管理设置的策略，Skype for Business Server用户将能够使用即时消息进行通信、查看彼此的状态以及启动音频和视频呼叫。 Skype连接也是 Skype for Business Online 的一项功能，可在Microsoft 365 管理中心内Skype for Business管理中心为Skype for Business联机客户启用。
  
> [!NOTE]
> 如果已将Skype for Business Server配置为使用公共即时消息连接 (PIC) 与 Windows Messenger 连接，则部署已配置为Skype连接。 您可能需要考虑的唯一更改是将现有的 Messenger PIC 条目重命名为Skype。 
  
### <a name="the-skype-for-business-server-public-im-connectivity-provisioning-site-is-no-longer-available"></a>Skype for Business Server公共 IM 连接预配站点不再可用

以前用于在Skype for Business本地部署和Skype之间手动预配联合的站点不再必要，将于 2019 年 8 月 15 日关闭。 与Skype联合现在利用联合合作伙伴发现，这是与 Skype for Business Online 联合所需的相同机制。

任何本地Skype for Business部署与通过现有公共 IM 基础结构Skype用户之间的通信现在要求本地 Edge Server 配置与 Skype for Business Online 兼容。

> [!NOTE]
> 大多数客户无需执行任何操作，包括与 Skype for Business Online 联合的所有部署。
  
需要本地部署才能为其托管的每个域发布联合 DNS SRV 记录。 [DNS 规划](../plan-your-deployment/edge-server-deployments/edge-environmental-requirements.md#dns-planning)中提供了指导。 每个域必须通过 DNS SRV 查询解析为满足域顶级后缀匹配的边缘服务器 FQDN。 例如，考虑域“contoso.com”：

|**有效的 FQDN**|**Comment**|
|:-----|:-----|
|sip.contoso.com   ||
|sipfed.contoso.com   |在每种情况下，必须在边缘服务器上安装的外部证书的 SN 或 SAN 中显示确切的 FQDN。   |
|access.contoso.com   ||
|**FQDN 无效**|**原因**|
|sip.contoso-edge.com   |不是后缀匹配项。  |
|sip.it.contoso.com   |不是顶级后缀匹配项。   |

有关外部证书的进一步指南，请参阅 [证书规划](../plan-your-deployment/edge-server-deployments/edge-environmental-requirements.md#certificate-planning)。

#### <a name="faqs"></a>常见问题解答

**为何要关闭预配网站？**
2006 年部署的公共 IM (PIC) 预配机制 (pic.lync.com) 不再可使用，将于 2019 年 8 月 15 日关闭。 相反，公共 IM 联合身份验证将采用 Skype for Business Online 使用的同一联合模型（称为“合作伙伴发现”），以便其联合 DNS SRV 记录 () 公开发现本地部署。

**此更改是否意味着已弃用公共 IM 联合身份验证？**
否。 公共 IM 联合身份验证将继续受支持多年，可能直到Skype for Business本地产品过期为止。

**我们公司与 Skype for Business Online (共享地址空间) 有混合关系，我们受到影响吗？**
否，因为已与 Skype for Business Online 联合，因此此更改不会影响你。
 
**此更改是否意味着我们的公司必须启用与 Skype for Business Online 的联合？**
否。 如果边缘服务器代理设置未启用与 Skype for Business Online 托管提供商 (sipfed.online.lync.com) 联合，则此更改不会影响这一点。 但是，适用于与 Skype for Business Online 联合的相同 DNS 和证书要求现在也适用于与Skype用户联合。
 
**我们的公司很大，由于监管/合规性/等原因无法更改其边缘配置...我们能做什么？**
任何无法按指定更改其边缘服务器配置的本地组织应尽早联系产品支持人员。

### <a name="enabling-federation-and-public-im-connectivity-pic"></a>启用联合身份验证和公共 IM 连接 (PIC) 

现在，重点关注配置Skype连接所需的Skype for Business Server环境和管理任务。 在本部分中，我们假设管理员已部署Skype for Business Server并配置了外部访问（也称为 Edge 服务器）。 
  
启用联合身份验证和 PIC 需要三个主要步骤。 分别是:
  
1. 配置联合身份验证和 PIC
    
2. 配置至少一个策略以支持联合用户访问
    
3. 配置Skype PIC 提供程序设置
    
#### <a name="1-configure-federation-and-pic"></a>1. 配置联合身份验证和 PIC

需要联合身份验证才能使Skype用户能够与组织中的Skype for Business用户通信。 公共即时消息连接 (PIC) 是一类联合，必须将其配置为使Skype for Business用户能够与Skype用户通信。 使用Skype for Business Server 控制面板配置联合身份验证和 PIC。
  
> [!NOTE]
> Lync Server 2010 (Live Communication Server、Office Communications Server) 之前的产品版本不再支持 PIC 联合身份验证。 PIC 联合支持的平台包括 Skype for Business Server、Lync Server 2013 和 Lync Server 2010。 
  
需要联合身份验证才能使Skype用户能够与组织中的Skype for Business用户通信。 公共即时消息连接 (PIC) 是一类联合，必须将其配置为使Skype for Business Server用户能够与Skype用户通信。 联合身份验证和 PIC 是使用Skype for Business Server 控制面板的 Edge 配置对话框配置的，如图所示。
  
![定义新边缘池。](../media/32d7f255-c6ad-426d-96c2-2ef4d81f3b51.png)
  
> [!NOTE]
> 需要在公共提供程序设置中将 EnableSkypeIdRouting 和 EnableSkypeDirectorySearch 属性设置为 true， (查看后续说明) 搜索才能正常工作。 
  
这会完成必须在服务器上执行的管理任务。 现在，你已设置为Skype连接。
  
#### <a name="2-configure-at-least-one-policy-to-support-federated-user-access"></a>2. 配置至少一个策略以支持联合用户访问

使用Skype for Business Server 控制面板，管理员必须配置一个或多个外部用户访问策略，以控制Skype用户是否可以与内部Skype for Business Server用户协作。
  
#### <a name="3-configure-the-skype-pic-provider-setting"></a>3. 配置Skype PIC 提供程序设置

使用 Skype for Business Server Management Shell，管理员必须将Skype for Business客户端策略配置为将Skype显示为其他 PIC 提供程序。 
  
> [!NOTE]
> 公共即时消息连接 (PIC) 服务提供商的用户无法参与组织中的即时消息或会议，除非在本过程前面配置了至少一个策略 (步骤 2，) 支持公共 IM 连接。 
  
对于新安装，可以通过使用Skype for Business Server 控制面板启用Skype公共提供程序来配置Skype连接，如图所示。
  
![SIP 联合提供商。](../media/8fc7b566-72b5-4c43-961c-9249fdf7e575.png)
  
> [!NOTE]
> 若要在升级到Skype for Business Server时配置Skype连接，必须删除并重新添加现有的Skype公共提供程序。 
  
也可以仅使用 PowerShell 配置Skype连接。 若要使用 PowerShell 配置Skype连接：
  
1. 从Skype for Business Server前端服务器打开 Skype for Business Server Management Shell。
    
2. 运行以下两个命令：
    
   ```powershell
    Remove-CsPublicProvider -Identity <identity-name>
   ```

    > [!NOTE]
    > 如果环境中还没有 PIC 提供程序，并且正在创建新的 PIC 提供程序，则无需运行Remove-CsPublicProvider cmdlet。 
  
   ```powershell
   New-CsPublicProvider -Identity Skype -ProxyFqdn federation.messenger.msn.com -IconUrl https://images.edge.messenger.live.com/Messenger_16x16.png -NameDecorationRoutingDomain msn.com -NameDecorationExcludedDomainList "msn.com,outlook.com,live.com,hotmail.com" -Enabled $true -EnableSkypeIdRouting $true -EnableSkypeDirectorySearch $true
   ```

    不太明显的参数有什么用？
    
   - ProxyFqdn：microsoft) 拥有/维护的Skype联合边缘 (位置
    
   - IconURL：Lync &amp; Skype for Business 客户端用于直观标识Skype联系人的图标
    
   - NameDecorationRoutingDomain 和 NameDecorationExcludedDomainList：设置这些允许用户输入Skype用户的 MSA，而无需了解如何使用“msn.com”“修饰”非 Microsoft 域。 这无需为所有不在 ExcludedDomainList 中的域键入“用户 (contoso.com) @msn.com”。 如果域不在“已排除”列表中，则 SfB 客户端会自动设置 MSA 的格式。 我们已将最常见的 Microsoft 帐户域添加到已排除的列表中。
    
     > [!NOTE]
     > 如果进行了更改，则必须删除公共提供程序并添加新的提供程序。 不允许进行就地更改。 
  
     > [!NOTE]
     > 在 Office 2013 SP1 的 Lync Server 2013 CU5 &amp; Lync 桌面客户端中添加了 NameDecorationRoutingDomain 和 NameDecorationExcludedDomainList 改进了 Lync 用户添加“修饰”非 Microsoft 域所需的Skype联系人以标识和路由它们以Skype (以下格式的情况：用户 (contoso.com) @msn.com) 。 这些新设置将允许使用 NameDecorationRoutingDomain (在“添加Skype联系人”对话框中自动设置地址用户输入的格式，如果该对话框中不包含 NameDecorationExcludedDomainList 中的域，则应将其设置为 msn.com)  (我们当前可以支持 msn.com、live.com、Hotmail.com、outlook.com) 。 
  
3. 从Skype for Business客户端用户现在可以搜索和添加Skype用户。
    
## <a name="clients-and-interoperability-matrix"></a>客户端和互操作性矩阵

下表概述了最新版本的Skype使用者与最新版本的Skype for Business之间的互操作状态。
  

|Skype客户端|添加联系人、IM、状态、音频和视频呼叫|评论|
|:-----|:-----|:-----|
|Skype Windows桌面   |7.6 或更高版本，Windows XP 及更高版本   |**新增**：添加了对Windows XP 上运行的Windows Skype客户端的支持，Windows Vista **(需要最新客户端版本 7.26 或更高版本)**  |
|Skype移动 - Android 电话和平板电脑   |6.19 或更高版本，Android OS 版本 4.0.3 或更高版本运行   |低规格设备可能不支持视频通话   |
|Skype移动 - iOS   |6.11 或更高版本，在 IOS 7 或更高版本上   |不支持iPhone第 4 代及更早版本、iPod 第 4 代及更早版本iPad第 1 代   |
|Skype Mac   |7.19 或更高， Mac OS X 10.9 (小牛) 或更高   |需要 Mac OSX 10.9 或更高版本   |
|Skype通用Windows应用 (Windows 10) 桌面和移动版   |Windows 10 (红石 1 更新或更高版本)    |Windows通用应用将在 2016 年秋季收到更新，添加互操作支持   |
   
下表概述了最新版本的Skype for Business与最新版本的Skype使用者之间的互操作状态。 
  
|客户端|Skype目录搜索和添加联系人|Skype A/V、IM 互操作|
|:-----|:-----|:-----|
|Skype for Business   |是   |是   |
|Mac 版 Skype for Business   |可以添加 (无搜索)    |是   |
|Lync Desktop 2013   |可以添加 (无搜索)    |是   |
|Lync Web App - 联机和本地   |不适用   |不适用   |
|Lync Mobile - Windows Phone   |即将推出   |是   |
|Lync Mobile - Android   |即将推出   |是   |
|Lync Mobile - iOS   |即将推出   |是   |
|Lync 会议室系统   |即将推出   |是   |
|Lync 新式应用 (Win 8.1)    |是   |是   |
|Lync Mac 2011   |可以添加 (无搜索)    |是   |
|Lync Desktop 2010   |可以添加 (无搜索)    |是   |
|Lync Phone Edition   |不适用   |不适用   |
|Lync 助理   |不适用   |不适用   |
   

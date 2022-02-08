---
title: 在Skype部署 Skype for Business Server
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
description: 摘要：了解如何将Skype for Business Server使用者Skype连接。 也称为连接Skype连接。
ms.openlocfilehash: 834d5329e15f5fc52a24e5f1c86a02c416f04d31
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/05/2022
ms.locfileid: "62389664"
---
# <a name="deploy-skype-connectivity-in-skype-for-business-server"></a>在Skype部署 Skype for Business Server

**摘要：** 了解如何与Skype for Business Server用户Skype连接。 也称为连接Skype连接。
  
本文逐步介绍了 Skype Connectivity 的部署。
  
## <a name="skype-connectivity-overview-for-it-professionals"></a>Skype IT 专业人员的连接概述

Skype连接Skype for Business用户能够搜索和添加Skype用户。 Skype连接是 Skype for Business 的一项功能，允许您启用与用户之间的联盟Skype搜索。 启用 Skype 连接后Skype for Business用户将能够搜索并添加Skype用户。
  
## <a name="skype-directory-search"></a>Skype目录搜索

Skype目录搜索功能Skype for Business用户能够搜索联系人Skype联系人。 搜索功能允许用户使用以下内容进行搜索：
  
- **按显示名称搜索，例如"John Doe"** - 这可能会返回许多结果，因此您可能找不到要查找的内容。
    
- **按显示名称位置进行搜索，例如"John Doe in This will narrow** the results of the search'2013"。
    
- **通过电子邮件搜索，例如"johndoe@outlook.com"** - 在大多数情况下，这应该返回一个结果;与指定电子邮件完全匹配的电子邮件。 但是，如果同一电子邮件与多个帐户关联，可能会返回多个结果。
    
- **按电话号码搜索，例如"123-123-1234"** - 这在大多数情况下应返回一个结果;与指定电话完全匹配的电话。 电话号码必须包含国家/地区代码 (1-xxx-yyy-zzzz) 。 如果同一电话号码与多个帐户关联，可能会返回多个结果。
    
- **按名称Skype搜索，例如"JohnDoe1456"** - 如果找到精确匹配，它将作为第一个结果返回。 可能会返回其他可能的"名称"匹配。
    
    > [!NOTE]
    > Skype 目录搜索必须能够与端口 443 上的以下 IP 地址进行通信：104.40.75.246、23.101.135.34 和 40.113.86.19。 
  
## <a name="supported-deployment-matrix-for-skype-directory-search"></a>支持用于目录搜索Skype部署矩阵

下表概述了对目录搜索Skype支持。
  

|&nbsp;|Skype for Business Server前端|Lync Server 2013 (或) 前端|备注|
|:-----|:-----|:-----|:-----|
|Skype for Business Server Edge   |支持   |不支持   |Skype for Business Server和边缘是进行Skype目录搜索的先决条件   |
|Skype for Business Server并行部署的边缘 + Lync Server 2013 边缘   |支持   |不支持   |Skype目录搜索流量流经Skype for Business Server边缘服务器。 联盟流量通过管理员配置的边缘。 例如，管理员可以选择继续通过 Lync Server 2013 边缘服务器发送联盟通信，这些边缘服务器不支持Skype搜索。   |
|Lync Server 2013 (或) Edge   |不支持   |不支持   ||
   
> [!NOTE]
> 前端上运行Skype for Business Server通讯簿服务通过边缘服务器中是否存在 Skype搜索端口 4443 来查找边缘。 
  
> [!NOTE]
> 如果客户在本地部署中有多个站点，并且他们仅部署了一个 Skype for Business Server 边缘服务器/池，则来自所有站点搜索的流量将经过一个可用的边缘服务器。 管理员需要确保所有站点中的池都可以访问边缘服务器/池中Skype for Business Server部署的内容。 
  
> [!NOTE]
> Skype如果请求速率超过 15 个请求/秒，Microsoft 365或 Office 365 客户限制来自任何本地或 Office 365 客户的搜索请求。 
  
> [!NOTE]
> 对于大型企业本地客户，域将需要添加到具有 Skype 搜索服务的允许列表中，以允许更高的请求速率。
  
> [!NOTE]
> Skype for Business Server队列中的待处理请求过多，将限制传入请求。 
  
## <a name="deploying-skype-connectivity-for-skype-for-business-online"></a>为 Skype Online 部署 Skype for Business Connectivity

Skype连接也是 Skype for Business Online 的一项功能，它是 Microsoft 365 和 Office 365。 可以从管理中心内的 Skype 管理Skype for Business启用 Microsoft 365 管理中心。
  
For Microsoft 365 Midsize Business， Office 365 企业版， Microsoft 365 教育版， and Office 365 for Government： Sign in to the Microsoft 365 管理中心 and navigate to theSkype for Business管理中心。 转到"外部通信"。 在"公共 IM 服务提供商"下，单击"启用"。 如果要控制单个用户对 Skype 连接的访问，可以通过编辑单个用户的"外部通信"设置来这样做。
  
For Office 365 小型企业高级版： Sign in to Office 365， and go to Admin \> Service 设置 \> Instant messaging， meetings and conferencing. 打开"外部通信"。 外部通信开关可同时Skype连接性，并与其他使用 Skype for Business。
  
有关联机管理Skype for Business，请参阅：
  
- [允许用户连接外部 Skype for Business 用户](../../SfbOnline/set-up-skype-for-business-online/allow-users-to-contact-external-skype-for-business-users.md)

- [无法与外部联系人或外部联系人Skype for Business Skype尝试](https://support.office.com/article/What-to-try-if-you-cant-IM-Skype-for-Business-Lync-or-Skype-external-contacts-87f6d5d7-3b8c-4196-9c8c-1dabb75f54b8?ui=en-US&amp;rs=en-US&amp;ad=US)
    
- [在联系人中心中添加Skype for Business](https://support.office.com/article/Add-a-contact-in-Skype-for-Business-89338023-2adf-4f5c-90b6-f8b6f72fadd1)
  
- [管理员：配置Skype for Business用户的用户设置](../../SfbOnline/set-up-skype-for-business-online/configure-skype-for-business-settings-for-individual-users.md)
    
## <a name="deploying-skype-connectivity-for-skype-for-business-server"></a>为Skype部署 Skype for Business Server

Skype for Business Server使用联合访问体系结构来支持与 Skype 的连接。 此连接使Skype for Business Server用户能够添加Skype。 Skype客户端还可以将Skype for Business添加到其联系人列表。 根据管理中设置的策略Skype for Business Server用户将能够使用即时消息进行通信、查看彼此状态以及发起音频和视频呼叫。 Skype连接也是 Skype for Business Online 的一项功能，可以从 Skype for Business 管理中心为 Skype for Business Online 客户Microsoft 365 管理中心。
  
> [!NOTE]
> 如果Skype for Business Server使用公共即时消息连接 (PIC) 与 Windows Messenger 连接，则您的部署已配置为 Skype 连接。 您可能要考虑的唯一更改是，将现有的 Messenger PIC 条目重命名为Skype。 
  
### <a name="the-skype-for-business-server-public-im-connectivity-provisioning-site-is-no-longer-available"></a>不再Skype for Business Server公共 IM 连接设置站点

以前用于在 Skype for Business 本地部署和 Skype 之间手动设置联盟的网站不再需要，将在 2019 年 8 月 15 日关闭。 与 Skype 联盟现在利用联盟伙伴发现，这是与 Skype for Business Online 联盟所需的相同机制。

通过现有公共 IM 基础结构Skype for Business本地部署Skype用户之间的通信现在要求本地边缘服务器配置与 Skype for Business Online 兼容。

> [!NOTE]
> 大多数客户无需任何操作，包括所有与 Skype for Business Online 联盟的部署。
  
本地部署需要为它们承载的每个域发布联合 DNS SRV 记录。 DNS 规划中 [提供了指南](../plan-your-deployment/edge-server-deployments/edge-environmental-requirements.md#dns-planning)。 每个域都必须通过 DNS SRV 查询解析为满足该域的顶级后缀匹配的边缘服务器 FQDN。 例如，考虑域"contoso.com"：

|**有效 FQDN**|**Comment**|
|:-----|:-----|
|sip.contoso.com   ||
|sipfed.contoso.com   |在每种情况下，边缘服务器上安装的外部证书的 SN 或 SAN 中都必须存在确切的 FQDN。   |
|access.contoso.com   ||
|**无效的 FQDN**|**原因**|
|sip.contoso-edge.com   |后缀不匹配。  |
|sip.it.contoso.com   |顶级后缀不匹配。   |

有关外部证书的进一步指南，可在证书 [规划中找到](../plan-your-deployment/edge-server-deployments/edge-environmental-requirements.md#certificate-planning)。

#### <a name="faqs"></a>常见问题解答

**为什么要关闭设置网站？**
2006 年 (公共 IM) PIC (pic.lync.com) 设置机制不再可用，将在 2019 年 8 月 15 日关闭。 相反，公共 IM 联盟将假定 Skype for Business Online 使用的联盟模型（称为"合作伙伴发现"，其中本地部署可以公开发现其联盟 DNS SRV 记录 (s) ）。

**此更改是否意味着公用 IM 联盟被弃用？**
不正确。 公共 IM 联盟将继续受支持很多年，可能Skype for Business本地产品生命周期结束。

**我们的公司与 (Online 共享) 空间Skype for Business，是否受到影响？**
否，由于你已与 Skype for Business Online 联盟，此更改不会影响你。
 
**此更改是否意味着公司必须启用与 Skype for Business Online 的联盟？**
不正确。 如果边缘服务器代理设置未启用与 Skype for Business Online 托管提供商的联盟 (sipfed.online.lync.com) 则此更改不会影响这一点。 但是，适用于与 Skype for Business Online 联盟的相同 DNS 和证书要求现在也适用于与 Skype 用户联盟。
 
**公司规模较大，因法规/合规性/等原因无法更改其边缘配置...我们可以做什么？**
任何无法根据指定更改其边缘服务器配置本地组织都应尽早联系产品支持部门。

### <a name="enabling-federation-and-public-im-connectivity-pic"></a>为 PIC 服务器启用联盟 (公共 IM) 

现在重点介绍配置 Skype for Business Server 连接所需的环境和管理Skype任务。 在此部分中，我们假定管理员已Skype for Business Server配置外部访问（也称为边缘服务器）。 
  
启用联盟和 PIC 需要执行三个主要步骤。 分别是：
  
1. 配置联盟和 PIC
    
2. 配置至少一个策略以支持联盟用户访问
    
3. 配置Skype PIC 提供程序设置
    
#### <a name="1-configure-federation-and-pic"></a>1. 配置联盟和 PIC

需要联盟，Skype才能与Skype for Business用户进行通信。 公共即时消息连接 (PIC) 是一类联盟，必须配置为允许 Skype for Business 用户与 Skype 用户通信。 联盟和 PIC 使用"控制面板"Skype for Business Server配置。
  
> [!NOTE]
> Lync Server 2010 (Live Communication Server、Office Communications Server) 之前的产品版本不再支持 PIC 联盟。 PIC 联盟支持的平台包括 Skype for Business Server、Lync Server 2013 和 Lync Server 2010。 
  
需要联盟，Skype才能与Skype for Business用户进行通信。 公共即时消息连接 (PIC) 是一类联盟，必须配置为允许 Skype for Business Server 用户与 Skype 通信。 联盟和 PIC 使用"Skype for Business Server控制面板的边缘配置"对话框进行配置，如图所示。
  
![定义新的边缘池。](../media/32d7f255-c6ad-426d-96c2-2ef4d81f3b51.png)
  
> [!NOTE]
> EnableSkypeIdRouting 和 EnableSkypeDirectorySearch 属性需要在公共提供程序设置中设置为 true， (请参阅稍后说明) 搜索才能正常工作。 
  
这将完成必须在服务器上执行的管理任务。 现在，你已设置为 Skype Connectivity。
  
#### <a name="2-configure-at-least-one-policy-to-support-federated-user-access"></a>2. 至少配置一个策略以支持联盟用户访问

通过使用Skype for Business Server控制面板，管理员必须配置一个或多个外部用户访问策略Skype用户能否与内部用户Skype for Business Server协作。
  
#### <a name="3-configure-the-skype-pic-provider-setting"></a>3. 配置Skype PIC 提供程序设置

使用 Skype for Business Server 命令行管理程序，管理员必须将 Skype for Business 客户端策略配置为Skype PIC 提供程序。 
  
> [!NOTE]
> 公共即时消息连接 (PIC) 服务提供商的用户不能参与组织的 IM 或会议，除非在此过程的前面步骤) 中至少配置了一个策略 (步骤 2 以支持公共 IM 连接。 
  
对于新安装，可以通过Skype控制面板Skype公共提供商来配置 Skype for Business Server 连接，如图所示。
  
![SIP 联盟提供程序。](../media/8fc7b566-72b5-4c43-961c-9249fdf7e575.png)
  
> [!NOTE]
> 若要在Skype时配置 Skype for Business Server 连接，必须删除现有连接，然后重新Skype公共提供商。 
  
此外，Skype PowerShell 配置连接。 若要使用 PowerShell Skype连接：：
  
1. 从 Skype for Business Server 前端服务器中，打开 Skype for Business Server 命令行管理程序。
    
2. 运行以下两个命令：
    
   ```powershell
    Remove-CsPublicProvider -Identity <identity-name>
   ```

    > [!NOTE]
    > 如果你的环境中还没有 PIC 提供程序，并且正在创建新的 PIC 提供程序，则无需运行 Remove-CsPublicProvider cmdlet。 
  
   ```powershell
   New-CsPublicProvider -Identity Skype -ProxyFqdn federation.messenger.msn.com -IconUrl https://images.edge.messenger.live.com/Messenger_16x16.png -NameDecorationRoutingDomain msn.com -NameDecorationExcludedDomainList "msn.com,outlook.com,live.com,hotmail.com" -Enabled $true -EnableSkypeIdRouting $true -EnableSkypeDirectorySearch $true
   ```

    不太明显的参数有什么用？
    
   - ProxyFqdn：Skype Microsoft (拥有/维护的联盟边缘) 
    
   - IconURL：Lync &amp; Skype for Business客户端用来直观标识联系人Skype图标
    
   - NameDecorationRoutingDomain 和 NameDecorationExcludedDomainList：通过设置它们，用户可以输入 Skype 用户的 MSA，而无需知道"修饰"具有"msn.com"的非 Microsoft 域。 这样就无需为不在 ExcludedDomainList 中的所有域键入"user (contoso.com) @msn.com"。 如果域不在"已排除"列表中，则 SfB 客户端将自动设置 MSA 的格式。 我们已将最常见的 Microsoft 帐户域添加到排除列表中。
    
     > [!NOTE]
     > 如果进行了更改，则必须删除公共提供商并添加新提供程序。 不允许进行就地更改。 
  
     > [!NOTE]
     > NameDecorationRoutingDomain 和 NameDecorationExcludedDomainList 在 Office 2013 SP1 的 Lync Server 2013 CU5 &amp; Lync 桌面客户端中新增了一些情况，即添加 Skype 联系人的 Lync 用户需要"修饰"非 Microsoft 域，以标识这些联系人，并采用以下格式将其路由至 Skype (：user (contoso.com) @msn.com) 。 这些新设置将允许自动设置用户在"添加 Skype 联系人"对话框中输入的地址格式，其名称为 NameDecorationRoutingDomain (如果 NameDecorationExcludedDomainList (我们当前可以支持 msn.com、live.com、Hotmail.com、outlook.com) ，应将其设置为 msn.com) 。 
  
3. 现在Skype for Business客户端用户现在可以搜索并添加Skype用户。
    
## <a name="clients-and-interoperability-matrix"></a>客户端和互操作性矩阵

下表概述了 Skype 消费者的最新版本与最新版本的 Skype for Business 之间的互操作状态。
  

|Skype 客户端|添加联系人、IM、状态、音频和视频呼叫|评论|
|:-----|:-----|:-----|
|Skype Windows 桌面   |7.6 或更高版本，Windows XP 和更高版本   |**新增**：增加了对在 Windows XP 上运行的 Windows Skype 客户端的支持，Windows Vista (需要最新的客户端版本 **7.26 或更高版本**)   |
|Skype移动版 - Android 电话 和平板电脑   |6.19 或更高版本，运行 Android OS 版本 4.0.3 或更高版本   |低规格设备可能不支持视频呼叫   |
|Skype Mobile - iOS   |IOS 7 或更高版本上的 6.11 或更高版本   |不支持 4 iPhone 4 及更早版本、iPod 第 4 代和更早版本，iPad 1 代   |
|Skype Mac   |7.19 或更高版本，在 Mac OS X 10.9 (Mave进行) 或更高版本   |需要 Mac OSX 10.9 或更高版本   |
|Skype桌面Windows移动 (Windows 10) 应用   |Windows 10 (Redstone 1 更新或更高版本)    |Windows通用应用将在 2016 年秋季收到更新，添加互操作支持   |
   
下表概述了最新版本的 Skype for Business 与最新版本的使用者之间的互操作Skype状态。 
  
|客户端|Skype目录搜索和添加联系人|Skype A/V，IM 互操作|
|:-----|:-----|:-----|
|Skype for Business   |是   |是   |
|Mac 版 Skype for Business   |可以添加 (搜索)    |是   |
|Lync Desktop 2013   |可以添加 (搜索)    |是   |
|Lync Web App - 联机和本地   |不适用   |不适用   |
|Lync Mobile - Windows Phone   |即将推出   |是   |
|Lync Mobile - Android   |即将推出   |是   |
|Lync Mobile - iOS   |即将推出   |是   |
|Lync 会议室系统   |即将推出   |是   |
|Lync Modern App (Win 8.1)    |是   |是   |
|Lync Mac 2011   |可以添加 (搜索)    |是   |
|Lync Desktop 2010   |可以添加 (搜索)    |是   |
|Lync Phone Edition   |不适用   |不适用   |
|Lync Attendant   |不适用   |不适用   |
   

---
title: 在Skype部署 Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: fb51860b-6f46-4b71-b8c8-682d0982d36d
description: 摘要：了解如何将Skype for Business Server使用者Skype连接。 也称为连接Skype连接。
ms.openlocfilehash: 752bae0797da1129d677dd962ad9dc6e4b9a6e99123babcf30ab8bd11bdbf668
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2021
ms.locfileid: "54307783"
---
# <a name="deploy-skype-connectivity-in-skype-for-business-server"></a>在Skype部署 Skype for Business Server

**摘要：** 了解如何与Skype for Business Server用户Skype连接。 也称为连接Skype连接。
  
本文逐步介绍了 Skype Connectivity 的部署。
  
## <a name="skype-connectivity-overview-for-it-professionals"></a>Skype适用于 IT 专业人员的连接概述

Skype连接Skype for Business用户能够搜索和添加Skype用户。 Skype连接是一项Skype for Business功能，允许您启用与用户之间的联盟Skype搜索。 启用 Skype 连接后Skype for Business用户将能够搜索并添加Skype用户。
  
## <a name="skype-directory-search"></a>Skype目录搜索

Skype目录搜索功能Skype for Business用户能够搜索Skype联系人。 搜索功能允许用户使用以下内容进行搜索：
  
- **按显示名称搜索，例如"John Doe"-** 这可能会返回许多结果，因此您可能找不到要查找的内容。
    
- **按显示名称位置进行搜索，例如"John Doe in This will narrow** the results of the search'2013"。
    
- **通过电子邮件搜索，例如"johndoe@outlook.com"-** 在大多数情况下，这应该返回一个结果;与指定电子邮件完全匹配的电子邮件。 但是，如果同一电子邮件与多个帐户关联，可能会返回多个结果。
    
- **按电话号码搜索，例如"123-123-1234"-** 这在大多数情况下应返回一个结果;与指定电话完全匹配的电话。 电话号码必须包含国家/地区代码 (1-xxx-yyy-zzzz) 。 如果同一电话号码与多个帐户关联，可能会返回多个结果。
    
- **按名称Skype搜索，例如"JohnDoe1456"** - 如果找到精确匹配，它将作为第一个结果返回。 可能会返回其他可能的"名称"匹配。
    
    > [!NOTE]
    > Skype目录搜索必须能够与端口 443 上的以下 IP 地址进行通信：104.40.75.246、23.101.135.34 和 40.113.86.19。 
  
## <a name="supported-deployment-matrix-for-skype-directory-search"></a>用于目录搜索Skype部署矩阵

下表概述了对目录搜索Skype支持。
  

||**Skype for Business Server前端**|**Lync Server 2013 (或) 前端**|**Comments**|
|:-----|:-----|:-----|:-----|
|Skype for Business ServerEdge  <br/> |支持  <br/> |不支持  <br/> |Skype for Business Server和边缘是执行 Skype 目录搜索的先决条件  <br/> |
|Skype for Business Server并行部署的边缘 + Lync Server 2013 边缘  <br/> |支持  <br/> |不支持  <br/> |Skype目录搜索流量流经Skype for Business Server服务器。 联盟流量通过管理员配置的边缘。 例如，管理员可以选择继续通过 Lync Server 2013 边缘服务器发送联盟通信，这些边缘服务器不支持Skype搜索。  <br/> |
|Lync Server 2013 (或) Edge  <br/> |不支持  <br/> |不支持  <br/> ||
   
> [!NOTE]
> 前端上运行Skype for Business Server通讯簿服务通过边缘服务器中是否存在 Skype搜索端口 4443 来查找边缘。 
  
> [!NOTE]
> 如果客户在本地部署中有多个站点，并且他们仅部署了一个 Skype for Business Server 边缘服务器/池，则来自所有站点搜索的流量将经过一个可用的边缘服务器。 管理员需要确保所有站点中的池都可以访问边缘服务器/池中Skype for Business Server部署的内容。 
  
> [!NOTE]
> Skype如果请求速率超过 15 个请求/秒，Microsoft 365或 Office 365 客户限制来自任何本地或 Office 365 客户的搜索请求。 
  
> [!NOTE]
> 对于大型企业本地客户，需要将域添加到具有 Skype 搜索服务的 allowlist，以允许更高的请求速率。
  
> [!NOTE]
> Skype for Business Server队列中的待处理请求过多，将限制传入请求。 
  
## <a name="deploying-skype-connectivity-for-skype-for-business-online"></a>为 Skype Online 部署 Skype for Business Connectivity

Skype连接也是 Skype for Business Online 的一项功能，它是 Microsoft 365 和 Office 365。 可以从管理中心内的 Skype 管理Skype for Business启用 Microsoft 365 管理中心。
  
For Microsoft 365 Midsize Business， Office 365 企业版， Microsoft 365 教育版， and Office 365 for Government： Sign in to the Microsoft 365 管理中心 and navigate to the Skype for Business Administration Center. 转到"外部通信"。 在"公共 IM 服务提供商"下，单击"启用"。 如果要控制单个用户对 Skype 连接的访问，可以通过编辑单个用户的"外部通信"设置来这样做。
  
For Office 365 小型企业高级版： Sign in to Office 365， and go to Admin \> Service 设置 \> Instant messaging， meetings and conferencing. 打开"外部通信"。 外部通信开关可同时Skype连接性，以及与其他使用 Skype for Business。
  
有关联机管理Skype for Business，请参阅：
  
- [允许用户连接外部 Skype for Business 用户](../../SfbOnline/set-up-skype-for-business-online/allow-users-to-contact-external-skype-for-business-users.md)

- [无法与外部联系人进行即时消息Skype for Business Skype尝试](https://support.office.com/article/What-to-try-if-you-cant-IM-Skype-for-Business-Lync-or-Skype-external-contacts-87f6d5d7-3b8c-4196-9c8c-1dabb75f54b8?ui=en-US&amp;rs=en-US&amp;ad=US)
    
- [在联系人中心中添加Skype for Business](https://support.office.com/article/Add-a-contact-in-Skype-for-Business-89338023-2adf-4f5c-90b6-f8b6f72fadd1)
  
- [管理员：配置Skype for Business用户的用户设置](../../SfbOnline/set-up-skype-for-business-online/configure-skype-for-business-settings-for-individual-users.md)
    
## <a name="deploying-skype-connectivity-for-skype-for-business-server"></a>为Skype部署 Skype for Business Server

Skype for Business Server使用联合访问体系结构来支持与 Skype 的连接。 此连接使Skype for Business Server用户能够添加Skype。 Skype客户端还可以将Skype for Business添加到其联系人列表。 根据管理中设置的策略Skype for Business Server用户将能够使用即时消息进行通信、查看彼此状态以及发起音频和视频呼叫。 Skype连接也是 Skype for Business Online 的一项功能，并且可以从 Skype for Business 管理中心内的 Skype for Business Online 客户Microsoft 365 管理中心。
  
> [!NOTE]
> 如果Skype for Business Server配置为使用公共即时消息连接 (PIC) 与 Windows Messenger 连接，则您的部署已配置为 Skype 连接。 您可能要考虑的唯一更改是，将现有 Messenger PIC 条目重命名为Skype。 
  
### <a name="the-skype-for-business-server-public-im-connectivity-provisioning-site-is-no-longer-available"></a>不再Skype for Business Server公共 IM 连接设置站点

以前用于在 Skype for Business 本地部署和 Skype 之间手动设置联盟的网站不再需要，将在 2019 年 8 月 15 日关闭。 与 Skype 联盟现在利用联盟伙伴发现，这是与 Skype for Business Online 联盟所需的相同机制。

通过现有公共 IM 基础结构Skype for Business本地部署Skype用户之间的通信现在要求本地边缘服务器配置与 Skype for Business Online 兼容。

> [!NOTE]
> 大多数客户无需任何操作，包括所有与 Skype for Business Online 联盟的部署。
  
本地部署需要为它们承载的每个域发布联合 DNS SRV 记录。 DNS 规划 中 [提供了指南](../plan-your-deployment/edge-server-deployments/edge-environmental-requirements.md#dns-planning)。 每个域都必须通过 DNS SRV 查询解析为满足该域的顶级后缀匹配的边缘服务器 FQDN。 例如，考虑域"contoso.com"：

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
2006 (PIC) 设置机制 (pic.lync.com) 不再可用，将在 2019 年 8 月 15 日关闭。 相反，公共 IM 联盟将假定 Skype for Business Online 使用的联盟模型（称为"合作伙伴发现"，其中本地部署可以公开发现其联盟 DNS SRV 记录 () ）。

**此更改是否意味着公用 IM 联盟被弃用？**
否。 公共 IM 联盟将继续受支持很多年，可能Skype for Business产品生命周期结束。

**我们公司与 (Online 的) 地址空间Skype for Business，是否受到影响？**
否，由于你已与 Skype for Business Online 联盟，此更改不会影响你。
 
**此更改是否意味着公司必须启用与 Skype for Business Online 的联盟？**
否。 如果边缘服务器代理设置未启用与 Skype for Business Online (sipfed.online.lync.com) 联盟，则此更改不会影响这一点。 但是，适用于与 Skype for Business Online 联盟的相同 DNS 和证书要求现在也适用于与 Skype 用户联盟。
 
**公司规模较大，因法规/合规性/等原因无法更改其边缘配置...我们可以做什么？**
任何无法根据指定更改其边缘服务器配置本地组织都应尽早联系产品支持部门。

### <a name="enabling-federation-and-public-im-connectivity-pic"></a>为 PIC 服务器启用联盟 (公共 IM) 

现在重点介绍配置 Skype for Business Server 连接所需的环境和管理Skype任务。 在此部分中，我们假定管理员已Skype for Business Server和配置外部访问（也称为边缘服务器）。 
  
启用联盟和 PIC 需要执行三个主要步骤。 分别是：
  
1. 配置联盟和 PIC
    
2. 配置至少一个策略以支持联盟用户访问
    
3. 配置Skype PIC 提供程序设置
    
#### <a name="1-configure-federation-and-pic"></a>1. 配置联盟和 PIC

需要联盟，Skype才能与Skype for Business用户进行通信。 公共即时消息连接 (PIC) 是一类联盟，必须配置为允许 Skype for Business 用户与 Skype 用户进行通信。 联盟和 PIC 使用"控制面板"Skype for Business Server配置。
  
> [!NOTE]
> Lync Server 2010 (Live Communication Server、Office Communications Server) 之前的产品版本不再支持 PIC 联盟。 PIC 联盟支持的平台包括 Skype for Business Server、Lync Server 2013 和 Lync Server 2010。 
  
需要联盟，Skype才能与Skype for Business用户进行通信。 公共即时消息连接 (PIC) 是一种联盟类，必须配置为允许 Skype for Business Server 用户与 Skype 通信。 联盟和 PIC 使用"Skype for Business Server控制面板的边缘配置"对话框进行配置，如图所示。
  
![定义新的边缘池](../media/32d7f255-c6ad-426d-96c2-2ef4d81f3b51.png)
  
> [!NOTE]
> EnableSkypeIdRouting 和 EnableSkypeDirectorySearch 属性需要在公共提供程序设置中设置为 true (请参阅稍后的说明) 搜索才能正常工作。 
  
这将完成必须在服务器上执行的管理任务。 现在，你已设置 Skype Connectivity。
  
#### <a name="2-configure-at-least-one-policy-to-support-federated-user-access"></a>2. 至少配置一个策略以支持联盟用户访问

通过使用Skype for Business Server控制面板，管理员必须配置一个或多个外部用户访问策略Skype用户能否与内部用户Skype for Business Server协作。
  
#### <a name="3-configure-the-skype-pic-provider-setting"></a>3. 配置Skype PIC 提供程序设置

使用 Skype for Business Server 命令行管理程序，管理员必须将 Skype for Business 客户端策略配置为Skype PIC 提供程序。 
  
> [!NOTE]
> 公共即时消息连接 (PIC) 服务提供商的用户不能参与您组织的 IM 或会议，除非在此过程的前面步骤) 中至少配置了一个策略 (步骤 2 以支持公共 IM 连接。 
  
对于新安装，Skype通过使用"Skype控制面板"启用 Skype for Business Server 公共提供商来配置连接，如图所示。
  
![SIP 联盟提供商](../media/8fc7b566-72b5-4c43-961c-9249fdf7e575.png)
  
> [!NOTE]
> 若要在Skype配置连接Skype for Business Server必须删除现有连接，然后重新Skype公共提供商。 
  
此外，Skype PowerShell 配置连接。 若要使用 powerShell Skype连接：：
  
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
    
   - NameDecorationRoutingDomain 和 NameDecorationExcludedDomainList：通过设置这些设置，用户可以输入 Skype 用户的 MSA，而无需知道"修饰"具有"msn.com"的非 Microsoft 域。 这样就无需为不在 ExcludedDomainList 中 (contoso.com 域键入"user (contoso.com) @msn.com"。 如果域不在"已排除"列表中，则 SfB 客户端将自动设置 MSA 的格式。 我们已将最常见的 Microsoft 帐户域添加到排除列表中。
    
     > [!NOTE]
     > 如果进行了更改，则必须删除公共提供商并添加新提供程序。 不允许进行就地更改。 
  
     > [!NOTE]
     > &amp;NameDecorationRoutingDomain 和 NameDecorationExcludedDomainList 在 Office 2013 SP1 的 Lync Server 2013 CU5 Lync 桌面客户端中新增了一些改进情况，即，添加 Skype 联系人的 Lync 用户需要"修饰"非 Microsoft 域，以标识这些联系人Skype (格式为：user (contoso.com) @msn.com) 。 这些新设置将允许在 NameDecorationRoutingDomain (如果 NameDecorationExcludedDomainList (中不包含域，则 NameDecorationRoutingDomain (将在"添加 Skype msn.com) 联系人"对话框中自动设置用户输入的地址的格式 (我们当前可以支持 msn.com、live.com、Hotmail.com、outlook.com) 。 
  
3. 现在，Skype for Business客户端用户可以搜索并添加Skype用户。
    
## <a name="clients-and-interoperability-matrix"></a>客户端和互操作性矩阵

下表概述了最新版本的使用者与最新版本的 Skype 之间的互操作Skype for Business。
  

|**Skype客户端**|**添加联系人、IM、状态、音频和视频呼叫**|**Comment**|
|:-----|:-----|:-----|
|Skype Windows 桌面  <br/> |7.6 或更高版本，Windows XP 及更高版本  <br/> |**新增**：增加了对在 Windows XP 上运行的 Windows Skype 客户端的支持，Windows Vista (需要最新的客户端版本 **7.26 或)** <br/> |
|Skype移动 - Android 电话 和平板电脑  <br/> |6.19 或更高版本，运行 Android OS 版本 4.0.3 或更高版本  <br/> |低规格设备可能不支持视频呼叫  <br/> |
|Skype移动 - iOS  <br/> |IOS 7 或更高版本上的 6.11 或更高版本  <br/> |第 4 代iPhone、iPod 第 4 代和更早版本（第 1 代iPad版本）不支持  <br/> |
|SkypeMac  <br/> |7.19 或更高版本，在 Mac OS X 10.9 (Mave进行) 或更高版本  <br/> |需要 Mac OSX 10.9 或更高版本  <br/> |
|Skype通用Windows应用 (Windows 10) 桌面和移动版  <br/> |Windows 10 (Redstone 1 更新或更高版本)   <br/> |Windows通用应用将在 2016 年秋季收到更新，添加互操作支持  <br/> |
   
下表概述了最新版本的 Skype for Business 与最新版本的使用者之间的互操作Skype状态。 
  
|**客户端**|**Skype目录搜索和添加联系人**|**SkypeA/V、IM 互操作**|
|:-----|:-----|:-----|
|Skype for Business  <br/> |是  <br/> |是  <br/> |
|Mac 版 Skype for Business  <br/> |可以添加 (搜索)   <br/> |是  <br/> |
|Lync Desktop 2013  <br/> |可以添加 (搜索)   <br/> |是  <br/> |
|Lync Web App - 联机和本地  <br/> |不适用  <br/> |不适用  <br/> |
|Lync Mobile - Windows Phone  <br/> |即将推出  <br/> |是  <br/> |
|Lync Mobile - Android  <br/> |即将推出  <br/> |是  <br/> |
|Lync Mobile - iOS  <br/> |即将推出  <br/> |是  <br/> |
|Lync 会议室系统  <br/> |即将推出  <br/> |是  <br/> |
|Lync Modern App (Win 8.1)   <br/> |是  <br/> |是  <br/> |
|Lync Mac 2011  <br/> |可以添加 (搜索)   <br/> |是  <br/> |
|Lync Desktop 2010  <br/> |可以添加 (搜索)   <br/> |是  <br/> |
|Lync Phone Edition  <br/> |不适用  <br/> |不适用  <br/> |
|Lync Attendant  <br/> |不适用  <br/> |不适用  <br/> |
   

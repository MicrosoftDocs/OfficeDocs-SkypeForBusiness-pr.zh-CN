---
title: 在 Skype for Business 服务器中部署 Skype 连接
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: fb51860b-6f46-4b71-b8c8-682d0982d36d
description: '摘要: 了解如何将 Skype for business 服务器与 Skype 消费者连接。 也称为 Skype 连接。'
ms.openlocfilehash: 1f03b873299828dedf6c0ffca113d60d277bf65c
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34302829"
---
# <a name="deploy-skype-connectivity-in-skype-for-business-server"></a>在 Skype for Business 服务器中部署 Skype 连接
 
**摘要:** 了解如何将 Skype for business 服务器与 Skype 消费者连接。 也称为 Skype 连接。
  
本文介绍了 Skype 连接的部署。
  
## <a name="skype-connectivity-overview-for-it-professionals"></a>面向 IT 专业人员的 Skype 连接概述

Skype 连接使 Skype for business 用户能够搜索和添加 Skype 用户。 Skype 连接是 Skype for Business 的一项功能, 使你能够与 Skype 用户进行联盟和目录搜索。 启用 Skype 连接后, 您的 Skype for Business 用户将能够搜索和添加 Skype 用户。
  
## <a name="skype-directory-search"></a>Skype 目录搜索

Skype 目录搜索功能允许 Skype for Business 用户搜索 Skype 联系人。该搜索功能允许用户使用以下方式进行搜索：
  
- **按显示名称搜索, 示例 "John Doe"** -这可能会返回许多结果, 因此你可能找不到要查找的内容。
    
- **按显示名称加位置搜索, 示例 "John Doe 于巴塞罗纳"** -这将显著缩小搜索结果的范围。
    
- **通过电子邮件进行搜索, 示例 "johndoe@outlook.com"** -这在大多数情况下应返回一个结果;与指定的电子邮件完全匹配的一个。 但是，如果同一电子邮件与多个账户关联，则可能返回多个结果。
    
- **按电话号码搜索, 例如 "123-123-1234"** -这在大多数情况下应返回一个结果;与指定电话完全匹配的一个。 电话号码必须包含国家/地区代码（例如 1-xxx-yyy-zzzz）。 如果同一电话号码与多个账户关联，则可能返回多个结果。
    
- **按 Skype 用户名进行搜索, 示例 "JohnDoe1456"** -如果找到精确匹配, 它将作为第一个结果返回。 可能会返回其他可能的 "名称" 匹配项。
    
    > [!NOTE]
    > Skype 目录搜索必须能够与端口 443 上的以下 IP 地址进行通信：104.40.75.246、23.101.135.34 和 40.113.86.19。 
  
## <a name="supported-deployment-matrix-for-skype-directory-search"></a>Skype 目录搜索支持的部署矩阵

下表概述了对 Skype 目录搜索的支持。
  

||**Skype for business 服务器前端**|**Lync Server 2013（或更早版本）前端**|**注释**|
|:-----|:-----|:-----|:-----|
|Skype for Business 服务器边缘  <br/> |支持  <br/> |否  <br/> |Skype for business 服务器和 Edge 是 Skype 目录搜索的先决条件  <br/> |
|Skype for business 服务器 Edge + Lync Server 2013 Edge 并排部署  <br/> |支持  <br/> |否  <br/> |Skype 目录搜索流量流经 Skype for Business Server 边缘服务器。联盟流量流经管理员配置的边缘。例如，管理员可以选择继续通过不支持 Skype 目录搜索的 Lync Server 2013 边缘服务器发送联盟流量。  <br/> |
|Lync Server 2013（或更早版本）边缘  <br/> |否  <br/> |否  <br/> ||
   
> [!NOTE]
> 在 Skype for Business 服务器前端运行的通讯录服务在边缘服务器中是否存在 Skype 搜索端口4443查找边缘。 
  
> [!NOTE]
> 如果客户在其本地部署中具有多个网站, 并且他们仅部署了一个 Skype for Business 服务器 Edge 服务器/池, 那么来自所有网站的搜索流量将经历单个可用的边缘服务器。 管理员需要确保所有网站的池都可以访问已部署的 Skype for Business Server Edge 服务器/池。 
  
> [!NOTE]
> 如果请求率超过 15 个请求/秒，Skype 图形服务将限制来自本地或 Office 365 客户的搜索请求。 
  
> [!NOTE]
> 对于大型企业本地客户，需要使用 Skype 搜索服务对域建立白名单才能允许更高的请求率。 
  
> [!NOTE]
> 如果队列中有太多挂起的请求, 则 Skype for business 服务器将阻止传入的请求。 
  
## <a name="deploying-skype-connectivity-for-skype-for-business-online-in-office-365"></a>在 Office 365 中部署 Skype for Business Online 的 Skype 连接

Skype 连接同样是 Skype for Business Online（Office 365 的一部分）的一项功能。您可以从 Office 365 门户中的 Skype for Business 管理中心启用 Skype 连接功能。
  
对于 Office 365 中型企业版、Office 365 企业版、Office 365 教育版和 Office 365 政府版：登录 Office 365 门户并导航到 Skype for Business 管理中心。 转至“外部通信”。 在“公共 IM 服务提供商”下，单击“启用”。 如果您想要控制单个用户对 Skype 连接的访问, 您可以通过编辑单个用户的外部通信设置来执行此操作。
  
对于 Office 365 小型企业高级版: 登录到 Office 365, 然后转到 " \>管理员服务\>设置" 即时消息、会议和会议。 打开“外部通信”。 “外部通信”开关会同时打开与其他使用 Skype for Business 的组织之间的 Skype 连接和通信。
  
有关 Skype for Business Online 管理的更多信息，请参阅：
  
- [允许用户连接外部 Skype for Business 用户](../../SfbOnline/set-up-skype-for-business-online/allow-users-to-contact-external-skype-for-business-users.md)

- [无法向 Skype for business 或 Skype 外部联系人发送即时消息时应尝试的操作](https://support.office.com/en-us/article/What-to-try-if-you-cant-IM-Skype-for-Business-Lync-or-Skype-external-contacts-87f6d5d7-3b8c-4196-9c8c-1dabb75f54b8?ui=en-US&amp;rs=en-US&amp;ad=US)
    
- [在 Skype for Business 中添加联系人](https://support.office.com/en-US/article/Add-a-contact-in-Skype-for-Business-89338023-2adf-4f5c-90b6-f8b6f72fadd1)
  
- [管理员：为单个用户配置 Skype for Business 设置](../../SfbOnline/set-up-skype-for-business-online/configure-skype-for-business-settings-for-individual-users.md)
    
## <a name="deploying-skype-connectivity-for-skype-for-business-server"></a>为 Skype for Business 服务器部署 Skype 连接

Skype for business 服务器使用联盟访问体系结构来支持与 Skype 的连接。 此连接允许您的 Skype for Business Server 用户添加 Skype。 Skype 客户端也可向联系人列表添加 Skype for Business 用户。 基于在 Skype for Business Server 用户中设置的策略, 用户将能够使用即时消息进行通信, 查看彼此的状态, 并启动音频和视频通话。 Skype 连接也是 Skype for Business Online 的一项功能，可从 Office 365 门户中的 Skype for Business 管理中心为 Skype for Business Online 客户启用。
  
> [!NOTE]
> 如果 Skype for Business Server 已配置为通过使用公共即时消息连接 (PIC) 连接 Windows Messenger，则您的部署已配置好了 Skype 连接。您可能希望作出的唯一更改是将您的现有 Messenger PIC 条目重命名为 Skype。 
  
### <a name="accessing-the-skype-for-business-server-public-im-connectivity-provisioning-site-from-skype-for-business-server"></a>从 Skype for Business 服务器访问 Skype for Business Server 公共 IM 连接设置网站

此设置过程最多需要 30 天才能完成，但也可能仅花费几天时间，具体取决于请求量。建议您在完成文档中的其余步骤之前先开始此过程。在为您的帐户完成 Skype 设置过程后，该帐户将被激活，并且将为符合资格的用户启用公共 IM 连接。 
  
要设置 Skype 连接，您需要以下信息：
  
- Microsoft 协议编号
    
- 访问边缘服务完全限定的域名 (FQDN)
    
- 会话初始协议 (SIP) 域
    
- 任何其他访问边缘服务 FQDN
    
- 联系信息
    
要启动 Skype 连接的设置过程，请执行下列操作：
  
1. 使用您的 Microsoft Windows Live https://pic.lync.comID 登录到网站。
    
2. 选择 Microsoft 许可协议类型。
    
3. 选中复选框，确保您已阅读并接受 Skype for Business Server 的产品使用权利。
    
4. 在“启动设置请求”页面上，单击合适的链接以启动设置请求：
    
5. 在“指定设置信息”页面上，输入访问边缘服务 FQDN。 例如，sip.contoso.com。
    
    > [!IMPORTANT]
    > 2017 年 7 月 1 日后，Microsoft 会另外要求客户部署联盟 DNS SRV 记录，以使公共 IM 连接继续有效。 
  
6. 输入至少一个或多个 SIP 域名，然后单击“添加”。
    
    > [!NOTE]
    > 需要至少一个访问边缘服务器才能完成设置过程。虽然单个访问边缘 FQDN 可支持多个 SIP 域，但是单个 SIP 域不能由多个访问边缘 FQDN 来表示。SIP 域和访问边缘服务器必须处于活动状态、正在运行，并且在网络上可访问。 
  
7. 在“公共 IM 服务提供商”列表中，选择“Skype”，然后单击“下一步”以添加联系信息并提交设置请求。
    
在提交设置请求之后，可能需要多达 30 天帐户才能激活并且才能为用户启用 Skype 连接，但此过程也可能只需耗费几天时间，具体取决于队列。
  
### <a name="enabling-federation-and-public-im-connectivity-pic"></a>启用联盟和公共 IM 连接 (PIC)

提交设置请求后，您可以将注意力放在 Skype for Business Server 环境和配置 Skype 连接所需的管理任务上。在此部分，我们假定管理员已部署了 Skype for Business Server 并配置了外部访问（即边缘服务器）。 
  
要启用联盟和 PIC，需要执行三个主要步骤。包括：
  
1. 配置联盟和 PIC
    
2. 配置至少一个策略以支持联盟的用户访问
    
3. 配置 Skype PIC 提供商设置
    
#### <a name="1-configure-federation-and-pic"></a>1. 配置联盟和 PIC

需要联盟，Skype 用户才能与您的组织中的 Skype for Business 用户进行通信。公共即时消息连接 (PIC) 是一种联盟类别，必须配置它，您的 Skype for Business 用户才能够与 Skype 用户进行通信。联盟和 PIC 可使用 Skype for Business Server 控制面板进行配置。
  
> [!NOTE]
> Live Communication Server 2005 SP1 或 Office Communications Server 2007 不再支持 PIC 联盟。 PIC 联盟支持的平台包括 Skype for business Server、Lync Server 2013、Lync Server 2010 和 Office 通信服务器 2007 R2。 
  
需要联盟，Skype 用户才能与您的组织中的 Skype for Business 用户进行通信。公共即时消息连接 (PIC) 是一种联盟类别，必须配置它，您的 Skype for Business Server 用户才能够与 Skype 用户进行通信。联盟和 PIC 可使用 Skype for Business Server 控制面板的边缘配置对话框进行配置，如图所示。
  
![定义新边缘池](../media/32d7f255-c6ad-426d-96c2-2ef4d81f3b51.png)
  
> [!NOTE]
> 要让搜索正常运行，EnableSkypeIdRouting 和 EnableSkypeDirectorySearch 属性需要在公共提供商设置中设为 true（参见后续说明）。 
  
这将完成必须在服务器上执行的管理任务。您现在可以设置 Skype 连接。
  
#### <a name="2-configure-at-least-one-policy-to-support-federated-user-access"></a>2. 至少配置一个用于支持联合用户访问的策略

使用 Skype for Business Server 控制面板，管理员必须配置一个或多个外部用户访问策略来控制 Skype 用户能否与内部 Skype for Business Server 用户进行协作。
  
#### <a name="3-configure-the-skype-pic-provider-setting"></a>3. 配置 Skype PIC 提供程序设置

使用 Skype for Business Server 命令行管理程序，管理员必须配置 Skype for Business 客户端策略以将 Skype 显示为附加 PIC 提供商。 
  
> [!NOTE]
> 公共即时消息连接 (PIC) 服务提供商的用户无法在你的组织中参与 IM 或会议, 直到你还配置了至少一个策略 (本过程前面的步骤 2) 以支持公用 IM 连接。 
  
对于新安装，您可以使用 Skype for Business Server 控制面板启用 Skype 公共提供商，从而配置 Skype 连接，如图所示。
  
![SIP 联盟提供商](../media/8fc7b566-72b5-4c43-961c-9249fdf7e575.png)
  
> [!NOTE]
> 要在升级为 Skype for Business Server 时配置 Skype 连接，您必须删除并重新添加现有 Skype 公共提供商。 
  
也可以仅使用 PowerShell 配置 Skype 连接。要使用 PowerShell 配置 Skype 连接：
  
1. 从 Skype for Business Server 前端服务器，打开 Skype for Business Server 命令行管理程序。
    
2. 运行以下两个命令：
    
   ```
    Remove-CsPublicProvider -Identity <identity-name>
   ```

    > [!NOTE]
    > 如果您的环境中没有 PIC 提供商，并且要创建新的 PIC 提供商，则您无需运行 Remove-CsPublicProvider cmdlet。 
  
   ```
   New-CsPublicProvider -Identity Skype -ProxyFqdn federation.messenger.msn.com -IconUrl https://images.edge.messenger.live.com/Messenger_16x16.png -NameDecorationRoutingDomain msn.com -NameDecorationExcludedDomainList "msn.com,outlook.com,live.com,hotmail.com" -Enabled $true -EnableSkypeIdRouting $true -EnableSkypeDirectorySearch $true
   ```

    这些不太明显的参数有什么作用？
    
   - ProxyFqdn：Skype 联盟边缘的位置（由 Microsoft 掌控/维护）
    
   - IconURL: Lync &amp; Skype for business 客户端使用的图标直观地标识 Skype 联系人
    
   - NameDecorationRoutingDomain 和 NameDecorationExcludedDomainList: 设置这些设置允许用户输入 Skype 用户的 MSAs, 而无需了解有关 "装修" 非 Microsoft 域的 "msn.com"。 这样, 就不需要为 ExcludedDomainList 中未提供的所有域键入 "user (contoso) @msn .com"。 SfB 客户端将自动格式化 MSA（如果域不在 Excluded 列表中）。 我们已将最常用的 Microsoft 帐户域添加到排除列表。
    
     > [!NOTE]
     > 如果作出了更改，则必须删除并重新添加公共提供商。 不允许进行就地更改。 
  
     > [!NOTE]
     > 在 Lync Server 2013 CU5 &amp;中添加的 OFFICE 2013 SP1 中的 lync 桌面客户端, NameDecorationRoutingDomain 和 NameDecorationExcludedDomainList 改善了 lync 用户将 "装饰" 非 Microsoft 域所需的 Skype 联系人添加到标识并将其路由到 Skype (格式为: user (contoso) @msn .com)。 这些新设置将允许在 "添加 Skype 联系人" 对话框中使用 "添加 Skype 联系人" 对话框自动设置地址格式, 如果该对话框中不包含域 NameDecorationRoutingDomain, 则该对话框应设置为 msn.com) (我们目前可以支持 msn.com、live.com、Hotmail.com、outlook.com)。 
  
3. 通过 Skype for Business 客户端，用户现在可以搜索和添加 Skype 用户。
    
## <a name="clients-and-interoperability-matrix"></a>客户端和互操作性矩阵

下表概括介绍了最新版本的 Skype 消费者产品与最新版本的 Skype for Business 之间的互操作状况。
  

|**Skype 客户端**|**添加联系人、IM、状态、语音和视频呼叫**|**注释**|
|:-----|:-----|:-----|
|Skype Windows 桌面  <br/> |7.6 或更高版本，Windows XP 和更高版本  <br/> |**新增**: 为在 windows XP 和 windows Vista 上运行的 windows Skype 客户端添加的支持 **(需要最新的客户端版本7.26 或更高版本)** <br/> |
|Skype 移动 - Android 手机和平板电脑   <br/> |6.19 或更高版本，运行 Android OS 4.0.3 或更高版本  <br/> |低规格设备可能不支持视频呼叫  <br/> |
|Skype Mobile-iOS  <br/> |6.11 或更高版本，在 IOS 7 或更高版本上  <br/> |在 iPhone 4 和更早版本、iPod 第 4 代和更早版本、Pad 第 1 代上不受支持  <br/> |
|Skype Mac  <br/> |7.19 或更高版本，在 Mac OS X 10.9 (Mavericks) 或更高版本上  <br/> |需要 Mac OSX 10.9 或更高版本  <br/> |
|Skype 通用 Windows 应用 (Windows 10) 桌面和移动版  <br/> |Windows 10（Redstone 1 更新或更高版本）  <br/> |Windows 通用应用将在 2016 年秋季收到更新，该更新添加了互操作性支持  <br/> |
   
下表概括介绍了最新版本的 Skype for Business 与最新版本的 Skype 消费者产品之间的互操作状况。 
  
|**客户端**|**Skype 目录搜索和添加联系人**|**Skype A/V、IM 互操作**|
|:-----|:-----|:-----|
|Skype for Business  <br/> |是  <br/> |是  <br/> |
|Mac 版 Skype for Business  <br/> |可以添加（无搜索）  <br/> |是  <br/> |
|Lync Desktop 2013  <br/> |可以添加（无搜索）  <br/> |是  <br/> |
|Lync Web App - 联机和本地  <br/> |不适用  <br/> |不适用  <br/> |
|Lync 移动 - Windows Phone  <br/> |即将提供  <br/> |是  <br/> |
|Lync 移动 - Android  <br/> |即将提供  <br/> |是  <br/> |
|Lync 移动 - iOS  <br/> |即将提供  <br/> |是  <br/> |
|Lync Room System  <br/> |即将提供  <br/> |是  <br/> |
|Lync Modern App (Win 8.1)  <br/> |是  <br/> |是  <br/> |
|Lync Mac 2011  <br/> |可以添加（无搜索）  <br/> |是  <br/> |
|Lync Desktop 2010  <br/> |可以添加（无搜索）  <br/> |是  <br/> |
|Lync Phone Edition  <br/> |不适用  <br/> |不适用  <br/> |
|Lync Attendant  <br/> |不适用  <br/> |不适用  <br/> |
   


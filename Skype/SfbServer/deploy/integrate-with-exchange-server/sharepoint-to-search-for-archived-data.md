---
title: 配置 SharePoint Server 以搜索存档的 Skype for Business 数据
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 12/20/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 17f49365-8778-4962-a41b-f96faf6902f1
description: 摘要： 配置 SharePoint Server 以搜索存档的 Exchange Server 和 Skype 业务服务器的数据。
ms.openlocfilehash: 0663874985063f4cf051aec69792ea0bdb32bb26
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25373319"
---
# <a name="configure-sharepoint-server-to-search-for-archived-skype-for-business-data"></a>配置 SharePoint Server 以搜索存档的 Skype for Business 数据
 
**摘要：** 配置 SharePoint Server 以搜索存档的 Exchange Server 2016 或 Exchange Server 2013 和 Skype 业务服务器的数据。
  
在 Exchange 存储即时消息和 Web 会议脚本的主要优点之一而不是 Skype 业务服务器的服务器是，在相同位置中存储数据，管理员可以使用单个工具搜索存档 Exchange 数据和/或存档的 Skype Business Server 数据。 因为所有的数据存储在同一个放置 (Exchange) 可以存档 Exchange 数据来搜索任何工具还可以搜索业务服务器数据的存档 Skype。
  
更加方便地搜索的存档数据的一个工具是 Microsoft SharePoint Server 2013。 如果您想要使用 SharePoint Business Server 数据的 Skype 搜索，您必须首先完成所有配置 Exchange 存档中 Skype Business Server 所涉及的步骤。 已成功集成 Exchange Server 和 Skype 业务服务器后，然后必须在 SharePoint 服务器上安装 Exchange [Web Services 托管 API](https://go.microsoft.com/fwlink/p/?LinkId=258305) 。 下载的文件 (EWSManagedAPI.msi) 可以保存到 SharePoint 服务器上的任何文件夹。
  
下载文件后，在 SharePoint 服务器上完成以下过程：
  
1. 打开命令窗口，方法是依次单击“**开始**”、“**所有程序**”、“**附件**”，右键单击“**命令提示符**”，然后单击“**以管理员身份运行**”。
    
2. 在命令窗口中，使用 cd 命令将当前目录更改为保存文件 EWSManagedAPI.msi 的文件夹。 例如，如果已将文件保存到 C:\Downloads 在命令窗口中键入以下命令，然后按 Enter:
    
   ```
   cd C:\Downloads
   ```

3. 若要安装该 API，键入以下命令，然后按 Enter:
    
   ```
   msiexec /I EwsManagedApi.msi addlocal="ExchangeWebServicesApi_Feature,ExchangeWebServicesApi_Gac"
   ```

4. 安装该 API 后，重置 IIS，通过键入以下命令并按 Enter:
    
   ```
   iisreset
   ```

安装 Exchange Web 服务之后，您必须然后配置 SharePoint Server 和 Exchange Server 之间的服务器到服务器身份验证。 若要执行此操作，首先打开 SharePoint Management Shell 并运行以下命令集：
  
```
New-SPTrustedSecurityTokenIssuer -Name "Exchange" -MetadataEndPoint "https://autodiscover.litwareinc.com/autodiscover/metadata/json/1"
$service = Get-SPSecurityTokenServiceConfig
$service.HybridStsSelectionEnabled = $True
$service.AllowMetadataOverHttp = $False
$service.AllowOAuthOverHttp = $False
$service.Update()
```

> [!NOTE]
> 务必要使用自动发现服务的 URI。 不使用示例 URI https://autodiscover.litwareinc.com/autodiscover/metadata/json/1。 
  
您已创建的令牌颁发者并配置令牌服务之后，运行以下命令，确保用您的 SharePoint 网站的 URL 替代示例 urlhttp://atl-sharepoint-001:
  
```
$exchange = Get-SPTrustedSecurityTokenIssuer "Exchange"
$app = Get-SPAppPrincipal -Site "https://atl-sharepoint-001" -NameIdentifier $exchange.NameID
$site = Get-SPSite  "https://atl-sharepoint-001"
Set-SPAppPrincipalPermission -AppPrincipal $app -Site $site.RootWeb -Scope "SiteSubscription" -Right "FullControl" -EnableAppOnlyPolicy
```

若要配置 Exchange server 的服务器到服务器身份验证，打开 Exchange Management Shell 并运行类似如下的命令 （假定 c： 驱动器上安装了 Exchange，并使其使用的默认文件夹路径）：
  
```
"C:\Program Files\Microsoft\Exchange Server\V15\Scripts\Configure-EnterprisePartnerApplication.ps1 -AuthMetaDataUrl 'https://atl-sharepoint-001/_layouts/15/metadata/json/1' -ApplicationType SharePoint"
```

配置合作伙伴应用程序后建议您停止并在所有 Exchange 邮箱和客户端访问服务器上重新启动 Internet 信息服务 (IIS)。 您可使用类似于以下命令的命令重新启动 IIS，以下命令将重新启动计算机 atl-exchange-001 上的此服务：
  
```
iisreset atl-exchange-001
```

在 Exchange 命令行管理程序中或从任何其他命令窗口，可以从运行此命令。
  
接下来，运行类似以下内容，这将使指定的用户 （在本例中为 kenmyer） 进行 Exchange 上的发现的权限的命令：
  
```
Add-RoleGroupMember "Discovery Management" -Member "kenmyer"
```

Exchange 和 SharePoint 之间建立服务器到服务器身份验证后下, 一步是在 SharePoint 中创建的电子数据展示网站。 可通过运行类似于以下从 SharePoint 命令行管理程序命令：
  
```
$template = Get-SPWebTemplate | Where-Object {$_.Title -eq "eDiscovery Center"}
New-SPSite -Url "https://atl-sharepoint-001/sites/discovery" -OwnerAlias "kenmyer" -Template $Template -Name "Discovery Center"
```

> [!NOTE]
> “eDiscovery”是“electronic discovery”（电子发现）的缩写，通常表示浏览可在法院“合理计算为可导致可靠证据”的项目的电子存档的过程。 
  
新的网站准备就绪后下, 一步是配置 Exchange Server for SharePoint 操作结果源。 通过完成以下过程从 SharePoint 管理中心页上，可以执行的操作：
  
1. 在“管理中心”页上，单击“**管理服务应用程序**”，然后单击“**Search Service 应用程序**”。
    
2. 在“Search Service 应用程序：搜索管理”页上，单击“**结果源**”，然后单击“**新建结果源**”。
    
3. 在“**新建结果源**”窗格中，在“**名称**”框中输入新结果源的名称（例如，“**Microsoft Exchange**”）。 选择**Exchange**作为结果源**协议**，并为您的 Exchange 服务器，在**Exchange 源 URL**框中输入 web 服务源 URL。 该源 URL 应类似如下：
    
    https://atl-exchange-001.litwareinc.com/ews/exchange.asmx
    
4. 确保未选择“**使用自动发现**”，然后单击“**确定**”。
    
最后，创建新的电子数据展示案例和新的电子数据展示 （例如，完成以下过程从 SharePoint 发现网站集https://atl-sharepoint-001/sites/discovery):
  
1. 在“网站内容”页上，单击“**创建新的案例**”。
    
2. 在“网站内容：新建 SharePoint 网站”页上，在“**标题**”框中输入用户的电子邮件别名（例如，“**kenmyer**”），然后将同一 URL 添加至“**网站地址**”框中。这将产生一个类似如下的 URL：
    
    https://atl-sharepoint-001/sites/eDiscovery/kenmyer
    
3. 单击“**创建**”。
    
4. 当电子数据展示集页出现时，单击“**标识和保留：发现集**”下的“**新建项目**”。
    
5. 在“新建：发现集”页上的“**发现集名称**”框中输入用户的电子邮件别名。 输入**电子数据展示 Lync\\*****筛选器**在框中，然后单击**添加&amp;管理源**。
    
6. 在添加&amp;管理源页上，在**邮箱**下的第一个文本框中输入用户的电子邮件别名。 单击位于文本框旁边的检查邮箱图标，以确认 SharePoint 可以连接至指定邮箱。
    
7. 单击“**确定**”。
    
8. 在“电子数据展示集”页上，单击“**保存**”，以保存新的电子数据展示集。
    
此时，您可以搜索指定的邮箱 (kenmyer) 和/或启用就地保留相同的方式的任何其他 SharePoint 内容或结果源。
  


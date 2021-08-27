---
title: 配置 SharePoint Server 以搜索存档Skype for Business数据
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 12/20/2018
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: 17f49365-8778-4962-a41b-f96faf6902f1
description: 摘要：配置 SharePoint Server 以搜索由 Exchange Server 和 Skype for Business Server 存档的数据。
ms.openlocfilehash: 8a27bb170f0e089d702417a32d93eee96c7c6299
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/26/2021
ms.locfileid: "58604201"
---
# <a name="configure-sharepoint-server-to-search-for-archived-skype-for-business-data"></a>配置 SharePoint Server 以搜索存档Skype for Business数据
 
**摘要：** 配置 SharePoint Server 以搜索由 Exchange Server 2016 或 Exchange Server 2013 和 Skype for Business Server 存档Skype for Business Server。
  
在 Exchange Server 而非 Skype for Business Server 中存储即时消息和 Web 会议脚本的主要好处之一是，在同一位置存储数据使管理员可以使用单个工具来搜索存档的 Exchange 数据和/或存档的 Skype for Business Server 数据。 由于所有数据存储在同一位置 (Exchange) 因此任何可搜索已存档数据Exchange也可以搜索已存档Skype for Business Server数据。
  
2013 年 10 月提供了一种可轻松搜索存档数据Microsoft SharePoint Server工具。 如果要使用 SharePoint 搜索 Skype for Business Server 数据，则必须先完成在 Skype for Business Server 中配置存档Exchange涉及的所有步骤。 在Exchange Server Skype for Business Server集成后，必须在 SharePoint 服务器上安装 Exchange Web 服务托管[API。](https://go.microsoft.com/fwlink/p/?LinkId=258305) 下载的文件 (EWSManagedAPI.msi) 可以保存到 SharePoint 服务器上的任何文件夹。
  
下载文件后，在 SharePoint 服务器上完成以下过程：
  
1. 打开命令窗口，方法是依次单击“开始”、“所有程序”、“附件”，右键单击“命令提示符”，然后单击“以管理员身份运行”。
    
2. 在命令窗口中，使用 cd 命令将当前目录更改为保存文件 EWSManagedAPI.msi 的文件夹。 例如，如果已将文件保存到 C：\Downloads，请在命令窗口中键入以下命令，然后按 Enter：
    
   ```console
   cd C:\Downloads
   ```

3. 若要安装 API，请键入以下命令，然后按 Enter：
    
   ```console
   msiexec /I EwsManagedApi.msi addlocal="ExchangeWebServicesApi_Feature,ExchangeWebServicesApi_Gac"
   ```

4. 安装 API 后，通过键入以下命令并按 Enter 重置 IIS：
    
   ```console
   iisreset
   ```

安装Exchange Web 服务后，必须在服务器与服务器之间配置服务器SharePoint身份验证Exchange Server。 为此，请首先打开命令行SharePoint命令行管理程序并运行以下命令集：
  
```powershell
New-SPTrustedSecurityTokenIssuer -Name "Exchange" -MetadataEndPoint "https://autodiscover.litwareinc.com/autodiscover/metadata/json/1"
$service = Get-SPSecurityTokenServiceConfig
$service.HybridStsSelectionEnabled = $True
$service.AllowMetadataOverHttp = $False
$service.AllowOAuthOverHttp = $False
$service.Update()
```

> [!NOTE]
> 务必要使用自动发现服务的 URI。 请勿使用示例 https://autodiscover.litwareinc.com/autodiscover/metadata/json/1 URI。 
  
创建令牌颁发者并配置令牌服务后，运行以下命令，确保将 SharePoint 网站的 URL 替换为示例 URLhttp://atl-sharepoint-001:
  
```powershell
$exchange = Get-SPTrustedSecurityTokenIssuer "Exchange"
$app = Get-SPAppPrincipal -Site "https://atl-sharepoint-001" -NameIdentifier $exchange.NameID
$site = Get-SPSite  "https://atl-sharepoint-001"
Set-SPAppPrincipalPermission -AppPrincipal $app -Site $site.RootWeb -Scope "SiteSubscription" -Right "FullControl" -EnableAppOnlyPolicy
```

若要为 Exchange Server 配置服务器到服务器身份验证，请打开 Exchange 命令行管理程序，并运行与此 (类似的命令（假定 Exchange 已安装在驱动器 C： 上，并使用默认文件夹路径) ：
  
```powershell
"C:\Program Files\Microsoft\Exchange Server\V15\Scripts\Configure-EnterprisePartnerApplication.ps1 -AuthMetaDataUrl 'https://atl-sharepoint-001/_layouts/15/metadata/json/1' -ApplicationType SharePoint"
```

配置合作伙伴应用程序后，建议您在所有 Internet Information Services (和客户端访问) IIS Exchange停止并重新启动。 您可使用类似于以下命令的命令重新启动 IIS，以下命令将重新启动计算机 atl-exchange-001 上的此服务：
  
```powershell
iisreset atl-exchange-001
```

此命令可以从命令行管理程序Exchange运行，也可以从任何其他命令窗口运行。
  
接下来，运行与以下内容类似的命令，该命令 (，kenmyer 有权) 用户进行发现Exchange：
  
```powershell
Add-RoleGroupMember "Discovery Management" -Member "kenmyer"
```

在 Exchange 和 SharePoint 之间建立服务器到服务器身份验证后，下一步是在 SharePoint 中创建电子数据展示网站。 这可以通过从命令行管理程序运行类似SharePoint完成：
  
```powershell
$template = Get-SPWebTemplate | Where-Object {$_.Title -eq "eDiscovery Center"}
New-SPSite -Url "https://atl-sharepoint-001/sites/discovery" -OwnerAlias "kenmyer" -Template $Template -Name "Discovery Center"
```

> [!NOTE]
> “eDiscovery”是“electronic discovery”（电子发现）的缩写，通常表示浏览可在法院“合理计算为可导致可靠证据”的项目的电子存档的过程。 
  
新网站准备就绪后，下一步是配置Exchange Server用作网站结果SharePoint。 为此，可以从"管理中心"页SharePoint过程：
  
1. 在“管理中心”页上，单击“管理服务应用程序”，然后单击“Search Service 应用程序”。
    
2. 在“Search Service 应用程序: 搜索管理”页上，单击“结果源”，然后单击“新建结果源”。
    
3. 在“新建结果源”窗格中，在“名称”框中输入新结果源的名称（例如，“Microsoft Exchange”）。 选择 **Exchange** 协议"作为结果源 **，** 然后在"源 URL"框中输入 Exchange 服务器的 Web Exchange **URL。** 该源 URL 应类似如下：
    
    https://atl-exchange-001.litwareinc.com/ews/exchange.asmx
    
4. 确保未选择“使用自动发现”，然后单击“确定”。
    
最后，SharePoint 通过从发现站点网站中完成以下过程，创建新的电子数据展示 (电子数据展示集，例如，https://atl-sharepoint-001/sites/discovery):
  
1. 在“网站内容”页上，单击“创建新的案例”。
    
2. 在“网站内容: 新建 SharePoint 网站”页上，在“标题”框中输入用户的电子邮件别名（例如，“kenmyer”），然后将同一 URL 添加至“网站地址”框中。这将产生一个类似如下的 URL：
    
    https://atl-sharepoint-001/sites/eDiscovery/kenmyer
    
3. 单击“创建”。
    
4. 当电子数据展示集页出现时，单击“标识和保留: 发现集”下的“新建项目”。
    
5. 在“新建: 发现集”页上的“发现集名称”框中输入用户的电子邮件别名。 在 *_Filter** 框中输入 **eDiscovery Lync \\** _ ，然后单击添加 **&amp; 管理源**。
    
6. 在"添加管理源"页上，在"邮箱"下的第一 &amp; 个文本框中输入 **用户的电子邮件别名**。 单击位于文本框旁边的检查邮箱图标，以确认 SharePoint 可以连接至指定邮箱。
    
7. 单击“确定”。
    
8. 在“电子数据展示集”页上，单击“保存”，以保存新的电子数据展示集。
    
此时，您可以在 kenmy) er (和/或启用 In-Place 搜索指定的邮箱，其保留方式与搜索任何其他内容SharePoint源的方式相同。
  


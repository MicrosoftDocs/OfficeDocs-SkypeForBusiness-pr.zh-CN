---
title: Lync Server 2013：配置 Microsoft SharePoint Server 2013 以搜索已存档的 Lync Server 2013 数据
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring SharePoint Server 2013 to search for archived Lync Server 2013 data
ms:assetid: 17f49365-8778-4962-a41b-f96faf6902f1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687978(v=OCS.15)
ms:contentKeyID: 49733566
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1e000f6116b112b3de9840c22c29510745303035
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41755916"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-microsoft-sharepoint-server-2013-to-search-for-archived-microsoft-lync-server-2013-data"></a>配置 Microsoft SharePoint Server 2013 以搜索已存档的 Microsoft Lync Server 2013 数据

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2014-02-04_

在 Microsoft Exchange Server 2013 而不是 Microsoft Lync Server 2013 中存储即时消息和 Web 会议脚本的主要优势之一是，在同一位置存储数据使管理员能够使用单个工具搜索已存档的 Exchange 数据和/或已存档的 Lync 服务器数据。 由于所有数据都存储在同一位置（Exchange），因此任何可以搜索已存档 Exchange 数据的工具也可以搜索已存档的 Lync 服务器数据。

使您能够轻松搜索已存档数据的一个工具是 Microsoft SharePoint Server 2013。 如果想要使用 SharePoint 搜索 Lync Server 数据，必须首先完成在 Lync Server 中配置 Exchange 存档所涉及的所有步骤。 成功集成 Exchange 2013 和 Lync Server 2013 后，必须在 SharePoint Server 上安装 Exchange Web Services 托管 API 版本 2.0;可以从 Microsoft 下载中心（[http://go.microsoft.com/fwlink/p/?LinkId=258305](http://go.microsoft.com/fwlink/p/?linkid=258305)）下载该 API 的安装程序。 下载的文件 (EWSManagedAPI.msi) 可以保存到 SharePoint 服务器上的任何文件夹。

下载文件后，在 SharePoint 服务器上完成以下过程：

1.  打开命令窗口，方法是依次单击“**开始**”、“**所有程序**”、“**附件**”，右键单击“**命令提示符**”，然后单击“**以管理员身份运行**”。

2.  在命令窗口中，使用 **cd** 命令将当前目录更改为保存文件 EWSManagedAPI.msi 的文件夹。 例如，如果您已将文件保存到 C：\\"下载"，请在 "命令" 窗口中键入以下命令，然后按 enter：
    
        cd C:\Downloads

3.  若要安装该 API，请键入以下命令，然后按 Enter：
    
        msiexec /I EwsManagedApi.msi addlocal="ExchangeWebServicesApi_Feature,ExchangeWebServicesApi_Gac"

4.  在安装该 API 后，通过键入以下命令然后按 Enter 来重置 IIS：
    
        iisreset

安装 Exchange Web 服务之后，必须在 SharePoint Server 2013 和 Exchange 2013 之间配置服务器到服务器的身份验证。 若要执行此操作，请首先打开 SharePoint 2013 命令行管理程序，然后运行以下命令集：

    New-SPTrustedSecurityTokenIssuer -Name "Exchange" -MetadataEndPoint "https://autodiscover.litwareinc.com/autodiscover/metadata/json/1"
    $service = Get-SPSecurityTokenServiceConfig
    $service.HybridStsSelectionEnabled = $True
    $service.AllowMetadataOverHttp = $False
    $service.AllowOAuthOverHttp = $False
    $service.Update()

<div>


> [!NOTE]  
> 务必要使用自动发现服务的 URI。 不要使用示例 URI https://autodiscover.litwareinc.com/autodiscover/metadata/json/1。



</div>

创建令牌颁发者并配置令牌服务后，运行这些命令，确保将 SharePoint 网站的 URL 替换为示例 URLhttp://atl-sharepoint-001:

    $exchange = Get-SPTrustedSecurityTokenIssuer "Exchange"
    $app = Get-SPAppPrincipal -Site "https://atl-sharepoint-001" -NameIdentifier $exchange.NameID
    $site = Get-SPSite  "https://atl-sharepoint-001"
    Set-SPAppPrincipalPermission -AppPrincipal $app -Site $site.RootWeb -Scope "SiteSubscription" -Right "FullControl" -EnableAppOnlyPolicy

若要为 Exchange 2013 配置服务器到服务器身份验证，请打开 Exchange 命令行管理程序并运行与此类似的命令（假设 Exchange 已安装在驱动器 C：上，并且它使用默认文件夹路径）：

    "C:\Program Files\Microsoft\Exchange Server\V15\Scripts\Configure-EnterprisePartnerApplication.ps1 -AuthMetaDataUrl 'https://atl-sharepoint-001/_layouts/15/metadata/json/1' -ApplicationType SharePoint"

配置合作伙伴应用程序后，建议您在所有 Exchange 邮箱和客户端访问服务器上停止并重新启动 Internet 信息服务（IIS）。 您可使用类似于以下命令的命令重新启动 IIS，以下命令将重新启动计算机 atl-exchange-001 上的此服务：

    iisreset atl-exchange-001

此命令可以从 Exchange 命令行管理程序或任何其他命令窗口中运行。

接下来，运行如下所示的命令，该命令将使指定用户（在此示例中，kenmyer）在 Exchange 上执行发现的权限：

    Add-RoleGroupMember "Discovery Management" -Member "kenmyer"

在 Exchange 和 SharePoint 之间建立服务器到服务器身份验证后，下一步是在 SharePoint 中创建电子数据展示网站。 可通过从 SharePoint 命令行管理程序运行类似以下命令来执行此操作：

    $template = Get-SPWebTemplate | Where-Object {$_.Title -eq "eDiscovery Center"}
    New-SPSite -Url "https://atl-sharepoint-001/sites/discovery" -OwnerAlias "kenmyer" -Template $Template -Name "Discovery Center"

<div>


> [!NOTE]  
> “eDiscovery”是“electronic discovery”（电子发现）的缩写，通常表示浏览可在法院“合理计算为可导致可靠证据”的项目的电子存档的过程。



</div>

新网站准备就绪后，下一步是将 Exchange 2013 配置为用作 SharePoint 的结果源。 可通过从 "SharePoint 2013 管理中心" 页面完成以下过程来执行此操作：

1.  在“管理中心”页上，单击“**管理服务应用程序**”，然后单击“**Search Service 应用程序**”。

2.  在“Search Service 应用程序：搜索管理”页上，单击“**结果源**”，然后单击“**新建结果源**”。

3.  在“**新建结果源**”窗格中，在“**名称**”框中输入新结果源的名称（例如，“**Microsoft Exchange**”）。 选择 " **exchange** " 作为结果源**协议**，然后在 " **exchange 源 URL** " 框中输入 EXCHANGE 服务器的 web services 源 url。 该源 URL 应类似如下：
    
    https://atl-exchange-001.litwareinc.com/ews/exchange.asmx

4.  确保未选择“**使用自动发现**”，然后单击“**确定**”。

最后，通过从 SharePoint 发现网站中完成以下过程创建新的电子数据展示事例和新的电子数据展示集（例如https://atl-sharepoint-001/sites/discovery):

1.  在“网站内容”页上，单击“**创建新的案例**”。

2.  在“网站内容：新建 SharePoint 网站”页上，在“**标题**”框中输入用户的电子邮件别名（例如，“**kenmyer**”），然后将同一 URL 添加至“**网站地址**”框中。这将产生一个类似如下的 URL：
    
    https://atl-sharepoint-001/sites/eDiscovery/kenmyer

3.  单击“**创建**”。

4.  当电子数据展示集页出现时，单击“**标识和保留：发现集**”下的“**新建项目**”。

5.  在“新建：发现集”页上的“**发现集名称**”框中输入用户的电子邮件别名。 在 "**筛选器**" 框中输入**电子数据展示 Lync\* ** ，然后单击 "**添加 & 管理源**"。

6.  在“添加和管理源”页上，在“**邮箱**”下的第一个文本框中输入用户的电子邮件别名。单击位于文本框旁边的检查邮箱图标，以确认 SharePoint 可以连接至指定邮箱。

7.  单击“**确定**”。

8.  在“电子数据展示集”页上，单击“**保存**”，以保存新的电子数据展示集。

此时，你可以搜索指定的邮箱（kenmyer）和/或启用就地保留，方式与任何其他 SharePoint 内容或结果源相同。

</div>

<span> </span>

</div>

</div>

</div>


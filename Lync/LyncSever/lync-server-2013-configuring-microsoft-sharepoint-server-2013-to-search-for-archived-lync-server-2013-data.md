---
title: 配置 Microsoft SharePoint Server 2013 以搜索存档的 Microsoft Lync Server 2013 数据
TOCTitle: 配置 Microsoft SharePoint Server 2013 以搜索存档的 Microsoft Lync Server 2013 数据
ms:assetid: 17f49365-8778-4962-a41b-f96faf6902f1
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ687978(v=OCS.15)
ms:contentKeyID: 49888315
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 配置 Microsoft SharePoint Server 2013 以搜索存档的 Microsoft Lync Server 2013 数据

 

_**上一次修改主题：** 2016-12-08_

在 Microsoft Exchange Server 2013 中而不是 Microsoft Lync Server 2013 中存储即时消息和 Web 会议脚本的一个主要优点是在同一位置存储数据使管理员可以使用单个池搜索存档的 Exchange 数据和/或存档的 Lync Server 数据。由于所有数据都存储在同一位置 (Exchange)，可以搜索存档的 Exchange 数据的任何工具还可以搜索存档的 Lync Server 数据。

便于搜索存档数据的一个工具是 Microsoft SharePoint Server 2013。如果您要使用 SharePoint 搜索 Lync Server 数据，则必须先完成在 Lync Server 中配置 Exchange 存档涉及的所有步骤。在 Exchange 2013 和 Lync Server 2013 已成功集成后，然后必须在 SharePoint 服务器上安装 Exchange Web Services Managed API 2.0 版；该 API 的安装程序可从 Microsoft 下载中心 ([http://go.microsoft.com/fwlink/?linkid=258305\&clcid=0x804](http://go.microsoft.com/fwlink/?linkid=258305%26clcid=0x804)) 下载。下载的文件 (EWSManagedAPI.msi) 可以保存到 SharePoint 服务器上的任何文件夹。

下载文件后，在 SharePoint 服务器上完成以下过程：

1.  打开命令窗口，方法是依次单击“开始”、“所有程序”、“附件”，右键单击“命令提示符”，然后单击“以管理员身份运行”。

2.  在命令窗口中，使用 **cd** 命令将当前目录更改为保存文件 EWSManagedAPI.msi 的文件夹。例如，如果已将该文件保存至 C:\\Downloads，请在命令窗口中键入以下命令，然后按 Enter：
    
        cd C:\Downloads

3.  若要安装该 API，请键入以下命令，然后按 Enter：
    
        msiexec /I EwsManagedApi.msi addlocal="ExchangeWebServicesApi_Feature,ExchangeWebServicesApi_Gac"

4.  在安装该 API 后，通过键入以下命令然后按 Enter 来重置 IIS：
    
        iisreset

在安装 Exchange Web 服务后，必须在 SharePoint Server 2013 与 Exchange 2013 之间配置服务器到服务器身份验证。为此，请先打开 SharePoint 2013 命令行管理程序并运行以下命令集：

    New-SPTrustedSecurityTokenIssuer -Name "Exchange" -MetadataEndPoint "https://autodiscover.litwareinc.com/autodiscover/metadata/json/1"
    $service = Get-SPSecurityTokenServiceConfig
    $service.HybridStsSelectionEnabled = $True
    $service.AllowMetadataOverHttp = $False
    $service.AllowOAuthOverHttp = $False
    $service.Update()

> [!NOTE]  
> 务必要使用自动发现服务的 URI。不要使用示例 URI https://autodiscover.litwareinc.com/autodiscover/metadata/json/1。



在创建令牌颁发者并配置令牌服务后，运行以下命令，确保用 SharePoint 网站的 URL 替代示例 URL http://atl-sharepoint-001：

    $exchange = Get-SPTrustedSecurityTokenIssuer "Exchange"
    $app = Get-SPAppPrincipal -Site "https://atl-sharepoint-001" -NameIdentifier $exchange.NameID
    $site = Get-SPSite  "https://atl-sharepoint-001"
    Set-SPAppPrincipalPermission -AppPrincipal $app -Site $site.RootWeb -Scope "SiteSubscription" -Right "FullControl" -EnableAppOnlyPolicy

若要为 Exchange 2013 配置服务器到服务器身份验证，请打开 Exchange 命令行管理程序并运行与此类似的命令（假定 Exchange 已安装在驱动器 C: 上并且它使用默认文件夹路径）：

    "C:\Program Files\Microsoft\Exchange Server\V15\Scripts\Configure-EnterprisePartnerApplication.ps1 -AuthMetaDataUrl 'https://atl-sharepoint-001/_layouts/15/metadata/json/1' -ApplicationType SharePoint"

在配置合作伙伴应用程序后，建议在所有 Exchange 邮箱和客户端访问服务器上停止并重新启动 Internet Information Services (IIS)。可以使用与此相似的命令重新启动 IIS，该命令将在计算机 atl-exchange-001 上重新启动该服务：

    iisreset atl-exchange-001

可在 Exchange 命令行管理程序中或从任何其他命令窗口中运行此命令。

接下来，运行类似如下的命令，该命令会向指定的用户（在此示例中为 kenmyer）授予在 Exchange 中执行发现的权限：

    Add-RoleGroupMember "Discovery Management" -Member "kenmyer"

在 Exchange 和 SharePoint 之间建立服务器到服务器身份验证后，下一步是在 SharePoint 中创建电子数据展示网站。通过从 SharePoint 命令行管理程序中运行与这些命令类似的命令可以完成此操作：

    $template = Get-SPWebTemplate | Where-Object {$_.Title -eq "eDiscovery Center"}
    New-SPSite -Url "https://atl-sharepoint-001/sites/discovery" -OwnerAlias "kenmyer" -Template $Template -Name "Discovery Center"

> [!NOTE]  
> “eDiscovery”是“electronic discovery”（电子发现）的缩写，通常表示浏览可在法院“合理计算为可导致可靠证据”的项目的电子存档的过程。



新网站准备就绪后，下一步是配置 Exchange 2013，以用作 SharePoint 的结果源。通过在 SharePoint 2013 管理中心页中完成以下过程可执行此操作：

1.  在“管理中心”页上，单击“管理服务应用程序”，然后单击“Search Service 应用程序”。

2.  在“Search Service 应用程序: 搜索管理”页上，单击“结果源”，然后单击“新建结果源”。

3.  在“新建结果源”窗格中，在“名称”框中输入新结果源的名称（例如，“Microsoft Exchange”）。选择“Exchange”作为结果源“协议”，然后在“Exchange 源 URL”框中输入 Exchange 服务器的 Web 服务源 URL。该源 URL 应类似如下：
    
    https://atl-exchange-001.litwareinc.com/ews/exchange.asmx

4.  确保未选择“使用自动发现”，然后单击“确定”。

最后，通过从 SharePoint 发现网站（例如，https://atl-sharepoint-001/sites/discovery）中完成以下过程来创建新的电子数据展示案例和新的电子数据展示集：

1.  在“网站内容”页上，单击“创建新的案例”。

2.  在“网站内容: 新建 SharePoint 网站”页上，在“标题”框中输入用户的电子邮件别名（例如，“kenmyer”），然后将同一 URL 添加至“网站地址”框中。这将产生一个类似如下的 URL：
    
    https://atl-sharepoint-001/sites/eDiscovery/kenmyer

3.  单击“创建”。

4.  当电子数据展示集页出现时，单击“标识和保留: 发现集”下的“新建项目”。

5.  在“新建: 发现集”页上的“发现集名称”框中输入用户的电子邮件别名。在“筛选器”框中输入“eDiscovery Lync\*”，然后单击“添加和管理源”。

6.  在“添加和管理源”页上，在“邮箱”下的第一个文本框中输入用户的电子邮件别名。单击位于文本框旁边的检查邮箱图标，以确认 SharePoint 可以连接至指定邮箱。

7.  单击“确定”。

8.  在“电子数据展示集”页上，单击“保存”，以保存新的电子数据展示集。

此时，您可以采用与任何其他 SharePoint 内容或结果源相同的方式搜索指定邮箱 (kenmyer) 和/或启用就地保留。


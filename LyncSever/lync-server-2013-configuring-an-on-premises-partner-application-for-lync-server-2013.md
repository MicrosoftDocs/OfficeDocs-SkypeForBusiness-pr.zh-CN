---
title: 配置 Microsoft Lync Server 2013 的内部合作伙伴应用程序
TOCTitle: 配置 Microsoft Lync Server 2013 的内部合作伙伴应用程序
ms:assetid: 696f2b26-e5d0-42b5-9785-a26c2ce25bb7
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ204975(v=OCS.15)
ms:contentKeyID: 49313120
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 配置 Microsoft Lync Server 2013 的内部合作伙伴应用程序

 

_**上一次修改主题：** 2013-02-04_

在分配 OAuthTokenIssuer 证书后，您必须配置 Microsoft Lync Server 2013 合作伙伴应用程序。（这是一个对 Microsoft Exchange Server 2013 和 Microsoft SharePoint 进行配置使其用作合作伙伴应用程序的过程，即将讨论此过程。）若要配置本地合作伙伴应用程序，必须先复制以下 Windows PowerShell 脚本并将代码粘贴到记事本（或任何其他文本编辑器）中：

    if ((Get-CsPartnerApplication -ErrorAction SilentlyContinue) -ne $Null)
       {
           Remove-CsPartnerApplication app
       }
    
    $exch = Get-CsPartnerApplication microsoft.exchange -ErrorAction SilentlyContinue
            
    if ($exch -eq $null)
       {
          New-CsPartnerApplication -Identity microsoft.exchange -MetadataUrl https://atl-exchange-001.litwareinc.com/autodiscover/metadata/json/1 -ApplicationTrustLevel Full 
        }
    else
        {
           if ($exch.ApplicationIdentifier -ne "00000002-0000-0ff1-ce00-000000000000")
              {
                 Remove-CsPartnerApplication microsoft.exchange
    New-CsPartnerApplication -Identity microsoft.exchange -MetadataUrl https://atl-exchange-001.litwareinc.com/autodiscover/metadata/json/1 -ApplicationTrustLevel Full 
               }
            else
               {
                 Set-CsPartnerApplication -Identity microsoft.exchange -ApplicationTrustLevel Full 
               }
         }
    
    $shp = Get-CsPartnerApplication microsoft.sharepoint -ErrorAction SilentlyContinue
            
    if ($shp -eq $null)
       {
          New-CsPartnerApplication -Identity microsoft.sharepoint -MetadataUrl http://atl-sharepoint-001.litwareinc.com/jsonmetadata.ashx -ApplicationTrustLevel Full 
        }
    else
        {
           if ($shp.ApplicationIdentifier -ne "00000003-0000-0ff1-ce00-000000000000")
              {
                 Remove-CsPartnerApplication microsoft.sharepoint
      
                 New-CsPartnerApplication -Identity microsoft.sharepoint -MetadataUrl http://atl-sharepoint-001.litwareinc.com/jsonmetadata.ashx -ApplicationTrustLevel Full 
               }
            else
               {
                 Set-CsPartnerApplication -Identity microsoft.sharepoint -ApplicationTrustLevel Full 
                }
       }
    
    Set-CsOAuthConfiguration -ServiceName 00000004-0000-0ff1-ce00-000000000000

复制代码后，使用文件扩展名 .PS1（例如，C:\\Scripts\\ServerToServerAuth.ps1）保存脚本。请注意，在运行此脚本之前，您必须将元数据 URL https://atl-exchange-001.litwareinc.com/autodiscover/metadata/json/1 和 http://atl-sharepoint-001.litwareinc.com/jsonmetadata.ashx 分别替换为 Exchange 2013 和 SharePoint Server 所使用的元数据 URL。有关如何标识单个产品的元数据 URL 的信息，请参阅 Exchange 2013 和 SharePoint 的产品文档。

如果查看脚本的最后一行，您将发现 Set-CsOAuthConfiguration cmdlet 是使用以下语法调用的：

    Set-CsOAuthConfiguration -ServiceName 00000004-0000-0ff1-ce00-000000000000

由于调用 Set-CsOAuthConfiguration 时未使用 Realm 参数，因此会将领域自动设置为您组织的完全限定域名 (FQDN)（例如，litwareinc.com）。如果领域名称与组织名称不同，则应包括领域名称，如下所示：

    Set-CsOAuthConfiguration -ServiceName 00000004-0000-0ff1-ce00-000000000000 -Realm "contoso.com"

在进行更改后，可以通过从 Lync Server 2013 命令行管理程序中运行脚本文件来执行脚本并将 Exchange 2013 和 SharePoint 配置为合作伙伴应用程序。例如：

    C:\Scripts\ServerToServerAuth.ps1

请注意，即使未安装 Exchange 2013 和 SharePoint Server，也可以运行此脚本；假定您将 SharePoint Server 配置为合作伙伴应用程序，即使未安装 SharePoint Server，也不会出现问题）。

运行此脚本时，您可能会收到与以下内容类似的错误消息：

    New-CsPartnerApplication : Cannot bind parameter 'MetadataUrl' to the target. Exception setting "MetadataUrl": "The metadata document could not be downloaded from the URL in the MetadataUrl parameter or downloaded data is not a valid metadata document."

此错误消息通常指示以下两种情况之一：1) 在脚本中指定的某个 URL 无效（即，某个元数据 URL 不是实际的元数据 URL）；2) 无法联系某个元数据 URL。如果出现此情况，请验证 URL 是否正确且可访问，然后重新运行此脚本。

在为 Lync Server 2013 创建合作伙伴应用程序后，您必须将 Lync Server 配置为 Exchange 2013 的合作伙伴应用程序。可通过运行脚本 Configure-EnterprisePartnerApplication.1 为 Exchange 2013 配置合作伙伴应用程序；您只需指定 Lync Server 的元数据 URL 并指示 Lync Server 是新的合作伙伴应用程序。

若要将 Lync Server 配置为 Exchange 的合作伙伴应用程序，请打开 Exchange 命令行管理程序并运行与以下内容类似的命令

    "c:\Program Files\Microsoft\Exchange Server\V15\Scripts\Configure-EnterprisePartnerApplication.ps1" -AuthMetadataUrl "https://lync.contoso.com/metadata/json/1" -ApplicationType "Lync"


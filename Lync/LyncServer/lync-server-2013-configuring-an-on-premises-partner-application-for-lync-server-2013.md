---
title: 为 Lync Server 2013 配置本地合作伙伴应用程序
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring an on-premises partner application for Lync Server 2013
ms:assetid: 696f2b26-e5d0-42b5-9785-a26c2ce25bb7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204975(v=OCS.15)
ms:contentKeyID: 48184412
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 34b6cd21d781f26ca734effd0c574c016aec3266
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48517579"
---
# <a name="configuring-an-on-premises-partner-application-for-microsoft-lync-server-2013"></a>为 Microsoft Lync Server 2013 配置本地合作伙伴应用程序

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2013-02-04_

分配 OAuthTokenIssuer 证书后，您必须配置您的 Microsoft Lync Server 2013 合作伙伴应用程序。  (要讨论的过程将配置 Microsoft Exchange Server 2013 和 Microsoft SharePoint 以充当合作伙伴应用程序。 ) 若要配置本地合作伙伴应用程序，您必须先复制以下 Windows PowerShell 脚本，然后将代码粘贴到记事本 (或任何其他文本编辑器中) ：

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

复制代码后，使用将脚本保存。PS1 文件扩展名 (例如，C： \\ Scripts \\ServerToServerAuth.ps1) 。 请注意，在运行此脚本之前，必须分别将元数据 Url 替换为 https://atl-exchange-001.litwareinc.com/autodiscover/metadata/json/1 http://atl-sharepoint-001.litwareinc.com/jsonmetadata.ashx Exchange 2013 和 SharePoint 服务器使用的元数据 url。 有关如何识别相应产品的元数据 URL 的信息，请参阅 Exchange 2013 和 SharePoint 的产品文档。

如果查看脚本的最后一行，您将发现 Set-CsOAuthConfiguration cmdlet 是使用以下语法调用的：

    Set-CsOAuthConfiguration -ServiceName 00000004-0000-0ff1-ce00-000000000000

由于调用 Set-CsOAuthConfiguration 时未使用 Realm 参数，因此会将领域自动设置为您组织的完全限定域名 (FQDN)（例如，litwareinc.com）。如果领域名称与组织名称不同，则应包括领域名称，如下所示：

    Set-CsOAuthConfiguration -ServiceName 00000004-0000-0ff1-ce00-000000000000 -Realm "contoso.com"

在进行这些更改之后，可以通过在 Lync Server 2013 命令行管理程序中运行脚本文件，来执行脚本，并将 Exchange 2013 和 SharePoint 配置为合作伙伴应用程序。 例如：

    C:\Scripts\ServerToServerAuth.ps1

请注意，即使您未安装 Exchange 2013 和 SharePoint Server，也可以运行此脚本：如果您不安装 SharePoint Server，则不会出现任何问题（例如，将 SharePoint Server 配置为合作伙伴应用程序）。

运行此脚本时，您可能会收到与以下内容类似的错误消息：

    New-CsPartnerApplication : Cannot bind parameter 'MetadataUrl' to the target. Exception setting "MetadataUrl": "The metadata document could not be downloaded from the URL in the MetadataUrl parameter or downloaded data is not a valid metadata document."

此错误消息通常指示以下两种情况之一：1) 在脚本中指定的某个 URL 无效（即，某个元数据 URL 不是实际的元数据 URL）；2) 无法联系某个元数据 URL。如果出现此情况，请验证 URL 是否正确且可访问，然后重新运行此脚本。

为 Lync Server 2013 创建合作伙伴应用程序后，必须将 Lync Server 配置为 Exchange 2013 的合作伙伴应用程序。 您可以通过运行脚本 Configure-EnterprisePartnerApplication.ps1 来配置 Exchange 2013 的合作伙伴应用程序。您只需指定 Lync Server 的元数据 URL，并指示 Lync Server 是新的合作伙伴应用程序。

若要将 Lync Server 配置为 Exchange 的合作伙伴应用程序，请打开 Exchange 命令行管理程序并运行与以下内容类似的命令

    "c:\Program Files\Microsoft\Exchange Server\V15\Scripts\Configure-EnterprisePartnerApplication.ps1" -AuthMetadataUrl "https://lync.contoso.com/metadata/json/1" -ApplicationType "Lync"

</div>

<span> </span>

</div>

</div>

</div>


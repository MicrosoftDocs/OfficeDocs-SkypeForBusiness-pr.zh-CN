---
title: 将混合应用程序终结点迁移到云
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: bjwhalen
audience: ITPro
f1.keywords:
- NOCSH
ms.topic: article
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.collection:
- Hybrid
- M365-voice
- M365-collaboration
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
description: 在停用本地环境之前迁移Skype for Business应用程序终结点。
ms.openlocfilehash: 2968cdb5ecec3bffb22fffaf43c77e97ab8004d1
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/26/2021
ms.locfileid: "58583416"
---
# <a name="migrate-hybrid-application-endpoints-before-decommissioning-your-on-premises-environment"></a>在停用本地环境之前迁移混合应用程序终结点

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

本文介绍如何在停用本地部署环境之前，将所需的混合应用程序终结点Skype for Business Microsoft 云。 这是停止使用本地环境的以下步骤的第 3 步：

- 步骤 1. [将所有所需的用户从本地移动到联机](decommission-move-on-prem-users.md)

- 步骤 2. [禁用混合配置](cloud-consolidation-disabling-hybrid.md)。

- **步骤 3.将混合应用程序终结点从本地迁移到联机。**  (本文) 

- 步骤 4. [删除本地部署Skype for Business部署](decommission-remove-on-prem.md)。


## <a name="migrate-all-required-hybrid-application-endpoints-from-on-premises-to-online"></a>将所有必需的混合应用程序终结点从本地迁移到联机

在可以将这些终结点移动到联机状态之前，必须确保已更新 DNS 记录Microsoft 365终结点使用的所有 sip 域的 DNS 记录。 请注意，一旦将 DNS 更新为指向Microsoft 365，在您完成此步骤之前，任何现有的混合应用程序终结点将无法再被发现。 由于此步骤 (创建联机资源帐户) 如果 DNS 记录指向本地，则不应在同一维护窗口中执行步骤 2 和步骤 3。 有关详细信息，请参阅 [禁用混合配置](cloud-consolidation-disabling-hybrid.md)。

1. 通过执行以下 PowerShell 命令本地混合应用程序终结点设置来检索Skype for Business Server导出这些设置：

   ```PowerShell
   Get-CsHybridApplicationEndpoint|select Sipaddress, DisplayName, ApplicationID, LineUri |Export-Csv -Path "c:\backup\HybridEndpoints.csv"
   ```
2. 在"[管理中心](/microsoftteams/manage-resource-accounts)"Microsoft 365并许可新的资源帐户，以替换现有的本地混合应用程序终结点。

3. 将新的资源帐户与现有的混合应用程序终结点关联。

4. 通过执行以下本地部署和 PowerShell 命令删除在本地混合应用程序终结点Skype for Business Server电话号码：

   ```PowerShell
   Get-CsHybridApplicationEndpoint -Filter {LineURI -ne $null} | Set-CsHybridApplicationEndpoint -LineURI ""
   ```
5. 由于这些帐户的电话号码有可能在 Microsoft 365 而非本地管理，因此在 PowerShell 中Teams命令：

   ```PowerShell
   $endpoints = import-csv "c:\backup\HybridEndpoints.csv"
   foreach ($endpoint in $endpoints)
   {
   if($endpoint.LineUri)
       {
           $upn = $endpoint.SipAddress.Replace("sip:","")
           $ra=Get-CsOnlineApplicationInstance | where UserPrincipalName -eq $upn 
           Set-CsOnlineApplicationInstance -Identity $ra.Objectid -OnpremPhoneNumber ""
       }
   }
   ```

6. 将电话号码分配给在步骤 2 中创建的新资源帐户。 若要详细了解如何将电话号码分配给资源帐户，请参阅以下文章： [分配服务号码](/microsoftteams/manage-resource-accounts)。

7. 通过执行 PowerShell 命令Skype for Business Server本地终结点：

   ```PowerShell
   Get-CsHybridApplicationEndpoint | Remove-CsHybridApplicationEndpoint
   ```
现在，你已准备好[删除本地部署Skype for Business部署](decommission-remove-on-prem.md)。

## <a name="see-also"></a>另请参阅

- [停用本地 Skype for Business 环境](decommission-on-prem-overview.md)

- [将所有所需的用户从本地移动到联机](decommission-move-on-prem-users.md)

- [禁用混合配置](cloud-consolidation-disabling-hybrid.md)

- [删除本地 Skype for Business 环境](decommission-remove-on-prem.md)





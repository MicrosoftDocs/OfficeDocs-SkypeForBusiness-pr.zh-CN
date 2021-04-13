---
title: 将混合应用程序终结点移动到云
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: bjwhalen
audience: ITPro
f1.keywords:
- NOCSH
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Hybrid
- M365-voice
- M365-collaboration
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
description: 在停用 Skype for Business 本地环境之前移动 hyrid 应用程序终结点。
ms.openlocfilehash: af8b521eaaf4a1e86027936f3d4d3600ab4bfa7b
ms.sourcegitcommit: 71d90f0a0056f7604109f64e9722c80cf0eda47d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2021
ms.locfileid: "51656874"
---
# <a name="move-hyrid-application-endpoints-before-decommissioning-your-on-premises-environment"></a>在停用本地环境之前移动 hyrid 应用程序终结点

本文介绍如何在停用本地 Skype for Business 环境之前，将所需的混合应用程序终结点移动到 Microsoft 云。 这是停止使用本地环境的以下步骤的第 3 步：

- 步骤 1. [将所有所需的用户从本地移动到联机](decommission-move-on-prem-users.md)

- 步骤 2. [禁用混合配置](cloud-consolidation-disabling-hybrid.md)。

- **步骤 3.将混合应用程序终结点从本地移动到联机。**  (本文) 

- 步骤 4. [删除本地 Skype for Business 部署](decommission-remove-on-prem.md)。


## <a name="move-all-required-hybrid-application-endpoints-from-on-premises-to-online"></a>将所有必需的混合应用程序终结点从本地移动到联机

在可以将这些终结点移动到联机状态之前，必须确保已针对终结点使用的所有 sip 域将 DNS 记录更新为指向 Microsoft 365。 如果 DNS 记录指向本地，则不能创建联机资源帐户。 有关详细信息，请参阅 [禁用混合配置](cloud-consolidation-disabling-hybrid.md)。

1. 通过执行以下本地 Skype for Business Server PowerShell 命令检索和导出本地混合应用程序终结点设置：

   ```PowerShell
   Get-CsHybridApplicationEndpoint|select Sipaddress, DisplayName, ApplicationID, LineUri |Export-Csv -Path "c:\backup\HybridEndpoints.csv"
   ```
2. 在 Microsoft [](https://docs.microsoft.com/microsoftteams/manage-resource-accounts) 365 中新建资源帐户并授予许可，以替换现有的本地混合应用程序终结点。

3. 将新的资源帐户与现有的混合应用程序终结点关联。

4. 通过执行以下本地 Skype for Business Server PowerShell 命令删除在本地混合应用程序终结点中定义的电话号码：

   ```PowerShell
   Get-CsHybridApplicationEndpoint -Filter {LineURI -ne $null} | Set-CsHybridApplicationEndpoint -LineURI ""
   ```
5. 由于这些帐户的电话号码有可能在 Microsoft 365 而非本地管理，因此在 Skype for Business Online PowerShell 中运行以下命令：

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

6. 将电话号码分配给在步骤 2 中创建的新资源帐户。 若要详细了解如何将电话号码分配给资源帐户，请参阅以下文章： [分配服务号码](https://docs.microsoft.com/microsoftteams/manage-resource-accounts#assign-a-service-number)。

7. 通过执行以下本地 Skype for Business Server PowerShell 命令删除本地终结点：

   ```PowerShell
   Get-CsHybridApplicationEndpoint | Remove-CsHybridApplicationEndpoint
   ```
现在，你已准备好 [删除本地 Skype for Business 部署](decommission-remove-on-prem.md)。

## <a name="see-also"></a>另请参阅

- [停用本地 Skype for Business 环境](decommission-on-prem-overview.md)

- [将所有所需的用户从本地移动到联机](decommission-move-on-prem-users.md)

- [禁用混合配置](cloud-consolidation-disabling-hybrid.md)

- [删除本地 Skype for Business 环境](decommission-remove-on-prem.md)





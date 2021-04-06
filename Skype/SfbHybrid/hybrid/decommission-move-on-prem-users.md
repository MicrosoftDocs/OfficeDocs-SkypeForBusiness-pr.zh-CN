---
title: 将用户和终结点移动到云
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
description: 在停用 Skype for Business 本地环境之前移动用户和终结点。
ms.openlocfilehash: 130f276d07dd33be33d3c038c2ead20c7a887e6b
ms.sourcegitcommit: f223b5f3735f165d46bb611a52fcdfb0f4b88f66
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/06/2021
ms.locfileid: "51593879"
---
# <a name="move-required-users-and-endpoints-before-decommissioning-your-on-premises-environment"></a>在停用本地环境之前移动所需的用户和终结点

本文介绍如何在停用本地 Skype for Business 环境之前，将所需的用户和应用程序终结点移动到 Microsoft 云。 这是停止使用本地环境的以下步骤的第 1 步：

- **步骤 1.将所有必需的用户和应用程序终结点从本地移动到联机。**  (本文.) 

- 步骤 2. [禁用混合配置](cloud-consolidation-disabling-hybrid.md)。

- 步骤 3. [删除本地 Skype for Business 部署](decommission-remove-on-prem.md)。


## <a name="move-all-required-users-from-on-premises-to-the-cloud"></a>将所有所需的用户从本地移动到云

完成迁移后将继续使用的任何用户必须先从本地迁移到云。 使用本地管理工具移动用户。 有关详细信息，请参阅在内部 [部署和云之间移动用户](move-users-between-on-premises-and-cloud.md)。

尽管拥有本地 Skype for Business Server 帐户的用户可以使用 Teams，但是这些用户没有 Teams 的全部功能。 这些用户无法与仍在使用 Skype for Business (用户进行互操作或联合，无论是联机还是本地) 。 这些用户也无法在 Teams 客户端中接收 PSTN 呼叫。 因此，必须将这些用户移至联机。 此步骤还可确保在 Skype for Business Server 中创建的任何联系人或会议都迁移到 Teams。

若要检查本地部署中是否有剩余用户，请在 Skype for Business Server PowerShell 窗口中运行以下 cmdlet。

```PowerShell
Get-CsUser -Filter { HostingProvider -eq "SRV:"}
```

如果返回了任何用户，请查看输出以确定是否必须将任何帐户移动到云，对于此类用户，请按照此处 [的步骤操作](move-users-between-on-premises-and-cloud.md)。 对于不再需要的用户帐户，请运行以下 Skype for Business Server PowerShell cmdlet：

```PowerShell
Get-CsUser -Filter { HostingProvider -eq "SRV:"} | Disable-CsUser
```

> [!NOTE]
> 运行Disable-CsUser将删除满足筛选条件的所有用户的所有 Skype for Business 属性。 在继续之前，请确认今后不再需要这些帐户。

## <a name="move-on-premises-hybrid-application-endpoints-to-microsoft-365"></a>将本地混合应用程序终结点移动到 Microsoft 365

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
现在，你已准备好 [禁用混合配置](cloud-consolidation-disabling-hybrid.md)。

## <a name="see-also"></a>另请参阅

- [停用本地 Skype for Business 环境](decommission-on-prem-overview.md)

- [禁用混合配置](cloud-consolidation-disabling-hybrid.md)

- [删除本地 Skype for Business 部署](decommission-remove-on-prem.md)





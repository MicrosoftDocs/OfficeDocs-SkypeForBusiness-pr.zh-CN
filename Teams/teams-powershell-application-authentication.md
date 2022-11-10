---
title: Teams PowerShell 模块中基于应用程序的身份验证
author: pbafna03
ms.author: pbafna
ms.reviewer: pbafna
manager: sshastri
ms.topic: conceptual
audience: admin
ms.service: msteams
ms.collection:
- M365-collaboration
description: 了解 Teams PowerShell 模块中基于应用程序的身份验证，该模块用于管理 Microsoft Teams。
appliesto:
- Microsoft Teams
ms.openlocfilehash: 89af4494a6cf20aab512c0430a6e16db622e53a2
ms.sourcegitcommit: 22f66e314e631b3c9262c5c7dc5664472f42971e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/10/2022
ms.locfileid: "68912641"
---
# <a name="application-based-authentication-in-teams-powershell-module"></a>Teams PowerShell 模块中基于应用程序的身份验证

Teams PowerShell 模块（预览版 4.7.1-preview 或更高版本）现在支持基于应用程序的身份验证。 目前，此身份验证模式仅在商业环境中受支持。


## <a name="cmdlets-supported"></a>支持的 Cmdlet

现在支持所有 cmdlet，下面提到的 cmdlet 除外。 

  - New-Team
  - [Get|设置|新增|Sync]-CsOnlineApplicationInstance
  - \*-CsUserCallingSettings
  - \*-CsUserCallingDelegate
  - \*PolicyPackage\*
  - \*-CsTeamsShiftsConnection\*
  - \*-CsBatchTeamsDeployment\*


## <a name="examples"></a>示例

以下示例演示如何将 Teams PowerShell 模块与基于 Azure AD 应用的身份验证配合使用： 

- 使用证书指纹进行连接：

  ```powershell
  Connect-MicrosoftTeams -CertificateThumbprint "XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX" -ApplicationId "00000000-0000-0000-0000-000000000000" -TenantId "YYYYYYYY-YYYY-YYYY-YYYY-YYYYYYYYYYYY"
  ```
  使用 CertificateThumbprint 参数时，需要在运行命令的计算机上安装证书。 证书应安装在用户证书存储中。
  
- 使用访问令牌进行连接：
  
  可以通过 login.microsoftonline.com 终结点检索访问令牌。 它需要两个访问令牌 -“MS Graph”和“Skype 和 Teams 租户管理员 API”资源。

  ```powershell
  $ClientSecret   = "…"
  $ApplicationID = "00000000-0000-0000-0000-000000000000"
  $TenantID = "YYYYYYYY-YYYY-YYYY-YYYY-YYYYYYYYYYYY"

  $graphtokenBody = @{   
     Grant_Type    = "client_credentials"   
     Scope         = "https://graph.microsoft.com/.default"   
     Client_Id     = $ApplicationID   
     Client_Secret = $ClientSecret   
  }  

  $graphToken = Invoke-RestMethod -Uri "https://login.microsoftonline.com/$TenantID/oauth2/v2.0/token" -Method POST -Body $graphtokenBody | Select-Object -ExpandProperty Access_Token 

  $teamstokenBody = @{   
     Grant_Type    = "client_credentials"   
     Scope         = "48ac35b8-9aa8-4d74-927d-1f4a14a0b239/.default"   
     Client_Id     = $ApplicationID   
     Client_Secret = $ClientSecret 
  } 

  $teamsToken = Invoke-RestMethod -Uri "https://login.microsoftonline.com/$TenantID/oauth2/v2.0/token" -Method POST -Body $teamstokenBody | Select-Object -ExpandProperty Access_Token 

  Connect-MicrosoftTeams -AccessTokens @("$graphToken", "$teamsToken")
  ```
  
## <a name="how-does-it-work"></a>它是如何工作的？

Teams PowerShell 模块使用应用程序 ID、租户 ID 和证书指纹提取基于应用的令牌。 在 Azure AD 中预配的应用程序对象具有分配给它的目录角色，该角色在访问令牌中返回。 会话的基于角色的访问控制 (RBAC) 是使用令牌中提供的目录角色信息配置的。


## <a name="setup-application-based-authentication"></a>设置基于应用程序的身份验证

使用应用程序对象进行身份验证需要初始载入。 应用程序和服务主体可互换使用，但应用程序类似于类对象，而服务主体类似于 类的实例。 有关这些对象的详细信息，请参阅 [Azure Active Directory 中的应用程序和服务主体对象](/azure/active-directory/develop/app-objects-and-service-principals)。

下面介绍了在 Azure Ad 中创建应用程序的示例步骤，有关详细步骤，请参阅 [本文](/azure/active-directory/develop/howto-create-service-principal-portal)。

1. 在 Azure AD 中注册应用程序
2. 向应用程序分配 API 权限
   - 对于 \*-Cs cmdlet - 不需要 API 权限。
   - 对于非 \*-Cs cmdlet - 所需的 Microsoft 图形 API权限为 `User.Read.All`、、`Group.ReadWrite.All`、`AppCatalog.ReadWrite.All`、`TeamSettings.ReadWrite.All``Channel.Delete.All`、`ChannelSettings.ReadWrite.All`、 `ChannelMember.ReadWrite.All`。  
3. 生成自签名证书
4. 将证书附加到 Azure AD 应用程序
5. 将 [Azure AD 角色](/microsoftteams/using-admin-roles#teams-roles-and-capabilities) 分配给应用程序

应用程序需要分配适当的 RBAC 角色。 由于应用是在 Azure AD 中预配的，因此可以使用任何受支持的内置角色。
 

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
ms.openlocfilehash: ea836225658292c312490704305261210ba0991c
ms.sourcegitcommit: 44d9f15f7f7c00b3651a11ff1e8b37dda1716a52
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/15/2022
ms.locfileid: "67732777"
---
# <a name="application-based-authentication-in-teams-powershell-module"></a>Teams PowerShell 模块中基于应用程序的身份验证

Teams PowerShell 模块现在支持基于应用程序的身份验证，用于预览版 4.7.1 预览版或更高版本的有限 cmdlet 集。 目前，这种身份验证模式仅在商业环境中受支持。 对于以前在 Skype for Business Online 中为区域托管会议启用或已启用的客户，不支持此功能。


## <a name="cmdlets-supported"></a>支持 Cmdlet

支持所有非 \*Cs cmdlet (，例如 Get-Team) 、Get-CsTenant Get-CsOnlineUser & Get-CsOnlineVoiceUser。 其他 cmdlet 将逐步推出。 


## <a name="examples"></a>示例

以下示例演示如何将 Teams PowerShell 模块与基于 Azure AD 应用的身份验证配合使用： 

- 使用证书指纹进行连接：

  ```powershell
  Connect-MicrosoftTeams -CertificateThumbprint "XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX" -ApplicationId "00000000-0000-0000-0000-000000000000" -TenantId "YYYYYYYY-YYYY-YYYY-YYYY-YYYYYYYYYYYY"
  ```
  使用 CertificateThumbprint 参数时，需要在运行该命令的计算机上安装证书。 证书应安装在用户证书存储中。
  
- 使用访问令牌进行连接：
  
  可以通过 login.microsoftonline.com 终结点检索访问令牌。 它需要两个访问令牌 - “MS Graph”和“Skype 和 Teams 租户管理员 API”资源。

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
  
## <a name="how-does-it-work"></a>它的工作原理是什么？

Teams PowerShell 模块使用应用程序 ID、租户 ID 和证书指纹提取基于应用的令牌。 在 Azure AD 中预配的应用程序对象具有分配给它的目录角色，该角色在访问令牌中返回。 会话的基于角色的访问控制 (RBAC) 使用令牌中可用的目录角色信息进行配置。


## <a name="setup-application-based-authentication"></a>设置基于应用程序的身份验证

使用应用程序对象进行身份验证需要初始载入。 应用程序和服务主体可互换使用，但应用程序类似于类对象，而服务主体类似于类的实例。 可以在 [Azure Active Directory 中的应用程序和服务主体对象中了解有关这些对象的详细信息](/azure/active-directory/develop/app-objects-and-service-principals)。

下面提到了在 Azure Ad 中创建应用程序的高级步骤，有关详细步骤，请参阅 [本文](/azure/active-directory/develop/howto-create-service-principal-portal)。
  1. 在 Azure AD 中注册应用程序
  2. 生成自签名证书
  3. 将证书附加到 Azure AD 应用程序
  4. 将 Azure AD 角色分配到应用程序

应用程序需要分配适当的 RBAC 角色。 由于应用是在 Azure AD 中预配的，因此可以使用任何受支持的内置角色。
 

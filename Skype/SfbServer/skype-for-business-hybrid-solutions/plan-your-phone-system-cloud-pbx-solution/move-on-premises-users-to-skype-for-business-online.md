---
title: 为业务 Online 将内部部署用户移至 Skype
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 1/27/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Ent_O365_Hybrid
- IT_Skype16
- IT_Skype4B_Hybrid
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 2475674a-f592-4fa8-ae99-f71cbea54dc0
description: 摘要： 有关移动信息内部部署用户移动到 Skype 业务 online。
ms.openlocfilehash: 1cb57e777b9353b1abb5b211563f5b6adc58e72c
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2018
ms.locfileid: "23882066"
---
# <a name="move-on-premises-users-to-skype-for-business-online"></a>为业务 Online 将内部部署用户移至 Skype
 
**摘要：** 有关业务 online 将内部部署用户移动到 Skype 的信息。
  
> [!CAUTION]
> 在迁移到 Skype for Business Online 之前，必须更新 Lync Phone Edition 设备以符合最低的必要固件要求。 如果在更新固件之前将用户从本地环境迁移到联机环境，用户将无法使用其电话进行连接。 要更正此问题，必须将用户移回到本地环境以将其电话固件更新为最低要求的固件。 请勿在将用户移回到本地环境之前尝试更新到最低要求的固件或对电话执行硬重置。
如果在设备未安装最低要求的固件时执行了硬重置，设备将默认为使用 PIN 身份验证，而 Skype for Business Online 不支持这种验证方式。 有关详细信息，请参阅[获取业务 online Skype 的电话](https://support.office.com/en-us/article/Getting-phones-for-Skype-for-Business-Online-91f2d947-45fc-4fab-bd8b-2e313531c477?ui=en-US&amp;rs=en-US&amp;ad=US)。
  
这是您的业务 online 将内部部署用户移动到 Skype 时才是必需的可选步骤。 为业务 Online 将用户移至 Skype 之前，检查 Business Online Connector （Windows PowerShell 模块） 的 Skype 部署在前端服务器上。 如果不是这样，您可以从[下载中心](https://www.microsoft.com/en-us/download/details.aspx?id=39366)下载。 此外，要准备 AD，您需要配置 Azure AD Connect。 所使用的 AAD Connect 版本必须是版本 1.0.9125.0 或更高版本。 如果您使用较早版本的 AAD Connect 工具或 DirSync，请升级到支持的版本。 您可以升级您的当前安装并维护您在环境中定义的任何自定义规则。
  
将使用任一 Skype 业务 Server Control Panel 或 Skype for Business Server 命令行管理程序在本地部署中的用户移动，但您必须为 Office 365 部署具有管理员凭据。
  
## <a name="moving-users-by-using-skype-for-business-control-panel"></a>使用 Skype 业务控制面板移动用户

### <a name="to-move-a-user-to-skype-for-business-online"></a>若要将用户移至 Skype，业务 online

1. 使用分配给 CsUserAdministrator 角色或 CsAdministrator 角色的用户帐户，登录到您的企业服务器，或在已 Skype 的内部部署中的任何计算机的业务服务器管理工具安装的最低 Skype。
    
2. 从开始菜单或桌面快捷方式中，打开 Skype 业务 Server Control Panel。
    
    如果配置了一个使用管理 URL，也可以访问 Skype 的业务 Server Control Panel。
    
3. 在左导航栏中，单击“**用户**”。
    
4. 在“搜索用户”**** 框中，键入要启用的用户帐户的显示名称、名字、姓氏、安全帐户管理器 (SAM) 帐户名、SIP 地址或线路统一资源标识符 (URI) 的全部或第一部分，然后单击“查找”****。
    
5. 单击用户，然后在“**操作**”菜单中单击“**将所选用户移动到 Skype for Business Online**”。
    
6. 在“**将用户移动到 Skype For Business Online**”页面上，阅读信息，然后单击“**下一步**”。
    
7. 在下一页上，如果您不尚未登录到 Office 365，单击**登录到 Office 365**，提供凭据，然后单击**确定**和**下一步**。
    
8. 确认要移动的用户数是否正确，然后单击“**下一步**”。
    
9. 在下一页上，查看结果，然后单击“**关闭**”。
    
## <a name="moving-users-by-using-skype-for-business-server-management-shell"></a>使用 Skype 业务 Server 命令行管理程序移动用户

若要将内部部署用户移动到您的业务 Online 租户的 Skype 中 Skype, 的业务 Server Management Shell，使用 Microsoft Office 365 租户管理员凭据运行以下 cmdlet。 使用要移动的用户的信息替换“username@contoso.com”。
  
```
$creds=Get-Credential
```

```
Move-CsUser -Identity username@contoso.com -Target sipfed.online.lync.com -Credential $creds -HostedMigrationOverrideUrl <URL>
```

指定的**HostedMigrationOverrideUrl**参数必须为托管迁移服务正在运行，采用以下格式的池的 URL 的 url 格式： _Https://\<池 FQDN\>/HostedMigration/hostedmigrationService.svc_。
  
通过查看业务 Online 管理中心的 Office 365 租户帐户的 Skype 的 URL，您可以确定承载迁移服务的 URL。
  
> [!NOTE]
> URL 区分大小写。 
  
### <a name="to-determine-the-hosted-migration-service-url-for-your-office-365-tenant"></a>确定 Office 365 租户的托管迁移服务 URL

1. 以管理员身份登录到 Office 365 租户。
    
2. 打开“Skype for Business 管理中心”****。
    
3. 显示“Skype for Business 管理中心”**** 后，选中并复制地址栏中一直到 **lync.com** 的 URL。示例 URL 如下所示：
    
     `https://webdir0a.online.lync.com/lscp/?language=en-US&amp;tenantID=`
    
4. 将 URL 中的 **webdir** 替换为 **admin**，得到以下 URL： 
    
     `https://admin0a.online.lync.com`
    
5. 向 URL 附加以下字符串：**/HostedMigration/hostedmigrationService.svc**。
    
    结果的 URL，即**HostedMigrationOverrideUrl**的值应如下所示：
    
     `https://admin0a.online.lync.com/HostedMigration/hostedmigrationService.svc`
    


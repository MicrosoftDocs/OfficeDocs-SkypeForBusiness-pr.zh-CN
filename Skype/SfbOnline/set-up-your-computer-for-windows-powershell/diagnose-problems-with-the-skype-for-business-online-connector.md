---
title: 诊断与 Skype for Business Online 连接器的连接问题
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: 866fadfd-16e2-4134-95db-c6aed7678416
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.custom:
- PowerShell
description: 排查创建远程 PowerShell 会话以连接到 Skype for Business Online 的问题，包括导入模块、并发 shell、Live ID 和权限错误。
ms.openlocfilehash: c2092da0324a147b182ce7715e757f1ed039aa65
ms.sourcegitcommit: 1ac37cc27d4ccb3e1dae20ca1929214e17be2075
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/07/2022
ms.locfileid: "65913390"
---
# <a name="diagnose-connection-problems-with-the-skype-for-business-online-connector"></a>诊断与 Skype for Business Online 连接器的连接问题

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

本主题提供的信息有助于诊断和解决尝试创建连接到 Skype for Business Online 的远程 Microsoft PowerShell 会话时可能出现的问题。 请参阅以下部分：
  
- [Windows PowerShell 执行策略导致的导入模块错误](diagnose-problems-with-the-skype-for-business-online-connector.md#BKMKPowerShellExecutionPolicy)
    
- [Windows PowerShell 版本不正确导致的导入模块错误](diagnose-problems-with-the-skype-for-business-online-connector.md#BKMKIncorrectVersion)
    
- [禁用 WinRM 基本身份验证时，新式身份验证失败](diagnose-problems-with-the-skype-for-business-online-connector.md#BKMKWinRMBasicAuth)
    
- [无法连接到 Live ID Server](diagnose-problems-with-the-skype-for-business-online-connector.md#BKMKFailedConnect)
      
- [用户登录失败](diagnose-problems-with-the-skype-for-business-online-connector.md#BKMKLogonFailed)
    
- [用户无权管理此租户](diagnose-problems-with-the-skype-for-business-online-connector.md#BKMKUserPermission)
    
- [Skype for Business Online 中已禁用连接到租户的功能](diagnose-problems-with-the-skype-for-business-online-connector.md#BKMKAbilityConnect)
    
- [已超出 Skype for Business Online 中此用户的最大并发 shell 数](#the-maximum-number-of-concurrent-shells-for-this-user-in-skype-for-business-online-has-been-exceeded)

- [已超出 Skype for Business Online 中此租户的最大并发 shell 数](#the-maximum-number-of-concurrent-shells-for-this-tenant-in-skype-for-business-online-has-been-exceeded)

## <a name="import-module-error-caused-by-windows-powershell-execution-policy"></a>由 Windows PowerShell 执行策略引起的Import-Module错误
<a name="BKMKPowerShellExecutionPolicy"> </a>

PowerShell 执行策略有助于确定哪些配置文件可以加载到 PowerShell 控制台，以及用户可从该控制台运行的脚本。 至少，除非执行策略已设置为 RemoteSigned，否则无法导入 Skype for Business Online 连接器模块。 如果尚未导入，则在尝试导入模块时会收到以下错误消息：
  
- **错误**：<em>导入模块：文件 C：\\Program Files Common Files\\\\Microsoft Lync Server 2013\\模块\\LyncOnlineConnector LyncOnlineConnectorStartup.psm1\\无法加载，因为此系统上禁用了正在运行的脚本。有关详细信息，请参阅about_Execution_Policies。https://go.microsoft.com/fwlink/?LinkID=135170</em>

- **分辨率** 若要解决此问题，请以管理员身份启动 PowerShell，然后运行以下命令：
    ```PowerShell
    Set-ExecutionPolicy RemoteSigned
    ```
    有关执行策略的详细信息， [请参阅“关于执行策略](/powershell/module/microsoft.powershell.core/about/about_execution_policies)”。
  
## <a name="import-module-error-caused-by-incorrect-version-of-windows-powershell"></a>Import-Module错误导致的 Windows PowerShell 版本不正确
<a name="BKMKIncorrectVersion"> </a>

Skype for Business Online 连接器模块只能在 Windows PowerShell 3.0 下运行。 如果尝试在早期版本的 PowerShell 下导入模块，则导入过程将失败，并出现类似于以下消息的错误消息：
  
  - **错误**：*Import-Module：加载的 PowerShell 的版本为“2.0”。模块“D：\\Program Files Common Files\\\\Microsoft Lync Server 2013\\Modules\\LyncOnlineConnector\\LyncOnlineConnector.psd1”需要执行最低 PowerShell 版本的“3.0”。请验证 PowerShell 的安装，然后重试。*

- **解决** 方法：解决此问题的唯一方法是安装 Windows PowerShell 3.0，可从 Microsoft 下载中心 [https://www.microsoft.com/download/details.aspx?id=34595](https://www.microsoft.com/download/details.aspx?id=34595)安装。
  
## <a name="modern-authentication-fails-when-winrm-basic-authentication-has-been-disabled"></a>禁用 WinRM 基本身份验证时，新式身份验证失败
<a name="BKMKWinRMBasicAuth"> </a>

最新版本的 Skype for Business Online 连接器模块使用新式身份验证，但基础 Windows 远程管理 (WinRM) 客户端必须配置为允许基本身份验证。  新式身份验证使用持有者令牌，这些令牌通常在 *Authorization： Bearer* 标头中传递。 构建 Skype for Business PowerShell 的 Windows PowerShell 不允许操作此标头。  相反，Skype for Business PowerShell 使用 *Authorization：Basic* 标头传递持有者令牌。

有关如何启用 WinRM for Basic 身份验证的说明，请参阅 [下载并安装 Windows PowerShell](./download-and-install-windows-powershell-5-1.md) 。

## <a name="failed-to-connect-to-live-id-server"></a>无法连接到 Live ID Server
<a name="BKMKFailedConnect"> </a>

> [!WARNING] 
> 已弃用 Skype For Business 在线连接器的实时 ID 身份验证。 使用 Teams PowerShell 模块管理联机租户。 管理混合环境时，请升级到最新的累积更新或使用 oAuth 身份验证。

连接尝试失败的原因通常有三个，以下错误消息如下：

  - **错误**： *Get-CsWebTicket：无法连接实时 ID 服务器。确保代理已启用或计算机与实时 ID 服务器建立网络连接。*

- **解决方法**：此错误通常意味着 Microsoft Online Services 登录助手未运行。 可以通过从 PowerShell 提示符运行以下命令来验证此服务的状态： 
    ```PowerShell
    Get-Service "msoidsvc"
    ```
    如果服务未运行，请使用以下命令启动服务：
    ```PowerShell
    Start-Service "msoidsvc"
    ```

    如果服务正在运行，则计算机与 Microsoft Live ID 身份验证服务器之间的网络连接可能会遇到问题。 若要检查此操作，请打开 Internet Explorer 并导航到 [https://login.microsoftonline.com/。](https://login.microsoftonline.com/.) 尝试从那里登录到 Microsoft 365 或 Office 365。 如果失败，则可能会遇到网络连接问题。
  
    通常情况下，Microsoft Live ID 身份验证服务器的连接 URI 可能配置为错误的值。 如果已确定Sign-In助手正在运行，并且未遇到网络连接问题，则可能是问题所在。 在这种情况下，请联系 Microsoft 支持部门。
  
## <a name="logon-failed-for-the-user"></a>用户登录失败
<a name="BKMKLogonFailed"> </a>

尝试与 Skype for Business Online 建立远程连接时，必须提供有效的 Skype for Business Online 用户帐户的用户名和密码。 如果不这样做，登录将失败，并出现类似于此消息的错误消息：

- **错误**： *Get-CsWebTicket：用户“kenmyer@litwareinc.com”登录失败。创建新的 PSCredential 对象，确保已使用正确的用户名和密码。*

- **解决方法**：如果认为使用的是有效的用户帐户且密码正确，请尝试再次登录。 如果失败，请使用相同的凭据，并尝试登录 [https://login.microsoftonline.com/](https://login.microsoftonline.com/)。 如果无法登录，请联系 Microsoft 支持部门。 

  
## <a name="the-user-does-not-have-permission-to-manage-this-tenant"></a>用户无权管理此租户
<a name="BKMKUserPermission"> </a>

除非你是租户管理员组的成员，否则无法与Skype for Business Online 建立远程 PowerShell 连接。 否则，连接尝试将失败，你将收到以下错误消息：

- **错误**： *New-PSSession：[admin.vdomain.com] 处理来自远程服务器的数据 admin.vdomain.com 失败，并出现以下错误消息：用户“user@foo.com”无权管理此租户。可以通过将用户分配到适当的 RBAC 角色来授予权限。有关详细信息，请参阅 [远程故障排除](/powershell/module/microsoft.powershell.core/about/about_remote_troubleshooting )。*

- **解决方法**：如果你认为你是或应该是租户管理员组的成员，则需要联系 Microsoft 支持部门。
  
## <a name="ability-to-connect-to-tenant-has-been-disabled-in-skype-for-business-online"></a>Skype for Business Online 中已禁用连接到租户的功能
<a name="BKMKAbilityConnect"> </a>

若要使用 PowerShell 管理 Skype for Business Online，租户 PowerShell 策略的 EnableRemotePowerShellAccess 属性必须设置为  `True`。 否则，连接将失败，你将收到以下错误消息：

- **错误**： *New-PSSession：[admin.vdomain.com] 处理来自远程服务器的数据 admin.vdomain.com 失败，并出现以下错误消息：已禁用使用远程 PowerShell 会话连接到此租户的功能。请联系 Lync 帮助，检查此租户的租户 PowerShell 策略。有关详细信息，请参阅 [远程故障排除](/powershell/module/microsoft.powershell.core/about/about_remote_troubleshooting )。*

- **解决方法**：如果看到此错误消息，则需要联系 Microsoft 支持部门并启用远程 PowerShell 访问。
  
## <a name="the-maximum-number-of-concurrent-shells-for-this-user-in-skype-for-business-online-has-been-exceeded"></a>已超出 Skype for Business Online 中此用户的最大并发 shell 数
<a name="BKMKMaxNumberShellsUser"> </a>

每个管理员最多允许三个同时连接到 Skype for Business Online 的远程连接。 如果已启动和运行三个远程 PowerShell 连接，则任何同时建立第四个连接的尝试都将失败，并出现以下错误消息： 

- **错误**： *New-PSSession：[admin.vdomain.com] 连接到远程服务器 admin.vdomain.com 失败，并出现以下错误消息：WS-Management服务无法处理请求。已超出此用户的最大并发 shell 数。关闭现有 shell 或提高此用户的配额。有关详细信息，请参阅 [远程故障排除](/powershell/module/microsoft.powershell.core/about/about_remote_troubleshooting )。*

- **解决** 方法：解决此问题的唯一方法是关闭之前的一个或多个连接。 完成 Skype for Business Online 会话后，建议使用 **Remove-PSSession** cmdlet 终止会话。 这有助于防止此问题。
  
## <a name="the-maximum-number-of-concurrent-shells-for-this-tenant-in-skype-for-business-online-has-been-exceeded"></a>已超出 Skype for Business Online 中此租户的最大并发 shell 数
<a name="BKMKMaxNumberShellsTenant"> </a>

尽管允许每个管理员同时与 Skype for Business Online 租户建立多达三个连接，但不允许单个租户同时连接超过 20 个。 例如，六个管理员可能各有三个打开的会话。 如果第四个管理员尝试建立两个以上的连接 (导致总共有 21 个同时连接) ，则此尝试将失败，并显示以下错误消息：
  
- **错误**： *New-PSSession：[admin.vdomain.com] 连接到远程服务器 admin.vdomain.com 失败，并出现以下错误消息：WS-Management服务无法处理请求。已超出此租户的最大并发 shell 数。关闭现有 shell 或提高此租户的配额。有关详细信息，请参阅 [远程故障排除](/powershell/module/microsoft.powershell.core/about/about_remote_troubleshooting )。*

- **解决** 方法：解决此问题的唯一方法是关闭之前的一个或多个连接。 完成 Skype for Business Online 会话后，建议使用 **Remove-PSSession** cmdlet 终止该会话。 这有助于防止此问题。  
 
## <a name="related-topics"></a>相关主题
[使用 Windows PowerShell 为 Skype for Business 联机管理设置计算机](set-up-your-computer-for-windows-powershell.md)

  

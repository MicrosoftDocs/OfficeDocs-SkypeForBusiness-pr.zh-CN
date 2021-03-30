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
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- PowerShell
description: 排查创建远程 PowerShell 会话以连接到 Skype for Business Online 的问题，包括 Import-Module、并发 shell、Live ID 和权限错误。
ms.openlocfilehash: b7cc45c0ea09c254f05d1cdd7609faea8877f299
ms.sourcegitcommit: 6505dd1fb891ab27fcc9f36423fda67aae6fcfd7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/30/2021
ms.locfileid: "51418740"
---
# <a name="diagnose-connection-problems-with-the-skype-for-business-online-connector"></a>诊断与 Skype for Business Online 连接器的连接问题

本主题提供有助于诊断和解决尝试创建连接到 Skype for Business Online 的远程 Microsoft PowerShell 会话时可能会出现的问题的信息。 请参阅以下部分：
  
- [执行策略导致Windows PowerShell模块错误](diagnose-problems-with-the-skype-for-business-online-connector.md#BKMKPowerShellExecutionPolicy)
    
- [错误版本错误导致的导入模块Windows PowerShell](diagnose-problems-with-the-skype-for-business-online-connector.md#BKMKIncorrectVersion)
    
- [当 WinRM 基本身份验证已禁用时，新式身份验证失败](diagnose-problems-with-the-skype-for-business-online-connector.md#BKMKWinRMBasicAuth)
    
- [无法连接到实时 ID 服务器](diagnose-problems-with-the-skype-for-business-online-connector.md#BKMKFailedConnect)
    
- [无法加载实时 ID 模块](diagnose-problems-with-the-skype-for-business-online-connector.md#BKMKFailedLoad)
    
- [用户登录失败](diagnose-problems-with-the-skype-for-business-online-connector.md#BKMKLogonFailed)
    
- [用户无权管理此租户](diagnose-problems-with-the-skype-for-business-online-connector.md#BKMKUserPermission)
    
- [Skype for Business Online 中已禁用连接到租户的能力](diagnose-problems-with-the-skype-for-business-online-connector.md#BKMKAbilityConnect)
    
- [已超过 Skype for Business Online 中此用户的最大并发 shell 数](#the-maximum-number-of-concurrent-shells-for-this-user-in-skype-for-business-online-has-been-exceeded)

- [已超过 Skype for Business Online 中此租户的最大并发 shell 数](#the-maximum-number-of-concurrent-shells-for-this-tenant-in-skype-for-business-online-has-been-exceeded)
    

> [!IMPORTANT]
> 默认情况下，PowerShell 会话在 60 分钟后会退出。 若要重新连接，必须关闭会话并启动新的 PowerShell 会话。 Skype for Business Online 的新版本 Windows PowerShell 模块 [ (2046.123 - 已发布 10/2/2019) ，](https://www.microsoft.com/download/details.aspx?id=39366)其中包括名为 **Enable-CsOnlineSessionForReconnection** 的新 cmdlet，可缓解 60 分钟的时出问题。
> PowerShell 会话重新连接并进行身份验证，这样无需启动新实例即可重新连接。



## <a name="import-module-error-caused-by-windows-powershell-execution-policy"></a>Import-Module策略导致的Windows PowerShell错误
<a name="BKMKPowerShellExecutionPolicy"> </a>

PowerShell 执行策略可帮助确定哪些配置文件可以加载到 PowerShell 控制台中，以及用户可以从该控制台运行哪些脚本。 除非执行策略已设置为 RemoteSigned，否则至少无法导入 Skype for Business Online 连接器模块。 如果尚未导入，则尝试导入模块时会收到以下错误消息：
  
- **错误**<em>：Import-Module ： 文件 C：程序文件公用文件 \\ Microsoft Lync Server \\ \\ 2013 \\ 模块 \\ LyncOnlineConnector \\ LyncOnlineConnectorStartup.psm1 无法加载，因为在此系统中禁用了正在运行的脚本。有关详细信息，请参阅 在 https://go.microsoft.com/fwlink/?LinkID=135170 about_Execution_Policies。</em>

- **解决方法** 若要解决此问题，请以管理员角色启动 PowerShell，然后运行以下命令：
    ```PowerShell
    Set-ExecutionPolicy RemoteSigned
    ```
    有关执行策略的详细信息，请参阅 [关于执行策略](/powershell/module/microsoft.powershell.core/about/about_execution_policies)。
  
## <a name="import-module-error-caused-by-incorrect-version-of-windows-powershell"></a>Import-Module版本不正确导致的Windows PowerShell
<a name="BKMKIncorrectVersion"> </a>

Skype for Business Online 连接器模块只能在 Windows PowerShell 3.0 下运行。 如果尝试在早期版本的 PowerShell 下导入模块，导入过程会失败，并出现类似于此消息的错误消息：
  
  - **错误***：Import-Module：加载的 PowerShell 的版本为"2.0"。模块"D： 程序文件通用文件 \\ \\ Microsoft Lync Server \\ 2013 \\ 模块 \\ LyncOnlineConnectorLyncOnlineConnector.psd1"要求执行最低 \\ PowerShell 版本"3.0"。请验证 PowerShell 的安装，然后重试。*

- **解决方法**：解决此问题的唯一方法就是安装 3.0 Windows PowerShell 3.0，可从 中的 Microsoft 下载中心获得 [https://www.microsoft.com/download/details.aspx?id=34595](https://www.microsoft.com/download/details.aspx?id=34595) 。
  
## <a name="modern-authentication-fails-when-winrm-basic-authentication-has-been-disabled"></a>当 WinRM 基本身份验证已禁用时，新式身份验证失败
<a name="BKMKWinRMBasicAuth"> </a>

最新版本的 Skype for Business Online 连接器模块使用新式身份验证，但必须将基础 Windows 远程管理 (WinRM) 客户端配置为允许基本身份验证。  新式身份验证使用通常在 *Authorization： Bearer* 标头中传递的 bearer 令牌。 Windows PowerShell Skype for Business PowerShell 的构建方式不允许操作此标头。  相反，Skype for Business PowerShell 使用 *Authorization： Basic 标头* 来传递 bearer 令牌。

有关如何启用 WinRM for Basic [身份验证的说明](./download-and-install-windows-powershell-5-1.md) ，请参阅下载并安装 Windows PowerShell。

## <a name="failed-to-connect-to-live-id-server"></a>无法连接到实时 ID 服务器
<a name="BKMKFailedConnect"> </a>

> [!WARNING] 
> Skype for Business Online Connector 已弃用实时 ID 身份验证。 使用 Teams PowerShell 模块管理联机租户。 管理混合环境时，请升级到最新的累积更新或使用 oAuth 身份验证。

连接尝试失败的原因通常有三个，并出现以下错误消息：

  - **错误***：Get-CsWebTicket：无法连接实时 ID 服务器。确保已启用代理或计算机已与实时 ID 服务器建立网络连接。*

- **解决方法**：此错误通常意味着Microsoft Online Services助手未运行。 可以通过从 PowerShell 提示符运行以下命令来验证此服务的状态： 
    ```PowerShell
    Get-Service "msoidsvc"
    ```
    如果服务未运行，请通过以下命令启动服务：
    ```PowerShell
    Start-Service "msoidsvc"
    ```

    如果服务正在运行，则可能会遇到计算机与 Microsoft Live ID 身份验证服务器之间的网络连接问题。 若要检查此状态，请Internet Explorer并导航到[ https://login.microsoftonline.com/ 。](https://login.microsoftonline.com/.) 尝试从该服务器登录到 Microsoft 365 或 Office 365。 如果此操作失败，则可能会遇到网络连接问题。
  
    不太常见的是，Microsoft Live ID 身份验证服务器的连接 URI 已配置为错误值。 如果已确定，Sign-In助手正在运行，并且未遇到网络连接问题，则这可能是问题。 在这种情况下，请联系 Microsoft 支持部门。
  
## <a name="failed-to-load-live-id-module"></a>无法加载实时 ID 模块
<a name="BKMKFailedLoad"> </a>

使用 PowerShell 管理 Skype for Business Online 的先决条件之一是安装 Microsoft Online Services登录助手。 如果未安装登录助手，当您尝试与 Skype for Business Online 建立远程会话时，您将收到以下错误消息：

- **错误***：Get-CsWebTicket：无法加载 Live ID 模块。确保安装了正确版本的 Live ID 登录助手。*

- **解决方法**：Microsoft Online Services适用于 IT 专业人员 RTW 的 Microsoft 下载Microsoft Online Services Sign-In [助手中提供了登录助手](https://www.microsoft.com/download/details.aspx?id=28177)

## <a name="logon-failed-for-the-user"></a>用户登录失败
<a name="BKMKLogonFailed"> </a>

尝试与 Skype for Business Online 建立远程连接时，必须提供有效的 Skype for Business Online 用户帐户的用户名和密码。 如果不这样做，登录会失败，并出现类似于此消息的错误消息：

- **错误***：Get-CsWebTicket：用户"kenmyer@litwareinc.com"登录失败。创建新的 PSCredential 对象，确保使用了正确的用户名和密码。*

- **解决方法**：如果认为你使用的是有效的用户帐户，并且拥有正确的密码，请尝试再次登录。 如果失败，请使用相同的凭据，并尝试在 登录 [https://login.microsoftonline.com/](https://login.microsoftonline.com/) 。 如果无法登录，请联系 Microsoft 支持部门。 

  
## <a name="the-user-does-not-have-permission-to-manage-this-tenant"></a>用户无权管理此租户
<a name="BKMKUserPermission"> </a>

无法与Skype for Business Online 建立远程 PowerShell 连接，除非你是租户管理员管理员组。 如果不是，连接尝试会失败，并且将收到以下错误消息：

- 错误 *：New-PSSession ： [admin.vdomain.com] 处理来自远程服务器 admin.vdomain.com 的数据失败，出现以下错误消息：用户"user@foo.com"无权管理此租户。可以通过将用户分配到相应的 RBAC 角色来授予权限。有关详细信息，请参阅 [远程故障排除](/powershell/module/microsoft.powershell.core/about/about_remote_troubleshooting?view=powershell-5.1)。*

- **解决方法**：如果您认为自己是或应该是租户管理员的成员管理员组，则需要联系 Microsoft 支持部门。
  
## <a name="ability-to-connect-to-tenant-has-been-disabled-in-skype-for-business-online"></a>Skype for Business Online 中已禁用连接到租户的能力
<a name="BKMKAbilityConnect"> </a>

若要使用 PowerShell 管理 Skype for Business Online，租户 PowerShell 策略的 EnableRemotePowerShellAccess 属性必须设置为  `True` 。 如果不是，连接会失败，并且将收到以下错误消息：

- 错误 *：New-PSSession ： [admin.vdomain.com] 无法处理来自远程服务器 admin.vdomain.com 的数据，并出现以下错误消息：已禁用使用远程 PowerShell 会话连接到此租户的能力。请联系 Lync 帮助以检查此租户的租户 Powershell 策略。有关详细信息，请参阅 [远程故障排除](/powershell/module/microsoft.powershell.core/about/about_remote_troubleshooting?view=powershell-5.1)。*

- **解决方法**：如果看到此错误消息，则需要联系 Microsoft 支持部门并启用远程 PowerShell 访问。
  
## <a name="the-maximum-number-of-concurrent-shells-for-this-user-in-skype-for-business-online-has-been-exceeded"></a>已超过 Skype for Business Online 中此用户的最大并发 shell 数
<a name="BKMKMaxNumberShellsUser"> </a>

每个管理员最多允许与 Skype for Business Online 同时进行三次远程连接。 如果已启动并运行三个远程 PowerShell 连接，则尝试进行第四次同时连接的任何尝试都将失败，并出现以下错误消息：

- **错误***：New-PSSession： [admin.vdomain.com] 连接到远程服务器 admin.vdomain.com 失败，出现以下错误消息：WS-Management 服务无法处理请求。已超过此用户的最大并发 shell 数。关闭现有 shell 或提高此用户的配额。有关详细信息，请参阅 https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_remote_troubleshooting?view=powershell-5.1 [远程故障排除] (*

- **解决方法**：解决此问题的唯一方法就是关闭一个或多个以前的连接。 完成 Skype for Business Online 会话后，建议使用 **Remove-PSSession** cmdlet 终止会话。 这有助于防止此问题。
  
## <a name="the-maximum-number-of-concurrent-shells-for-this-tenant-in-skype-for-business-online-has-been-exceeded"></a>已超过 Skype for Business Online 中此租户的最大并发 shell 数
<a name="BKMKMaxNumberShellsTenant"> </a>

尽管允许每个管理员同时与 Skype for Business Online 租户建立三个连接，但不允许单个租户同时具有 20 多个连接。 例如，六个管理员可能各自有三个打开的会话。 如果第四个管理员尝试建立两 (连接，导致总共 21 个同时连接) ，则此尝试会失败，并出现以下错误消息：
  
- **错误***：New-PSSession： [admin.vdomain.com] 连接到远程服务器 admin.vdomain.com 失败并出现以下错误消息：WS-Management 服务无法处理请求。已超过此租户的最大并发 shell 数。关闭现有 shell 或提高此租户的配额。有关详细信息，请参阅 https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_remote_troubleshooting?view=powershell-5.1 [远程故障排除] (*

- **解决方法**：解决此问题的唯一方法就是关闭一个或多个以前的连接。 完成 Skype for Business Online 会话后，建议使用 **Remove-PSSession** cmdlet 终止该会话。 这有助于防止此问题。  
 
## <a name="related-topics"></a>相关主题
[使用 skype for business Online 管理设置计算机Windows PowerShell](set-up-your-computer-for-windows-powershell.md)

  

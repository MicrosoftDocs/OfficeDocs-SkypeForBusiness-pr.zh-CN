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
f1keywords: None
ms.custom:
- PowerShell
description: 有关创建用于连接到 Skype for business Online 的远程 PowerShell 会话的疑难解答，包括导入模块、并发 shell、实时 ID 和权限错误。
ms.openlocfilehash: 38f6195a6c8e0c2a5f963d476e26abeb46f6ff4f
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/08/2020
ms.locfileid: "40991317"
---
# <a name="diagnose-connection-problems-with-the-skype-for-business-online-connector"></a>诊断与 Skype for Business Online 连接器的连接问题

本主题提供的信息可帮助你诊断和解决尝试创建连接到 Skype for business Online 的远程 Microsoft PowerShell 会话时可能出现的问题。 请参阅以下部分：
  
- [Windows PowerShell 执行策略导致的导入模块错误](diagnose-connection-problems-with-the-skype-for-business-online-connector.md#BKMKPowerShellExecutionPolicy)
    
- [由不正确版本的 Windows PowerShell 导致的导入模块错误](diagnose-connection-problems-with-the-skype-for-business-online-connector.md#BKMKIncorrectVersion)
    
- [无法连接到 Live ID 服务器](diagnose-connection-problems-with-the-skype-for-business-online-connector.md#BKMKFailedConnect)
    
- [无法加载实时 ID 模块](diagnose-connection-problems-with-the-skype-for-business-online-connector.md#BKMKFailedLoad)
    
- [用户登录失败](diagnose-connection-problems-with-the-skype-for-business-online-connector.md#BKMKLogonFailed)
    
- [用户没有管理此租户的权限](diagnose-connection-problems-with-the-skype-for-business-online-connector.md#BKMKUserPermission)
    
- [Skype for Business Online 中已禁用连接到租户的功能](diagnose-connection-problems-with-the-skype-for-business-online-connector.md#BKMKAbilityConnect)

- [已超出 Skype for Business Online 中此用户的并发 shell 的最大数量](#the-maximum-number-of-concurrent-shells-for-this-user-in-skype-for-business-online-has-been-exceeded)

- [已超出 Skype for Business Online 中此租户的最大并发 shell 数](#the-maximum-number-of-concurrent-shells-for-this-tenant-in-skype-for-business-online-has-been-exceeded)

    
## <a name="import-module-error-caused-by-windows-powershell-execution-policy"></a>Windows PowerShell 执行策略导致的导入模块错误
<a name="BKMKPowerShellExecutionPolicy"> </a>

PowerShell 执行策略有助于确定哪些配置文件可以加载到 PowerShell 控制台，以及用户可以从该控制台运行哪些脚本。 除非已将执行策略设置为 RemoteSigned，否则，至少无法导入 Skype for Business Online 连接器模块。 如果不是这样，当您尝试导入该模块时，您将收到以下错误消息：
  
- **错误**：<em>导入-模块：文件 C\\：程序\\文件常见\\文件 Microsoft Lync Server\\2013\\模块\\LyncOnlineConnector 无法加载 psm1，因为此系统上已禁用运行脚本。有关详细信息，请参阅 about_Execution_Policies https://go.microsoft.com/fwlink/?LinkID=135170。</em>

- **解决方案**：若要解决此问题，请以管理员身份启动 PowerShell，然后运行以下命令：
    ```PowerShell
    Set-ExecutionPolicy RemoteSigned
    ```
    有关执行策略的详细信息，请参阅[关于执行策略](https://go.microsoft.com/fwlink/?LinkID=135170)。
  
## <a name="import-module-error-caused-by-incorrect-version-of-windows-powershell"></a>由不正确版本的 Windows PowerShell 导致的导入模块错误
<a name="BKMKIncorrectVersion"> </a>

Skype for Business Online 连接器模块只能在 Windows PowerShell 3.0 下运行。 如果你尝试在早期版本的 PowerShell 下导入该模块，则导入过程将失败，并出现类似以下内容的错误消息：
  
  - **错误**：*导入-模块：加载的 PowerShell 的版本为 "2.0"。该模块的：\\程序文件\\常见文件\\Microsoft Lync Server 2013\\模块\\LyncOnlineConnector\\LyncOnlineConnector "psd1" 需要 "3.0" 的最低 PowerShell 版本才能执行。请验证 PowerShell 的安装并重试。*

- **解决方案**：修复此问题的唯一方法是安装 Windows PowerShell 3.0，可从 Microsoft 下载中心获取该功能[https://www.microsoft.com/en-us/download/details.aspx?id=34595](https://www.microsoft.com/en-us/download/details.aspx?id=34595)。
  
## <a name="failed-to-connect-to-live-id-server"></a>无法连接到 Live ID 服务器
<a name="BKMKFailedConnect"> </a>

连接尝试可能失败的原因通常有三个，并显示以下错误消息：

  - **错误**： *CsWebTicket：无法连接 live id 服务器。确保已启用代理，或者计算机具有与 live id 服务器的网络连接。*

- **解决方案**：此错误通常表示 Microsoft Online Services 登录助手未运行。 你可以通过从 PowerShell 提示符运行以下命令来验证此服务的状态： 
    ```PowerShell
    Get-Service "msoidsvc"
    ```
    如果服务未运行，请使用以下命令启动服务：
    ```PowerShell
    Start-Service "msoidsvc"
    ```

    如果服务正在运行，则你的计算机和 Microsoft Live ID 身份验证服务器之间的网络连接可能会遇到问题。 若要检查此情况，请打开 Internet Explorer，然后导航到[ https://login.microsoftonline.com/。](https://login.microsoftonline.com/.) 尝试从此处登录到 Office 365。 如果此操作失败，则你可能遇到网络连接问题。
  
    通常情况下，Microsoft Live ID 身份验证服务器的连接 URI 可能已配置为错误值。 如果你已确定登录助手正在运行，但你未遇到网络连接问题，则可能是此问题。 在这种情况下，请联系 Office 365 支持人员。
  
## <a name="failed-to-load-live-id-module"></a>无法加载实时 ID 模块
<a name="BKMKFailedLoad"> </a>

使用 PowerShell 管理 Skype for Business Online 的先决条件之一是安装 Microsoft Online Services 登录助手。 如果未安装登录助手，当您尝试建立与 Skype for Business Online 的远程会话时，将收到以下错误消息：

- **错误**： *CsWebTicket：无法加载 "实时 Id" 模块。请确保安装了正确版本的 Live Id 登录助手。*

- **解决方案**： Microsoft Online Services 登录助手适用于[IT 专业人员的 Microsoft Online services 登录助手](https://www.microsoft.com/en-us/download/details.aspx?id=28177)的 microsoft 下载中心 RTW

## <a name="logon-failed-for-the-user"></a>用户登录失败
<a name="BKMKLogonFailed"> </a>

当您尝试建立与 Skype for business Online 的远程连接时，您必须提供有效的 Skype for business Online 用户帐户的用户名和密码。 如果不这样做，登录将失败，并出现类似下面的错误消息：

- **错误**： *CsWebTicket：登录用户 ' kenmyer@litwareinc.com ' 失败。请创建一个新的 PSCredential 对象，确保您使用了正确的用户名和密码。*

- **解决方案**：如果你认为你使用的是有效的用户帐户，并且你拥有正确的密码，请尝试再次登录。 如果此操作失败，请使用相同的凭据，然后尝试登录[https://login.microsoftonline.com/](https://login.microsoftonline.com/)。 如果您无法登录，请联系 Office 365 支持。 

  
## <a name="the-user-does-not-have-permission-to-manage-this-tenant"></a>用户没有管理此租户的权限
<a name="BKMKUserPermission"> </a>

除非您是租户管理员组的成员，否则不能创建远程 PowerShell 连接 Skype for Business Online。 如果不是，则连接尝试将失败，您将收到以下错误消息：

- **错误**：*新建-PSSession： [admin.vdomain.com] 从远程服务器 admin.vdomain.com 处理数据失败，出现以下错误消息：用户 "user@foo.com" 没有管理此租户的权限。可通过将用户分配给相应的 RBAC 角色来授予权限。有关详细信息，请参阅[远程故障排除](https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_remote_troubleshooting?view=powershell-5.1)。*

- **解决方案**：如果你认为你是或应该是租户管理员组的成员，则需要联系 Office 365 支持。
  
## <a name="ability-to-connect-to-tenant-has-been-disabled-in-skype-for-business-online"></a>Skype for Business Online 中已禁用连接到租户的功能
<a name="BKMKAbilityConnect"> </a>

若要使用 PowerShell 管理 Skype for Business Online，租户 PowerShell 策略的 EnableRemotePowerShellAccess 属性必须设置为`True`。 如果不是，您的连接将失败，您将收到以下错误消息：

- **错误**：*新建-PSSession： [admin.vdomain.com] 从远程服务器 admin.vdomain.com 处理数据失败，出现以下错误消息：已禁用通过使用远程 PowerShell 会话连接到此租户的功能。请联系 Lync 帮助以检查此租户的租户 Powershell 策略。有关详细信息，请参阅[远程故障排除](https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_remote_troubleshooting?view=powershell-5.1)。*

- **解决方案**：如果看到此错误消息，则需要联系 Office 365 支持并启用远程 PowerShell 访问。
  
## <a name="the-maximum-number-of-concurrent-shells-for-this-user-in-skype-for-business-online-has-been-exceeded"></a>已超出 Skype for Business Online 中此用户的并发 shell 的最大数量
<a name="BKMKMaxNumberShellsUser"> </a>

每个管理员最多允许同时有三个与 Skype for business Online 的远程连接。 如果有三个远程 PowerShell 连接正常运行，则连接第四个同时连接的任何尝试都将失败，并出现以下错误消息：

- **错误**：*新的 PSSession： [admin.vdomain.com] 连接到远程服务器 admin.vdomain.com 失败，出现以下错误消息： ws-management 服务无法处理该请求。已超出此用户的并发 shell 的最大数量。关闭现有外壳程序或提高此用户的配额。有关详细信息，请参阅 [远程疑难解答] （https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_remote_troubleshooting?view=powershell-5.1 *

- **解决方案**：解决此问题的唯一方法是关闭一个或多个以前的连接。 使用 Skype for Business Online 会话完成后，建议使用**Remove-PSSession** cmdlet 终止会话。 这将帮助您避免此问题。
  
## <a name="the-maximum-number-of-concurrent-shells-for-this-tenant-in-skype-for-business-online-has-been-exceeded"></a>已超出 Skype for Business Online 中此租户的最大并发 shell 数
<a name="BKMKMaxNumberShellsTenant"> </a>

虽然每个管理员都允许将多达三个同时连接到 Skype for Business Online 租户，但不允许单个租户具有超过9个同时连接。 例如，三个管理员可能都有三个打开的会话。 如果第四个管理员尝试建立连接（总共导致10个同步连接），此尝试将失败，并出现以下错误消息：
  
- **错误**：*新的 PSSession： [admin.vdomain.com] 连接到远程服务器 admin.vdomain.com 失败，出现以下错误消息： ws-management 服务无法处理该请求。已超出此租户的并发 shell 的最大数量。关闭现有外壳程序或提高此租户的配额。有关详细信息，请参阅 [远程疑难解答] （https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_remote_troubleshooting?view=powershell-5.1 *

- **解决方案**：解决此问题的唯一方法是关闭一个或多个以前的连接。 使用 Skype for Business Online 会话完成后，我们建议你使用**Remove-PSSession** cmdlet 终止该会话。 这将帮助您避免此问题。  
 
## <a name="related-topics"></a>相关主题
[使用 Windows PowerShell 为 skype for business online 管理设置计算机](set-up-your-computer-for-windows-powershell.md)

  
 

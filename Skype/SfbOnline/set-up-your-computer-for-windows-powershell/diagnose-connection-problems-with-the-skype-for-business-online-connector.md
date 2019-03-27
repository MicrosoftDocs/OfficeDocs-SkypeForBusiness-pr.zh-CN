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
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- PowerShell
description: Troubleshoot 创建远程 PowerShell 会话来连接到 Skype 业务 Online，包括导入模块、 并发命令行管理程序、 Live ID 为和权限错误。
ms.openlocfilehash: c394995245521c88b4ca5b2b4a12376fdd5f267e
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/27/2019
ms.locfileid: "30897725"
---
# <a name="diagnose-connection-problems-with-the-skype-for-business-online-connector"></a>诊断与 Skype for Business Online 连接器的连接问题

本主题提供将帮助您诊断和解决尝试创建连接到 Skype 业务 online 远程 Microsoft PowerShell 会话时可能出现的问题的信息。 请参阅以下各节：
  
- [导入模块错误导致的 Windows PowerShell 执行策略](diagnose-connection-problems-with-the-skype-for-business-online-connector.md#BKMKPowerShellExecutionPolicy)
    
- [导入模块错误导致的不正确版本的 Windows PowerShell](diagnose-connection-problems-with-the-skype-for-business-online-connector.md#BKMKIncorrectVersion)
    
- [未能连接到 Live ID 服务器](diagnose-connection-problems-with-the-skype-for-business-online-connector.md#BKMKFailedConnect)
    
- [未能加载 Live ID 模块](diagnose-connection-problems-with-the-skype-for-business-online-connector.md#BKMKFailedLoad)
    
- [登录失败的用户](diagnose-connection-problems-with-the-skype-for-business-online-connector.md#BKMKLogonFailed)
    
- [用户没有管理此租户的权限](diagnose-connection-problems-with-the-skype-for-business-online-connector.md#BKMKUserPermission)
    
- [能够连接到租户中已禁用 Skype 业务 online](diagnose-connection-problems-with-the-skype-for-business-online-connector.md#BKMKAbilityConnect)
    
- [已超出最大并发 shells Skype 业务 online 中的此用户数](diagnose-connection-problems-with-the-skype-for-business-online-connector.md#BKMKMaxNumberShellsUser)
    
- [已超出此租户中的业务联机 Skype 的并发 shells 的最大数量](diagnose-connection-problems-with-the-skype-for-business-online-connector.md#BKMK_MaxNumberShellsTenant)
    
## <a name="import-module-error-caused-by-windows-powershell-execution-policy"></a>导入模块错误导致的 Windows PowerShell 执行策略
<a name="BKMKPowerShellExecutionPolicy"> </a>

PowerShell 执行策略有助于确定哪些配置文件可以加载到 PowerShell 控制台中，并的脚本的用户可以从该控制台中运行。 至少 for Business Online Connector 模块 Skype 无法导入除非已设置为 RemoteSigned 执行策略。 如果未，然后当您尝试导入模块时将收到以下错误消息：
  
- **错误**：<em>导入模块： 文件 c:\\Program Files\\Common Files\\Microsoft Lync Server 2013\\模块\\LyncOnlineConnector\\无法加载 LyncOnlineConnectorStartup.psm1，因为运行在此系统上禁用脚本。有关详细信息，请参阅在 about_Execution_Policies https://go.microsoft.com/fwlink/?LinkID=135170。</em>

- **解决方案**： 若要解决此问题，以管理员身份启动 PowerShell，然后运行以下命令：
    ```
    Set-ExecutionPolicy RemoteSigned
    ```
    有关执行策略的详细信息，请参阅[有关执行策略](https://go.microsoft.com/fwlink/?LinkID=135170)。
  
## <a name="import-module-error-caused-by-incorrect-version-of-windows-powershell"></a>导入模块错误导致的不正确版本的 Windows PowerShell
<a name="BKMKIncorrectVersion"> </a>

For Business Online Connector 模块 Skype 可以仅在 Windows PowerShell 3.0 下运行。 如果您尝试导入下以前版本的 PowerShell 模块，导入过程将失败并出现错误消息类似如下：
  
  - **错误**：*导入模块： 加载 PowerShell 版是"2.0"。模块 d:\\Program Files\\Common Files\\Microsoft Lync Server 2013\\模块\\LyncOnlineConnector\\LyncOnlineConnector.psd1 需要"3.0"，以执行的最小 PowerShell 版本。请验证安装的 PowerShell 并重试。*

- **解决方案**： 修复此问题的唯一方法是安装 Windows PowerShell 3.0，可从 Microsoft 下载中心在[https://www.microsoft.com/en-us/download/details.aspx?id=34595](https://www.microsoft.com/en-us/download/details.aspx?id=34595)。
  
## <a name="failed-to-connect-to-live-id-server"></a>未能连接到 Live ID 服务器
<a name="BKMKFailedConnect"> </a>

通常，有三个连接尝试可能无法与以下错误消息的原因：

  - **错误**： *Get CsWebTicket： 未能连接到 live id。请确保启用了代理或者计算机具有网络连接到 live id 服务器。*

- **解决方案**： 此错误通常意味着 Microsoft Online Services 登录助手未运行。 您可以通过从 PowerShell 提示符处运行以下命令验证该服务的状态： 
    ```
    Get-Service "msoidsvc"
    ```
    如果服务未运行，请使用以下命令启动服务：
    ```
    Start-Service "msoidsvc"
    ```

    如果该服务正在运行，您可能遇到的网络连接问题计算机和 Microsoft Live ID 身份验证服务器之间。 若要检查此，打开 Internet Explorer 并导航到[https://login.microsoftonline.com/。](https://login.microsoftonline.com/.) 尝试登录到 Office 365 从该处。 如果失败，您可能遇到网络连接问题。
  
    通常，较低，则可能 Microsoft Live ID 身份验证服务器连接 URI 确认已配置为错误值。 如果您已确定了登录助手正在运行，并且您没有遇到网络连接问题，这可能是问题。 在这种情况下，与 Office 365 支持联系。
  
## <a name="failed-to-load-live-id-module"></a>未能加载 Live ID 模块
<a name="BKMKFailedLoad"> </a>

使用 PowerShell 管理业务 online Skype 的必备组件之一是安装 Microsoft Online Services 登录助手。 如果未安装登录助手，您会收到以下错误消息，当您尝试业务 online 建立与 Skype 的远程会话时：

- **错误**： *Get CsWebTicket： 无法加载 Live Id 模块。请确保正确安装了版本的 Live Id 登录助手。*

- **解决方案**： Microsoft Online Services 登录助手位于 Microsoft 下载中心在[Microsoft Online Services 登录助手的 IT 专业人员的一项](https://www.microsoft.com/en-us/download/details.aspx?id=28177)

## <a name="logon-failed-for-the-user"></a>登录失败的用户
<a name="BKMKLogonFailed"> </a>

当您尝试进行远程连接到 Skype 业务 online 时，您必须提供的用户名和密码有效 Skype 业务 Online 用户帐户。 如果您没有登录将失败以及类似于以下错误消息：

- **错误**： *Get CsWebTicket： 用户 kenmyer@litwareinc.com 登录失败。请创建一个新的 PSCredential 对象，并确保您已经使用正确的用户名和密码。*

- **解决方案**： 如果您认为您使用的有效的用户帐户，并且必须正确的密码，尝试再次登录。 如果失败，使用相同的凭据，然后重试登录在[https://login.microsoftonline.com/](https://login.microsoftonline.com/)。 如果您不能有登录，请与 Office 365 支持。 

  
## <a name="the-user-does-not-have-permission-to-manage-this-tenant"></a>用户没有管理此租户的权限
<a name="BKMKUserPermission"> </a>

您不能进行远程 PowerShell 连接 toSkype 业务 online，除非您是租户管理员组的成员。 如果您不是，您的连接尝试将失败，并您会收到以下错误消息：

- **错误**：*新建 PSSession: [admin.vdomain.com] 处理数据从远程服务器 admin.vdomain.com 失败，出现以下错误消息: user@foo.com' 用户没有管理此租户的权限。可以通过向相应的 RBAC 角色分配用户授予权限。有关详细信息，请参阅[远程疑难解答](https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_remote_troubleshooting?view=powershell-5.1)。*

- **解决方案**： 如果您认为您，或者是应该是，租户管理员组的成员需要与 Office 365 支持部门联系。
  
## <a name="ability-to-connect-to-tenant-has-been-disabled-in-skype-for-business-online"></a>能够连接到租户中已禁用 Skype 业务 online
<a name="BKMKAbilityConnect"> </a>

若要使用 PowerShell 管理 Skype 业务 online，您的租户 PowerShell 策略的 EnableRemotePowerShellAccess 属性必须设置为`True`。 如果不存在，连接将失败，并且您会收到以下错误消息：

- **错误**：*新建 PSSession: [admin.vdomain.com] 处理数据从远程服务器 admin.vdomain.com 失败，出现以下错误消息： 已禁用连接到此租户使用远程 PowerShell 会话的能力。请 Lync 帮助检查此租户的租户 Powershell 策略，联系。有关详细信息，请参阅[远程疑难解答](https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_remote_troubleshooting?view=powershell-5.1)。*

- **解决方案**： 如果您看到此错误消息，您需要与 Office 365 支持部门联系并获取已启用的远程 PowerShell 访问。
  
## <a name="the-maximum-number-of-concurrent-shells-for-this-user-in-skype-for-business-online-has-been-exceeded"></a>已超出最大并发 shells Skype 业务 online 中的此用户数
<a name="BKMKMaxNumberShellsUser"> </a>

每个管理员允许，最多的三个远程连接到 Skype 业务 online。 如果您具有三个 up 的远程 PowerShell 连接和运行，以使第四个同时任何尝试将失败并连接，出现以下错误消息：

- **错误**：*新建 PSSession: [admin.vdomain.com] 连接到远程服务器 admin.vdomain.com 失败，出现以下错误消息： WS 管理服务无法处理请求。已超出为此用户的并发 shells 的最大数量。关闭现有 shells 或引发此用户的配额。有关详细信息，请参阅项 [远程 Troubleshooting] (https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_remote_troubleshooting?view=powershell-5.1 *

- **解决方案**： 若要解决此问题的唯一方法是关闭一个或多个以前的连接。 在完成时与 Skype 业务 Online 会话，我们建议使用**Remove-pssession** cmdlet 终止会话。 这将帮助您避免此问题。
  
## <a name="the-maximum-number-of-concurrent-shells-for-this-tenant-in-skype-for-business-online-has-been-exceeded"></a>已超出此租户中的业务联机 Skype 的并发 shells 的最大数量
<a name="BKMKMaxNumberShellsTenant"> </a>

尽管每个管理员允许具有三个同时连接到业务 Online 租户 Skype，但没有单租户允许具有多个九个同时连接。 例如，三个管理员可能每个具有三个打开的会话。 如果尝试进行连接 （10 个同时连接的总结果） 的第四个管理员，则此尝试将失败，使用以下错误消息：
  
- **错误**：*新建 PSSession: [admin.vdomain.com] 连接到远程服务器 admin.vdomain.com 失败，出现以下错误消息： WS 管理服务无法处理请求。已超出本租户的并发 shells 的最大数量。关闭现有 shells 或引发此租户配额。有关详细信息，请参阅项 [远程 Troubleshooting] (https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_remote_troubleshooting?view=powershell-5.1 *

- **解决方案**： 若要解决此问题的唯一方法是关闭一个或多个以前的连接。 在完成时与 Skype 业务 Online 会话，我们建议使用**Remove-pssession** cmdlet 终止该会话。 这将帮助您避免此问题。  
 
## <a name="related-topics"></a>相关主题
[设置您的计算机的业务联机管理使用 Windows PowerShell 的 Skype](set-up-your-computer-for-windows-powershell.md)

  
 

---
title: 诊断连接问题与 Skype 业务在线连接器
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 01/22/2018
ms.topic: article
ms.assetid: 866fadfd-16e2-4134-95db-c6aed7678416
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- PowerShell
description: 创建远程 PowerShell 会话连接到 Skype 的业务联机，包括导入模块、 并发的外壳，Live ID 和权限错误进行故障诊断。
ms.openlocfilehash: 3b00bfba29a8523d49690059ce1faceabcf040ab
ms.sourcegitcommit: 627d3108e3e2f232e911162d9d2db9558e8ead0c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/03/2018
---
# <a name="diagnose-connection-problems-with-the-skype-for-business-online-connector"></a>诊断连接问题与 Skype 业务在线连接器

本主题提供了可帮助您诊断并解决问题，当您尝试创建远程 Microsoft PowerShell 会话连接到 Skype 的在线业务可能发生的信息。 请参阅以下各节：
  
- [由 Windows PowerShell 执行策略的导入模块错误](diagnose-problems-with-the-skype-for-business-online-connector.md#BKMKPowerShellExecutionPolicy)
    
- [导入模块错误由 Windows PowerShell 的版本不正确](diagnose-problems-with-the-skype-for-business-online-connector.md#BKMKIncorrectVersion)
    
- [未能连接到 Live ID 服务器](diagnose-problems-with-the-skype-for-business-online-connector.md#BKMKFailedConnect)
    
- [未能加载 Live ID 模块](diagnose-problems-with-the-skype-for-business-online-connector.md#BKMKFailedLoad)
    
- [登录失败的用户](diagnose-problems-with-the-skype-for-business-online-connector.md#BKMKLogonFailed)
    
- [用户没有权限，管理本组织](diagnose-problems-with-the-skype-for-business-online-connector.md#BKMKUserPermission)
    
- [能够连接到组织中已禁用 Skype 的在线业务](diagnose-problems-with-the-skype-for-business-online-connector.md#BKMKAbilityConnect)
    
- [已超出此用户 Skype 的在线业务中的并发外壳的最大数量](diagnose-problems-with-the-skype-for-business-online-connector.md#BKMK_MaxNumberShellsUser)
    
- [已超出此租户在 Skype 的在线业务中的并发外壳的最大数量](diagnose-problems-with-the-skype-for-business-online-connector.md#BKMK_MaxNumberShellsTenant)
    
## <a name="import-module-error-caused-by-windows-powershell-execution-policy"></a>由 Windows PowerShell 执行策略的导入模块错误
<a name="BKMKPowerShellExecutionPolicy"> </a>

PowerShell 执行策略有助于确定哪些配置文件可以加载到 PowerShell 控制台中，并且该脚本的用户可以从该控制台上运行。 至少，Skype 业务在线连接器模块不能被导入，除非已设置为 RemoteSigned 执行策略。 如果还没有，然后当您试图导入模块时将收到以下错误消息：
  
- **错误**： 导入模块*： 文件 c:\\程序文件\\通用文件\\Microsoft Lync Server 2013\\模块\\LyncOnlineConnector\\LyncOnlineConnectorStartup.psm1 无法加载，因为运行在此系统上已禁用脚本。有关详细信息，请参阅在 about_Execution_Policies https://go.microsoft.com/fwlink/?LinkID=135170。*

- **解析**要解决此问题，请以管理员的身份，开始 PowerShell，然后运行下面的命令：
    ```
    Set-ExecutionPolicy RemoteSigned
    ```
    执行策略的详细信息，请参阅[关于执行策略](https://go.microsoft.com/fwlink/?LinkID=135170)。
  
## <a name="import-module-error-caused-by-incorrect-version-of-windows-powershell"></a>导入模块错误由 Windows PowerShell 的版本不正确
<a name="BKMKIncorrectVersion"> </a>

可以仅在 Windows PowerShell 3.0 下运行 Skype 业务在线连接器模块。 如果您尝试导入模块下 PowerShell 的早期版本，导入过程将失败并显示错误消息类似于下面：
  
  - **错误**： 导入模块*： 载入 PowerShell 的版本是"2.0"。模块 d:\\程序文件\\通用文件\\Microsoft Lync Server 2013\\模块\\LyncOnlineConnector\\LyncOnlineConnector.psd1 需要最小 PowerShell 版本的"3.0"执行。请验证安装的 PowerShell，然后再试一次。*

- **解决方案**： 要解决该问题的唯一方法就是安装 Windows PowerShell 3.0，可从 Microsoft 下载中心获取[https://www.microsoft.com/en-us/download/details.aspx?id=34595](https://www.microsoft.com/en-us/download/details.aspx?id=34595)。
  
## <a name="failed-to-connect-to-live-id-server"></a>未能连接到 Live ID 服务器
<a name="BKMKFailedConnect"> </a>

通常有三个原因为什么您的连接尝试可能会失败并显示以下错误消息：

  - **错误**： 获取 CsWebTicket *： 连接活动 id 的服务器失败。请确保启用了代理或者机器具有 live id 的服务器的网络连接。*

- **解析**： 此错误通常意味着助手登录 Microsoft 在线服务未在运行。 您可以验证此服务的状态 PowerShell 提示符下运行以下命令： 
    ```
    Get-Service "msoidsvc"
    ```
    如果该服务未运行，请使用此命令启动服务：
    ```
    Start-Service "msoidsvc"
    ```

    如果该服务正在运行，您可能会遇到网络连接问题您的计算机与 Microsoft Live ID 身份验证服务器之间。 要检查此项，打开 Internet Explorer，然后定位到[https://login.microsoftonline.com/。](https://login.microsoftonline.com/.) 尝试登录到 Office 365 从那里。 如果此操作失败，则您可能遇到网络连接问题。
  
    不太常见的情况是，可能是连接 URI 为 Microsoft Live ID 身份验证服务器已被配置为不正确的值。 如果您已经确定登录助手正在运行，并且您没有遇到网络连接问题，这可能是问题。 在这种情况下，与 Office 365 支持联系。
  
## <a name="failed-to-load-live-id-module"></a>未能加载 Live ID 模块
<a name="BKMKFailedLoad"> </a>

有关使用 PowerShell 管理 Skype 的在线业务的前提条件之一是安装 Microsoft 在线服务登录的助手。 如果未安装登录的助手，将收到下面的错误消息，当您尝试建立在线业务与 Skype 的远程会话：

- **错误**： 获取 CsWebTicket *： 无法加载 Live Id 模块。请确保正确安装版本的 Live Id 登录助手。*

- **解决方法**： 在 Microsoft 下载中心在[Microsoft 联机服务登录助手为 IT 专业人员的一项](https://www.microsoft.com/en-us/download/details.aspx?id=28177)在线服务的 Microsoft 的签到助手是可用

## <a name="logon-failed-for-the-user"></a>登录失败的用户
<a name="BKMKLogonFailed"> </a>

当您尝试建立远程连接到 Skype 的在线业务时，必须提供用户名和密码有效 Skype 的在线业务的用户帐户。 如果不这样做，则登录将失败以及与以下类似的错误消息：

- **错误**： 获取 CsWebTicket *： 登录失败，用户 kenmyer@litwareinc.com。请创建一个新的 PSCredential 对象，并确保使用正确的用户名称和密码。*

- **解决方案**： 如果您认为您使用有效的用户帐户，您拥有正确的密码，请尝试重新登录。 如果查找失败，使用相同的凭据并尝试登录[https://login.microsoftonline.com/](https://login.microsoftonline.com/)。 如果您仍无法登录存在，请与 Office 365 的支持。 

  
## <a name="the-user-does-not-have-permission-to-manage-this-tenant"></a>用户没有权限，管理本组织
<a name="BKMKUserPermission"> </a>

除非您是租户管理员组的成员，不能进行远程的 PowerShell 连接 toSkype 在线业务。 如果不是，您的连接尝试将会失败，并且您将收到以下错误消息：

- **错误**： *New PSSession: [admin.vdomain.com] 处理从远程服务器 admin.vdomain.com 的数据失败，出现以下错误消息: user@foo.com 的用户没有权限，管理本组织。可以通过将用户分配给相应的 RBAC 角色授予权限。有关详细信息，请参阅[远程故障诊断](https://docs.microsoft.com/en-us/powershell/module/microsoft.powershell.core/about/about_remote_troubleshooting?view=powershell-5.1)的。*

- **解决方案**： 如果您认为您是，或者应该是，成员的租户管理员组中，您将需要与 Office 365 支持部门联系。
  
## <a name="ability-to-connect-to-tenant-has-been-disabled-in-skype-for-business-online"></a>能够连接到组织中已禁用 Skype 的在线业务
<a name="BKMKAbilityConnect"> </a>

若要使用 PowerShell 管理 Skype 的在线业务，您租户 PowerShell 策略的 EnableRemotePowerShellAccess 属性必须设置为`True`。 如果不是，您的连接将会失败，并且您将收到以下错误消息：

- **错误**： *New PSSession: [admin.vdomain.com] 处理从远程服务器 admin.vdomain.com 的数据失败，出现以下错误消息： 使用远程 PowerShell 会话连接到该租户的能力已被禁用。请联系 Lync 帮助检查该租户的租户 Powershell 策略。有关详细信息，请参阅[远程故障诊断](https://docs.microsoft.com/en-us/powershell/module/microsoft.powershell.core/about/about_remote_troubleshooting?view=powershell-5.1)的。*

- **解决方案**： 如果您看到此错误消息，则需要联系 Office 365 支持并启用远程 PowerShell 访问。
  
## <a name="the-maximum-number-of-concurrent-shells-for-this-user-in-skype-for-business-online-has-been-exceeded"></a>已超出此用户 Skype 的在线业务中的并发外壳的最大数量
<a name="BKMKMaxNumberShellsUser"> </a>

每个管理员允许的最多的三个同时远程连接到 Skype 的在线业务。 如果您有三个向上的远程 PowerShell 连接和运行，使第四个同时发生的任何尝试连接将失败，并显示以下错误消息：

- **错误**： *New PSSession: [admin.vdomain.com] 连接到远程服务器 admin.vdomain.com 失败，出现以下错误消息： WS 管理服务无法处理此请求。已超出此用户的并发外壳的最大数量。关闭现有命令行程序或引发此用户的配额。有关详细信息，请参阅 [远程故障诊断] (https://docs.microsoft.com/en-us/powershell/module/microsoft.powershell.core/about/about_remote_troubleshooting?view=powershell-5.1 *

- **解决方案**： 要解决此问题的唯一方法是关闭一个或多个以前的连接。 当您完成了与 Skype 业务联机会话时，我们建议使用**删除 PSSession** cmdlet 以终止会话。 这将有助于防止出现此问题。
  
## <a name="the-maximum-number-of-concurrent-shells-for-this-tenant-in-skype-for-business-online-has-been-exceeded"></a>已超出此租户在 Skype 的在线业务中的并发外壳的最大数量
<a name="BKMKMaxNumberShellsTenant"> </a>

虽然每个管理员可拥有三个同时连接到 Skype 的在线业务的租户，则允许没有单个租户有 9 个以上的并发连接。 例如，三种管理员每个有三个打开的会话。 如果第四个管理员尝试进行连接 （导致总共 10 个同时连接），则此尝试将失败，并显示以下错误消息：
  
- **错误**： *New PSSession: [admin.vdomain.com] 连接到远程服务器 admin.vdomain.com 失败，出现以下错误消息： WS 管理服务无法处理此请求。已超出此租户的并发外壳的最大数量。关闭现有命令行程序或提高本组织的配额。有关详细信息，请参阅 [远程故障诊断] (https://docs.microsoft.com/en-us/powershell/module/microsoft.powershell.core/about/about_remote_troubleshooting?view=powershell-5.1 *

- **解决方案**： 要解决此问题的唯一方法是关闭一个或多个以前的连接。 当您完成了与 Skype 业务联机会话时，我们建议使用**删除 PSSession** cmdlet 以终止该会话。 这将有助于防止出现此问题。  
 
## <a name="related-topics"></a>相关主题
[设置计算机上的 Skype 业务在线管理使用 Windows PowerShell](set-up-your-computer-for-windows-powershell.md)

  
 

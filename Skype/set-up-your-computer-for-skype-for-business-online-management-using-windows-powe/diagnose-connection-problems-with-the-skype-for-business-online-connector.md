---
title: "诊断连接问题的 Skype for Business Online 连接器"
ms.author: tonysmit
author: tonysmit
ms.date: 5/17/2017
ms.audience: Admin
ms.topic: troubleshooting
ms.prod: office-online-server
localization_priority: Normal
ms.collection: Adm_Skype4B_Online
ms.assetid: 866fadfd-16e2-4134-95db-c6aed7678416
description: "Troubleshoot creating a remote PowerShell session to connect to Skype for Business Online, including Import-Module, concurrent shell, Live ID, and permission errors."
---

# 诊断连接问题的 Skype for Business Online 连接器

> [!IMPORTANT]
> 本文是由机器翻译的，请参阅[免责声明](866fadfd-16e2-4134-95db-c6aed7678416.md#MT_Footer)。请在 [此处](https://support.office.com/en-us/article/866fadfd-16e2-4134-95db-c6aed7678416) 中查找本文的英文版本以便参考。
  
本主题提供了可帮助您诊断和解决当您尝试创建连接到Skype for Business Online远程Microsoft PowerShell会话时出现问题的信息。请参阅以下部分︰
  
- [导入模块错误引起的 Windows PowerShell 执行策略](866fadfd-16e2-4134-95db-c6aed7678416.md#BKMK_PowerShellExecutionPolicy)
    
- [导入模块错误引起的 Windows PowerShell 版本不正确](866fadfd-16e2-4134-95db-c6aed7678416.md#BKMK_IncorrectVersion)
    
- [无法连接到 Live ID 服务器](866fadfd-16e2-4134-95db-c6aed7678416.md#BKMK_FailedConnect)
    
- [无法加载 Live ID 模块](866fadfd-16e2-4134-95db-c6aed7678416.md#BKMK_FailedLoad)
    
- [登录失败的用户](866fadfd-16e2-4134-95db-c6aed7678416.md#BKMK_LogonFailed)
    
- [用户没有权限管理该租户](866fadfd-16e2-4134-95db-c6aed7678416.md#BKMK_UserPermission)
    
- [能够连接到租户中已禁用 Skype for Business Online](866fadfd-16e2-4134-95db-c6aed7678416.md#BKMK_AbilityConnect)
    
- [在 Skype for Business Online 此用户的并发外壳的最大数目超过了](866fadfd-16e2-4134-95db-c6aed7678416.md#BKMK_MaxNumberShellsUser)
    
- [在 Skype for Business Online 此租户的并发外壳的最大数目超过了](866fadfd-16e2-4134-95db-c6aed7678416.md#BKMK_MaxNumberShellsTenant)
    
## 导入模块错误引起的 Windows PowerShell 执行策略
<a name="BKMK_PowerShellExecutionPolicy"> </a>

PowerShell执行策略帮助确定哪些配置文件可以加载到PowerShell控制台，并从该控制台的脚本用户可以运行。至少Skype for Business Online 连接器模块不能导入，除非已设置为 RemoteSigned 执行策略。如果仍然存在，然后当您尝试导入该模块将收到以下错误消息︰
  
```
Import-Module : File C:\\Program Files\\Common Files\\Microsoft Lync Server 2013\\Modules\\LyncOnlineConnector\\LyncOnlineConnectorStartup.psm1 cannot be loaded because running scripts is disabled on this system. For more information, see about_Execution_Policies at https://go.microsoft.com/fwlink/?LinkID=135170.
```

要解决此问题，启动PowerShell作为管理员，然后运行以下命令︰
  
```
Set-ExecutionPolicy RemoteSigned
```

有关执行策略的详细信息，请参阅[有关执行策略](https://go.microsoft.com/fwlink/?LinkID=135170)。
  
## 导入模块错误引起的 Windows PowerShell 版本不正确
<a name="BKMK_IncorrectVersion"> </a>

仅在Windows PowerShell 3.0下，可以运行Skype for Business Online 连接器模块 。如果您尝试导入在早期版本的PowerShell下模块，导入过程将失败与此类似的错误消息︰
  
```
Import-Module : The version of the loaded PowerShell is '2.0'. The module 'D:\\Program Files\\Common Files\\Microsoft Lync Server 2013\\Modules\\LyncOnlineConnector\\LyncOnlineConnector.psd1' requires a minimum PowerShell version of '3.0' to execute. Please verify the installation of the PowerShell and try again.
```

若要修复此问题的唯一方法是安装Windows PowerShell 3.0，可从在[http://www.microsoft.com/en-us/download/details.aspx?id=29939](http://www.microsoft.com/en-us/download/details.aspx?id=29939)Microsoft 下载中心 。
  
## 无法连接到 Live ID 服务器
<a name="BKMK_FailedConnect"> </a>

通常，有三个为什么连接尝试可能会失败并出现以下错误消息的原因︰
  
```
Get-CsWebTicket : Failed to connect live id servers. Make sure proxy is enabled or machine has network connection to live id servers.
```

通常此错误意味着Microsoft Online Services 登录助手未在运行。您可以通过从PowerShell提示符中运行以下命令验证此服务的状态︰
  
```
Get-Service "msoidsvc"
```

如果未运行该服务，请使用此命令启动服务︰
  
```
Start-Service "msoidsvc"
```

如果正在运行该服务，您可能会遇到问题的网络连接您的计算机和 Microsoft Live ID 身份验证服务器之间。要检查此问题，请打开 Internet Explorer，导航到[https://login.microsoftonline.com/。](https://login.microsoftonline.com/.)请尝试从这里Office 365登录。如果失败，您可能遇到的网络连接问题。
  
不太常见的是，则可能 Microsoft Live ID 身份验证服务器连接 URI 确认已配置为错误值。如果您已经确定登录助手正在运行，并且您没有遇到网络连接问题，这可能是问题。在此例中，请联系Office 365支持。
  
## 无法加载 Live ID 模块
<a name="BKMK_FailedLoad"> </a>

有关使用PowerShell管理Skype for Business Online先决条件之一是安装Microsoft Online Services 登录助手。如果未安装登录助手，您将收到以下错误消息，当您尝试建立与Skype for Business Online远程会话︰
  
```
Get-CsWebTicket : Can not load Live Id module. Make sure correct version of Live Id Sign-in assistant is installed.
```

在[Microsoft Online Services 登录助手的 IT 专业人员的一项](https://www.microsoft.com/en-us/download/details.aspx?id=28177)Microsoft 下载中心Microsoft Online Services 登录助手有。
  
## 登录失败的用户
<a name="BKMK_LogonFailed"> </a>

当您尝试远程连接到Skype for Business Online时，您必须提供的用户名和密码的有效Skype for Business Online用户帐户。如果您没有登录将会失败，以及与此类似一条错误消息︰
  
```
Get-CsWebTicket : Logon failed for the user 'kenmyer@litwareinc.com'. Please create a new PSCredential object, making sure that you have used the correct user name and password.
```

如果您认为您正在使用有效的用户帐户，并且您有正确的密码，请尝试重新登录。如果失败，使用相同的凭据，然后尝试在[https://login.microsoftonline.com/](https://login.microsoftonline.com/)上登录。如果您不能有登录，请联系Office 365支持。
  
## 用户没有权限管理该租户
<a name="BKMK_UserPermission"> </a>

您不能进行Skype for Business Online远程PowerShell连接，除非您是租户管理员组的成员。如果您未连接尝试将失败，并且您将收到以下错误消息︰
  
```
New-PSSession : [admin.vdomain.com] Processing data from remote server admin.vdomain.com failed with the following error message: The user 'user@foo.com' does not have permission to manage this tenant. Permissions can be granted by assigning the user to the appropriate RBAC role. For more information, see the about_Remote_Troubleshooting Help topic.
```

如果您认为您，或者是应在组的成员租户管理员，您需要联系Office 365支持。
  
## 能够连接到租户中已禁用 Skype for Business Online
<a name="BKMK_AbilityConnect"> </a>

若要使用PowerShell管理Skype for Business Online，必须将您的租户PowerShell策略的 EnableRemotePowerShellAccess 属性设置为 `True`。如果不是这样，您的连接会失败，并将收到以下错误消息︰
  
```
New-PSSession : [admin.vdomain.com] Processing data from remote server admin.vdomain.com failed with the following error message: The ability to connect to this tenant by using a remote PowerShell session has been disabled. Please contact Lync Help to check Tenant Powershell Policy of this tenant. For more information, see the about_Remote_Troubleshooting Help topic.
```

如果您看到此错误消息，您需要联系Office 365支持并启用远程PowerShell访问。
  
## 在 Skype for Business Online 此用户的并发外壳的最大数目超过了
<a name="BKMK_MaxNumberShellsUser"> </a>

每个管理员允许三个远程连接到Skype for Business Online最大值。如果您有三个远程PowerShell连接设置和运行，请尝试第四个同时连接将失败，并出现以下错误消息︰
  
```
New-PSSession : [admin.vdomain.com] Connecting to remote server admin.vdomain.com failed with the following error message : The WS-Management service cannot process the request. The maximum number of concurrent shells for this user has been exceeded. Close existing shells or raise the quota for this user. For more information, see the about_Remote_Troubleshooting Help topic.
```

若要解决此问题的唯一方法是以关闭一个或多个以前的连接。与Skype for Business Online会话完成后，我们建议使用 **Remove-PSSession** cmdlet 终止会话。这将帮助您避免此问题。
  
## 在 Skype for Business Online 此租户的并发外壳的最大数目超过了
<a name="BKMK_MaxNumberShellsTenant"> </a>

虽然每个管理员允许具有到Skype for Business Online租户的多达三个连接，但没有单个租户允许有多个九个同时连接。例如，三个管理员可能各有三个打开的会话。如果第四个管理员尝试建立连接 （导致 10 个连接的总计），则此尝试将失败，并出现以下错误消息︰
  
```
New-PSSession : [admin.vdomain.com] Connecting to remote server admin.vdomain.com failed with the following error message : The WS-Management service cannot process the request. The maximum number of concurrent shells for this tenant has been exceeded. Close existing shells or raise the quota for this tenant. For more information, see the about_Remote_Troubleshooting Help topic.
```

若要解决此问题的唯一方法是关闭一个或多个以前的连接。与Skype for Business Online会话完成后，我们建议使用 **Remove-PSSession** cmdlet 终止该会话。这将帮助您避免此问题。
  
## 
<a name="MT_Footer"> </a>

> [!NOTE]
> **机器翻译免责声明**：本文是由无人工介入的计算机系统翻译的。Microsoft 提供机器翻译是为了帮助非英语国家/地区用户方便阅读有关 Microsoft 产品、服务和技术的内容。由于机器翻译的原因，本文可能包含词汇、语法或文法方面的错误。 
  


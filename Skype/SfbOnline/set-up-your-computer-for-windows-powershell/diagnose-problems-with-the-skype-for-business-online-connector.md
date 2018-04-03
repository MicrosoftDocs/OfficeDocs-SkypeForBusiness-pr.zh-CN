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
# <a name="diagnose-connection-problems-with-the-skype-for-business-online-connector"></a><span data-ttu-id="47432-103">诊断连接问题与 Skype 业务在线连接器</span><span class="sxs-lookup"><span data-stu-id="47432-103">Diagnose connection problems with the Skype for Business Online Connector</span></span>

<span data-ttu-id="47432-104">本主题提供了可帮助您诊断并解决问题，当您尝试创建远程 Microsoft PowerShell 会话连接到 Skype 的在线业务可能发生的信息。</span><span class="sxs-lookup"><span data-stu-id="47432-104">This topic provides information that will help you diagnose and resolve problems that can occur when you try to create a remote Microsoft PowerShell session that connects to Skype for Business Online.</span></span> <span data-ttu-id="47432-105">请参阅以下各节：</span><span class="sxs-lookup"><span data-stu-id="47432-105">See the following sections:</span></span>
  
- [<span data-ttu-id="47432-106">由 Windows PowerShell 执行策略的导入模块错误</span><span class="sxs-lookup"><span data-stu-id="47432-106">Import-Module error caused by Windows PowerShell execution policy</span></span>](diagnose-problems-with-the-skype-for-business-online-connector.md#BKMKPowerShellExecutionPolicy)
    
- [<span data-ttu-id="47432-107">导入模块错误由 Windows PowerShell 的版本不正确</span><span class="sxs-lookup"><span data-stu-id="47432-107">Import-Module Error caused by incorrect version of Windows PowerShell</span></span>](diagnose-problems-with-the-skype-for-business-online-connector.md#BKMKIncorrectVersion)
    
- [<span data-ttu-id="47432-108">未能连接到 Live ID 服务器</span><span class="sxs-lookup"><span data-stu-id="47432-108">Failed to connect to Live ID Server</span></span>](diagnose-problems-with-the-skype-for-business-online-connector.md#BKMKFailedConnect)
    
- [<span data-ttu-id="47432-109">未能加载 Live ID 模块</span><span class="sxs-lookup"><span data-stu-id="47432-109">Failed to load Live ID module</span></span>](diagnose-problems-with-the-skype-for-business-online-connector.md#BKMKFailedLoad)
    
- [<span data-ttu-id="47432-110">登录失败的用户</span><span class="sxs-lookup"><span data-stu-id="47432-110">Logon failed for the user</span></span>](diagnose-problems-with-the-skype-for-business-online-connector.md#BKMKLogonFailed)
    
- [<span data-ttu-id="47432-111">用户没有权限，管理本组织</span><span class="sxs-lookup"><span data-stu-id="47432-111">The user does not have permission to manage this tenant</span></span>](diagnose-problems-with-the-skype-for-business-online-connector.md#BKMKUserPermission)
    
- [<span data-ttu-id="47432-112">能够连接到组织中已禁用 Skype 的在线业务</span><span class="sxs-lookup"><span data-stu-id="47432-112">Ability to connect to tenant has been disabled in Skype for Business Online</span></span>](diagnose-problems-with-the-skype-for-business-online-connector.md#BKMKAbilityConnect)
    
- [<span data-ttu-id="47432-113">已超出此用户 Skype 的在线业务中的并发外壳的最大数量</span><span class="sxs-lookup"><span data-stu-id="47432-113">The maximum number of concurrent shells for this user in Skype for Business Online has been exceeded </span></span>](diagnose-problems-with-the-skype-for-business-online-connector.md#BKMK_MaxNumberShellsUser)
    
- [<span data-ttu-id="47432-114">已超出此租户在 Skype 的在线业务中的并发外壳的最大数量</span><span class="sxs-lookup"><span data-stu-id="47432-114">The maximum number of concurrent shells for this tenant in Skype for Business Online has been exceeded </span></span>](diagnose-problems-with-the-skype-for-business-online-connector.md#BKMK_MaxNumberShellsTenant)
    
## <a name="import-module-error-caused-by-windows-powershell-execution-policy"></a><span data-ttu-id="47432-115">由 Windows PowerShell 执行策略的导入模块错误</span><span class="sxs-lookup"><span data-stu-id="47432-115">Import-Module error caused by Windows PowerShell execution policy</span></span>
<span data-ttu-id="47432-116"><a name="BKMKPowerShellExecutionPolicy"> </a></span><span class="sxs-lookup"><span data-stu-id="47432-116"></span></span>

<span data-ttu-id="47432-117">PowerShell 执行策略有助于确定哪些配置文件可以加载到 PowerShell 控制台中，并且该脚本的用户可以从该控制台上运行。</span><span class="sxs-lookup"><span data-stu-id="47432-117">The PowerShell execution policy helps to determine which configuration files can be loaded into the PowerShell console, and which scripts a user can run from that console.</span></span> <span data-ttu-id="47432-118">至少，Skype 业务在线连接器模块不能被导入，除非已设置为 RemoteSigned 执行策略。</span><span class="sxs-lookup"><span data-stu-id="47432-118">At a minimum, the Skype for Business Online Connector module cannot be imported unless the execution policy has been set to RemoteSigned.</span></span> <span data-ttu-id="47432-119">如果还没有，然后当您试图导入模块时将收到以下错误消息：</span><span class="sxs-lookup"><span data-stu-id="47432-119">If it has not, then you will receive the following error message when you attempt to import the module:</span></span>
  
- <span data-ttu-id="47432-120">**错误**： 导入模块*： 文件 c:\\程序文件\\通用文件\\Microsoft Lync Server 2013\\模块\\LyncOnlineConnector\\LyncOnlineConnectorStartup.psm1 无法加载，因为运行在此系统上已禁用脚本。有关详细信息，请参阅在 about_Execution_Policies https://go.microsoft.com/fwlink/?LinkID=135170。*</span><span class="sxs-lookup"><span data-stu-id="47432-120">**Error**: *Import-Module : File C:\\Program Files\\Common Files\\Microsoft Lync Server 2013\\Modules\\LyncOnlineConnector\\LyncOnlineConnectorStartup.psm1 cannot be loaded because running scripts is disabled on this system. For more information, see about_Execution_Policies at https://go.microsoft.com/fwlink/?LinkID=135170.*</span></span>

- <span data-ttu-id="47432-121">**解析**要解决此问题，请以管理员的身份，开始 PowerShell，然后运行下面的命令：</span><span class="sxs-lookup"><span data-stu-id="47432-121">**Resolution** To resolve this issue, start PowerShell as an administrator, and then run the following command:</span></span>
    ```
    Set-ExecutionPolicy RemoteSigned
    ```
    <span data-ttu-id="47432-122">执行策略的详细信息，请参阅[关于执行策略](https://go.microsoft.com/fwlink/?LinkID=135170)。</span><span class="sxs-lookup"><span data-stu-id="47432-122">For details about execution policy, see [About Execution Policies](https://go.microsoft.com/fwlink/?LinkID=135170).</span></span>
  
## <a name="import-module-error-caused-by-incorrect-version-of-windows-powershell"></a><span data-ttu-id="47432-123">导入模块错误由 Windows PowerShell 的版本不正确</span><span class="sxs-lookup"><span data-stu-id="47432-123">Import-Module Error caused by incorrect version of Windows PowerShell</span></span>
<span data-ttu-id="47432-124"><a name="BKMKIncorrectVersion"> </a></span><span class="sxs-lookup"><span data-stu-id="47432-124"></span></span>

<span data-ttu-id="47432-125">可以仅在 Windows PowerShell 3.0 下运行 Skype 业务在线连接器模块。</span><span class="sxs-lookup"><span data-stu-id="47432-125">The Skype for Business Online Connector module can be run only under Windows PowerShell 3.0.</span></span> <span data-ttu-id="47432-126">如果您尝试导入模块下 PowerShell 的早期版本，导入过程将失败并显示错误消息类似于下面：</span><span class="sxs-lookup"><span data-stu-id="47432-126">If you try to import the module under a previous version of PowerShell, the import process will fail with an error message similar to this:</span></span>
  
  - <span data-ttu-id="47432-127">**错误**： 导入模块*： 载入 PowerShell 的版本是"2.0"。模块 d:\\程序文件\\通用文件\\Microsoft Lync Server 2013\\模块\\LyncOnlineConnector\\LyncOnlineConnector.psd1 需要最小 PowerShell 版本的"3.0"执行。请验证安装的 PowerShell，然后再试一次。*</span><span class="sxs-lookup"><span data-stu-id="47432-127">**Error**: *Import-Module : The version of the loaded PowerShell is '2.0'. The module 'D:\\Program Files\\Common Files\\Microsoft Lync Server 2013\\Modules\\LyncOnlineConnector\\LyncOnlineConnector.psd1' requires a minimum PowerShell version of '3.0' to execute. Please verify the installation of the PowerShell and try again.*</span></span>

- <span data-ttu-id="47432-128">**解决方案**： 要解决该问题的唯一方法就是安装 Windows PowerShell 3.0，可从 Microsoft 下载中心获取[https://www.microsoft.com/en-us/download/details.aspx?id=34595](https://www.microsoft.com/en-us/download/details.aspx?id=34595)。</span><span class="sxs-lookup"><span data-stu-id="47432-128">**Resolution**: The only way to fix this problem is to install Windows PowerShell 3.0, which is available from the Microsoft Download Center at [https://www.microsoft.com/en-us/download/details.aspx?id=34595](https://www.microsoft.com/en-us/download/details.aspx?id=34595).</span></span>
  
## <a name="failed-to-connect-to-live-id-server"></a><span data-ttu-id="47432-129">未能连接到 Live ID 服务器</span><span class="sxs-lookup"><span data-stu-id="47432-129">Failed to connect to Live ID Server</span></span>
<span data-ttu-id="47432-130"><a name="BKMKFailedConnect"> </a></span><span class="sxs-lookup"><span data-stu-id="47432-130"></span></span>

<span data-ttu-id="47432-131">通常有三个原因为什么您的连接尝试可能会失败并显示以下错误消息：</span><span class="sxs-lookup"><span data-stu-id="47432-131">There are typically three reasons why your connection attempt might fail with the following error message:</span></span>

  - <span data-ttu-id="47432-132">**错误**： 获取 CsWebTicket *： 连接活动 id 的服务器失败。请确保启用了代理或者机器具有 live id 的服务器的网络连接。*</span><span class="sxs-lookup"><span data-stu-id="47432-132">**Error**: *Get-CsWebTicket : Failed to connect live id servers. Make sure proxy is enabled or machine has network connection to live id servers.*</span></span>

- <span data-ttu-id="47432-133">**解析**： 此错误通常意味着助手登录 Microsoft 在线服务未在运行。</span><span class="sxs-lookup"><span data-stu-id="47432-133">**Resolution**: Often this error means that the Microsoft Online Services Sign-in Assistant is not running.</span></span> <span data-ttu-id="47432-134">您可以验证此服务的状态 PowerShell 提示符下运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="47432-134">You can verify the status of this service by running the following command from the PowerShell prompt:</span></span> 
    ```
    Get-Service "msoidsvc"
    ```
    <span data-ttu-id="47432-135">如果该服务未运行，请使用此命令启动服务：</span><span class="sxs-lookup"><span data-stu-id="47432-135">If the service is not running, start the service by using this command:</span></span>
    ```
    Start-Service "msoidsvc"
    ```

    <span data-ttu-id="47432-136">如果该服务正在运行，您可能会遇到网络连接问题您的计算机与 Microsoft Live ID 身份验证服务器之间。</span><span class="sxs-lookup"><span data-stu-id="47432-136">If the service is running, you might be encountering problems with the network connection between your computer and the Microsoft Live ID Authentication Server.</span></span> <span data-ttu-id="47432-137">要检查此项，打开 Internet Explorer，然后定位到[https://login.microsoftonline.com/。](https://login.microsoftonline.com/.)</span><span class="sxs-lookup"><span data-stu-id="47432-137">To check this, open Internet Explorer and navigate to [https://login.microsoftonline.com/.](https://login.microsoftonline.com/.)</span></span> <span data-ttu-id="47432-138">尝试登录到 Office 365 从那里。</span><span class="sxs-lookup"><span data-stu-id="47432-138">Try logging on to Office 365 from there.</span></span> <span data-ttu-id="47432-139">如果此操作失败，则您可能遇到网络连接问题。</span><span class="sxs-lookup"><span data-stu-id="47432-139">If this fails, you are probably experiencing network connection issues.</span></span>
  
    <span data-ttu-id="47432-140">不太常见的情况是，可能是连接 URI 为 Microsoft Live ID 身份验证服务器已被配置为不正确的值。</span><span class="sxs-lookup"><span data-stu-id="47432-140">Less commonly, it is possible that the Connection URI for Microsoft Live ID Authentication Server has been configured to the wrong value.</span></span> <span data-ttu-id="47432-141">如果您已经确定登录助手正在运行，并且您没有遇到网络连接问题，这可能是问题。</span><span class="sxs-lookup"><span data-stu-id="47432-141">If you've already determined that the Sign-In Assistant is running and that you are not experiencing network connectivity issues, this might be the issue.</span></span> <span data-ttu-id="47432-142">在这种情况下，与 Office 365 支持联系。</span><span class="sxs-lookup"><span data-stu-id="47432-142">In this case, contact Office 365 Support.</span></span>
  
## <a name="failed-to-load-live-id-module"></a><span data-ttu-id="47432-143">未能加载 Live ID 模块</span><span class="sxs-lookup"><span data-stu-id="47432-143">Failed to load Live ID module</span></span>
<span data-ttu-id="47432-144"><a name="BKMKFailedLoad"> </a></span><span class="sxs-lookup"><span data-stu-id="47432-144"></span></span>

<span data-ttu-id="47432-145">有关使用 PowerShell 管理 Skype 的在线业务的前提条件之一是安装 Microsoft 在线服务登录的助手。</span><span class="sxs-lookup"><span data-stu-id="47432-145">One of the prerequisites for using PowerShell to manage Skype for Business Online is to install the Microsoft Online Services Sign-in Assistant.</span></span> <span data-ttu-id="47432-146">如果未安装登录的助手，将收到下面的错误消息，当您尝试建立在线业务与 Skype 的远程会话：</span><span class="sxs-lookup"><span data-stu-id="47432-146">If the Sign-in Assistant is not installed, you will receive the following error message when you try to establish a remote session with Skype for Business Online:</span></span>

- <span data-ttu-id="47432-147">**错误**： 获取 CsWebTicket *： 无法加载 Live Id 模块。请确保正确安装版本的 Live Id 登录助手。*</span><span class="sxs-lookup"><span data-stu-id="47432-147">**Error**: *Get-CsWebTicket : Can not load Live Id module. Make sure correct version of Live Id Sign-in assistant is installed.*</span></span>

- <span data-ttu-id="47432-148">**解决方法**： 在 Microsoft 下载中心在[Microsoft 联机服务登录助手为 IT 专业人员的一项](https://www.microsoft.com/en-us/download/details.aspx?id=28177)在线服务的 Microsoft 的签到助手是可用</span><span class="sxs-lookup"><span data-stu-id="47432-148">**Resolution**: The Microsoft Online Services Sign-in Assistant is available in the Microsoft Download Center at [Microsoft Online Services Sign-In Assistant for IT Professionals RTW](https://www.microsoft.com/en-us/download/details.aspx?id=28177)</span></span>

## <a name="logon-failed-for-the-user"></a><span data-ttu-id="47432-149">登录失败的用户</span><span class="sxs-lookup"><span data-stu-id="47432-149">Logon failed for the user</span></span>
<span data-ttu-id="47432-150"><a name="BKMKLogonFailed"> </a></span><span class="sxs-lookup"><span data-stu-id="47432-150"></span></span>

<span data-ttu-id="47432-151">当您尝试建立远程连接到 Skype 的在线业务时，必须提供用户名和密码有效 Skype 的在线业务的用户帐户。</span><span class="sxs-lookup"><span data-stu-id="47432-151">When you attempt to make a remote connection to Skype for Business Online, you must supply the user name and password of a valid Skype for Business Online user account.</span></span> <span data-ttu-id="47432-152">如果不这样做，则登录将失败以及与以下类似的错误消息：</span><span class="sxs-lookup"><span data-stu-id="47432-152">If you do not, logon will fail along with an error message similar to this:</span></span>

- <span data-ttu-id="47432-153">**错误**： 获取 CsWebTicket *： 登录失败，用户 kenmyer@litwareinc.com。请创建一个新的 PSCredential 对象，并确保使用正确的用户名称和密码。*</span><span class="sxs-lookup"><span data-stu-id="47432-153">**Error**: *Get-CsWebTicket : Logon failed for the user 'kenmyer@litwareinc.com'. Please create a new PSCredential object, making sure that you have used the correct user name and password.*</span></span>

- <span data-ttu-id="47432-154">**解决方案**： 如果您认为您使用有效的用户帐户，您拥有正确的密码，请尝试重新登录。</span><span class="sxs-lookup"><span data-stu-id="47432-154">**Resolution**: If you think that you are using a valid user account and that you have the correct password, try logging on again.</span></span> <span data-ttu-id="47432-155">如果查找失败，使用相同的凭据并尝试登录[https://login.microsoftonline.com/](https://login.microsoftonline.com/)。</span><span class="sxs-lookup"><span data-stu-id="47432-155">If that fails, use the same credentials and try to log on at [https://login.microsoftonline.com/](https://login.microsoftonline.com/).</span></span> <span data-ttu-id="47432-156">如果您仍无法登录存在，请与 Office 365 的支持。</span><span class="sxs-lookup"><span data-stu-id="47432-156">If you are unable to log on there, contact Office 365 Support.</span></span> 

  
## <a name="the-user-does-not-have-permission-to-manage-this-tenant"></a><span data-ttu-id="47432-157">用户没有权限，管理本组织</span><span class="sxs-lookup"><span data-stu-id="47432-157">The user does not have permission to manage this tenant</span></span>
<span data-ttu-id="47432-158"><a name="BKMKUserPermission"> </a></span><span class="sxs-lookup"><span data-stu-id="47432-158"></span></span>

<span data-ttu-id="47432-159">除非您是租户管理员组的成员，不能进行远程的 PowerShell 连接 toSkype 在线业务。</span><span class="sxs-lookup"><span data-stu-id="47432-159">You cannot make a remote PowerShell connection toSkype for Business Online unless you are a member of the Tenant Administrators group.</span></span> <span data-ttu-id="47432-160">如果不是，您的连接尝试将会失败，并且您将收到以下错误消息：</span><span class="sxs-lookup"><span data-stu-id="47432-160">If you are not, your connection attempt will fail, and you'll receive the following error message:</span></span>

- <span data-ttu-id="47432-161">**错误**： *New PSSession: [admin.vdomain.com] 处理从远程服务器 admin.vdomain.com 的数据失败，出现以下错误消息: user@foo.com 的用户没有权限，管理本组织。可以通过将用户分配给相应的 RBAC 角色授予权限。有关详细信息，请参阅[远程故障诊断](https://docs.microsoft.com/en-us/powershell/module/microsoft.powershell.core/about/about_remote_troubleshooting?view=powershell-5.1)的。*</span><span class="sxs-lookup"><span data-stu-id="47432-161">**Error**: *New-PSSession : [admin.vdomain.com] Processing data from remote server admin.vdomain.com failed with the following error message: The user 'user@foo.com' does not have permission to manage this tenant. Permissions can be granted by assigning the user to the appropriate RBAC role. For more information, see the [Remote Troubleshooting](https://docs.microsoft.com/en-us/powershell/module/microsoft.powershell.core/about/about_remote_troubleshooting?view=powershell-5.1).*</span></span>

- <span data-ttu-id="47432-162">**解决方案**： 如果您认为您是，或者应该是，成员的租户管理员组中，您将需要与 Office 365 支持部门联系。</span><span class="sxs-lookup"><span data-stu-id="47432-162">**Resolution**: If you think that you are, or are supposed to be, a member of the Tenant Administrators group, you'll need to contact Office 365 Support.</span></span>
  
## <a name="ability-to-connect-to-tenant-has-been-disabled-in-skype-for-business-online"></a><span data-ttu-id="47432-163">能够连接到组织中已禁用 Skype 的在线业务</span><span class="sxs-lookup"><span data-stu-id="47432-163">Ability to connect to tenant has been disabled in Skype for Business Online</span></span>
<span data-ttu-id="47432-164"><a name="BKMKAbilityConnect"> </a></span><span class="sxs-lookup"><span data-stu-id="47432-164"></span></span>

<span data-ttu-id="47432-165">若要使用 PowerShell 管理 Skype 的在线业务，您租户 PowerShell 策略的 EnableRemotePowerShellAccess 属性必须设置为`True`。</span><span class="sxs-lookup"><span data-stu-id="47432-165">To use PowerShell to manage Skype for Business Online, the EnableRemotePowerShellAccess property of your tenant PowerShell policy must be set to  `True`.</span></span> <span data-ttu-id="47432-166">如果不是，您的连接将会失败，并且您将收到以下错误消息：</span><span class="sxs-lookup"><span data-stu-id="47432-166">If it is not, your connection will fail, and you'll receive the following error message:</span></span>

- <span data-ttu-id="47432-167">**错误**： *New PSSession: [admin.vdomain.com] 处理从远程服务器 admin.vdomain.com 的数据失败，出现以下错误消息： 使用远程 PowerShell 会话连接到该租户的能力已被禁用。请联系 Lync 帮助检查该租户的租户 Powershell 策略。有关详细信息，请参阅[远程故障诊断](https://docs.microsoft.com/en-us/powershell/module/microsoft.powershell.core/about/about_remote_troubleshooting?view=powershell-5.1)的。*</span><span class="sxs-lookup"><span data-stu-id="47432-167">**Error**: *New-PSSession : [admin.vdomain.com] Processing data from remote server admin.vdomain.com failed with the following error message: The ability to connect to this tenant by using a remote PowerShell session has been disabled. Please contact Lync Help to check Tenant Powershell Policy of this tenant. For more information, see the [Remote Troubleshooting](https://docs.microsoft.com/en-us/powershell/module/microsoft.powershell.core/about/about_remote_troubleshooting?view=powershell-5.1).*</span></span>

- <span data-ttu-id="47432-168">**解决方案**： 如果您看到此错误消息，则需要联系 Office 365 支持并启用远程 PowerShell 访问。</span><span class="sxs-lookup"><span data-stu-id="47432-168">**Resolution**: If you see this error message, you'll need to contact Office 365 Support and get remote PowerShell access enabled.</span></span>
  
## <a name="the-maximum-number-of-concurrent-shells-for-this-user-in-skype-for-business-online-has-been-exceeded"></a><span data-ttu-id="47432-169">已超出此用户 Skype 的在线业务中的并发外壳的最大数量</span><span class="sxs-lookup"><span data-stu-id="47432-169">The maximum number of concurrent shells for this user in Skype for Business Online has been exceeded</span></span>
<span data-ttu-id="47432-170"><a name="BKMKMaxNumberShellsUser"> </a></span><span class="sxs-lookup"><span data-stu-id="47432-170"></span></span>

<span data-ttu-id="47432-171">每个管理员允许的最多的三个同时远程连接到 Skype 的在线业务。</span><span class="sxs-lookup"><span data-stu-id="47432-171">Each administrator is allowed a maximum of three simultaneous remote connections to Skype for Business Online.</span></span> <span data-ttu-id="47432-172">如果您有三个向上的远程 PowerShell 连接和运行，使第四个同时发生的任何尝试连接将失败，并显示以下错误消息：</span><span class="sxs-lookup"><span data-stu-id="47432-172">If you have three remote PowerShell connections up and running, any attempt to make a fourth simultaneous connection will fail, with the following error message:</span></span>

- <span data-ttu-id="47432-173">**错误**： *New PSSession: [admin.vdomain.com] 连接到远程服务器 admin.vdomain.com 失败，出现以下错误消息： WS 管理服务无法处理此请求。已超出此用户的并发外壳的最大数量。关闭现有命令行程序或引发此用户的配额。有关详细信息，请参阅 [远程故障诊断] (https://docs.microsoft.com/en-us/powershell/module/microsoft.powershell.core/about/about_remote_troubleshooting?view=powershell-5.1 *</span><span class="sxs-lookup"><span data-stu-id="47432-173">**Error**: *New-PSSession : [admin.vdomain.com] Connecting to remote server admin.vdomain.com failed with the following error message : The WS-Management service cannot process the request. The maximum number of concurrent shells for this user has been exceeded. Close existing shells or raise the quota for this user. For more information, see the [Remote Troubleshooting](https://docs.microsoft.com/en-us/powershell/module/microsoft.powershell.core/about/about_remote_troubleshooting?view=powershell-5.1*</span></span>

- <span data-ttu-id="47432-174">**解决方案**： 要解决此问题的唯一方法是关闭一个或多个以前的连接。</span><span class="sxs-lookup"><span data-stu-id="47432-174">**Resolution**: The only way to resolve this issue is to close one or more of the previous connections.</span></span> <span data-ttu-id="47432-175">当您完成了与 Skype 业务联机会话时，我们建议使用**删除 PSSession** cmdlet 以终止会话。</span><span class="sxs-lookup"><span data-stu-id="47432-175">When you are finished with a Skype for Business Online session, we recommend that you use the **Remove-PSSession** cmdlet to terminate the session.</span></span> <span data-ttu-id="47432-176">这将有助于防止出现此问题。</span><span class="sxs-lookup"><span data-stu-id="47432-176">This will help you to prevent this issue.</span></span>
  
## <a name="the-maximum-number-of-concurrent-shells-for-this-tenant-in-skype-for-business-online-has-been-exceeded"></a><span data-ttu-id="47432-177">已超出此租户在 Skype 的在线业务中的并发外壳的最大数量</span><span class="sxs-lookup"><span data-stu-id="47432-177">The maximum number of concurrent shells for this tenant in Skype for Business Online has been exceeded</span></span>
<span data-ttu-id="47432-178"><a name="BKMKMaxNumberShellsTenant"> </a></span><span class="sxs-lookup"><span data-stu-id="47432-178"></span></span>

<span data-ttu-id="47432-179">虽然每个管理员可拥有三个同时连接到 Skype 的在线业务的租户，则允许没有单个租户有 9 个以上的并发连接。</span><span class="sxs-lookup"><span data-stu-id="47432-179">Although each administrator is allowed to have as many as three simultaneous connections to a Skype for Business Online tenant, no single tenant is allowed to have more than nine simultaneous connections.</span></span> <span data-ttu-id="47432-180">例如，三种管理员每个有三个打开的会话。</span><span class="sxs-lookup"><span data-stu-id="47432-180">For example, three administrators might each have three open sessions.</span></span> <span data-ttu-id="47432-181">如果第四个管理员尝试进行连接 （导致总共 10 个同时连接），则此尝试将失败，并显示以下错误消息：</span><span class="sxs-lookup"><span data-stu-id="47432-181">If a fourth administrator tries to make a connection (resulting in a total of 10 simultaneous connections), this attempt will fail, with the following error message:</span></span>
  
- <span data-ttu-id="47432-182">**错误**： *New PSSession: [admin.vdomain.com] 连接到远程服务器 admin.vdomain.com 失败，出现以下错误消息： WS 管理服务无法处理此请求。已超出此租户的并发外壳的最大数量。关闭现有命令行程序或提高本组织的配额。有关详细信息，请参阅 [远程故障诊断] (https://docs.microsoft.com/en-us/powershell/module/microsoft.powershell.core/about/about_remote_troubleshooting?view=powershell-5.1 *</span><span class="sxs-lookup"><span data-stu-id="47432-182">**Error**: *New-PSSession : [admin.vdomain.com] Connecting to remote server admin.vdomain.com failed with the following error message : The WS-Management service cannot process the request. The maximum number of concurrent shells for this tenant has been exceeded. Close existing shells or raise the quota for this tenant. For more information, see the [Remote Troubleshooting](https://docs.microsoft.com/en-us/powershell/module/microsoft.powershell.core/about/about_remote_troubleshooting?view=powershell-5.1*</span></span>

- <span data-ttu-id="47432-183">**解决方案**： 要解决此问题的唯一方法是关闭一个或多个以前的连接。</span><span class="sxs-lookup"><span data-stu-id="47432-183">**Resolution**: The only way to resolve this issue is to close one or more of the previous connections.</span></span> <span data-ttu-id="47432-184">当您完成了与 Skype 业务联机会话时，我们建议使用**删除 PSSession** cmdlet 以终止该会话。</span><span class="sxs-lookup"><span data-stu-id="47432-184">When you are finished with a Skype for Business Online session, we recommend that you use the **Remove-PSSession** cmdlet to terminate that session.</span></span> <span data-ttu-id="47432-185">这将有助于防止出现此问题。</span><span class="sxs-lookup"><span data-stu-id="47432-185">This will help you to prevent this issue.</span></span>  
 
## <a name="related-topics"></a><span data-ttu-id="47432-186">相关主题</span><span class="sxs-lookup"><span data-stu-id="47432-186">Related topics</span></span>
[<span data-ttu-id="47432-187">设置计算机上的 Skype 业务在线管理使用 Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="47432-187">Set up your computer for skype for business online management using Windows PowerShell</span></span>](set-up-your-computer-for-windows-powershell.md)

  
 

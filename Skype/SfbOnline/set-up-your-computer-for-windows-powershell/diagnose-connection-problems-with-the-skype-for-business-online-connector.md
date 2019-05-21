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
description: 有关创建用于连接到 Skype for business Online 的远程 PowerShell 会话的疑难解答, 包括导入模块、并发 shell、实时 ID 和权限错误。
ms.openlocfilehash: be3fc4d3597e00ae2274bc8793a5f99091384713
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34284864"
---
# <a name="diagnose-connection-problems-with-the-skype-for-business-online-connector"></a><span data-ttu-id="2b85a-103">诊断与 Skype for Business Online 连接器的连接问题</span><span class="sxs-lookup"><span data-stu-id="2b85a-103">Diagnose connection problems with the Skype for Business Online Connector</span></span>

<span data-ttu-id="2b85a-104">本主题提供的信息可帮助你诊断和解决尝试创建连接到 Skype for business Online 的远程 Microsoft PowerShell 会话时可能出现的问题。</span><span class="sxs-lookup"><span data-stu-id="2b85a-104">This topic provides information that will help you diagnose and resolve problems that can occur when you try to create a remote Microsoft PowerShell session that connects to Skype for Business Online.</span></span> <span data-ttu-id="2b85a-105">请参阅以下部分:</span><span class="sxs-lookup"><span data-stu-id="2b85a-105">See the following sections:</span></span>
  
- [<span data-ttu-id="2b85a-106">Windows PowerShell 执行策略导致的导入模块错误</span><span class="sxs-lookup"><span data-stu-id="2b85a-106">Import-Module error caused by Windows PowerShell execution policy</span></span>](diagnose-connection-problems-with-the-skype-for-business-online-connector.md#BKMKPowerShellExecutionPolicy)
    
- [<span data-ttu-id="2b85a-107">由不正确版本的 Windows PowerShell 导致的导入模块错误</span><span class="sxs-lookup"><span data-stu-id="2b85a-107">Import-Module Error caused by incorrect version of Windows PowerShell</span></span>](diagnose-connection-problems-with-the-skype-for-business-online-connector.md#BKMKIncorrectVersion)
    
- [<span data-ttu-id="2b85a-108">无法连接到 Live ID 服务器</span><span class="sxs-lookup"><span data-stu-id="2b85a-108">Failed to connect to Live ID Server</span></span>](diagnose-connection-problems-with-the-skype-for-business-online-connector.md#BKMKFailedConnect)
    
- [<span data-ttu-id="2b85a-109">无法加载实时 ID 模块</span><span class="sxs-lookup"><span data-stu-id="2b85a-109">Failed to load Live ID module</span></span>](diagnose-connection-problems-with-the-skype-for-business-online-connector.md#BKMKFailedLoad)
    
- [<span data-ttu-id="2b85a-110">用户登录失败</span><span class="sxs-lookup"><span data-stu-id="2b85a-110">Logon failed for the user</span></span>](diagnose-connection-problems-with-the-skype-for-business-online-connector.md#BKMKLogonFailed)
    
- [<span data-ttu-id="2b85a-111">用户没有管理此租户的权限</span><span class="sxs-lookup"><span data-stu-id="2b85a-111">The user does not have permission to manage this tenant</span></span>](diagnose-connection-problems-with-the-skype-for-business-online-connector.md#BKMKUserPermission)
    
- [<span data-ttu-id="2b85a-112">Skype for Business Online 中已禁用连接到租户的功能</span><span class="sxs-lookup"><span data-stu-id="2b85a-112">Ability to connect to tenant has been disabled in Skype for Business Online</span></span>](diagnose-connection-problems-with-the-skype-for-business-online-connector.md#BKMKAbilityConnect)
    
- [<span data-ttu-id="2b85a-113">已超出 Skype for Business Online 中此用户的并发 shell 的最大数量</span><span class="sxs-lookup"><span data-stu-id="2b85a-113">The maximum number of concurrent shells for this user in Skype for Business Online has been exceeded</span></span>](diagnose-connection-problems-with-the-skype-for-business-online-connector.md#BKMKMaxNumberShellsUser)
    
- [<span data-ttu-id="2b85a-114">已超出 Skype for Business Online 中此租户的最大并发 shell 数</span><span class="sxs-lookup"><span data-stu-id="2b85a-114">The maximum number of concurrent shells for this tenant in Skype for Business Online has been exceeded</span></span>](diagnose-connection-problems-with-the-skype-for-business-online-connector.md#BKMK_MaxNumberShellsTenant)
    
## <a name="import-module-error-caused-by-windows-powershell-execution-policy"></a><span data-ttu-id="2b85a-115">Windows PowerShell 执行策略导致的导入模块错误</span><span class="sxs-lookup"><span data-stu-id="2b85a-115">Import-Module error caused by Windows PowerShell execution policy</span></span>
<span data-ttu-id="2b85a-116"><a name="BKMKPowerShellExecutionPolicy"> </a></span><span class="sxs-lookup"><span data-stu-id="2b85a-116"></span></span>

<span data-ttu-id="2b85a-117">PowerShell 执行策略有助于确定哪些配置文件可以加载到 PowerShell 控制台, 以及用户可以从该控制台运行哪些脚本。</span><span class="sxs-lookup"><span data-stu-id="2b85a-117">The PowerShell execution policy helps to determine which configuration files can be loaded into the PowerShell console, and which scripts a user can run from that console.</span></span> <span data-ttu-id="2b85a-118">除非已将执行策略设置为 RemoteSigned, 否则, 至少无法导入 Skype for Business Online 连接器模块。</span><span class="sxs-lookup"><span data-stu-id="2b85a-118">At a minimum, the Skype for Business Online Connector module cannot be imported unless the execution policy has been set to RemoteSigned.</span></span> <span data-ttu-id="2b85a-119">如果不是这样, 当您尝试导入该模块时, 您将收到以下错误消息:</span><span class="sxs-lookup"><span data-stu-id="2b85a-119">If it has not, then you will receive the following error message when you attempt to import the module:</span></span>
  
- <span data-ttu-id="2b85a-120">**错误**:<em>导入-模块: 文件 C\\: 程序\\文件常见\\文件 Microsoft Lync Server\\2013\\模块\\LyncOnlineConnector LyncOnlineConnectorStartup。无法加载 psm1, 因为运行在此系统上禁用了脚本。有关详细信息, 请参阅 about_Execution_Policies https://go.microsoft.com/fwlink/?LinkID=135170。</em></span><span class="sxs-lookup"><span data-stu-id="2b85a-120">**Error**: <em>Import-Module : File C:\\Program Files\\Common Files\\Microsoft Lync Server 2013\\Modules\\LyncOnlineConnector\\LyncOnlineConnectorStartup.psm1 cannot be loaded because running scripts is disabled on this system. For more information, see about_Execution_Policies at https://go.microsoft.com/fwlink/?LinkID=135170.</em></span></span>

- <span data-ttu-id="2b85a-121">**解决方案**: 若要解决此问题, 请以管理员身份启动 PowerShell, 然后运行以下命令:</span><span class="sxs-lookup"><span data-stu-id="2b85a-121">**Resolution**: To resolve this issue, start PowerShell as an administrator, and then run the following command:</span></span>
    ```
    Set-ExecutionPolicy RemoteSigned
    ```
    <span data-ttu-id="2b85a-122">有关执行策略的详细信息, 请参阅[关于执行策略](https://go.microsoft.com/fwlink/?LinkID=135170)。</span><span class="sxs-lookup"><span data-stu-id="2b85a-122">For details about execution policy, see [About Execution Policies](https://go.microsoft.com/fwlink/?LinkID=135170).</span></span>
  
## <a name="import-module-error-caused-by-incorrect-version-of-windows-powershell"></a><span data-ttu-id="2b85a-123">由不正确版本的 Windows PowerShell 导致的导入模块错误</span><span class="sxs-lookup"><span data-stu-id="2b85a-123">Import-Module Error caused by incorrect version of Windows PowerShell</span></span>
<span data-ttu-id="2b85a-124"><a name="BKMKIncorrectVersion"> </a></span><span class="sxs-lookup"><span data-stu-id="2b85a-124"></span></span>

<span data-ttu-id="2b85a-125">Skype for Business Online 连接器模块只能在 Windows PowerShell 3.0 下运行。</span><span class="sxs-lookup"><span data-stu-id="2b85a-125">The Skype for Business Online Connector module can be run only under Windows PowerShell 3.0.</span></span> <span data-ttu-id="2b85a-126">如果你尝试在早期版本的 PowerShell 下导入该模块, 则导入过程将失败, 并出现类似以下内容的错误消息:</span><span class="sxs-lookup"><span data-stu-id="2b85a-126">If you try to import the module under a previous version of PowerShell, the import process will fail with an error message similar to this:</span></span>
  
  - <span data-ttu-id="2b85a-127">**错误**:*导入-模块: 加载的 PowerShell 的版本为 "2.0"。该模块的:\\程序文件\\常见文件\\Microsoft Lync Server 2013\\模块\\LyncOnlineConnector\\LyncOnlineConnector "psd1" 需要 "3.0" 的最低 PowerShell 版本才能执行。请验证 PowerShell 的安装并重试。*</span><span class="sxs-lookup"><span data-stu-id="2b85a-127">**Error**: *Import-Module : The version of the loaded PowerShell is '2.0'. The module 'D:\\Program Files\\Common Files\\Microsoft Lync Server 2013\\Modules\\LyncOnlineConnector\\LyncOnlineConnector.psd1' requires a minimum PowerShell version of '3.0' to execute. Please verify the installation of the PowerShell and try again.*</span></span>

- <span data-ttu-id="2b85a-128">**解决方案**: 修复此问题的唯一方法是安装 Windows PowerShell 3.0, 可从 Microsoft 下载中心获取该功能[https://www.microsoft.com/en-us/download/details.aspx?id=34595](https://www.microsoft.com/en-us/download/details.aspx?id=34595)。</span><span class="sxs-lookup"><span data-stu-id="2b85a-128">**Resolution**: The only way to fix this problem is to install Windows PowerShell 3.0, which is available from the Microsoft Download Center at [https://www.microsoft.com/en-us/download/details.aspx?id=34595](https://www.microsoft.com/en-us/download/details.aspx?id=34595).</span></span>
  
## <a name="failed-to-connect-to-live-id-server"></a><span data-ttu-id="2b85a-129">无法连接到 Live ID 服务器</span><span class="sxs-lookup"><span data-stu-id="2b85a-129">Failed to connect to Live ID Server</span></span>
<span data-ttu-id="2b85a-130"><a name="BKMKFailedConnect"> </a></span><span class="sxs-lookup"><span data-stu-id="2b85a-130"></span></span>

<span data-ttu-id="2b85a-131">连接尝试可能失败的原因通常有三个, 并显示以下错误消息:</span><span class="sxs-lookup"><span data-stu-id="2b85a-131">There are typically three reasons why your connection attempt might fail with the following error message:</span></span>

  - <span data-ttu-id="2b85a-132">**错误**: *CsWebTicket: 无法连接 live id 服务器。确保已启用代理, 或者计算机具有与 live id 服务器的网络连接。*</span><span class="sxs-lookup"><span data-stu-id="2b85a-132">**Error**: *Get-CsWebTicket : Failed to connect live id servers. Make sure proxy is enabled or machine has network connection to live id servers.*</span></span>

- <span data-ttu-id="2b85a-133">**解决方案**: 此错误通常表示 Microsoft Online Services 登录助手未运行。</span><span class="sxs-lookup"><span data-stu-id="2b85a-133">**Resolution**: Often this error means that the Microsoft Online Services Sign-in Assistant is not running.</span></span> <span data-ttu-id="2b85a-134">你可以通过从 PowerShell 提示符运行以下命令来验证此服务的状态:</span><span class="sxs-lookup"><span data-stu-id="2b85a-134">You can verify the status of this service by running the following command from the PowerShell prompt:</span></span> 
    ```
    Get-Service "msoidsvc"
    ```
    <span data-ttu-id="2b85a-135">如果服务未运行, 请使用以下命令启动服务:</span><span class="sxs-lookup"><span data-stu-id="2b85a-135">If the service is not running, start the service by using this command:</span></span>
    ```
    Start-Service "msoidsvc"
    ```

    <span data-ttu-id="2b85a-136">如果服务正在运行, 则你的计算机和 Microsoft Live ID 身份验证服务器之间的网络连接可能会遇到问题。</span><span class="sxs-lookup"><span data-stu-id="2b85a-136">If the service is running, you might be encountering problems with the network connection between your computer and the Microsoft Live ID Authentication Server.</span></span> <span data-ttu-id="2b85a-137">若要检查此情况, 请打开 Internet Explorer, 然后导航到[ https://login.microsoftonline.com/。](https://login.microsoftonline.com/.)</span><span class="sxs-lookup"><span data-stu-id="2b85a-137">To check this, open Internet Explorer and navigate to [https://login.microsoftonline.com/.](https://login.microsoftonline.com/.)</span></span> <span data-ttu-id="2b85a-138">尝试从此处登录到 Office 365。</span><span class="sxs-lookup"><span data-stu-id="2b85a-138">Try logging on to Office 365 from there.</span></span> <span data-ttu-id="2b85a-139">如果此操作失败, 则你可能遇到网络连接问题。</span><span class="sxs-lookup"><span data-stu-id="2b85a-139">If this fails, you are probably experiencing network connection issues.</span></span>
  
    <span data-ttu-id="2b85a-140">通常情况下, Microsoft Live ID 身份验证服务器的连接 URI 可能已配置为错误值。</span><span class="sxs-lookup"><span data-stu-id="2b85a-140">Less commonly, it is possible that the Connection URI for Microsoft Live ID Authentication Server has been configured to the wrong value.</span></span> <span data-ttu-id="2b85a-141">如果你已确定登录助手正在运行, 但你未遇到网络连接问题, 则可能是此问题。</span><span class="sxs-lookup"><span data-stu-id="2b85a-141">If you've already determined that the Sign-In Assistant is running and that you are not experiencing network connectivity issues, this might be the issue.</span></span> <span data-ttu-id="2b85a-142">在这种情况下, 请联系 Office 365 支持人员。</span><span class="sxs-lookup"><span data-stu-id="2b85a-142">In this case, contact Office 365 Support.</span></span>
  
## <a name="failed-to-load-live-id-module"></a><span data-ttu-id="2b85a-143">无法加载实时 ID 模块</span><span class="sxs-lookup"><span data-stu-id="2b85a-143">Failed to load Live ID module</span></span>
<span data-ttu-id="2b85a-144"><a name="BKMKFailedLoad"> </a></span><span class="sxs-lookup"><span data-stu-id="2b85a-144"></span></span>

<span data-ttu-id="2b85a-145">使用 PowerShell 管理 Skype for Business Online 的先决条件之一是安装 Microsoft Online Services 登录助手。</span><span class="sxs-lookup"><span data-stu-id="2b85a-145">One of the prerequisites for using PowerShell to manage Skype for Business Online is to install the Microsoft Online Services Sign-in Assistant.</span></span> <span data-ttu-id="2b85a-146">如果未安装登录助手, 当您尝试建立与 Skype for Business Online 的远程会话时, 将收到以下错误消息:</span><span class="sxs-lookup"><span data-stu-id="2b85a-146">If the Sign-in Assistant is not installed, you will receive the following error message when you try to establish a remote session with Skype for Business Online:</span></span>

- <span data-ttu-id="2b85a-147">**错误**: *CsWebTicket: 无法加载 "实时 Id" 模块。请确保安装了正确版本的 Live Id 登录助手。*</span><span class="sxs-lookup"><span data-stu-id="2b85a-147">**Error**: *Get-CsWebTicket : Can not load Live Id module. Make sure correct version of Live Id Sign-in assistant is installed.*</span></span>

- <span data-ttu-id="2b85a-148">**解决方案**: Microsoft Online Services 登录助手适用于[IT 专业人员的 Microsoft Online services 登录助手](https://www.microsoft.com/en-us/download/details.aspx?id=28177)的 microsoft 下载中心 RTW</span><span class="sxs-lookup"><span data-stu-id="2b85a-148">**Resolution**: The Microsoft Online Services Sign-in Assistant is available in the Microsoft Download Center at [Microsoft Online Services Sign-In Assistant for IT Professionals RTW](https://www.microsoft.com/en-us/download/details.aspx?id=28177)</span></span>

## <a name="logon-failed-for-the-user"></a><span data-ttu-id="2b85a-149">用户登录失败</span><span class="sxs-lookup"><span data-stu-id="2b85a-149">Logon failed for the user</span></span>
<span data-ttu-id="2b85a-150"><a name="BKMKLogonFailed"> </a></span><span class="sxs-lookup"><span data-stu-id="2b85a-150"></span></span>

<span data-ttu-id="2b85a-151">当您尝试建立与 Skype for business Online 的远程连接时, 您必须提供有效的 Skype for business Online 用户帐户的用户名和密码。</span><span class="sxs-lookup"><span data-stu-id="2b85a-151">When you attempt to make a remote connection to Skype for Business Online, you must supply the user name and password of a valid Skype for Business Online user account.</span></span> <span data-ttu-id="2b85a-152">如果不这样做, 登录将失败, 并出现类似下面的错误消息:</span><span class="sxs-lookup"><span data-stu-id="2b85a-152">If you do not, logon will fail along with an error message similar to this:</span></span>

- <span data-ttu-id="2b85a-153">**错误**: *CsWebTicket: 登录用户 ' kenmyer@litwareinc.com ' 失败。请创建一个新的 PSCredential 对象, 确保您使用了正确的用户名和密码。*</span><span class="sxs-lookup"><span data-stu-id="2b85a-153">**Error**: *Get-CsWebTicket : Logon failed for the user 'kenmyer@litwareinc.com'. Please create a new PSCredential object, making sure that you have used the correct user name and password.*</span></span>

- <span data-ttu-id="2b85a-154">**解决方案**: 如果你认为你使用的是有效的用户帐户, 并且你拥有正确的密码, 请尝试再次登录。</span><span class="sxs-lookup"><span data-stu-id="2b85a-154">**Resolution**: If you think that you are using a valid user account and that you have the correct password, try logging on again.</span></span> <span data-ttu-id="2b85a-155">如果此操作失败, 请使用相同的凭据, 然后尝试登录[https://login.microsoftonline.com/](https://login.microsoftonline.com/)。</span><span class="sxs-lookup"><span data-stu-id="2b85a-155">If that fails, use the same credentials and try to log on at [https://login.microsoftonline.com/](https://login.microsoftonline.com/).</span></span> <span data-ttu-id="2b85a-156">如果您无法登录, 请联系 Office 365 支持。</span><span class="sxs-lookup"><span data-stu-id="2b85a-156">If you are unable to log on there, contact Office 365 Support.</span></span> 

  
## <a name="the-user-does-not-have-permission-to-manage-this-tenant"></a><span data-ttu-id="2b85a-157">用户没有管理此租户的权限</span><span class="sxs-lookup"><span data-stu-id="2b85a-157">The user does not have permission to manage this tenant</span></span>
<span data-ttu-id="2b85a-158"><a name="BKMKUserPermission"> </a></span><span class="sxs-lookup"><span data-stu-id="2b85a-158"></span></span>

<span data-ttu-id="2b85a-159">除非您是租户管理员组的成员, 否则不能创建远程 PowerShell 连接 Skype for Business Online。</span><span class="sxs-lookup"><span data-stu-id="2b85a-159">You cannot make a remote PowerShell connection toSkype for Business Online unless you are a member of the Tenant Administrators group.</span></span> <span data-ttu-id="2b85a-160">如果不是, 则连接尝试将失败, 您将收到以下错误消息:</span><span class="sxs-lookup"><span data-stu-id="2b85a-160">If you are not, your connection attempt will fail, and you'll receive the following error message:</span></span>

- <span data-ttu-id="2b85a-161">**错误**:*新建-PSSession: [admin.vdomain.com] 从远程服务器 admin.vdomain.com 处理数据失败, 出现以下错误消息: 用户 "user@foo.com" 没有管理此租户的权限。可通过将用户分配给相应的 RBAC 角色来授予权限。有关详细信息, 请参阅[远程故障排除](https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_remote_troubleshooting?view=powershell-5.1)。*</span><span class="sxs-lookup"><span data-stu-id="2b85a-161">**Error**: *New-PSSession : [admin.vdomain.com] Processing data from remote server admin.vdomain.com failed with the following error message: The user 'user@foo.com' does not have permission to manage this tenant. Permissions can be granted by assigning the user to the appropriate RBAC role. For more information, see the [Remote Troubleshooting](https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_remote_troubleshooting?view=powershell-5.1).*</span></span>

- <span data-ttu-id="2b85a-162">**解决方案**: 如果你认为你是或应该是租户管理员组的成员, 则需要联系 Office 365 支持。</span><span class="sxs-lookup"><span data-stu-id="2b85a-162">**Resolution**: If you think that you are, or are supposed to be, a member of the Tenant Administrators group, you'll need to contact Office 365 Support.</span></span>
  
## <a name="ability-to-connect-to-tenant-has-been-disabled-in-skype-for-business-online"></a><span data-ttu-id="2b85a-163">Skype for Business Online 中已禁用连接到租户的功能</span><span class="sxs-lookup"><span data-stu-id="2b85a-163">Ability to connect to tenant has been disabled in Skype for Business Online</span></span>
<span data-ttu-id="2b85a-164"><a name="BKMKAbilityConnect"> </a></span><span class="sxs-lookup"><span data-stu-id="2b85a-164"></span></span>

<span data-ttu-id="2b85a-165">若要使用 PowerShell 管理 Skype for Business Online, 租户 PowerShell 策略的 EnableRemotePowerShellAccess 属性必须设置为`True`。</span><span class="sxs-lookup"><span data-stu-id="2b85a-165">To use PowerShell to manage Skype for Business Online, the EnableRemotePowerShellAccess property of your tenant PowerShell policy must be set to  `True`.</span></span> <span data-ttu-id="2b85a-166">如果不是, 您的连接将失败, 您将收到以下错误消息:</span><span class="sxs-lookup"><span data-stu-id="2b85a-166">If it is not, your connection will fail, and you'll receive the following error message:</span></span>

- <span data-ttu-id="2b85a-167">**错误**:*新建-PSSession: [admin.vdomain.com] 从远程服务器 admin.vdomain.com 处理数据失败, 出现以下错误消息: 已禁用通过使用远程 PowerShell 会话连接到此租户的功能。请联系 Lync 帮助以检查此租户的租户 Powershell 策略。有关详细信息, 请参阅[远程故障排除](https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_remote_troubleshooting?view=powershell-5.1)。*</span><span class="sxs-lookup"><span data-stu-id="2b85a-167">**Error**: *New-PSSession : [admin.vdomain.com] Processing data from remote server admin.vdomain.com failed with the following error message: The ability to connect to this tenant by using a remote PowerShell session has been disabled. Please contact Lync Help to check Tenant Powershell Policy of this tenant. For more information, see the [Remote Troubleshooting](https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_remote_troubleshooting?view=powershell-5.1).*</span></span>

- <span data-ttu-id="2b85a-168">**解决方案**: 如果看到此错误消息, 则需要联系 Office 365 支持并启用远程 PowerShell 访问。</span><span class="sxs-lookup"><span data-stu-id="2b85a-168">**Resolution**: If you see this error message, you'll need to contact Office 365 Support and get remote PowerShell access enabled.</span></span>
  
## <a name="the-maximum-number-of-concurrent-shells-for-this-user-in-skype-for-business-online-has-been-exceeded"></a><span data-ttu-id="2b85a-169">已超出 Skype for Business Online 中此用户的并发 shell 的最大数量</span><span class="sxs-lookup"><span data-stu-id="2b85a-169">The maximum number of concurrent shells for this user in Skype for Business Online has been exceeded</span></span>
<span data-ttu-id="2b85a-170"><a name="BKMKMaxNumberShellsUser"> </a></span><span class="sxs-lookup"><span data-stu-id="2b85a-170"></span></span>

<span data-ttu-id="2b85a-171">每个管理员最多允许同时有三个与 Skype for business Online 的远程连接。</span><span class="sxs-lookup"><span data-stu-id="2b85a-171">Each administrator is allowed a maximum of three simultaneous remote connections to Skype for Business Online.</span></span> <span data-ttu-id="2b85a-172">如果有三个远程 PowerShell 连接正常运行, 则连接第四个同时连接的任何尝试都将失败, 并出现以下错误消息:</span><span class="sxs-lookup"><span data-stu-id="2b85a-172">If you have three remote PowerShell connections up and running, any attempt to make a fourth simultaneous connection will fail, with the following error message:</span></span>

- <span data-ttu-id="2b85a-173">**错误**:\*新的 PSSession: [admin.vdomain.com] 连接到远程服务器 admin.vdomain.com 失败, 出现以下错误消息: ws-management 服务无法处理该请求。已超出此用户的并发 shell 的最大数量。关闭现有外壳程序或提高此用户的配额。有关详细信息, 请参阅 [远程疑难解答] (https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_remote_troubleshooting?view=powershell-5.1 \*</span><span class="sxs-lookup"><span data-stu-id="2b85a-173">**Error**: *New-PSSession : [admin.vdomain.com] Connecting to remote server admin.vdomain.com failed with the following error message : The WS-Management service cannot process the request. The maximum number of concurrent shells for this user has been exceeded. Close existing shells or raise the quota for this user. For more information, see the [Remote Troubleshooting](https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_remote_troubleshooting?view=powershell-5.1*</span></span>

- <span data-ttu-id="2b85a-174">**解决方案**: 解决此问题的唯一方法是关闭一个或多个以前的连接。</span><span class="sxs-lookup"><span data-stu-id="2b85a-174">**Resolution**: The only way to resolve this issue is to close one or more of the previous connections.</span></span> <span data-ttu-id="2b85a-175">使用 Skype for Business Online 会话完成后, 建议使用**Remove-PSSession** cmdlet 终止会话。</span><span class="sxs-lookup"><span data-stu-id="2b85a-175">When you are finished with a Skype for Business Online session, we recommend that you use the **Remove-PSSession** cmdlet to terminate the session.</span></span> <span data-ttu-id="2b85a-176">这将帮助您避免此问题。</span><span class="sxs-lookup"><span data-stu-id="2b85a-176">This will help you to prevent this issue.</span></span>
  
## <a name="the-maximum-number-of-concurrent-shells-for-this-tenant-in-skype-for-business-online-has-been-exceeded"></a><span data-ttu-id="2b85a-177">已超出 Skype for Business Online 中此租户的最大并发 shell 数</span><span class="sxs-lookup"><span data-stu-id="2b85a-177">The maximum number of concurrent shells for this tenant in Skype for Business Online has been exceeded</span></span>
<span data-ttu-id="2b85a-178"><a name="BKMKMaxNumberShellsTenant"> </a></span><span class="sxs-lookup"><span data-stu-id="2b85a-178"></span></span>

<span data-ttu-id="2b85a-179">虽然每个管理员都允许将多达三个同时连接到 Skype for Business Online 租户, 但不允许单个租户具有超过9个同时连接。</span><span class="sxs-lookup"><span data-stu-id="2b85a-179">Although each administrator is allowed to have as many as three simultaneous connections to a Skype for Business Online tenant, no single tenant is allowed to have more than nine simultaneous connections.</span></span> <span data-ttu-id="2b85a-180">例如, 三个管理员可能都有三个打开的会话。</span><span class="sxs-lookup"><span data-stu-id="2b85a-180">For example, three administrators might each have three open sessions.</span></span> <span data-ttu-id="2b85a-181">如果第四个管理员尝试建立连接 (总共导致10个同步连接), 此尝试将失败, 并出现以下错误消息:</span><span class="sxs-lookup"><span data-stu-id="2b85a-181">If a fourth administrator tries to make a connection (resulting in a total of 10 simultaneous connections), this attempt will fail, with the following error message:</span></span>
  
- <span data-ttu-id="2b85a-182">**错误**:\*新的 PSSession: [admin.vdomain.com] 连接到远程服务器 admin.vdomain.com 失败, 出现以下错误消息: ws-management 服务无法处理该请求。已超出此租户的并发 shell 的最大数量。关闭现有外壳程序或提高此租户的配额。有关详细信息, 请参阅 [远程疑难解答] (https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_remote_troubleshooting?view=powershell-5.1 \*</span><span class="sxs-lookup"><span data-stu-id="2b85a-182">**Error**: *New-PSSession : [admin.vdomain.com] Connecting to remote server admin.vdomain.com failed with the following error message : The WS-Management service cannot process the request. The maximum number of concurrent shells for this tenant has been exceeded. Close existing shells or raise the quota for this tenant. For more information, see the [Remote Troubleshooting](https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_remote_troubleshooting?view=powershell-5.1*</span></span>

- <span data-ttu-id="2b85a-183">**解决方案**: 解决此问题的唯一方法是关闭一个或多个以前的连接。</span><span class="sxs-lookup"><span data-stu-id="2b85a-183">**Resolution**: The only way to resolve this issue is to close one or more of the previous connections.</span></span> <span data-ttu-id="2b85a-184">使用 Skype for Business Online 会话完成后, 我们建议你使用**Remove-PSSession** cmdlet 终止该会话。</span><span class="sxs-lookup"><span data-stu-id="2b85a-184">When you are finished with a Skype for Business Online session, we recommend that you use the **Remove-PSSession** cmdlet to terminate that session.</span></span> <span data-ttu-id="2b85a-185">这将帮助您避免此问题。</span><span class="sxs-lookup"><span data-stu-id="2b85a-185">This will help you to prevent this issue.</span></span>  
 
## <a name="related-topics"></a><span data-ttu-id="2b85a-186">相关主题</span><span class="sxs-lookup"><span data-stu-id="2b85a-186">Related topics</span></span>
[<span data-ttu-id="2b85a-187">使用 Windows PowerShell 为 skype for business online 管理设置计算机</span><span class="sxs-lookup"><span data-stu-id="2b85a-187">Set up your computer for skype for business online management using Windows PowerShell</span></span>](set-up-your-computer-for-windows-powershell.md)

  
 

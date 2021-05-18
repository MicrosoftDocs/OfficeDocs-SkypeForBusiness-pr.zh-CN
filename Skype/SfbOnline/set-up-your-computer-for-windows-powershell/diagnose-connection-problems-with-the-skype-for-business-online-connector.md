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
ms.openlocfilehash: f4bcb9c758d1660cafd7a6bd3f57c95d6bf3b546
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/06/2021
ms.locfileid: "52238903"
---
# <a name="diagnose-connection-problems-with-the-skype-for-business-online-connector"></a><span data-ttu-id="2d155-103">诊断与 Skype for Business Online 连接器的连接问题</span><span class="sxs-lookup"><span data-stu-id="2d155-103">Diagnose connection problems with the Skype for Business Online Connector</span></span>

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

<span data-ttu-id="2d155-104">本主题提供有助于诊断和解决尝试创建连接到 Skype for Business Online 的远程 Microsoft PowerShell 会话时Skype for Business的信息。</span><span class="sxs-lookup"><span data-stu-id="2d155-104">This topic provides information that will help you diagnose and resolve problems that can occur when you try to create a remote Microsoft PowerShell session that connects to Skype for Business Online.</span></span> <span data-ttu-id="2d155-105">请参阅以下部分：</span><span class="sxs-lookup"><span data-stu-id="2d155-105">See the following sections:</span></span>
  
- [<span data-ttu-id="2d155-106">执行策略导致导入模块Windows PowerShell错误</span><span class="sxs-lookup"><span data-stu-id="2d155-106">Import-Module error caused by Windows PowerShell execution policy</span></span>](diagnose-connection-problems-with-the-skype-for-business-online-connector.md#BKMKPowerShellExecutionPolicy)
    
- [<span data-ttu-id="2d155-107">错误版本错误导致的导入模块错误Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="2d155-107">Import-Module Error caused by incorrect version of Windows PowerShell</span></span>](diagnose-connection-problems-with-the-skype-for-business-online-connector.md#BKMKIncorrectVersion)
    
- [<span data-ttu-id="2d155-108">无法连接到实时 ID 服务器</span><span class="sxs-lookup"><span data-stu-id="2d155-108">Failed to connect to Live ID Server</span></span>](diagnose-connection-problems-with-the-skype-for-business-online-connector.md#BKMKFailedConnect)
    
- [<span data-ttu-id="2d155-109">无法加载实时 ID 模块</span><span class="sxs-lookup"><span data-stu-id="2d155-109">Failed to load Live ID module</span></span>](diagnose-connection-problems-with-the-skype-for-business-online-connector.md#BKMKFailedLoad)
    
- [<span data-ttu-id="2d155-110">用户登录失败</span><span class="sxs-lookup"><span data-stu-id="2d155-110">Logon failed for the user</span></span>](diagnose-connection-problems-with-the-skype-for-business-online-connector.md#BKMKLogonFailed)
    
- [<span data-ttu-id="2d155-111">用户无权管理此租户</span><span class="sxs-lookup"><span data-stu-id="2d155-111">The user does not have permission to manage this tenant</span></span>](diagnose-connection-problems-with-the-skype-for-business-online-connector.md#BKMKUserPermission)
    
- [<span data-ttu-id="2d155-112">在 Skype for Business Online 中禁用了连接到租户的能力</span><span class="sxs-lookup"><span data-stu-id="2d155-112">Ability to connect to tenant has been disabled in Skype for Business Online</span></span>](diagnose-connection-problems-with-the-skype-for-business-online-connector.md#BKMKAbilityConnect)

- [<span data-ttu-id="2d155-113">已超过 Skype for Business Online 中此用户的最大并发 shell 数</span><span class="sxs-lookup"><span data-stu-id="2d155-113">The maximum number of concurrent shells for this user in Skype for Business Online has been exceeded</span></span>](#the-maximum-number-of-concurrent-shells-for-this-user-in-skype-for-business-online-has-been-exceeded)

- [<span data-ttu-id="2d155-114">已超过 Skype for Business Online 中此租户的最大并发 shell 数</span><span class="sxs-lookup"><span data-stu-id="2d155-114">The maximum number of concurrent shells for this tenant in Skype for Business Online has been exceeded</span></span>](#the-maximum-number-of-concurrent-shells-for-this-tenant-in-skype-for-business-online-has-been-exceeded)

    
## <a name="import-module-error-caused-by-windows-powershell-execution-policy"></a><span data-ttu-id="2d155-115">Import-Module策略导致的Windows PowerShell错误</span><span class="sxs-lookup"><span data-stu-id="2d155-115">Import-Module error caused by Windows PowerShell execution policy</span></span>
<span data-ttu-id="2d155-116"><a name="BKMKPowerShellExecutionPolicy"> </a></span><span class="sxs-lookup"><span data-stu-id="2d155-116"><a name="BKMKPowerShellExecutionPolicy"> </a></span></span>

<span data-ttu-id="2d155-117">PowerShell 执行策略可帮助确定哪些配置文件可以加载到 PowerShell 控制台中，以及用户可以从该控制台运行哪些脚本。</span><span class="sxs-lookup"><span data-stu-id="2d155-117">The PowerShell execution policy helps to determine which configuration files can be loaded into the PowerShell console, and which scripts a user can run from that console.</span></span> <span data-ttu-id="2d155-118">除非执行策略Skype for Business RemoteSigned，否则至少无法导入 Skype for Business Online 连接器模块。</span><span class="sxs-lookup"><span data-stu-id="2d155-118">At a minimum, the Skype for Business Online Connector module cannot be imported unless the execution policy has been set to RemoteSigned.</span></span> <span data-ttu-id="2d155-119">如果尚未导入，则尝试导入模块时会收到以下错误消息：</span><span class="sxs-lookup"><span data-stu-id="2d155-119">If it has not, then you will receive the following error message when you attempt to import the module:</span></span>
  
- <span data-ttu-id="2d155-120">**错误**<em>：Import-Module ： 文件 C：程序文件公用文件 \\ Microsoft Lync Server \\ \\ 2013 \\ 模块 \\ LyncOnlineConnector \\ LyncOnlineConnectorStartup.psm1 无法加载，因为在此系统中禁用了正在运行的脚本。有关详细信息，请参阅 在 https://go.microsoft.com/fwlink/?LinkID=135170 about_Execution_Policies。</em></span><span class="sxs-lookup"><span data-stu-id="2d155-120">**Error**: <em>Import-Module : File C:\\Program Files\\Common Files\\Microsoft Lync Server 2013\\Modules\\LyncOnlineConnector\\LyncOnlineConnectorStartup.psm1 cannot be loaded because running scripts is disabled on this system. For more information, see about_Execution_Policies at https://go.microsoft.com/fwlink/?LinkID=135170.</em></span></span>

- <span data-ttu-id="2d155-121">**解决方法**：若要解决此问题，请以管理员角色启动 PowerShell，然后运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="2d155-121">**Resolution**: To resolve this issue, start PowerShell as an administrator, and then run the following command:</span></span>
    ```PowerShell
    Set-ExecutionPolicy RemoteSigned
    ```
    <span data-ttu-id="2d155-122">有关执行策略的详细信息，请参阅 [关于执行策略](/powershell/module/microsoft.powershell.core/about/about_execution_policies)。</span><span class="sxs-lookup"><span data-stu-id="2d155-122">For details about execution policy, see [About Execution Policies](/powershell/module/microsoft.powershell.core/about/about_execution_policies).</span></span>
  
## <a name="import-module-error-caused-by-incorrect-version-of-windows-powershell"></a><span data-ttu-id="2d155-123">Import-Module版本不正确导致的Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="2d155-123">Import-Module Error caused by incorrect version of Windows PowerShell</span></span>
<span data-ttu-id="2d155-124"><a name="BKMKIncorrectVersion"> </a></span><span class="sxs-lookup"><span data-stu-id="2d155-124"><a name="BKMKIncorrectVersion"> </a></span></span>

<span data-ttu-id="2d155-125">Skype for Business Online 连接器模块只能在 Windows PowerShell 3.0 下运行。</span><span class="sxs-lookup"><span data-stu-id="2d155-125">The Skype for Business Online Connector module can be run only under Windows PowerShell 3.0.</span></span> <span data-ttu-id="2d155-126">如果尝试在早期版本的 PowerShell 下导入模块，导入过程会失败，并出现类似于以下的错误消息：</span><span class="sxs-lookup"><span data-stu-id="2d155-126">If you try to import the module under a previous version of PowerShell, the import process will fail with an error message similar to this:</span></span>
  
  - <span data-ttu-id="2d155-127">\**错误\*\*\*：Import-Module：加载的 PowerShell 的版本为"2.0"。模块"D： 程序文件通用文件 \\ \\ Microsoft Lync Server \\ 2013 \\ 模块 \\ LyncOnlineConnectorLyncOnlineConnector.psd1"要求执行最低 \\ PowerShell 版本"3.0"。请验证 PowerShell 的安装，然后重试。*</span><span class="sxs-lookup"><span data-stu-id="2d155-127">**Error**: *Import-Module : The version of the loaded PowerShell is '2.0'. The module 'D:\\Program Files\\Common Files\\Microsoft Lync Server 2013\\Modules\\LyncOnlineConnector\\LyncOnlineConnector.psd1' requires a minimum PowerShell version of '3.0' to execute. Please verify the installation of the PowerShell and try again.*</span></span>

- <span data-ttu-id="2d155-128">**解决方法**：解决此问题的唯一方法就是安装 3.0 Windows PowerShell 3.0，可从 中的 Microsoft 下载中心获得 [https://www.microsoft.com/download/details.aspx?id=34595](https://www.microsoft.com/download/details.aspx?id=34595) 。</span><span class="sxs-lookup"><span data-stu-id="2d155-128">**Resolution**: The only way to fix this problem is to install Windows PowerShell 3.0, which is available from the Microsoft Download Center at [https://www.microsoft.com/download/details.aspx?id=34595](https://www.microsoft.com/download/details.aspx?id=34595).</span></span>
  
## <a name="failed-to-connect-to-live-id-server"></a><span data-ttu-id="2d155-129">无法连接到实时 ID 服务器</span><span class="sxs-lookup"><span data-stu-id="2d155-129">Failed to connect to Live ID Server</span></span>
<span data-ttu-id="2d155-130"><a name="BKMKFailedConnect"> </a></span><span class="sxs-lookup"><span data-stu-id="2d155-130"><a name="BKMKFailedConnect"> </a></span></span>

<span data-ttu-id="2d155-131">连接尝试失败的原因通常有三个，并出现以下错误消息：</span><span class="sxs-lookup"><span data-stu-id="2d155-131">There are typically three reasons why your connection attempt might fail with the following error message:</span></span>

  - <span data-ttu-id="2d155-132">\**错误\*\*\*：Get-CsWebTicket：无法连接实时 ID 服务器。确保已启用代理或计算机已与实时 ID 服务器建立网络连接。*</span><span class="sxs-lookup"><span data-stu-id="2d155-132">**Error**: *Get-CsWebTicket : Failed to connect live id servers. Make sure proxy is enabled or machine has network connection to live id servers.*</span></span>

- <span data-ttu-id="2d155-133">**解决方法**：此错误通常意味着Microsoft Online Services助手未运行。</span><span class="sxs-lookup"><span data-stu-id="2d155-133">**Resolution**: Often this error means that the Microsoft Online Services Sign-in Assistant is not running.</span></span> <span data-ttu-id="2d155-134">可以通过从 PowerShell 提示符运行以下命令来验证此服务的状态：</span><span class="sxs-lookup"><span data-stu-id="2d155-134">You can verify the status of this service by running the following command from the PowerShell prompt:</span></span> 
    ```PowerShell
    Get-Service "msoidsvc"
    ```
    <span data-ttu-id="2d155-135">如果服务未运行，请通过以下命令启动服务：</span><span class="sxs-lookup"><span data-stu-id="2d155-135">If the service is not running, start the service by using this command:</span></span>
    ```PowerShell
    Start-Service "msoidsvc"
    ```

    <span data-ttu-id="2d155-136">如果服务正在运行，则可能会遇到计算机与 Microsoft Live ID 身份验证服务器之间的网络连接问题。</span><span class="sxs-lookup"><span data-stu-id="2d155-136">If the service is running, you might be encountering problems with the network connection between your computer and the Microsoft Live ID Authentication Server.</span></span> <span data-ttu-id="2d155-137">若要检查此状态，请Internet Explorer并导航到[ https://login.microsoftonline.com/ 。](https://login.microsoftonline.com/.)</span><span class="sxs-lookup"><span data-stu-id="2d155-137">To check this, open Internet Explorer and navigate to [https://login.microsoftonline.com/.](https://login.microsoftonline.com/.)</span></span> <span data-ttu-id="2d155-138">尝试从Microsoft 365 Office 365登录。</span><span class="sxs-lookup"><span data-stu-id="2d155-138">Try logging on to Microsoft 365 or Office 365 from there.</span></span> <span data-ttu-id="2d155-139">如果此操作失败，则可能会遇到网络连接问题。</span><span class="sxs-lookup"><span data-stu-id="2d155-139">If this fails, you are probably experiencing network connection issues.</span></span>
  
    <span data-ttu-id="2d155-140">不太常见的是，Microsoft Live ID 身份验证服务器的连接 URI 已配置为错误值。</span><span class="sxs-lookup"><span data-stu-id="2d155-140">Less commonly, it is possible that the Connection URI for Microsoft Live ID Authentication Server has been configured to the wrong value.</span></span> <span data-ttu-id="2d155-141">如果已确定，Sign-In助手正在运行，并且未遇到网络连接问题，则这可能是问题。</span><span class="sxs-lookup"><span data-stu-id="2d155-141">If you've already determined that the Sign-In Assistant is running and that you are not experiencing network connectivity issues, this might be the issue.</span></span> <span data-ttu-id="2d155-142">在这种情况下，请联系 Microsoft 支持部门。</span><span class="sxs-lookup"><span data-stu-id="2d155-142">In this case, contact Microsoft Support.</span></span>
  
## <a name="failed-to-load-live-id-module"></a><span data-ttu-id="2d155-143">无法加载实时 ID 模块</span><span class="sxs-lookup"><span data-stu-id="2d155-143">Failed to load Live ID module</span></span>
<span data-ttu-id="2d155-144"><a name="BKMKFailedLoad"> </a></span><span class="sxs-lookup"><span data-stu-id="2d155-144"><a name="BKMKFailedLoad"> </a></span></span>

<span data-ttu-id="2d155-145">使用 PowerShell 管理 Skype for Business Online 的先决条件之一是安装 Microsoft Online Services 登录助手。</span><span class="sxs-lookup"><span data-stu-id="2d155-145">One of the prerequisites for using PowerShell to manage Skype for Business Online is to install the Microsoft Online Services Sign-in Assistant.</span></span> <span data-ttu-id="2d155-146">如果未安装登录助手，当您尝试与 Skype for Business Online 建立远程会话时，将收到以下错误消息：</span><span class="sxs-lookup"><span data-stu-id="2d155-146">If the Sign-in Assistant is not installed, you will receive the following error message when you try to establish a remote session with Skype for Business Online:</span></span>

- <span data-ttu-id="2d155-147">\**错误\*\*\*：Get-CsWebTicket：无法加载实时 ID 模块。确保安装了正确版本的 Live ID 登录助手。*</span><span class="sxs-lookup"><span data-stu-id="2d155-147">**Error**: *Get-CsWebTicket : Can not load Live Id module. Make sure correct version of Live Id Sign-in assistant is installed.*</span></span>

- <span data-ttu-id="2d155-148">**解决方法**：Microsoft Online Services适用于 IT 专业人员 RTW 的 Microsoft 下载Microsoft Online Services Sign-In [助手中提供了登录助手](https://www.microsoft.com/download/details.aspx?id=28177)</span><span class="sxs-lookup"><span data-stu-id="2d155-148">**Resolution**: The Microsoft Online Services Sign-in Assistant is available in the Microsoft Download Center at [Microsoft Online Services Sign-In Assistant for IT Professionals RTW](https://www.microsoft.com/download/details.aspx?id=28177)</span></span>

## <a name="logon-failed-for-the-user"></a><span data-ttu-id="2d155-149">用户登录失败</span><span class="sxs-lookup"><span data-stu-id="2d155-149">Logon failed for the user</span></span>
<span data-ttu-id="2d155-150"><a name="BKMKLogonFailed"> </a></span><span class="sxs-lookup"><span data-stu-id="2d155-150"><a name="BKMKLogonFailed"> </a></span></span>

<span data-ttu-id="2d155-151">尝试与 Skype for Business Online 建立远程连接时，必须提供有效的 Skype for Business Online 用户帐户的用户名和密码。</span><span class="sxs-lookup"><span data-stu-id="2d155-151">When you attempt to make a remote connection to Skype for Business Online, you must supply the user name and password of a valid Skype for Business Online user account.</span></span> <span data-ttu-id="2d155-152">如果不这样做，登录会失败，并出现类似于以下的错误消息：</span><span class="sxs-lookup"><span data-stu-id="2d155-152">If you do not, logon will fail along with an error message similar to this:</span></span>

- <span data-ttu-id="2d155-153">\**错误\*\*\*：Get-CsWebTicket：用户"kenmyer@litwareinc.com"登录失败。请创建新的 PSCredential 对象，* 确保使用了正确的用户名和密码。</span><span class="sxs-lookup"><span data-stu-id="2d155-153">**Error**: *Get-CsWebTicket : Logon failed for the user 'kenmyer@litwareinc.com'. Please create a new PSCredential object, making sure that you have used the correct user name and password.*</span></span>

- <span data-ttu-id="2d155-154">**解决方法**：如果认为你使用的是有效的用户帐户，并且拥有正确的密码，请尝试再次登录。</span><span class="sxs-lookup"><span data-stu-id="2d155-154">**Resolution**: If you think that you are using a valid user account and that you have the correct password, try logging on again.</span></span> <span data-ttu-id="2d155-155">如果失败，请使用相同的凭据并尝试在 登录 [https://login.microsoftonline.com/](https://login.microsoftonline.com/) 。</span><span class="sxs-lookup"><span data-stu-id="2d155-155">If that fails, use the same credentials and try to log on at [https://login.microsoftonline.com/](https://login.microsoftonline.com/).</span></span> <span data-ttu-id="2d155-156">如果无法登录，请联系 Microsoft 支持部门。</span><span class="sxs-lookup"><span data-stu-id="2d155-156">If you are unable to log on there, contact Microsoft Support.</span></span> 

  
## <a name="the-user-does-not-have-permission-to-manage-this-tenant"></a><span data-ttu-id="2d155-157">用户无权管理此租户</span><span class="sxs-lookup"><span data-stu-id="2d155-157">The user does not have permission to manage this tenant</span></span>
<span data-ttu-id="2d155-158"><a name="BKMKUserPermission"> </a></span><span class="sxs-lookup"><span data-stu-id="2d155-158"><a name="BKMKUserPermission"> </a></span></span>

<span data-ttu-id="2d155-159">无法与Skype for Business Online 建立远程 PowerShell 连接，除非你是租户管理员管理员组。</span><span class="sxs-lookup"><span data-stu-id="2d155-159">You cannot make a remote PowerShell connection toSkype for Business Online unless you are a member of the Tenant Administrators group.</span></span> <span data-ttu-id="2d155-160">如果不是，连接尝试会失败，并且将收到以下错误消息：</span><span class="sxs-lookup"><span data-stu-id="2d155-160">If you are not, your connection attempt will fail, and you'll receive the following error message:</span></span>

- <span data-ttu-id="2d155-161">错误 *：New-PSSession ： [admin.vdomain.com] 处理来自远程服务器 admin.vdomain.com 的数据失败，出现以下错误消息：用户"user@foo.com"无权管理此租户。可以通过将用户分配到相应的 RBAC 角色来授予权限。有关详细信息，请参阅 [远程故障排除](/powershell/module/microsoft.powershell.core/about/about_remote_troubleshooting?view=powershell-5.1)。*</span><span class="sxs-lookup"><span data-stu-id="2d155-161">**Error**: *New-PSSession : [admin.vdomain.com] Processing data from remote server admin.vdomain.com failed with the following error message: The user 'user@foo.com' does not have permission to manage this tenant. Permissions can be granted by assigning the user to the appropriate RBAC role. For more information, see the [Remote Troubleshooting](/powershell/module/microsoft.powershell.core/about/about_remote_troubleshooting?view=powershell-5.1).*</span></span>

- <span data-ttu-id="2d155-162">**解决方法**：如果您认为自己是或应该是租户管理员的成员管理员组，则需要联系 Microsoft 支持部门。</span><span class="sxs-lookup"><span data-stu-id="2d155-162">**Resolution**: If you think that you are, or are supposed to be, a member of the Tenant Administrators group, you'll need to contact Microsoft Support.</span></span>
  
## <a name="ability-to-connect-to-tenant-has-been-disabled-in-skype-for-business-online"></a><span data-ttu-id="2d155-163">在 Skype for Business Online 中禁用了连接到租户的能力</span><span class="sxs-lookup"><span data-stu-id="2d155-163">Ability to connect to tenant has been disabled in Skype for Business Online</span></span>
<span data-ttu-id="2d155-164"><a name="BKMKAbilityConnect"> </a></span><span class="sxs-lookup"><span data-stu-id="2d155-164"><a name="BKMKAbilityConnect"> </a></span></span>

<span data-ttu-id="2d155-165">若要使用 PowerShell 管理 Skype for Business Online，租户 PowerShell 策略的 EnableRemotePowerShellAccess 属性必须设置为 `True` 。</span><span class="sxs-lookup"><span data-stu-id="2d155-165">To use PowerShell to manage Skype for Business Online, the EnableRemotePowerShellAccess property of your tenant PowerShell policy must be set to  `True`.</span></span> <span data-ttu-id="2d155-166">如果不是，连接会失败，并且将收到以下错误消息：</span><span class="sxs-lookup"><span data-stu-id="2d155-166">If it is not, your connection will fail, and you'll receive the following error message:</span></span>

- <span data-ttu-id="2d155-167">错误 *：New-PSSession ： [admin.vdomain.com] 无法处理来自远程服务器 admin.vdomain.com 的数据，并出现以下错误消息：已禁用使用远程 PowerShell 会话连接到此租户的能力。请联系 Lync 帮助以检查此租户的租户 Powershell 策略。有关详细信息，请参阅 [远程故障排除](/powershell/module/microsoft.powershell.core/about/about_remote_troubleshooting?view=powershell-5.1)。*</span><span class="sxs-lookup"><span data-stu-id="2d155-167">**Error**: *New-PSSession : [admin.vdomain.com] Processing data from remote server admin.vdomain.com failed with the following error message: The ability to connect to this tenant by using a remote PowerShell session has been disabled. Please contact Lync Help to check Tenant Powershell Policy of this tenant. For more information, see the [Remote Troubleshooting](/powershell/module/microsoft.powershell.core/about/about_remote_troubleshooting?view=powershell-5.1).*</span></span>

- <span data-ttu-id="2d155-168">**解决方法**：如果看到此错误消息，则需要联系 Microsoft 支持部门并启用远程 PowerShell 访问。</span><span class="sxs-lookup"><span data-stu-id="2d155-168">**Resolution**: If you see this error message, you'll need to contact Microsoft Support and get remote PowerShell access enabled.</span></span>
  
## <a name="the-maximum-number-of-concurrent-shells-for-this-user-in-skype-for-business-online-has-been-exceeded"></a><span data-ttu-id="2d155-169">已超过 Skype for Business Online 中此用户的最大并发 shell 数</span><span class="sxs-lookup"><span data-stu-id="2d155-169">The maximum number of concurrent shells for this user in Skype for Business Online has been exceeded</span></span>
<span data-ttu-id="2d155-170"><a name="BKMKMaxNumberShellsUser"> </a></span><span class="sxs-lookup"><span data-stu-id="2d155-170"><a name="BKMKMaxNumberShellsUser"> </a></span></span>

<span data-ttu-id="2d155-171">每个管理员最多允许三个同时进行远程连接才能连接到 Skype for Business Online。</span><span class="sxs-lookup"><span data-stu-id="2d155-171">Each administrator is allowed a maximum of three simultaneous remote connections to Skype for Business Online.</span></span> <span data-ttu-id="2d155-172">如果已启动并运行三个远程 PowerShell 连接，则尝试进行第四次同时连接的任何尝试都将失败，并出现以下错误消息：</span><span class="sxs-lookup"><span data-stu-id="2d155-172">If you have three remote PowerShell connections up and running, any attempt to make a fourth simultaneous connection will fail, with the following error message:</span></span>

- <span data-ttu-id="2d155-173">\**错误\*\*\*：New-PSSession： [admin.vdomain.com] 连接到远程服务器 admin.vdomain.com 失败，出现以下错误消息：WS-Management 服务无法处理请求。已超过此用户的最大并发 shell 数。关闭现有 shell 或提高此用户的配额。有关详细信息，请参阅 https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_remote_troubleshooting?view=powershell-5.1 [远程故障排除] (*</span><span class="sxs-lookup"><span data-stu-id="2d155-173">**Error**: *New-PSSession : [admin.vdomain.com] Connecting to remote server admin.vdomain.com failed with the following error message : The WS-Management service cannot process the request. The maximum number of concurrent shells for this user has been exceeded. Close existing shells or raise the quota for this user. For more information, see the [Remote Troubleshooting](https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_remote_troubleshooting?view=powershell-5.1*</span></span>

- <span data-ttu-id="2d155-174">**解决方法**：解决此问题的唯一方法就是关闭一个或多个以前的连接。</span><span class="sxs-lookup"><span data-stu-id="2d155-174">**Resolution**: The only way to resolve this issue is to close one or more of the previous connections.</span></span> <span data-ttu-id="2d155-175">完成联机会话Skype for Business，建议使用 **Remove-PSSession** cmdlet 终止会话。</span><span class="sxs-lookup"><span data-stu-id="2d155-175">When you are finished with a Skype for Business Online session, we recommend that you use the **Remove-PSSession** cmdlet to terminate the session.</span></span> <span data-ttu-id="2d155-176">这有助于防止此问题。</span><span class="sxs-lookup"><span data-stu-id="2d155-176">This will help you to prevent this issue.</span></span>
  
## <a name="the-maximum-number-of-concurrent-shells-for-this-tenant-in-skype-for-business-online-has-been-exceeded"></a><span data-ttu-id="2d155-177">已超过 Skype for Business Online 中此租户的最大并发 shell 数</span><span class="sxs-lookup"><span data-stu-id="2d155-177">The maximum number of concurrent shells for this tenant in Skype for Business Online has been exceeded</span></span>
<span data-ttu-id="2d155-178"><a name="BKMKMaxNumberShellsTenant"> </a></span><span class="sxs-lookup"><span data-stu-id="2d155-178"><a name="BKMKMaxNumberShellsTenant"> </a></span></span>

<span data-ttu-id="2d155-179">尽管允许每个管理员同时与 Skype for Business Online 租户建立三个连接，但不允许单个租户同时具有 20 多个连接。</span><span class="sxs-lookup"><span data-stu-id="2d155-179">Although each administrator is allowed to have as many as three simultaneous connections to a Skype for Business Online tenant, no single tenant is allowed to have more than twenty simultaneous connections.</span></span> <span data-ttu-id="2d155-180">例如，六个管理员可能各自有三个打开的会话。</span><span class="sxs-lookup"><span data-stu-id="2d155-180">For example, six administrators might each have three open sessions.</span></span> <span data-ttu-id="2d155-181">如果第七个管理员尝试打开两 (连接，导致总共 21 个连接同时) ，则此尝试会失败，并出现以下错误消息：</span><span class="sxs-lookup"><span data-stu-id="2d155-181">If a seventh administrator tries to open more than two connections (resulting in a total of 21 simultaneous connections), this attempt will fail, with the following error message:</span></span>
  
- <span data-ttu-id="2d155-182">\**错误\*\*\*：New-PSSession： [admin.vdomain.com] 连接到远程服务器 admin.vdomain.com 失败，出现以下错误消息：WS-Management 服务无法处理请求。已超过此租户的最大并发 shell 数。关闭现有 shell 或提高此租户的配额。有关详细信息，请参阅 https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_remote_troubleshooting?view=powershell-5.1 [远程故障排除] (*</span><span class="sxs-lookup"><span data-stu-id="2d155-182">**Error**: *New-PSSession : [admin.vdomain.com] Connecting to remote server admin.vdomain.com failed with the following error message : The WS-Management service cannot process the request. The maximum number of concurrent shells for this tenant has been exceeded. Close existing shells or raise the quota for this tenant. For more information, see the [Remote Troubleshooting](https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_remote_troubleshooting?view=powershell-5.1*</span></span>

- <span data-ttu-id="2d155-183">**解决方法**：解决此问题的唯一方法就是关闭一个或多个以前的连接。</span><span class="sxs-lookup"><span data-stu-id="2d155-183">**Resolution**: The only way to resolve this issue is to close one or more of the previous connections.</span></span> <span data-ttu-id="2d155-184">完成联机会话Skype for Business，建议使用 **Remove-PSSession** cmdlet 终止该会话。</span><span class="sxs-lookup"><span data-stu-id="2d155-184">When you are finished with a Skype for Business Online session, we recommend that you use the **Remove-PSSession** cmdlet to terminate that session.</span></span> <span data-ttu-id="2d155-185">这有助于防止此问题。</span><span class="sxs-lookup"><span data-stu-id="2d155-185">This will help you to prevent this issue.</span></span>  
 
## <a name="related-topics"></a><span data-ttu-id="2d155-186">相关主题</span><span class="sxs-lookup"><span data-stu-id="2d155-186">Related topics</span></span>
[<span data-ttu-id="2d155-187">使用 Skype for business Online 管理设置计算机Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="2d155-187">Set up your computer for skype for business online management using Windows PowerShell</span></span>](set-up-your-computer-for-windows-powershell.md)

  

---
title: 诊断与 Skype for Business Online 连接器的连接问题
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
ms.openlocfilehash: d377d234ff4242ac99d751b1c14d3270e1776c6c
ms.sourcegitcommit: 30620021ceba916a505437ab641a23393f55827a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/15/2018
ms.locfileid: "26530701"
---
# <a name="diagnose-connection-problems-with-the-skype-for-business-online-connector"></a><span data-ttu-id="cbc05-103">诊断与 Skype for Business Online 连接器的连接问题</span><span class="sxs-lookup"><span data-stu-id="cbc05-103">Diagnose connection problems with the Skype for Business Online Connector</span></span>

<span data-ttu-id="cbc05-104">本主题提供将帮助您诊断和解决尝试创建连接到 Skype 业务 online 远程 Microsoft PowerShell 会话时可能出现的问题的信息。</span><span class="sxs-lookup"><span data-stu-id="cbc05-104">This topic provides information that will help you diagnose and resolve problems that can occur when you try to create a remote Microsoft PowerShell session that connects to Skype for Business Online.</span></span> <span data-ttu-id="cbc05-105">请参阅以下各节：</span><span class="sxs-lookup"><span data-stu-id="cbc05-105">See the following sections:</span></span>
  
- [<span data-ttu-id="cbc05-106">导入模块错误导致的 Windows PowerShell 执行策略</span><span class="sxs-lookup"><span data-stu-id="cbc05-106">Import-Module error caused by Windows PowerShell execution policy</span></span>](diagnose-connection-problems-with-the-skype-for-business-online-connector.md#BKMKPowerShellExecutionPolicy)
    
- [<span data-ttu-id="cbc05-107">导入模块错误导致的不正确版本的 Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="cbc05-107">Import-Module Error caused by incorrect version of Windows PowerShell</span></span>](diagnose-connection-problems-with-the-skype-for-business-online-connector.md#BKMKIncorrectVersion)
    
- [<span data-ttu-id="cbc05-108">未能连接到 Live ID 服务器</span><span class="sxs-lookup"><span data-stu-id="cbc05-108">Failed to connect to Live ID Server</span></span>](diagnose-connection-problems-with-the-skype-for-business-online-connector.md#BKMKFailedConnect)
    
- [<span data-ttu-id="cbc05-109">未能加载 Live ID 模块</span><span class="sxs-lookup"><span data-stu-id="cbc05-109">Failed to load Live ID module</span></span>](diagnose-connection-problems-with-the-skype-for-business-online-connector.md#BKMKFailedLoad)
    
- [<span data-ttu-id="cbc05-110">登录失败的用户</span><span class="sxs-lookup"><span data-stu-id="cbc05-110">Logon failed for the user</span></span>](diagnose-connection-problems-with-the-skype-for-business-online-connector.md#BKMKLogonFailed)
    
- [<span data-ttu-id="cbc05-111">用户没有管理此租户的权限</span><span class="sxs-lookup"><span data-stu-id="cbc05-111">The user does not have permission to manage this tenant</span></span>](diagnose-connection-problems-with-the-skype-for-business-online-connector.md#BKMKUserPermission)
    
- [<span data-ttu-id="cbc05-112">能够连接到租户中已禁用 Skype 业务 online</span><span class="sxs-lookup"><span data-stu-id="cbc05-112">Ability to connect to tenant has been disabled in Skype for Business Online</span></span>](diagnose-connection-problems-with-the-skype-for-business-online-connector.md#BKMKAbilityConnect)
    
- [<span data-ttu-id="cbc05-113">已超出最大并发 shells Skype 业务 online 中的此用户数</span><span class="sxs-lookup"><span data-stu-id="cbc05-113">The maximum number of concurrent shells for this user in Skype for Business Online has been exceeded</span></span>](diagnose-connection-problems-with-the-skype-for-business-online-connector.md#BKMKMaxNumberShellsUser)
    
- [<span data-ttu-id="cbc05-114">已超出此租户中的业务联机 Skype 的并发 shells 的最大数量</span><span class="sxs-lookup"><span data-stu-id="cbc05-114">The maximum number of concurrent shells for this tenant in Skype for Business Online has been exceeded</span></span>](diagnose-connection-problems-with-the-skype-for-business-online-connector.md#BKMK_MaxNumberShellsTenant)
    
## <a name="import-module-error-caused-by-windows-powershell-execution-policy"></a><span data-ttu-id="cbc05-115">导入模块错误导致的 Windows PowerShell 执行策略</span><span class="sxs-lookup"><span data-stu-id="cbc05-115">Import-Module error caused by Windows PowerShell execution policy</span></span>
<span data-ttu-id="cbc05-116"><a name="BKMKPowerShellExecutionPolicy"> </a></span><span class="sxs-lookup"><span data-stu-id="cbc05-116"></span></span>

<span data-ttu-id="cbc05-117">PowerShell 执行策略有助于确定哪些配置文件可以加载到 PowerShell 控制台中，并的脚本的用户可以从该控制台中运行。</span><span class="sxs-lookup"><span data-stu-id="cbc05-117">The PowerShell execution policy helps to determine which configuration files can be loaded into the PowerShell console, and which scripts a user can run from that console.</span></span> <span data-ttu-id="cbc05-118">至少 for Business Online Connector 模块 Skype 无法导入除非已设置为 RemoteSigned 执行策略。</span><span class="sxs-lookup"><span data-stu-id="cbc05-118">At a minimum, the Skype for Business Online Connector module cannot be imported unless the execution policy has been set to RemoteSigned.</span></span> <span data-ttu-id="cbc05-119">如果未，然后当您尝试导入模块时将收到以下错误消息：</span><span class="sxs-lookup"><span data-stu-id="cbc05-119">If it has not, then you will receive the following error message when you attempt to import the module:</span></span>
  
- <span data-ttu-id="cbc05-120">**错误**：<em>导入模块： 文件 c:\\Program Files\\Common Files\\Microsoft Lync Server 2013\\模块\\LyncOnlineConnector\\无法加载 LyncOnlineConnectorStartup.psm1，因为运行在此系统上禁用脚本。有关详细信息，请参阅在 about_Execution_Policies https://go.microsoft.com/fwlink/?LinkID=135170。</em></span><span class="sxs-lookup"><span data-stu-id="cbc05-120">**Error**: <em>Import-Module : File C:\\Program Files\\Common Files\\Microsoft Lync Server 2013\\Modules\\LyncOnlineConnector\\LyncOnlineConnectorStartup.psm1 cannot be loaded because running scripts is disabled on this system. For more information, see about_Execution_Policies at https://go.microsoft.com/fwlink/?LinkID=135170.</em></span></span>

- <span data-ttu-id="cbc05-121">**解决方案**： 若要解决此问题，以管理员身份启动 PowerShell，然后运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="cbc05-121">**Resolution**: To resolve this issue, start PowerShell as an administrator, and then run the following command:</span></span>
    ```
    Set-ExecutionPolicy RemoteSigned
    ```
    <span data-ttu-id="cbc05-122">有关执行策略的详细信息，请参阅[有关执行策略](https://go.microsoft.com/fwlink/?LinkID=135170)。</span><span class="sxs-lookup"><span data-stu-id="cbc05-122">For details about execution policy, see [About Execution Policies](https://go.microsoft.com/fwlink/?LinkID=135170).</span></span>
  
## <a name="import-module-error-caused-by-incorrect-version-of-windows-powershell"></a><span data-ttu-id="cbc05-123">导入模块错误导致的不正确版本的 Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="cbc05-123">Import-Module Error caused by incorrect version of Windows PowerShell</span></span>
<span data-ttu-id="cbc05-124"><a name="BKMKIncorrectVersion"> </a></span><span class="sxs-lookup"><span data-stu-id="cbc05-124"></span></span>

<span data-ttu-id="cbc05-125">For Business Online Connector 模块 Skype 可以仅在 Windows PowerShell 3.0 下运行。</span><span class="sxs-lookup"><span data-stu-id="cbc05-125">The Skype for Business Online Connector module can be run only under Windows PowerShell 3.0.</span></span> <span data-ttu-id="cbc05-126">如果您尝试导入下以前版本的 PowerShell 模块，导入过程将失败并出现错误消息类似如下：</span><span class="sxs-lookup"><span data-stu-id="cbc05-126">If you try to import the module under a previous version of PowerShell, the import process will fail with an error message similar to this:</span></span>
  
  - <span data-ttu-id="cbc05-127">**错误**：*导入模块： 加载 PowerShell 版是"2.0"。模块 d:\\Program Files\\Common Files\\Microsoft Lync Server 2013\\模块\\LyncOnlineConnector\\LyncOnlineConnector.psd1 需要"3.0"，以执行的最小 PowerShell 版本。请验证安装的 PowerShell 并重试。*</span><span class="sxs-lookup"><span data-stu-id="cbc05-127">**Error**: *Import-Module : The version of the loaded PowerShell is '2.0'. The module 'D:\\Program Files\\Common Files\\Microsoft Lync Server 2013\\Modules\\LyncOnlineConnector\\LyncOnlineConnector.psd1' requires a minimum PowerShell version of '3.0' to execute. Please verify the installation of the PowerShell and try again.*</span></span>

- <span data-ttu-id="cbc05-128">**解决方案**： 修复此问题的唯一方法是安装 Windows PowerShell 3.0，可从 Microsoft 下载中心在[https://www.microsoft.com/en-us/download/details.aspx?id=34595](https://www.microsoft.com/en-us/download/details.aspx?id=34595)。</span><span class="sxs-lookup"><span data-stu-id="cbc05-128">**Resolution**: The only way to fix this problem is to install Windows PowerShell 3.0, which is available from the Microsoft Download Center at [https://www.microsoft.com/en-us/download/details.aspx?id=34595](https://www.microsoft.com/en-us/download/details.aspx?id=34595).</span></span>
  
## <a name="failed-to-connect-to-live-id-server"></a><span data-ttu-id="cbc05-129">未能连接到 Live ID 服务器</span><span class="sxs-lookup"><span data-stu-id="cbc05-129">Failed to connect to Live ID Server</span></span>
<span data-ttu-id="cbc05-130"><a name="BKMKFailedConnect"> </a></span><span class="sxs-lookup"><span data-stu-id="cbc05-130"></span></span>

<span data-ttu-id="cbc05-131">通常，有三个连接尝试可能无法与以下错误消息的原因：</span><span class="sxs-lookup"><span data-stu-id="cbc05-131">There are typically three reasons why your connection attempt might fail with the following error message:</span></span>

  - <span data-ttu-id="cbc05-132">**错误**： *Get CsWebTicket： 未能连接到 live id。请确保启用了代理或者计算机具有网络连接到 live id 服务器。*</span><span class="sxs-lookup"><span data-stu-id="cbc05-132">**Error**: *Get-CsWebTicket : Failed to connect live id servers. Make sure proxy is enabled or machine has network connection to live id servers.*</span></span>

- <span data-ttu-id="cbc05-133">**解决方案**： 此错误通常意味着 Microsoft Online Services 登录助手未运行。</span><span class="sxs-lookup"><span data-stu-id="cbc05-133">**Resolution**: Often this error means that the Microsoft Online Services Sign-in Assistant is not running.</span></span> <span data-ttu-id="cbc05-134">您可以通过从 PowerShell 提示符处运行以下命令验证该服务的状态：</span><span class="sxs-lookup"><span data-stu-id="cbc05-134">You can verify the status of this service by running the following command from the PowerShell prompt:</span></span> 
    ```
    Get-Service "msoidsvc"
    ```
    <span data-ttu-id="cbc05-135">如果服务未运行，请使用以下命令启动服务：</span><span class="sxs-lookup"><span data-stu-id="cbc05-135">If the service is not running, start the service by using this command:</span></span>
    ```
    Start-Service "msoidsvc"
    ```

    <span data-ttu-id="cbc05-136">如果该服务正在运行，您可能遇到的网络连接问题计算机和 Microsoft Live ID 身份验证服务器之间。</span><span class="sxs-lookup"><span data-stu-id="cbc05-136">If the service is running, you might be encountering problems with the network connection between your computer and the Microsoft Live ID Authentication Server.</span></span> <span data-ttu-id="cbc05-137">若要检查此，打开 Internet Explorer 并导航到[https://login.microsoftonline.com/。](https://login.microsoftonline.com/.)</span><span class="sxs-lookup"><span data-stu-id="cbc05-137">To check this, open Internet Explorer and navigate to [https://login.microsoftonline.com/.](https://login.microsoftonline.com/.)</span></span> <span data-ttu-id="cbc05-138">尝试登录到 Office 365 从该处。</span><span class="sxs-lookup"><span data-stu-id="cbc05-138">Try logging on to Office 365 from there.</span></span> <span data-ttu-id="cbc05-139">如果失败，您可能遇到网络连接问题。</span><span class="sxs-lookup"><span data-stu-id="cbc05-139">If this fails, you are probably experiencing network connection issues.</span></span>
  
    <span data-ttu-id="cbc05-140">通常，较低，则可能 Microsoft Live ID 身份验证服务器连接 URI 确认已配置为错误值。</span><span class="sxs-lookup"><span data-stu-id="cbc05-140">Less commonly, it is possible that the Connection URI for Microsoft Live ID Authentication Server has been configured to the wrong value.</span></span> <span data-ttu-id="cbc05-141">如果您已确定了登录助手正在运行，并且您没有遇到网络连接问题，这可能是问题。</span><span class="sxs-lookup"><span data-stu-id="cbc05-141">If you've already determined that the Sign-In Assistant is running and that you are not experiencing network connectivity issues, this might be the issue.</span></span> <span data-ttu-id="cbc05-142">在这种情况下，与 Office 365 支持联系。</span><span class="sxs-lookup"><span data-stu-id="cbc05-142">In this case, contact Office 365 Support.</span></span>
  
## <a name="failed-to-load-live-id-module"></a><span data-ttu-id="cbc05-143">未能加载 Live ID 模块</span><span class="sxs-lookup"><span data-stu-id="cbc05-143">Failed to load Live ID module</span></span>
<span data-ttu-id="cbc05-144"><a name="BKMKFailedLoad"> </a></span><span class="sxs-lookup"><span data-stu-id="cbc05-144"></span></span>

<span data-ttu-id="cbc05-145">使用 PowerShell 管理业务 online Skype 的必备组件之一是安装 Microsoft Online Services 登录助手。</span><span class="sxs-lookup"><span data-stu-id="cbc05-145">One of the prerequisites for using PowerShell to manage Skype for Business Online is to install the Microsoft Online Services Sign-in Assistant.</span></span> <span data-ttu-id="cbc05-146">如果未安装登录助手，您会收到以下错误消息，当您尝试业务 online 建立与 Skype 的远程会话时：</span><span class="sxs-lookup"><span data-stu-id="cbc05-146">If the Sign-in Assistant is not installed, you will receive the following error message when you try to establish a remote session with Skype for Business Online:</span></span>

- <span data-ttu-id="cbc05-147">**错误**： *Get CsWebTicket： 无法加载 Live Id 模块。请确保正确安装了版本的 Live Id 登录助手。*</span><span class="sxs-lookup"><span data-stu-id="cbc05-147">**Error**: *Get-CsWebTicket : Can not load Live Id module. Make sure correct version of Live Id Sign-in assistant is installed.*</span></span>

- <span data-ttu-id="cbc05-148">**解决方案**： Microsoft Online Services 登录助手位于 Microsoft 下载中心在[Microsoft Online Services 登录助手的 IT 专业人员的一项](https://www.microsoft.com/en-us/download/details.aspx?id=28177)</span><span class="sxs-lookup"><span data-stu-id="cbc05-148">**Resolution**: The Microsoft Online Services Sign-in Assistant is available in the Microsoft Download Center at [Microsoft Online Services Sign-In Assistant for IT Professionals RTW](https://www.microsoft.com/en-us/download/details.aspx?id=28177)</span></span>

## <a name="logon-failed-for-the-user"></a><span data-ttu-id="cbc05-149">登录失败的用户</span><span class="sxs-lookup"><span data-stu-id="cbc05-149">Logon failed for the user</span></span>
<span data-ttu-id="cbc05-150"><a name="BKMKLogonFailed"> </a></span><span class="sxs-lookup"><span data-stu-id="cbc05-150"></span></span>

<span data-ttu-id="cbc05-151">当您尝试进行远程连接到 Skype 业务 online 时，您必须提供的用户名和密码有效 Skype 业务 Online 用户帐户。</span><span class="sxs-lookup"><span data-stu-id="cbc05-151">When you attempt to make a remote connection to Skype for Business Online, you must supply the user name and password of a valid Skype for Business Online user account.</span></span> <span data-ttu-id="cbc05-152">如果您没有登录将失败以及类似于以下错误消息：</span><span class="sxs-lookup"><span data-stu-id="cbc05-152">If you do not, logon will fail along with an error message similar to this:</span></span>

- <span data-ttu-id="cbc05-153">**错误**： *Get CsWebTicket： 用户 kenmyer@litwareinc.com 登录失败。请创建一个新的 PSCredential 对象，并确保您已经使用正确的用户名和密码。*</span><span class="sxs-lookup"><span data-stu-id="cbc05-153">**Error**: *Get-CsWebTicket : Logon failed for the user 'kenmyer@litwareinc.com'. Please create a new PSCredential object, making sure that you have used the correct user name and password.*</span></span>

- <span data-ttu-id="cbc05-154">**解决方案**： 如果您认为您使用的有效的用户帐户，并且必须正确的密码，尝试再次登录。</span><span class="sxs-lookup"><span data-stu-id="cbc05-154">**Resolution**: If you think that you are using a valid user account and that you have the correct password, try logging on again.</span></span> <span data-ttu-id="cbc05-155">如果失败，使用相同的凭据，然后重试登录在[https://login.microsoftonline.com/](https://login.microsoftonline.com/)。</span><span class="sxs-lookup"><span data-stu-id="cbc05-155">If that fails, use the same credentials and try to log on at [https://login.microsoftonline.com/](https://login.microsoftonline.com/).</span></span> <span data-ttu-id="cbc05-156">如果您不能有登录，请与 Office 365 支持。</span><span class="sxs-lookup"><span data-stu-id="cbc05-156">If you are unable to log on there, contact Office 365 Support.</span></span> 

  
## <a name="the-user-does-not-have-permission-to-manage-this-tenant"></a><span data-ttu-id="cbc05-157">用户没有管理此租户的权限</span><span class="sxs-lookup"><span data-stu-id="cbc05-157">The user does not have permission to manage this tenant</span></span>
<span data-ttu-id="cbc05-158"><a name="BKMKUserPermission"> </a></span><span class="sxs-lookup"><span data-stu-id="cbc05-158"></span></span>

<span data-ttu-id="cbc05-159">您不能进行远程 PowerShell 连接 toSkype 业务 online，除非您是租户管理员组的成员。</span><span class="sxs-lookup"><span data-stu-id="cbc05-159">You cannot make a remote PowerShell connection toSkype for Business Online unless you are a member of the Tenant Administrators group.</span></span> <span data-ttu-id="cbc05-160">如果您不是，您的连接尝试将失败，并您会收到以下错误消息：</span><span class="sxs-lookup"><span data-stu-id="cbc05-160">If you are not, your connection attempt will fail, and you'll receive the following error message:</span></span>

- <span data-ttu-id="cbc05-161">**错误**：*新建 PSSession: [admin.vdomain.com] 处理数据从远程服务器 admin.vdomain.com 失败，出现以下错误消息: user@foo.com' 用户没有管理此租户的权限。可以通过向相应的 RBAC 角色分配用户授予权限。有关详细信息，请参阅[远程疑难解答](https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_remote_troubleshooting?view=powershell-5.1)。*</span><span class="sxs-lookup"><span data-stu-id="cbc05-161">**Error**: *New-PSSession : [admin.vdomain.com] Processing data from remote server admin.vdomain.com failed with the following error message: The user 'user@foo.com' does not have permission to manage this tenant. Permissions can be granted by assigning the user to the appropriate RBAC role. For more information, see the [Remote Troubleshooting](https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_remote_troubleshooting?view=powershell-5.1).*</span></span>

- <span data-ttu-id="cbc05-162">**解决方案**： 如果您认为您，或者是应该是，租户管理员组的成员需要与 Office 365 支持部门联系。</span><span class="sxs-lookup"><span data-stu-id="cbc05-162">**Resolution**: If you think that you are, or are supposed to be, a member of the Tenant Administrators group, you'll need to contact Office 365 Support.</span></span>
  
## <a name="ability-to-connect-to-tenant-has-been-disabled-in-skype-for-business-online"></a><span data-ttu-id="cbc05-163">能够连接到租户中已禁用 Skype 业务 online</span><span class="sxs-lookup"><span data-stu-id="cbc05-163">Ability to connect to tenant has been disabled in Skype for Business Online</span></span>
<span data-ttu-id="cbc05-164"><a name="BKMKAbilityConnect"> </a></span><span class="sxs-lookup"><span data-stu-id="cbc05-164"></span></span>

<span data-ttu-id="cbc05-165">若要使用 PowerShell 管理 Skype 业务 online，您的租户 PowerShell 策略的 EnableRemotePowerShellAccess 属性必须设置为`True`。</span><span class="sxs-lookup"><span data-stu-id="cbc05-165">To use PowerShell to manage Skype for Business Online, the EnableRemotePowerShellAccess property of your tenant PowerShell policy must be set to  `True`.</span></span> <span data-ttu-id="cbc05-166">如果不存在，连接将失败，并且您会收到以下错误消息：</span><span class="sxs-lookup"><span data-stu-id="cbc05-166">If it is not, your connection will fail, and you'll receive the following error message:</span></span>

- <span data-ttu-id="cbc05-167">**错误**：*新建 PSSession: [admin.vdomain.com] 处理数据从远程服务器 admin.vdomain.com 失败，出现以下错误消息： 已禁用连接到此租户使用远程 PowerShell 会话的能力。请 Lync 帮助检查此租户的租户 Powershell 策略，联系。有关详细信息，请参阅[远程疑难解答](https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_remote_troubleshooting?view=powershell-5.1)。*</span><span class="sxs-lookup"><span data-stu-id="cbc05-167">**Error**: *New-PSSession : [admin.vdomain.com] Processing data from remote server admin.vdomain.com failed with the following error message: The ability to connect to this tenant by using a remote PowerShell session has been disabled. Please contact Lync Help to check Tenant Powershell Policy of this tenant. For more information, see the [Remote Troubleshooting](https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_remote_troubleshooting?view=powershell-5.1).*</span></span>

- <span data-ttu-id="cbc05-168">**解决方案**： 如果您看到此错误消息，您需要与 Office 365 支持部门联系并获取已启用的远程 PowerShell 访问。</span><span class="sxs-lookup"><span data-stu-id="cbc05-168">**Resolution**: If you see this error message, you'll need to contact Office 365 Support and get remote PowerShell access enabled.</span></span>
  
## <a name="the-maximum-number-of-concurrent-shells-for-this-user-in-skype-for-business-online-has-been-exceeded"></a><span data-ttu-id="cbc05-169">已超出最大并发 shells Skype 业务 online 中的此用户数</span><span class="sxs-lookup"><span data-stu-id="cbc05-169">The maximum number of concurrent shells for this user in Skype for Business Online has been exceeded</span></span>
<span data-ttu-id="cbc05-170"><a name="BKMKMaxNumberShellsUser"> </a></span><span class="sxs-lookup"><span data-stu-id="cbc05-170"></span></span>

<span data-ttu-id="cbc05-171">每个管理员允许，最多的三个远程连接到 Skype 业务 online。</span><span class="sxs-lookup"><span data-stu-id="cbc05-171">Each administrator is allowed a maximum of three simultaneous remote connections to Skype for Business Online.</span></span> <span data-ttu-id="cbc05-172">如果您具有三个 up 的远程 PowerShell 连接和运行，以使第四个同时任何尝试将失败并连接，出现以下错误消息：</span><span class="sxs-lookup"><span data-stu-id="cbc05-172">If you have three remote PowerShell connections up and running, any attempt to make a fourth simultaneous connection will fail, with the following error message:</span></span>

- <span data-ttu-id="cbc05-173">**错误**：\*新建 PSSession: [admin.vdomain.com] 连接到远程服务器 admin.vdomain.com 失败，出现以下错误消息： WS 管理服务无法处理请求。已超出为此用户的并发 shells 的最大数量。关闭现有 shells 或引发此用户的配额。有关详细信息，请参阅项 [远程 Troubleshooting] (https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_remote_troubleshooting?view=powershell-5.1 \*</span><span class="sxs-lookup"><span data-stu-id="cbc05-173">**Error**: *New-PSSession : [admin.vdomain.com] Connecting to remote server admin.vdomain.com failed with the following error message : The WS-Management service cannot process the request. The maximum number of concurrent shells for this user has been exceeded. Close existing shells or raise the quota for this user. For more information, see the [Remote Troubleshooting](https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_remote_troubleshooting?view=powershell-5.1*</span></span>

- <span data-ttu-id="cbc05-174">**解决方案**： 若要解决此问题的唯一方法是关闭一个或多个以前的连接。</span><span class="sxs-lookup"><span data-stu-id="cbc05-174">**Resolution**: The only way to resolve this issue is to close one or more of the previous connections.</span></span> <span data-ttu-id="cbc05-175">在完成时与 Skype 业务 Online 会话，我们建议使用**Remove-pssession** cmdlet 终止会话。</span><span class="sxs-lookup"><span data-stu-id="cbc05-175">When you are finished with a Skype for Business Online session, we recommend that you use the **Remove-PSSession** cmdlet to terminate the session.</span></span> <span data-ttu-id="cbc05-176">这将帮助您避免此问题。</span><span class="sxs-lookup"><span data-stu-id="cbc05-176">This will help you to prevent this issue.</span></span>
  
## <a name="the-maximum-number-of-concurrent-shells-for-this-tenant-in-skype-for-business-online-has-been-exceeded"></a><span data-ttu-id="cbc05-177">已超出此租户中的业务联机 Skype 的并发 shells 的最大数量</span><span class="sxs-lookup"><span data-stu-id="cbc05-177">The maximum number of concurrent shells for this tenant in Skype for Business Online has been exceeded</span></span>
<span data-ttu-id="cbc05-178"><a name="BKMKMaxNumberShellsTenant"> </a></span><span class="sxs-lookup"><span data-stu-id="cbc05-178"></span></span>

<span data-ttu-id="cbc05-179">尽管每个管理员允许具有三个同时连接到业务 Online 租户 Skype，但没有单租户允许具有多个九个同时连接。</span><span class="sxs-lookup"><span data-stu-id="cbc05-179">Although each administrator is allowed to have as many as three simultaneous connections to a Skype for Business Online tenant, no single tenant is allowed to have more than nine simultaneous connections.</span></span> <span data-ttu-id="cbc05-180">例如，三个管理员可能每个具有三个打开的会话。</span><span class="sxs-lookup"><span data-stu-id="cbc05-180">For example, three administrators might each have three open sessions.</span></span> <span data-ttu-id="cbc05-181">如果尝试进行连接 （10 个同时连接的总结果） 的第四个管理员，则此尝试将失败，使用以下错误消息：</span><span class="sxs-lookup"><span data-stu-id="cbc05-181">If a fourth administrator tries to make a connection (resulting in a total of 10 simultaneous connections), this attempt will fail, with the following error message:</span></span>
  
- <span data-ttu-id="cbc05-182">**错误**：\*新建 PSSession: [admin.vdomain.com] 连接到远程服务器 admin.vdomain.com 失败，出现以下错误消息： WS 管理服务无法处理请求。已超出本租户的并发 shells 的最大数量。关闭现有 shells 或引发此租户配额。有关详细信息，请参阅项 [远程 Troubleshooting] (https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_remote_troubleshooting?view=powershell-5.1 \*</span><span class="sxs-lookup"><span data-stu-id="cbc05-182">**Error**: *New-PSSession : [admin.vdomain.com] Connecting to remote server admin.vdomain.com failed with the following error message : The WS-Management service cannot process the request. The maximum number of concurrent shells for this tenant has been exceeded. Close existing shells or raise the quota for this tenant. For more information, see the [Remote Troubleshooting](https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_remote_troubleshooting?view=powershell-5.1*</span></span>

- <span data-ttu-id="cbc05-183">**解决方案**： 若要解决此问题的唯一方法是关闭一个或多个以前的连接。</span><span class="sxs-lookup"><span data-stu-id="cbc05-183">**Resolution**: The only way to resolve this issue is to close one or more of the previous connections.</span></span> <span data-ttu-id="cbc05-184">在完成时与 Skype 业务 Online 会话，我们建议使用**Remove-pssession** cmdlet 终止该会话。</span><span class="sxs-lookup"><span data-stu-id="cbc05-184">When you are finished with a Skype for Business Online session, we recommend that you use the **Remove-PSSession** cmdlet to terminate that session.</span></span> <span data-ttu-id="cbc05-185">这将帮助您避免此问题。</span><span class="sxs-lookup"><span data-stu-id="cbc05-185">This will help you to prevent this issue.</span></span>  
 
## <a name="related-topics"></a><span data-ttu-id="cbc05-186">相关主题</span><span class="sxs-lookup"><span data-stu-id="cbc05-186">Related topics</span></span>
[<span data-ttu-id="cbc05-187">设置您的计算机的业务联机管理使用 Windows PowerShell 的 Skype</span><span class="sxs-lookup"><span data-stu-id="cbc05-187">Set up your computer for skype for business online management using Windows PowerShell</span></span>](set-up-your-computer-for-windows-powershell.md)

  
 

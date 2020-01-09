---
title: 移动会议目录
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 在取消池之前，必须针对旧版池中的每个会议目录执行以下过程。
ms.openlocfilehash: 1cd4a3a3359ec1638c3ae93c6ce81d8ba2227b96
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/08/2020
ms.locfileid: "40988937"
---
# <a name="move-conference-directories"></a><span data-ttu-id="3f836-103">移动会议目录</span><span class="sxs-lookup"><span data-stu-id="3f836-103">Move Conference Directories</span></span>

<span data-ttu-id="3f836-104">在解除池之前，必须针对旧版池中的每个会议目录执行以下过程。</span><span class="sxs-lookup"><span data-stu-id="3f836-104">Before decommissioning a pool, you must perform the following procedure for each conference directory in your legacy pool.</span></span>
  
### <a name="to-move-a-conference-directory-to-skype-for-business-server-2019"></a><span data-ttu-id="3f836-105">将会议目录移动到 Skype for business Server 2019</span><span class="sxs-lookup"><span data-stu-id="3f836-105">To Move a Conference Directory to Skype for Business Server 2019</span></span>

1. <span data-ttu-id="3f836-106">打开 Skype for Business 服务器命令行管理程序。</span><span class="sxs-lookup"><span data-stu-id="3f836-106">Open the Skype for Business Server Management Shell.</span></span>
    
2. <span data-ttu-id="3f836-107">若要获取组织中的会议目录的标识，请运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="3f836-107">To obtain the identity of the conference directories in your organization, run the following command:</span></span>
    
   ```PowerShell
   Get-CsConferenceDirectory
   ```

    <span data-ttu-id="3f836-108">上面的命令返回你的组织中的所有会议目录。</span><span class="sxs-lookup"><span data-stu-id="3f836-108">The preceding command returns all the conference directories in your organization.</span></span> <span data-ttu-id="3f836-109">因此，你可能希望将结果限制为即将停止的池。</span><span class="sxs-lookup"><span data-stu-id="3f836-109">Because of that, you might want to limit the results to the pool being decommissioned.</span></span> <span data-ttu-id="3f836-110">例如，如果你使用完全限定的域名（FQDN） pool01.contoso.net 取消池，请使用此命令将返回的数据限制为来自该池中的会议目录：</span><span class="sxs-lookup"><span data-stu-id="3f836-110">For example, if you are decommissioning the pool with the fully qualified domain name (FQDN) pool01.contoso.net, use this command to limit the returned data to conference directories from that pool:</span></span>
    
   ```PowerShell
   Get-CsConferenceDirectory | Where-Object {$_.ServiceID -match "pool01.contoso.net"}
   ```

    <span data-ttu-id="3f836-111">该命令仅返回 ServiceID 属性包含 FQDN pool01.contoso.net 的会议目录。</span><span class="sxs-lookup"><span data-stu-id="3f836-111">That command returns only the conference directories where the ServiceID property contains the FQDN pool01.contoso.net.</span></span>
    
3. <span data-ttu-id="3f836-112">若要移动会议目录，请对池中的每个会议目录运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="3f836-112">To move conference directories, run the following command for each conference directory in the pool:</span></span>
    
   ```PowerShell
   Move-CsConferenceDirectory -Identity <Numeric identity of conference directory> -TargetPool <FQDN of pool where ownership is to be transitioned>
   ```

    <span data-ttu-id="3f836-113">例如，若要移动会议目录3，请使用此命令，将 Skype for Business Server 2019 池指定为 TargetPool：</span><span class="sxs-lookup"><span data-stu-id="3f836-113">For example, to move conference directory 3, use this command, specifying a Skype for Business Server 2019 pool as the TargetPool:</span></span>
    
   ```PowerShell
   Move-CsConferenceDirectory -Identity 3 -TargetPool "pool02.contoso.net"
   ```

    <span data-ttu-id="3f836-114">如果要移动池中的所有会议目录，请使用类似于以下内容的命令：</span><span class="sxs-lookup"><span data-stu-id="3f836-114">If you want to move all the conference directories on a pool, use a command similar to the following:</span></span>
    
   ```PowerShell
   Get-CsConferenceDirectory | Where-Object {$_.ServiceID -match "pool01.contoso.net"} | Move-CsConferenceDirectory -TargetPool "pool02.contoso.net"
   ```

<span data-ttu-id="3f836-115">下载[Microsoft 旧版和删除服务器角色](https://go.microsoft.com/fwlink/p/?linkId=246227)，获取有关取消旧版池的全面的分步说明。</span><span class="sxs-lookup"><span data-stu-id="3f836-115">Download [Uninstalling Microsoft legacy and Removing Server Roles](https://go.microsoft.com/fwlink/p/?linkId=246227) for comprehensive, step-by-step instructions on decommissioning legacy pools.</span></span>
  
<span data-ttu-id="3f836-116">移动会议目录时，可能会遇到以下错误：</span><span class="sxs-lookup"><span data-stu-id="3f836-116">When moving conference directories, you might encounter the following error:</span></span>
  
```
WARNING: Move operation failed for conference directory with ID "5". Cannot perform a rollback because data migration might have already started. Retry the operation.
WARNING: Before using the -Force parameter, ensure that you have exported the conference directory data using DBImpExp.exe and imported the data on the target pool. Refer to the DBImpExp-Readme.htm file for more information.
Move-CsConferenceDirectory : Unable to cast COM object of type 'System._ComObject' to interface type 'Microsoft.Rtc.Interop.User.IRtcConfDirManagement'. 
This operation failed because the QueryInterface call on the COM component for the interface with SID '{4262B886-503F-4BEA-868C-04E8DF562CEB}' failed due to the following error: The specified module could not be found.
```

<span data-ttu-id="3f836-117">此错误通常在 Skype for Business 服务器管理外壳需要更新的一组 Active Directory 权限以完成任务时出现。</span><span class="sxs-lookup"><span data-stu-id="3f836-117">This error typically occurs when the Skype for Business Server Management Shell requires an updated set of Active Directory permissions in order to complete a task.</span></span> <span data-ttu-id="3f836-118">若要解决此问题，请关闭该命令行管理程序的当前实例，然后打开一个新的 Shell 实例，然后重新运行该命令以移动会议目录。</span><span class="sxs-lookup"><span data-stu-id="3f836-118">To resolve the problem, close the current instance of the Management Shell, then open a new instance of the shell and re-run the command to move the conference directory.</span></span>
  


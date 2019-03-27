---
title: 移动会议目录
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 停用池之前必须执行以下过程的每个会议目录在旧池中。
ms.openlocfilehash: 32ebe22c54585a206c90888238d96e41fce30a58
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/27/2019
ms.locfileid: "30895717"
---
# <a name="move-conference-directories"></a><span data-ttu-id="56ea5-103">移动会议目录</span><span class="sxs-lookup"><span data-stu-id="56ea5-103">Move Conference Directories</span></span>

<span data-ttu-id="56ea5-104">停用池之前, 必须执行以下过程的每个会议目录在旧池中。</span><span class="sxs-lookup"><span data-stu-id="56ea5-104">Before decommissioning a pool, you must perform the following procedure for each conference directory in your legacy pool.</span></span>
  
### <a name="to-move-a-conference-directory-to-skype-for-business-server-2019"></a><span data-ttu-id="56ea5-105">将业务服务器 2019年会议目录移到 Skype</span><span class="sxs-lookup"><span data-stu-id="56ea5-105">To Move a Conference Directory to Skype for Business Server 2019</span></span>

1. <span data-ttu-id="56ea5-106">打开 Skype 业务 Server 命令行管理程序。</span><span class="sxs-lookup"><span data-stu-id="56ea5-106">Open the Skype for Business Server Management Shell.</span></span>
    
2. <span data-ttu-id="56ea5-107">若要获取组织中会议目录的标识，请运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="56ea5-107">To obtain the identity of the conference directories in your organization, run the following command:</span></span>
    
   ```
   Get-CsConferenceDirectory
   ```

    <span data-ttu-id="56ea5-108">上述命令返回组织中的所有会议目录。</span><span class="sxs-lookup"><span data-stu-id="56ea5-108">The preceding command returns all the conference directories in your organization.</span></span> <span data-ttu-id="56ea5-109">因此，您可能想要将结果限制为正在停用该池。</span><span class="sxs-lookup"><span data-stu-id="56ea5-109">Because of that, you might want to limit the results to the pool being decommissioned.</span></span> <span data-ttu-id="56ea5-110">例如，如果您要停用具有完全限定域名 (FQDN) pool01.contoso.net 池，使用此命令返回的数据限制为会议目录从该池：</span><span class="sxs-lookup"><span data-stu-id="56ea5-110">For example, if you are decommissioning the pool with the fully qualified domain name (FQDN) pool01.contoso.net, use this command to limit the returned data to conference directories from that pool:</span></span>
    
   ```
   Get-CsConferenceDirectory | Where-Object {$_.ServiceID -match "pool01.contoso.net"}
   ```

    <span data-ttu-id="56ea5-111">该命令返回其中 ServiceID 属性包含 FQDN pool01.contoso.net 仅会议目录。</span><span class="sxs-lookup"><span data-stu-id="56ea5-111">That command returns only the conference directories where the ServiceID property contains the FQDN pool01.contoso.net.</span></span>
    
3. <span data-ttu-id="56ea5-112">若要移动会议目录，请对池中运行的每个会议目录的以下命令：</span><span class="sxs-lookup"><span data-stu-id="56ea5-112">To move conference directories, run the following command for each conference directory in the pool:</span></span>
    
   ```
   Move-CsConferenceDirectory -Identity <Numeric identity of conference directory> -TargetPool <FQDN of pool where ownership is to be transitioned>
   ```

    <span data-ttu-id="56ea5-113">例如，若要移动会议目录 3，使用此命令中，指定为业务服务器 2019年池 Skype 作为 TargetPool:</span><span class="sxs-lookup"><span data-stu-id="56ea5-113">For example, to move conference directory 3, use this command, specifying a Skype for Business Server 2019 pool as the TargetPool:</span></span>
    
   ```
   Move-CsConferenceDirectory -Identity 3 -TargetPool "pool02.contoso.net"
   ```

    <span data-ttu-id="56ea5-114">如果您想要移动的所有会议目录的池上，使用类似如下的命令：</span><span class="sxs-lookup"><span data-stu-id="56ea5-114">If you want to move all the conference directories on a pool, use a command similar to the following:</span></span>
    
   ```
   Get-CsConferenceDirectory | Where-Object {$_.ServiceID -match "pool01.contoso.net"} | Move-CsConferenceDirectory -TargetPool "pool02.contoso.net"
   ```

<span data-ttu-id="56ea5-115">有关停用旧池全面的分步说明下载[卸载旧的 Microsoft and Removing Server Roles](https://go.microsoft.com/fwlink/p/?linkId=246227) 。</span><span class="sxs-lookup"><span data-stu-id="56ea5-115">Download [Uninstalling Microsoft legacy and Removing Server Roles](https://go.microsoft.com/fwlink/p/?linkId=246227) for comprehensive, step-by-step instructions on decommissioning legacy pools.</span></span>
  
<span data-ttu-id="56ea5-116">移动会议目录时, 可能会遇到以下错误：</span><span class="sxs-lookup"><span data-stu-id="56ea5-116">When moving conference directories, you might encounter the following error:</span></span>
  
```
WARNING: Move operation failed for conference directory with ID "5". Cannot perform a rollback because data migration might have already started. Retry the operation.
WARNING: Before using the -Force parameter, ensure that you have exported the conference directory data using DBImpExp.exe and imported the data on the target pool. Refer to the DBImpExp-Readme.htm file for more information.
Move-CsConferenceDirectory : Unable to cast COM object of type 'System._ComObject' to interface type 'Microsoft.Rtc.Interop.User.IRtcConfDirManagement'. 
This operation failed because the QueryInterface call on the COM component for the interface with SID '{4262B886-503F-4BEA-868C-04E8DF562CEB}' failed due to the following error: The specified module could not be found.
```

<span data-ttu-id="56ea5-117">通常，当业务 Server 命令行管理程序 Skype 需要更新的 Active Directory 权限才能完成任务集，将发生此错误。</span><span class="sxs-lookup"><span data-stu-id="56ea5-117">This error typically occurs when the Skype for Business Server Management Shell requires an updated set of Active Directory permissions in order to complete a task.</span></span> <span data-ttu-id="56ea5-118">若要解决此问题，关闭当前实例的命令行管理程序，然后打开命令行管理程序的新实例并重新运行此命令移动会议目录。</span><span class="sxs-lookup"><span data-stu-id="56ea5-118">To resolve the problem, close the current instance of the Management Shell, then open a new instance of the shell and re-run the command to move the conference directory.</span></span>
  


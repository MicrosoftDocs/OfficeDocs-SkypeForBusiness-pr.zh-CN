---
title: 配置存档选项为业务服务器处理中 Skype 失败
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 31fd4e7c-3c68-48dd-9fad-8863831accd7
description: 摘要： 了解如何阻止 IM 和会议会话 Skype 对于业务服务器故障会阻止存档。
ms.openlocfilehash: 4fe63319f2b480557c73e238f2b19692df06440f
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/27/2019
ms.locfileid: "30883016"
---
# <a name="configure-archiving-options-to-handle-failures-in-skype-for-business-server"></a><span data-ttu-id="78997-103">配置存档选项为业务服务器处理中 Skype 失败</span><span class="sxs-lookup"><span data-stu-id="78997-103">Configure archiving options to handle failures in Skype for Business Server</span></span>

<span data-ttu-id="78997-104">**摘要：** 了解如何阻止 IM 和会议会话 Skype 对于业务服务器故障会阻止存档。</span><span class="sxs-lookup"><span data-stu-id="78997-104">**Summary:** Learn how to block IM and conferencing sessions in the case of a Skype for Business Server failure that would prevent archiving.</span></span>
  
<span data-ttu-id="78997-105">如果存档是组织的要求，您可以发生业务服务器故障会阻止存档的 Skype 阻止 IM 和会议会话。</span><span class="sxs-lookup"><span data-stu-id="78997-105">If archiving is a requirement for your organization, you can block IM and conferencing sessions in the event of a Skype for Business Server failure that would prevent archiving.</span></span> <span data-ttu-id="78997-106">此功能有时被称作关键模式。</span><span class="sxs-lookup"><span data-stu-id="78997-106">This is sometimes called critical mode.</span></span> <span data-ttu-id="78997-107">例如，如果存储服务出现问题，将为启用通信存档的用户阻止 IM。</span><span class="sxs-lookup"><span data-stu-id="78997-107">For example, if there is a problem with a storage service, IM would be blocked for users whose communications are enabled for archiving.</span></span> <span data-ttu-id="78997-108">在修复故障后，IM 和会议都会自动恢复。</span><span class="sxs-lookup"><span data-stu-id="78997-108">Both IM and conferencing automatically recover after the failures are corrected.</span></span> 
  
## <a name="configure-critical-mode-by-using-the-control-panel"></a><span data-ttu-id="78997-109">使用控制面板配置关键模式</span><span class="sxs-lookup"><span data-stu-id="78997-109">Configure critical mode by using the Control Panel</span></span>

<span data-ttu-id="78997-110">要指定在出现可阻止存档的故障时是否应允许通信会话：</span><span class="sxs-lookup"><span data-stu-id="78997-110">To specify whether communication sessions should be allowed in case of a failure that would prevent archiving:</span></span>
  
1. <span data-ttu-id="78997-111">使用分配给 CsArchivingAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="78997-111">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span> 
    
2. <span data-ttu-id="78997-112">打开一个浏览器窗口，然后输入管理 URL 以打开 Skype 业务 Server Control Panel。</span><span class="sxs-lookup"><span data-stu-id="78997-112">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="78997-113">在左侧导航栏中，单击“监控和存档”\*\*\*\*，然后单击“存档配置”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="78997-113">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Configuration**.</span></span>
    
4. <span data-ttu-id="78997-114">单击存档配置列表中相应的全局、站点或池配置的名称，单击“**编辑**”，然后单击“**显示详细信息**”。</span><span class="sxs-lookup"><span data-stu-id="78997-114">Click the name of the appropriate global, site, or pool configuration in the list of archiving configurations, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="78997-115">要设置存档在失败时的行为方式，请选中或清除“**存档失败时阻止即时消息 (IM) 或 Web 会议会话**”复选框。</span><span class="sxs-lookup"><span data-stu-id="78997-115">To set how archiving behaves when a failure occurs, select or clear the **Block instant messaging (IM) or web conferencing sessions if archiving fails** check box.</span></span>
    
6. <span data-ttu-id="78997-116">单击“**提交**”。</span><span class="sxs-lookup"><span data-stu-id="78997-116">Click **Commit**.</span></span>
    
## <a name="configure-critical-mode-by-using-windows-powershell"></a><span data-ttu-id="78997-117">使用 Windows PowerShell 配置关键模式</span><span class="sxs-lookup"><span data-stu-id="78997-117">Configure critical mode by using Windows PowerShell</span></span>

<span data-ttu-id="78997-118">您还可以指定是否应出现故障会阻止存档与 BlockOnArchiveFailure 参数一起使用**Set-csarchivingconfiguration** cmdlet 的时允许通信会话。</span><span class="sxs-lookup"><span data-stu-id="78997-118">You can also specify whether communication sessions should be allowed in case of a failure that would prevent archiving by using the **Set-CsArchivingConfiguration** cmdlet with the BlockOnArchiveFailure parameter.</span></span>
  
<span data-ttu-id="78997-119">例如，下面的命令禁用 communications 存档失败的情况下：</span><span class="sxs-lookup"><span data-stu-id="78997-119">For example, the following command disables communications in the case of an archiving failure:</span></span>
  
```
Set-CsArchivingConfiguration -Identity "site:Redmond" -BlockOnArchiveFailure $True
```

<span data-ttu-id="78997-120">下一条命令可在出现存档故障时启用通信：</span><span class="sxs-lookup"><span data-stu-id="78997-120">The next command enables communications in the case of an archiving failure:</span></span>
  
```
Set-CsArchivingConfiguration -Identity "site:Redmond" -BlockOnArchiveFailure $False
```

<span data-ttu-id="78997-121">有关详细信息，请参阅[Set-csarchivingconfiguration](https://docs.microsoft.com/powershell/module/skype/set-csarchivingconfiguration?view=skype-ps) cmdlet 的帮助主题。</span><span class="sxs-lookup"><span data-stu-id="78997-121">For more information, see the Help topic for the [Set-CsArchivingConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csarchivingconfiguration?view=skype-ps) cmdlet.</span></span>
  


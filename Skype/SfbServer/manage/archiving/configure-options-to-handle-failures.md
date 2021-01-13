---
title: 配置存档选项以处理 Skype for Business Server 中的故障
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 31fd4e7c-3c68-48dd-9fad-8863831accd7
description: 摘要：了解如何在 Skype for Business Server 出现故障时阻止 IM 和会议会话，这将阻止存档。
ms.openlocfilehash: 9a39c5f54fbdd4a738f4e67e7f70ff199a204672
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49817672"
---
# <a name="configure-archiving-options-to-handle-failures-in-skype-for-business-server"></a><span data-ttu-id="b9562-103">配置存档选项以处理 Skype for Business Server 中的故障</span><span class="sxs-lookup"><span data-stu-id="b9562-103">Configure archiving options to handle failures in Skype for Business Server</span></span>

<span data-ttu-id="b9562-104">**摘要：** 了解如何在 Skype for Business Server 出现故障时阻止阻止 IM 和会议会话，这将阻止存档。</span><span class="sxs-lookup"><span data-stu-id="b9562-104">**Summary:** Learn how to block IM and conferencing sessions in the case of a Skype for Business Server failure that would prevent archiving.</span></span>
  
<span data-ttu-id="b9562-105">如果存档是组织的一项要求，可以在 Skype for Business Server 发生故障时阻止 IM 和会议会话，这将阻止存档。</span><span class="sxs-lookup"><span data-stu-id="b9562-105">If archiving is a requirement for your organization, you can block IM and conferencing sessions in the event of a Skype for Business Server failure that would prevent archiving.</span></span> <span data-ttu-id="b9562-106">这有时称为临界模式。</span><span class="sxs-lookup"><span data-stu-id="b9562-106">This is sometimes called critical mode.</span></span> <span data-ttu-id="b9562-107">例如，如果存储服务出现问题，将阻止其通信已启用存档的用户使用 IM。</span><span class="sxs-lookup"><span data-stu-id="b9562-107">For example, if there is a problem with a storage service, IM would be blocked for users whose communications are enabled for archiving.</span></span> <span data-ttu-id="b9562-108">IM 和会议都能在修复故障后自动恢复。</span><span class="sxs-lookup"><span data-stu-id="b9562-108">Both IM and conferencing automatically recover after the failures are corrected.</span></span> 
  
## <a name="configure-critical-mode-by-using-the-control-panel"></a><span data-ttu-id="b9562-109">使用控制面板配置临界模式</span><span class="sxs-lookup"><span data-stu-id="b9562-109">Configure critical mode by using the Control Panel</span></span>

<span data-ttu-id="b9562-110">若要指定在将阻止存档的故障时是否允许通信会话：</span><span class="sxs-lookup"><span data-stu-id="b9562-110">To specify whether communication sessions should be allowed in case of a failure that would prevent archiving:</span></span>
  
1. <span data-ttu-id="b9562-111">使用分配给 CsArchivingAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="b9562-111">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span> 
    
2. <span data-ttu-id="b9562-112">打开浏览器窗口，然后输入管理 URL 以打开 Skype for Business Server 控制面板。</span><span class="sxs-lookup"><span data-stu-id="b9562-112">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="b9562-113">在左侧导航栏中，单击 **“监控和存档”**，然后单击 **“存档配置”**。</span><span class="sxs-lookup"><span data-stu-id="b9562-113">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Configuration**.</span></span>
    
4. <span data-ttu-id="b9562-114">在存档配置列表中单击相应的全局、站点或池配置的名称，单击"编辑"，然后单击"**显示详细信息"。**</span><span class="sxs-lookup"><span data-stu-id="b9562-114">Click the name of the appropriate global, site, or pool configuration in the list of archiving configurations, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="b9562-115">要设置存档在失败时的行为方式，请选中或清除“存档失败时阻止即时消息(IM)或 Web 会议会话”复选框。</span><span class="sxs-lookup"><span data-stu-id="b9562-115">To set how archiving behaves when a failure occurs, select or clear the **Block instant messaging (IM) or web conferencing sessions if archiving fails** check box.</span></span>
    
6. <span data-ttu-id="b9562-116">单击“提交”。</span><span class="sxs-lookup"><span data-stu-id="b9562-116">Click **Commit**.</span></span>
    
## <a name="configure-critical-mode-by-using-windows-powershell"></a><span data-ttu-id="b9562-117">使用配置关键模式Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="b9562-117">Configure critical mode by using Windows PowerShell</span></span>

<span data-ttu-id="b9562-118">您还可以指定在将 **Set-CsArchivingConfiguration** cmdlet 与 BlockOnArchiveFailure 参数一起使用阻止存档的故障时，是否允许通信会话。</span><span class="sxs-lookup"><span data-stu-id="b9562-118">You can also specify whether communication sessions should be allowed in case of a failure that would prevent archiving by using the **Set-CsArchivingConfiguration** cmdlet with the BlockOnArchiveFailure parameter.</span></span>
  
<span data-ttu-id="b9562-119">例如，以下命令在存档失败时禁用通信：</span><span class="sxs-lookup"><span data-stu-id="b9562-119">For example, the following command disables communications in the case of an archiving failure:</span></span>
  
```PowerShell
Set-CsArchivingConfiguration -Identity "site:Redmond" -BlockOnArchiveFailure $True
```

<span data-ttu-id="b9562-120">下一个命令在存档失败时启用通信：</span><span class="sxs-lookup"><span data-stu-id="b9562-120">The next command enables communications in the case of an archiving failure:</span></span>
  
```PowerShell
Set-CsArchivingConfiguration -Identity "site:Redmond" -BlockOnArchiveFailure $False
```

<span data-ttu-id="b9562-121">有关详细信息，请参阅 [Set-CsArchivingConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csarchivingconfiguration?view=skype-ps) cmdlet 的帮助主题。</span><span class="sxs-lookup"><span data-stu-id="b9562-121">For more information, see the Help topic for the [Set-CsArchivingConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csarchivingconfiguration?view=skype-ps) cmdlet.</span></span>
  


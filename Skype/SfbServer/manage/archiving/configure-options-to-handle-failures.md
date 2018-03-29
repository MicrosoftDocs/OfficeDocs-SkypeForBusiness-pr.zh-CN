---
title: 在 Skype for Business Server 2015 中配置存档选项以处理故障
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 31fd4e7c-3c68-48dd-9fad-8863831accd7
description: 摘要： 了解如何阻止 IM 和会议会话在 Skype 的情况下会阻止归档的业务服务器 2015年失败。
ms.openlocfilehash: 4ad6b8eb496555751aab31949aa3e710749e0262
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="configure-archiving-options-to-handle-failures-in-skype-for-business-server-2015"></a><span data-ttu-id="b4021-103">在 Skype for Business Server 2015 中配置存档选项以处理故障</span><span class="sxs-lookup"><span data-stu-id="b4021-103">Configure archiving options to handle failures in Skype for Business Server 2015</span></span>

<span data-ttu-id="b4021-104">**摘要：**了解如何阻止 IM 和会议会话在 Skype 的情况下会阻止归档的业务服务器 2015年失败。</span><span class="sxs-lookup"><span data-stu-id="b4021-104">**Summary:** Learn how to block IM and conferencing sessions in the case of a Skype for Business Server 2015 failure that would prevent archiving.</span></span>
  
<span data-ttu-id="b4021-105">如果存档是为您的组织的要求，可以在 Skype 业务服务器故障，将导致无法存档的阻止 IM 和会议会话。</span><span class="sxs-lookup"><span data-stu-id="b4021-105">If archiving is a requirement for your organization, you can block IM and conferencing sessions in the event of a Skype for Business Server failure that would prevent archiving.</span></span> <span data-ttu-id="b4021-106">此功能有时被称作关键模式。</span><span class="sxs-lookup"><span data-stu-id="b4021-106">This is sometimes called critical mode.</span></span> <span data-ttu-id="b4021-107">例如，如果存储服务出现问题，将为启用通信存档的用户阻止 IM。</span><span class="sxs-lookup"><span data-stu-id="b4021-107">For example, if there is a problem with a storage service, IM would be blocked for users whose communications are enabled for archiving.</span></span> <span data-ttu-id="b4021-108">在修复故障后，IM 和会议都会自动恢复。</span><span class="sxs-lookup"><span data-stu-id="b4021-108">Both IM and conferencing automatically recover after the failures are corrected.</span></span> 
  
## <a name="configure-critical-mode-by-using-the-control-panel"></a><span data-ttu-id="b4021-109">使用控制面板配置关键模式</span><span class="sxs-lookup"><span data-stu-id="b4021-109">Configure critical mode by using the Control Panel</span></span>

<span data-ttu-id="b4021-110">要指定在出现可阻止存档的故障时是否应允许通信会话：</span><span class="sxs-lookup"><span data-stu-id="b4021-110">To specify whether communication sessions should be allowed in case of a failure that would prevent archiving:</span></span>
  
1. <span data-ttu-id="b4021-111">使用分配给 CsArchivingAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="b4021-111">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span> 
    
2. <span data-ttu-id="b4021-112">打开浏览器窗口，然后输入管理员 URL 打开 Skype 业务服务器控件面板。</span><span class="sxs-lookup"><span data-stu-id="b4021-112">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="b4021-113">在左侧导航栏中，单击“**监控和存档**”，然后单击“**存档配置**”。</span><span class="sxs-lookup"><span data-stu-id="b4021-113">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Configuration**.</span></span>
    
4. <span data-ttu-id="b4021-114">单击存档配置列表中相应的全局、站点或池配置的名称，单击“**编辑**”，然后单击“**显示详细信息**”。</span><span class="sxs-lookup"><span data-stu-id="b4021-114">Click the name of the appropriate global, site, or pool configuration in the list of archiving configurations, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="b4021-115">要设置存档在失败时的行为方式，请选中或清除“**存档失败时阻止即时消息 (IM) 或 Web 会议会话**”复选框。</span><span class="sxs-lookup"><span data-stu-id="b4021-115">To set how archiving behaves when a failure occurs, select or clear the **Block instant messaging (IM) or web conferencing sessions if archiving fails** check box.</span></span>
    
6. <span data-ttu-id="b4021-116">单击“**提交**”。</span><span class="sxs-lookup"><span data-stu-id="b4021-116">Click **Commit**.</span></span>
    
## <a name="configure-critical-mode-by-using-windows-powershell"></a><span data-ttu-id="b4021-117">使用 Windows PowerShell 配置关键模式</span><span class="sxs-lookup"><span data-stu-id="b4021-117">Configure critical mode by using Windows PowerShell</span></span>

<span data-ttu-id="b4021-118">您还可以指定是否应该存档**集 CsArchivingConfiguration** cmdlet 使用 BlockOnArchiveFailure 参数也会导致出现故障时允许通信会话。</span><span class="sxs-lookup"><span data-stu-id="b4021-118">You can also specify whether communication sessions should be allowed in case of a failure that would prevent archiving by using the **Set-CsArchivingConfiguration** cmdlet with the BlockOnArchiveFailure parameter.</span></span>
  
<span data-ttu-id="b4021-119">例如，以下命令禁用在存档失败情况下的通信：</span><span class="sxs-lookup"><span data-stu-id="b4021-119">For example, the following command disables communications in the case of an archiving failure:</span></span>
  
```
Set-CsArchivingConfiguration -Identity "site:Redmond" -BlockOnArchiveFailure $True
```

<span data-ttu-id="b4021-120">下一条命令可在出现存档故障时启用通信：</span><span class="sxs-lookup"><span data-stu-id="b4021-120">The next command enables communications in the case of an archiving failure:</span></span>
  
```
Set-CsArchivingConfiguration -Identity "site:Redmond" -BlockOnArchiveFailure $False
```

<span data-ttu-id="b4021-121">有关详细信息，请参阅[设置 CsArchivingConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csarchivingconfiguration?view=skype-ps) cmdlet 的帮助主题。</span><span class="sxs-lookup"><span data-stu-id="b4021-121">For more information, see the Help topic for the [Set-CsArchivingConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csarchivingconfiguration?view=skype-ps) cmdlet.</span></span>
  


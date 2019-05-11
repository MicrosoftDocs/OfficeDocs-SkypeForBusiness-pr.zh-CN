---
title: 启用或禁用存档中 Skype 业务服务器
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: d5aed328-e89d-4a7b-b603-15ae5c33c5dd
description: 摘要： 了解如何启用或禁用存档中 Skype 业务服务器。
ms.openlocfilehash: 27cb7aab08c6a85f21e058848963bb42de6e1635
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "33885029"
---
# <a name="enable-or-disable-archiving-in-skype-for-business-server"></a><span data-ttu-id="80915-103">启用或禁用存档中 Skype 业务服务器</span><span class="sxs-lookup"><span data-stu-id="80915-103">Enable or disable archiving in Skype for Business Server</span></span>

<span data-ttu-id="80915-104">**摘要：** 了解如何启用或禁用存档中 Skype 业务服务器。</span><span class="sxs-lookup"><span data-stu-id="80915-104">**Summary:** Learn how to enable or disable archiving in Skype for Business Server.</span></span>
  
## <a name="enable-or-disable-archiving-by-using-the-control-panel"></a><span data-ttu-id="80915-105">使用控制面板启用或禁用存档</span><span class="sxs-lookup"><span data-stu-id="80915-105">Enable or disable archiving by using the Control Panel</span></span>

1. <span data-ttu-id="80915-106">使用分配给 CsArchivingAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="80915-106">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span> 
    
2. <span data-ttu-id="80915-107">打开一个浏览器窗口，然后输入管理 URL 以打开 Skype 业务 Server Control Panel。</span><span class="sxs-lookup"><span data-stu-id="80915-107">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="80915-108">在左侧导航栏中，单击“监控和存档”\*\*\*\*，然后单击“存档配置”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="80915-108">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Configuration**.</span></span>
    
4. <span data-ttu-id="80915-109">从存档配置列表中选择相应的全局、站点或池策略，单击“**编辑**”，再单击“**显示详细信息**”，然后执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="80915-109">Select the appropriate global, site, or pool configuration from the list of archiving configurations, click **Edit**, click **Show details**, and then do the following:</span></span>
    
   - <span data-ttu-id="80915-110">若要只为即时消息 (IM) 会话启用存档，请单击“**存档 IM 会话**”。</span><span class="sxs-lookup"><span data-stu-id="80915-110">To enable archiving only for instant messaging (IM) sessions, click **Archive IM sessions**.</span></span>
    
   - <span data-ttu-id="80915-111">若要同时为 IM 会话和会议启用存档，请单击“**存档 IM 和会议会话**”。</span><span class="sxs-lookup"><span data-stu-id="80915-111">To enable archiving for both IM sessions and conferences, click **Archive IM and conferencing sessions**.</span></span>
    
   - <span data-ttu-id="80915-112">若要为此配置禁用存档，请单击“**禁用存档**”。</span><span class="sxs-lookup"><span data-stu-id="80915-112">To disable archiving for the configuration, click **Disable archiving**.</span></span>
    
5. <span data-ttu-id="80915-113">单击“**提交**”。</span><span class="sxs-lookup"><span data-stu-id="80915-113">Click **Commit**.</span></span>
    
## <a name="enable-or-disable-archiving-by-using-windows-powershell"></a><span data-ttu-id="80915-114">使用 Windows PowerShell 启用或禁用存档</span><span class="sxs-lookup"><span data-stu-id="80915-114">Enable or disable archiving by using Windows PowerShell</span></span>

<span data-ttu-id="80915-115">您也可以使用 **Set-CsArchivingConfiguration** cmdlet 启用或禁用存档。</span><span class="sxs-lookup"><span data-stu-id="80915-115">You can also enable or disable archiving by using the **Set-CsArchivingConfiguration** cmdlet.</span></span> <span data-ttu-id="80915-116">例如，以下命令可修改所有存档配置设置，从而仅存档 IM 会话。</span><span class="sxs-lookup"><span data-stu-id="80915-116">For example, the following command modifies the all of the archiving configuration settings so that only IM sessions are archived.</span></span> <span data-ttu-id="80915-117">该命令可调用不带任何参数的 **Get-CsArchivingConfiguration** cmdlet 以返回当前在组织内使用的所有存档配置设置。</span><span class="sxs-lookup"><span data-stu-id="80915-117">The command calls the **Get-CsArchivingConfiguration** cmdlet without any parameters in order to return all the archiving configuration settings currently in use in the organization.</span></span> <span data-ttu-id="80915-118">然后将此集合通过管道传递到 **Where-Object** cmdlet，后者将仅挑选出 EnableArchiving 属性等于 (-eq) "ImAndWebConf" 的设置。</span><span class="sxs-lookup"><span data-stu-id="80915-118">This collection is then piped to the **Where-Object** cmdlet, which selects only those settings where the EnableArchiving property is equal to (-eq) "ImAndWebConf".</span></span> <span data-ttu-id="80915-119">然后，将筛选出的集合通过管道传递到 **Set-CsArchivingConfiguration** cmdlet，后者将选取集合中的每一项，并将 EnableArchiving 的值更改为 "ImOnly"。</span><span class="sxs-lookup"><span data-stu-id="80915-119">The filtered collection is then piped to the **Set-CsArchivingConfiguration** cmdlet, which takes each item in the collection and changes the value of EnableArchiving to "ImOnly":</span></span>
  
```
Get-CsArchivingConfiguration | Where-Object {$_.EnableArchiving -eq "ImAndWebConf"} | Set-CsArchivingConfiguration -EnableArchiving "ImOnly"
```

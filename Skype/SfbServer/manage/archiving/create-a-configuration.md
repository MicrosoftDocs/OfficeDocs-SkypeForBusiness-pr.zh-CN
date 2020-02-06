---
title: 在 Skype for Business 服务器中创建存档配置
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: dc574afa-0b7d-404f-99b3-c812430b7c70
description: 摘要：了解如何为 Skype for Business 服务器创建存档配置。
ms.openlocfilehash: bc7319f2de8398dd3d9e9a79948d1af6eaeb98bc
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818954"
---
# <a name="create-an-archiving-configuration-in-skype-for-business-server"></a><span data-ttu-id="4c8b7-103">在 Skype for Business 服务器中创建存档配置</span><span class="sxs-lookup"><span data-stu-id="4c8b7-103">Create an archiving configuration in Skype for Business Server</span></span>

<span data-ttu-id="4c8b7-104">**摘要：** 了解如何为 Skype for Business 服务器创建存档配置。</span><span class="sxs-lookup"><span data-stu-id="4c8b7-104">**Summary:** Learn how to create an archiving configuration for Skype for Business Server.</span></span>
  
## <a name="configure-archiving-options-by-using-the-control-panel"></a><span data-ttu-id="4c8b7-105">使用控制面板配置存档选项</span><span class="sxs-lookup"><span data-stu-id="4c8b7-105">Configure archiving options by using the Control Panel</span></span>

<span data-ttu-id="4c8b7-106">要为特定站点或池配置存档选项：</span><span class="sxs-lookup"><span data-stu-id="4c8b7-106">To configure archiving options for a specific site or pool:</span></span> 
  
1. <span data-ttu-id="4c8b7-107">使用分配给 CsArchivingAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="4c8b7-107">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span> 
    
2. <span data-ttu-id="4c8b7-108">打开一个浏览器窗口，然后输入管理员 URL 以打开 Skype for Business 服务器控制面板。</span><span class="sxs-lookup"><span data-stu-id="4c8b7-108">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="4c8b7-109">在左侧导航栏中，单击“监控和存档”\*\*\*\*，然后单击“存档配置”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="4c8b7-109">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Configuration**.</span></span>
    
4. <span data-ttu-id="4c8b7-110">在“**存档配置**”页上，单击“**新建**”，然后执行下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="4c8b7-110">On the **Archiving Configuration** page, click **New**, and then do one of the following:</span></span> 
    
   - <span data-ttu-id="4c8b7-111">要创建站点存档配置，请单击“**站点配置**”，然后在“**选择站点**”中，选择要为存档配置的站点。</span><span class="sxs-lookup"><span data-stu-id="4c8b7-111">To create a site archiving configuration, click **Site Configuration**, and then in **Select a site**, select the site to be configured for archiving.</span></span>
    
   - <span data-ttu-id="4c8b7-112">要创建池存档配置，请单击“**池配置**”，然后在“**选择池**”中，选择要为存档配置的池。</span><span class="sxs-lookup"><span data-stu-id="4c8b7-112">To create a pool archiving configuration, click **Pool Configuration**, and then in **Select a pool**, select the pool to be configured for archiving.</span></span>
    
5. <span data-ttu-id="4c8b7-113">在“**新建存档设置**”的“**存档设置**”下拉列表框中，执行下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="4c8b7-113">In **New Archiving Setting**, in the **Archiving setting** drop-down list box, do one of the following:</span></span>
    
   - <span data-ttu-id="4c8b7-114">若要只为即时消息 (IM) 会话启用存档，请单击“**存档 IM 会话**”。</span><span class="sxs-lookup"><span data-stu-id="4c8b7-114">To enable archiving only for instant messaging (IM) sessions, click **Archive IM sessions**.</span></span>
    
   - <span data-ttu-id="4c8b7-115">若要为 IM 会话和 Web 会议启用存档，请单击“**存档 IM 和 Web 会议会话**”。</span><span class="sxs-lookup"><span data-stu-id="4c8b7-115">To enable archiving for both IM sessions and web conferences, click **Archive IM and web conferencing sessions**.</span></span>
    
   - <span data-ttu-id="4c8b7-116">若要为此配置禁用存档，请单击“**禁用存档**”。</span><span class="sxs-lookup"><span data-stu-id="4c8b7-116">To disable archiving for this configuration, click **Disable archiving**.</span></span>
    
6. <span data-ttu-id="4c8b7-117">另请在“**新建存档设置**”中，执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="4c8b7-117">Also in **New Archiving Setting**, do the following:</span></span>
    
   - <span data-ttu-id="4c8b7-118">要在存档不可用时阻止活动，请选中“**存档失败时阻止即时消息 (IM) 或 Web 会议会话**”复选框。</span><span class="sxs-lookup"><span data-stu-id="4c8b7-118">To block activity when archiving is not available, select the **Block instant messaging (IM) or web conferencing sessions if archiving fails** check box.</span></span>
    
   - <span data-ttu-id="4c8b7-119">若要使用 Microsoft Exchange Server 存储存档数据，请单击 " **Microsoft exchange 集成**" 复选框。</span><span class="sxs-lookup"><span data-stu-id="4c8b7-119">To use Microsoft Exchange Server to store archiving data, click the **Microsoft Exchange integration** check box.</span></span>
    
   - <span data-ttu-id="4c8b7-120">若要启用数据清除，请选中“**启用存档数据清除**”复选框，然后执行下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="4c8b7-120">To enable data purging, select the **Enable purging of archiving data** check box, and then do one of the following:</span></span>
    
     - <span data-ttu-id="4c8b7-121">要指定在特定的天数之后清除，请单击“**在最长期限（天）后清除导出的存档数据和存储的存档数据**”，然后指定天数。</span><span class="sxs-lookup"><span data-stu-id="4c8b7-121">To specify purging after a specific number of days, click **Purge exported archiving data and stored archiving data after maximum duration (days)**, and then specify the number of days.</span></span>
    
     - <span data-ttu-id="4c8b7-122">要限制仅清除已导出的存档数据，请单击“**仅清除导出的存档数据**”。</span><span class="sxs-lookup"><span data-stu-id="4c8b7-122">To limit purging to archiving data that has been exported, click **Purge exported archiving data only**.</span></span>
    
7. <span data-ttu-id="4c8b7-123">单击“**提交**”。</span><span class="sxs-lookup"><span data-stu-id="4c8b7-123">Click **Commit**.</span></span>
    
## <a name="configure-archiving-options-by-using-windows-powershell"></a><span data-ttu-id="4c8b7-124">使用 Windows PowerShell 配置存档选项</span><span class="sxs-lookup"><span data-stu-id="4c8b7-124">Configure archiving options by using Windows PowerShell</span></span>

<span data-ttu-id="4c8b7-125">您也可以使用 **New-CsArchivingConfiguration** cmdlet 为特定站点或池配置存档选项。</span><span class="sxs-lookup"><span data-stu-id="4c8b7-125">You can also configure archiving options for a specific site or pool by using the **New-CsArchivingConfiguration** cmdlet.</span></span>
  
<span data-ttu-id="4c8b7-126">以下命令为 Redmond 站点创建一个新的存档配置设置集合：</span><span class="sxs-lookup"><span data-stu-id="4c8b7-126">The following command creates a new collection of archiving configuration settings for the Redmond site:</span></span>
  
```PowerShell
New-CsArchivingConfiguration -Identity "site:Redmond"
```

<span data-ttu-id="4c8b7-127">由于前面的命令中未指定参数（必需的 Identity 参数之外），因此新的配置设置集合将对其所有属性使用默认值。</span><span class="sxs-lookup"><span data-stu-id="4c8b7-127">Because no parameters (other than the mandatory Identity parameter) were specified in the preceding command, the new collection of configuration settings will use the default values for all its properties.</span></span> 
  
<span data-ttu-id="4c8b7-p101">若要创建使用不同属性值的设置，只需包含相应的参数和参数值。以下示例会创建一组存档配置设置，这些设置在默认情况下允许仅存档即时消息会话：</span><span class="sxs-lookup"><span data-stu-id="4c8b7-p101">To create settings that use different property values, simply include the appropriate parameter and parameter value. The following example creates a collection of archiving configuration settings that, by default, allow archiving of instant messaging sessions only:</span></span>
  
```PowerShell
New-CsArchivingConfiguration -Identity "site:Redmond" -EnableArchiving "ImOnly"
```

<span data-ttu-id="4c8b7-p102">可以通过包含多个参数来修改多个属性值。例如，以下命令将新设置配置为存档即时消息会话并阻止不可用的存档服务的即时消息：</span><span class="sxs-lookup"><span data-stu-id="4c8b7-p102">Multiple property values can be modified by including multiple parameters. For example, this command configures the new settings to archive instant messaging sessions and to block instant messaging of the archiving service is not available:</span></span>
  
```PowerShell
New-CsArchivingConfiguration -Identity "site:Redmond" -EnableArchiving "ImOnly" -BlockOnArchiveFailure $True
```

<span data-ttu-id="4c8b7-132">有关详细信息，请参阅[CsArchivingConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csarchivingconfiguration?view=skype-ps) cmdlet 的帮助主题。</span><span class="sxs-lookup"><span data-stu-id="4c8b7-132">For more information, see the help topic for the [New-CsArchivingConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csarchivingconfiguration?view=skype-ps) cmdlet.</span></span>

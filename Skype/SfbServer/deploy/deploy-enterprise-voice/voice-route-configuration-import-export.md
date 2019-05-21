---
title: 在 Skype for Business 中导出或导入语音路线配置文件
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 02ce922d-9ca8-4513-b09f-9de51f5c5bdc
description: '摘要: 了解如何使用 Skype for business Server 控制面板导出或导入 Skype for Business 服务器中的语音路由配置文件。'
ms.openlocfilehash: 14637694e5604419fcd344b43af98263588f117a
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34300878"
---
# <a name="export-or-import-a-voice-route-configuration-file-in-skype-for-business"></a><span data-ttu-id="fd57f-103">在 Skype for Business 中导出或导入语音路线配置文件</span><span class="sxs-lookup"><span data-stu-id="fd57f-103">Export or import a voice route configuration file in Skype for Business</span></span>
 
<span data-ttu-id="fd57f-104">**摘要:** 了解如何使用 Skype for business Server 控制面板导出或导入 Skype for Business 服务器中的 "语音路由配置" 文件。</span><span class="sxs-lookup"><span data-stu-id="fd57f-104">**Summary:** Learn how to export or import a voice routing configuration file in Skype for Business Server by using the Skype for Business Server Control Panel.</span></span>
  
<span data-ttu-id="fd57f-105">如果要在未发布语音路由配置的情况下保存该配置，请按照以下步骤保存和检索语音路由配置的快照。</span><span class="sxs-lookup"><span data-stu-id="fd57f-105">If you want to save your voice routing configuration without publishing it, follow these steps to save and retrieve a snapshot of your voice routing configuration.</span></span> 
  
<span data-ttu-id="fd57f-106">当您导入一个语音路由配置文件 (vcfg), 但同时在服务器上对语音路由配置进行了更改时, Skype for Business Server 控制面板中的 "**语音路由**" 组中的页面将显示有未提交的语音路由更改。</span><span class="sxs-lookup"><span data-stu-id="fd57f-106">When you import a voice routing configuration file (.vcfg), but changes have been made to the voice routing configuration on the server in the meantime, the pages in the **Voice Routing** group in Skype for Business Server Control Panel will indicate that there are uncommitted changes to voice routing.</span></span> <span data-ttu-id="fd57f-107">这些未提交的更改是两种需要调节的配置之间的差异。</span><span class="sxs-lookup"><span data-stu-id="fd57f-107">Those uncommitted changes are the differences between the two configurations that require reconciliation.</span></span>
  
<span data-ttu-id="fd57f-108">如果你对组内任何页面上的设置进行了任何未提交的更改, 则所做的更改将保存在导出的语音配置文件 (vcfg) 中。</span><span class="sxs-lookup"><span data-stu-id="fd57f-108">If you have made any uncommitted changes to the settings on any page within the group, the changes are saved in the exported voice configuration file (.vcfg).</span></span> <span data-ttu-id="fd57f-109">这使你可以在发布更改之前在多个会话期间进行语音路由配置更改。</span><span class="sxs-lookup"><span data-stu-id="fd57f-109">This enables you to make voice routing configuration changes during multiple sessions before you publish the changes.</span></span> 
  
### <a name="to-export-a-voice-routing-configuration"></a><span data-ttu-id="fd57f-110">导出语音路由配置</span><span class="sxs-lookup"><span data-stu-id="fd57f-110">To export a voice routing configuration</span></span>

1. <span data-ttu-id="fd57f-111">以 RTCUniversalServerAdmins 组成员或者 **CsVoiceAdministrator**、**CsServerAdministrator** 或 **CsAdministrator** 管理角色成员的身份登录计算机。</span><span class="sxs-lookup"><span data-stu-id="fd57f-111">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the **CsVoiceAdministrator**, **CsServerAdministrator**, or **CsAdministrator** administrative role.</span></span>
    
2. <span data-ttu-id="fd57f-112">打开 "Skype for Business 服务器" 控制面板。</span><span class="sxs-lookup"><span data-stu-id="fd57f-112">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="fd57f-113">在左侧导航栏中，单击“语音路由”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="fd57f-113">In the left navigation bar, click **Voice Routing**.</span></span>
    
4. <span data-ttu-id="fd57f-114">在“操作”\*\*\*\* 菜单上，单击“导出配置”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="fd57f-114">On the **Actions** menu, click **Export configuration**.</span></span>
    
5. <span data-ttu-id="fd57f-115">指定位置和文件名，然后单击“保存”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="fd57f-115">Specify a location and file name, and then click **Save**.</span></span>
    
### <a name="to-import-a-voice-routing-configuration"></a><span data-ttu-id="fd57f-116">导入语音路由配置</span><span class="sxs-lookup"><span data-stu-id="fd57f-116">To import a voice routing configuration</span></span>

1. <span data-ttu-id="fd57f-117">以 RTCUniversalServerAdmins 组成员或者 **CsVoiceAdministrator**、**CsServerAdministrator** 或 **CsAdministrator** 管理角色成员的身份登录计算机。</span><span class="sxs-lookup"><span data-stu-id="fd57f-117">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the **CsVoiceAdministrator**, **CsServerAdministrator**, or **CsAdministrator** administrative role.</span></span>
    
2. <span data-ttu-id="fd57f-118">打开 "Skype for Business 服务器" 控制面板。</span><span class="sxs-lookup"><span data-stu-id="fd57f-118">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="fd57f-119">在左侧导航栏中，单击“语音路由”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="fd57f-119">In the left navigation bar, click **Voice Routing**.</span></span>
    
4. <span data-ttu-id="fd57f-120">在“操作”\*\*\*\* 菜单上，单击“导入配置”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="fd57f-120">On the **Actions** menu, click **Import configuration**.</span></span>
    
5. <span data-ttu-id="fd57f-121">找到要导入的配置文件，然后单击“打开”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="fd57f-121">Find the configuration file you want to import and then click **Open**.</span></span>
    
6. <span data-ttu-id="fd57f-122">单击“提交”\*\*\*\*，然后单击“全部提交”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="fd57f-122">Click **Commit**, and then click **Commit all**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="fd57f-123">任何时候导入语音配置文件，都必须运行“全部提交”\*\*\*\* 命令以发布配置更改。</span><span class="sxs-lookup"><span data-stu-id="fd57f-123">Whenever you import a voice configuration file, you must run the **Commit all** command to publish the configuration change.</span></span> <span data-ttu-id="fd57f-124">有关详细信息, 请参阅操作文档中的[Skype For business 中的 "发布待处理的语音路由配置更改"](voice-route-config-changes.md) 。</span><span class="sxs-lookup"><span data-stu-id="fd57f-124">For details, see [Publish pending changes to the voice routing configuration in Skype for Business](voice-route-config-changes.md) in the Operations documentation.</span></span>
  


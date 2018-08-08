---
title: 导出或导入语音路由配置中的文件 Skype for Business
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 02ce922d-9ca8-4513-b09f-9de51f5c5bdc
description: 摘要： 了解如何导出或为业务服务器导入语音路由配置文件中 Skype，使用 Skype 业务 Server Control Panel。
ms.openlocfilehash: 462bcf471e4a43bfedf32b0d062731ea7cbd06f9
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/24/2018
ms.locfileid: "20965406"
---
# <a name="export-or-import-a-voice-route-configuration-file-in-skype-for-business"></a><span data-ttu-id="8d755-103">导出或导入语音路由配置中的文件 Skype for Business</span><span class="sxs-lookup"><span data-stu-id="8d755-103">Export or import a voice route configuration file in Skype for Business</span></span>
 
<span data-ttu-id="8d755-104">**摘要：** 了解如何导出或为业务服务器导入语音路由配置文件中 Skype，使用 Skype 业务 Server Control Panel。</span><span class="sxs-lookup"><span data-stu-id="8d755-104">**Summary:** Learn how to export or import a voice routing configuration file in Skype for Business Server by using the Skype for Business Server Control Panel.</span></span>
  
<span data-ttu-id="8d755-105">如果要在未发布语音路由配置的情况下保存该配置，请按照以下步骤保存和检索语音路由配置的快照。</span><span class="sxs-lookup"><span data-stu-id="8d755-105">If you want to save your voice routing configuration without publishing it, follow these steps to save and retrieve a snapshot of your voice routing configuration.</span></span> 
  
<span data-ttu-id="8d755-106">当您导入语音路由配置文件 (.vcfg)，但语音路由配置的服务器上同时发生更改时，**语音路由**组中的业务 Server Control Panel Skype 中的页面将指示那里未提交的更改到语音路由。</span><span class="sxs-lookup"><span data-stu-id="8d755-106">When you import a voice routing configuration file (.vcfg), but changes have been made to the voice routing configuration on the server in the meantime, the pages in the **Voice Routing** group in Skype for Business Server Control Panel will indicate that there are uncommitted changes to voice routing.</span></span> <span data-ttu-id="8d755-107">这些未提交的更改是两种需要调节的配置之间的差异。</span><span class="sxs-lookup"><span data-stu-id="8d755-107">Those uncommitted changes are the differences between the two configurations that require reconciliation.</span></span>
  
<span data-ttu-id="8d755-108">如果对组中的任何页面上的设置进行任何未提交的更改，更改将保存导出的语音配置文件 (.vcfg) 中。</span><span class="sxs-lookup"><span data-stu-id="8d755-108">If you have made any uncommitted changes to the settings on any page within the group, the changes are saved in the exported voice configuration file (.vcfg).</span></span> <span data-ttu-id="8d755-109">这使您能够语音路由配置更改期间之前发布更改的多个会话。</span><span class="sxs-lookup"><span data-stu-id="8d755-109">This enables you to make voice routing configuration changes during multiple sessions before you publish the changes.</span></span> 
  
### <a name="to-export-a-voice-routing-configuration"></a><span data-ttu-id="8d755-110">导出语音路由配置</span><span class="sxs-lookup"><span data-stu-id="8d755-110">To export a voice routing configuration</span></span>

1. <span data-ttu-id="8d755-111">以 RTCUniversalServerAdmins 组成员或者 **CsVoiceAdministrator**、**CsServerAdministrator** 或 **CsAdministrator** 管理角色成员的身份登录计算机。</span><span class="sxs-lookup"><span data-stu-id="8d755-111">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the **CsVoiceAdministrator**, **CsServerAdministrator**, or **CsAdministrator** administrative role.</span></span>
    
2. <span data-ttu-id="8d755-112">打开 Skype 业务 Server Control Panel。</span><span class="sxs-lookup"><span data-stu-id="8d755-112">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="8d755-113">在左侧导航栏中，单击“语音路由”****。</span><span class="sxs-lookup"><span data-stu-id="8d755-113">In the left navigation bar, click **Voice Routing**.</span></span>
    
4. <span data-ttu-id="8d755-114">在“操作”**** 菜单上，单击“导出配置”****。</span><span class="sxs-lookup"><span data-stu-id="8d755-114">On the **Actions** menu, click **Export configuration**.</span></span>
    
5. <span data-ttu-id="8d755-115">指定位置和文件名，然后单击“保存”****。</span><span class="sxs-lookup"><span data-stu-id="8d755-115">Specify a location and file name, and then click **Save**.</span></span>
    
### <a name="to-import-a-voice-routing-configuration"></a><span data-ttu-id="8d755-116">导入语音路由配置</span><span class="sxs-lookup"><span data-stu-id="8d755-116">To import a voice routing configuration</span></span>

1. <span data-ttu-id="8d755-117">以 RTCUniversalServerAdmins 组成员或者 **CsVoiceAdministrator**、**CsServerAdministrator** 或 **CsAdministrator** 管理角色成员的身份登录计算机。</span><span class="sxs-lookup"><span data-stu-id="8d755-117">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the **CsVoiceAdministrator**, **CsServerAdministrator**, or **CsAdministrator** administrative role.</span></span>
    
2. <span data-ttu-id="8d755-118">打开 Skype 业务 Server Control Panel。</span><span class="sxs-lookup"><span data-stu-id="8d755-118">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="8d755-119">在左侧导航栏中，单击“语音路由”****。</span><span class="sxs-lookup"><span data-stu-id="8d755-119">In the left navigation bar, click **Voice Routing**.</span></span>
    
4. <span data-ttu-id="8d755-120">在“操作”**** 菜单上，单击“导入配置”****。</span><span class="sxs-lookup"><span data-stu-id="8d755-120">On the **Actions** menu, click **Import configuration**.</span></span>
    
5. <span data-ttu-id="8d755-121">找到要导入的配置文件，然后单击“打开”****。</span><span class="sxs-lookup"><span data-stu-id="8d755-121">Find the configuration file you want to import and then click **Open**.</span></span>
    
6. <span data-ttu-id="8d755-122">单击“提交”****，然后单击“全部提交”****。</span><span class="sxs-lookup"><span data-stu-id="8d755-122">Click **Commit**, and then click **Commit all**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="8d755-123">任何时候导入语音配置文件，都必须运行“全部提交”**** 命令以发布配置更改。</span><span class="sxs-lookup"><span data-stu-id="8d755-123">Whenever you import a voice configuration file, you must run the **Commit all** command to publish the configuration change.</span></span> <span data-ttu-id="8d755-124">有关详细信息，请参阅操作文档中的[Publish 挂起的 Skype for Business 中的语音路由配置更改](voice-route-config-changes.md)。</span><span class="sxs-lookup"><span data-stu-id="8d755-124">For details, see [Publish pending changes to the voice routing configuration in Skype for Business](voice-route-config-changes.md) in the Operations documentation.</span></span>
  


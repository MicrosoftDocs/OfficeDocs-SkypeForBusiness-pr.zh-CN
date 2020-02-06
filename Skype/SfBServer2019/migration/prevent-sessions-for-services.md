---
title: 阻止服务的会话
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 可以使用 "旧版安装" 控制面板阻止在特定计算机上运行的所有旧式服务的新会话或阻止特定旧服务的新会话。
ms.openlocfilehash: 5bba30bee0fb8c25bed25e2c3cbd593179aa9b97
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41813050"
---
# <a name="prevent-sessions-for-services"></a><span data-ttu-id="48e52-103">阻止服务的会话</span><span class="sxs-lookup"><span data-stu-id="48e52-103">Prevent sessions for services</span></span>

<span data-ttu-id="48e52-104">可以使用 "旧版安装" 控制面板阻止在特定计算机上运行的所有旧式服务的新会话或阻止特定旧服务的新会话。</span><span class="sxs-lookup"><span data-stu-id="48e52-104">You can use the legacy installs Control Panel to prevent new sessions for all the legacy services running on a specific computer or to prevent new sessions for a specific legacy service.</span></span>
  
## <a name="to-prevent-new-sessions-for-services-on-a-computer"></a><span data-ttu-id="48e52-105">阻止计算机上的新会话服务</span><span class="sxs-lookup"><span data-stu-id="48e52-105">To prevent new sessions for services on a computer</span></span>

1. <span data-ttu-id="48e52-106">从 RTCUniversalServerAdmins 组的成员（或具有等效用户权限）或分配给 CsServerAdministrator 或 CsAdministrator 角色的用户帐户，登录到你部署了 Skype for Business 服务器的网络中的任何计算机2019。</span><span class="sxs-lookup"><span data-stu-id="48e52-106">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server 2019.</span></span>
    
2. <span data-ttu-id="48e52-107">打开 "Skype for Business 控制面板"。</span><span class="sxs-lookup"><span data-stu-id="48e52-107">Open Skype for Business Control Panel.</span></span>
    
3. <span data-ttu-id="48e52-108">在左侧导航栏中，单击“**拓扑**”，然后单击“**状态**”。</span><span class="sxs-lookup"><span data-stu-id="48e52-108">In the left navigation bar, click **Topology**, and then click **Status**.</span></span>
    
4. <span data-ttu-id="48e52-109">在 "**状态**" 页面上，根据需要对列表进行排序或搜索以查找运行要阻止新会话的服务的计算机，然后单击该计算机。</span><span class="sxs-lookup"><span data-stu-id="48e52-109">On the **Status** page, sort or search through the list as needed to find the computer that is running the services for which you want to prevent new sessions, and then click it.</span></span> 
    
5. <span data-ttu-id="48e52-110">单击 "**操作**"。</span><span class="sxs-lookup"><span data-stu-id="48e52-110">Click **Action**.</span></span>
    
6. <span data-ttu-id="48e52-111">单击 "**阻止所有服务的新会话**"。</span><span class="sxs-lookup"><span data-stu-id="48e52-111">Click **Prevent new sessions for all services**.</span></span>
    
## <a name="to-prevent-new-sessions-for-a-specific-service"></a><span data-ttu-id="48e52-112">阻止特定服务的新会话</span><span class="sxs-lookup"><span data-stu-id="48e52-112">To prevent new sessions for a specific service</span></span>

1. <span data-ttu-id="48e52-113">从 RTCUniversalServerAdmins 组的成员（或具有等效用户权限）或分配给 CsServerAdministrator 或 CsAdministrator 角色的用户帐户，登录到你部署了 Skype for Business 服务器的网络中的任何计算机2019。</span><span class="sxs-lookup"><span data-stu-id="48e52-113">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server 2019.</span></span>
    
2. <span data-ttu-id="48e52-114">打开 "Skype for Business 控制面板"。</span><span class="sxs-lookup"><span data-stu-id="48e52-114">Open Skype for Business Control Panel.</span></span>
    
3. <span data-ttu-id="48e52-115">在左侧导航栏中，单击“**拓扑**”，然后单击“**状态**”。</span><span class="sxs-lookup"><span data-stu-id="48e52-115">In the left navigation bar, click **Topology**, and then click **Status**.</span></span>
    
4. <span data-ttu-id="48e52-116">在 "**状态**" 页面上，根据需要对列表进行排序或搜索以查找运行要启动或停止的服务的计算机，然后单击它。</span><span class="sxs-lookup"><span data-stu-id="48e52-116">On the **Status** page, sort or search through the list as needed to find the computer that is running the service you want to start or stop, and then click it.</span></span> 
    
5. <span data-ttu-id="48e52-117">单击 "**属性**"。</span><span class="sxs-lookup"><span data-stu-id="48e52-117">Click **Properties**.</span></span>
    
6. <span data-ttu-id="48e52-118">对服务列表进行排序（如有必要），然后单击要阻止新会话的服务。</span><span class="sxs-lookup"><span data-stu-id="48e52-118">Sort the list of services, if necessary, and click the service for which you want to prevent new sessions.</span></span>
    
7. <span data-ttu-id="48e52-119">单击 "**操作**"。</span><span class="sxs-lookup"><span data-stu-id="48e52-119">Click **Action**.</span></span>
    
8. <span data-ttu-id="48e52-120">单击 "**阻止新的服务会话**"。</span><span class="sxs-lookup"><span data-stu-id="48e52-120">Click **Prevent new sessions for service**.</span></span>
    
9. <span data-ttu-id="48e52-121">单击“关闭”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="48e52-121">Click **Close**.</span></span>
    


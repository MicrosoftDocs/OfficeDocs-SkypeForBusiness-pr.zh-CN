---
title: 阻止服务的会话
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 您可以使用旧版安装控制面板来阻止在特定计算机上运行的所有旧版服务的新会话或阻止特定旧版服务的新会话。
ms.openlocfilehash: c5cc8846febaf690376e01c36b9fa023b8377970
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752284"
---
# <a name="prevent-sessions-for-services"></a><span data-ttu-id="af588-103">阻止服务的会话</span><span class="sxs-lookup"><span data-stu-id="af588-103">Prevent sessions for services</span></span>

<span data-ttu-id="af588-104">您可以使用旧版安装控制面板来阻止在特定计算机上运行的所有旧版服务的新会话或阻止特定旧版服务的新会话。</span><span class="sxs-lookup"><span data-stu-id="af588-104">You can use the legacy installs Control Panel to prevent new sessions for all the legacy services running on a specific computer or to prevent new sessions for a specific legacy service.</span></span>
  
## <a name="to-prevent-new-sessions-for-services-on-a-computer"></a><span data-ttu-id="af588-105">阻止对计算机上的服务的新会话</span><span class="sxs-lookup"><span data-stu-id="af588-105">To prevent new sessions for services on a computer</span></span>

1. <span data-ttu-id="af588-106">从 RTCUniversalServerAdmins 组的成员（或具有等效用户权限）或分配给 CsServerAdministrator 或 CsAdministrator 角色的用户帐户，登录到您在其中部署了 Skype for Business Server 2019 的网络中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="af588-106">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server 2019.</span></span>
    
2. <span data-ttu-id="af588-107">打开 "Skype for Business 控制面板"。</span><span class="sxs-lookup"><span data-stu-id="af588-107">Open Skype for Business Control Panel.</span></span>
    
3. <span data-ttu-id="af588-108">在左侧导航栏中，单击“拓扑”\*\*\*\*，然后单击“状态”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="af588-108">In the left navigation bar, click **Topology**, and then click **Status**.</span></span>
    
4. <span data-ttu-id="af588-109">在“状态”\*\*\*\* 页上，根据需要对列表进行排序或搜索，以查找正在运行要对其阻止新会话的服务的计算机，然后单击该计算机。</span><span class="sxs-lookup"><span data-stu-id="af588-109">On the **Status** page, sort or search through the list as needed to find the computer that is running the services for which you want to prevent new sessions, and then click it.</span></span> 
    
5. <span data-ttu-id="af588-110">单击“操作”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="af588-110">Click **Action**.</span></span>
    
6. <span data-ttu-id="af588-111">单击“阻止所有服务的新会话”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="af588-111">Click **Prevent new sessions for all services**.</span></span>
    
## <a name="to-prevent-new-sessions-for-a-specific-service"></a><span data-ttu-id="af588-112">阻止特定服务的新会话</span><span class="sxs-lookup"><span data-stu-id="af588-112">To prevent new sessions for a specific service</span></span>

1. <span data-ttu-id="af588-113">从 RTCUniversalServerAdmins 组的成员（或具有等效用户权限）或分配给 CsServerAdministrator 或 CsAdministrator 角色的用户帐户，登录到您在其中部署了 Skype for Business Server 2019 的网络中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="af588-113">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server 2019.</span></span>
    
2. <span data-ttu-id="af588-114">打开 "Skype for Business 控制面板"。</span><span class="sxs-lookup"><span data-stu-id="af588-114">Open Skype for Business Control Panel.</span></span>
    
3. <span data-ttu-id="af588-115">在左侧导航栏中，单击“拓扑”\*\*\*\*，然后单击“状态”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="af588-115">In the left navigation bar, click **Topology**, and then click **Status**.</span></span>
    
4. <span data-ttu-id="af588-116">在“状态”\*\*\*\* 页上，根据需要对列表进行排序或搜索列表，以查找正在运行要启动或停止的服务的计算机，然后单击该计算机。</span><span class="sxs-lookup"><span data-stu-id="af588-116">On the **Status** page, sort or search through the list as needed to find the computer that is running the service you want to start or stop, and then click it.</span></span> 
    
5. <span data-ttu-id="af588-117">单击“属性”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="af588-117">Click **Properties**.</span></span>
    
6. <span data-ttu-id="af588-118">如有必要，对服务列表进行排序，然后单击要对其阻止新会话的服务。</span><span class="sxs-lookup"><span data-stu-id="af588-118">Sort the list of services, if necessary, and click the service for which you want to prevent new sessions.</span></span>
    
7. <span data-ttu-id="af588-119">单击“操作”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="af588-119">Click **Action**.</span></span>
    
8. <span data-ttu-id="af588-120">单击“阻止服务的新会话”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="af588-120">Click **Prevent new sessions for service**.</span></span>
    
9. <span data-ttu-id="af588-121">单击“关闭”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="af588-121">Click **Close**.</span></span>
    


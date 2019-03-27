---
title: 阻止服务的会话
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 阻止特定计算机上运行的所有旧的服务的新会话或阻止特定的旧服务的新会话，您可以使用旧式安装 Control Panel。
ms.openlocfilehash: 9f3f9bb301841d7e71c18f4d3ca052f3d0c74dce
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/27/2019
ms.locfileid: "30875530"
---
# <a name="prevent-sessions-for-services"></a><span data-ttu-id="73f39-103">阻止服务的会话</span><span class="sxs-lookup"><span data-stu-id="73f39-103">Prevent sessions for services</span></span>

<span data-ttu-id="73f39-104">阻止特定计算机上运行的所有旧的服务的新会话或阻止特定的旧服务的新会话，您可以使用旧式安装 Control Panel。</span><span class="sxs-lookup"><span data-stu-id="73f39-104">You can use the legacy installs Control Panel to prevent new sessions for all the legacy services running on a specific computer or to prevent new sessions for a specific legacy service.</span></span>
  
## <a name="to-prevent-new-sessions-for-services-on-a-computer"></a><span data-ttu-id="73f39-105">若要阻止的计算机上的服务的新会话</span><span class="sxs-lookup"><span data-stu-id="73f39-105">To prevent new sessions for services on a computer</span></span>

1. <span data-ttu-id="73f39-106">从用户帐户是 RTCUniversalServerAdmins 组的成员 （或具有同等用户权限），或分配给 CsServerAdministrator 或 CsAdministrator 角色，登录到在其中在部署 Skype Business Server 网络中的任一计算机2019。</span><span class="sxs-lookup"><span data-stu-id="73f39-106">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server 2019.</span></span>
    
2. <span data-ttu-id="73f39-107">打开 Skype 业务 Control Panel。</span><span class="sxs-lookup"><span data-stu-id="73f39-107">Open Skype for Business Control Panel.</span></span>
    
3. <span data-ttu-id="73f39-108">在左侧导航栏中，单击“**拓扑**”，然后单击“**状态**”。</span><span class="sxs-lookup"><span data-stu-id="73f39-108">In the left navigation bar, click **Topology**, and then click **Status**.</span></span>
    
4. <span data-ttu-id="73f39-109">在**状态**页上排序或列表作为搜索所需找到正在运行要为其阻止新会话，然后单击的服务的计算机。</span><span class="sxs-lookup"><span data-stu-id="73f39-109">On the **Status** page, sort or search through the list as needed to find the computer that is running the services for which you want to prevent new sessions, and then click it.</span></span> 
    
5. <span data-ttu-id="73f39-110">单击**操作**。</span><span class="sxs-lookup"><span data-stu-id="73f39-110">Click **Action**.</span></span>
    
6. <span data-ttu-id="73f39-111">单击**阻止所有服务的新会话**。</span><span class="sxs-lookup"><span data-stu-id="73f39-111">Click **Prevent new sessions for all services**.</span></span>
    
## <a name="to-prevent-new-sessions-for-a-specific-service"></a><span data-ttu-id="73f39-112">阻止特定服务的新会话</span><span class="sxs-lookup"><span data-stu-id="73f39-112">To prevent new sessions for a specific service</span></span>

1. <span data-ttu-id="73f39-113">从用户帐户是 RTCUniversalServerAdmins 组的成员 （或具有同等用户权限），或分配给 CsServerAdministrator 或 CsAdministrator 角色，登录到在其中在部署 Skype Business Server 网络中的任一计算机2019。</span><span class="sxs-lookup"><span data-stu-id="73f39-113">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server 2019.</span></span>
    
2. <span data-ttu-id="73f39-114">打开 Skype 业务 Control Panel。</span><span class="sxs-lookup"><span data-stu-id="73f39-114">Open Skype for Business Control Panel.</span></span>
    
3. <span data-ttu-id="73f39-115">在左侧导航栏中，单击“**拓扑**”，然后单击“**状态**”。</span><span class="sxs-lookup"><span data-stu-id="73f39-115">In the left navigation bar, click **Topology**, and then click **Status**.</span></span>
    
4. <span data-ttu-id="73f39-116">**状态**页、 排序或搜索列表根据需要查找运行服务的计算机上要启动或停止，然后单击它。</span><span class="sxs-lookup"><span data-stu-id="73f39-116">On the **Status** page, sort or search through the list as needed to find the computer that is running the service you want to start or stop, and then click it.</span></span> 
    
5. <span data-ttu-id="73f39-117">单击**属性**。</span><span class="sxs-lookup"><span data-stu-id="73f39-117">Click **Properties**.</span></span>
    
6. <span data-ttu-id="73f39-118">如有必要，对服务，对列表进行排序，然后单击您要为其阻止新会话的服务。</span><span class="sxs-lookup"><span data-stu-id="73f39-118">Sort the list of services, if necessary, and click the service for which you want to prevent new sessions.</span></span>
    
7. <span data-ttu-id="73f39-119">单击**操作**。</span><span class="sxs-lookup"><span data-stu-id="73f39-119">Click **Action**.</span></span>
    
8. <span data-ttu-id="73f39-120">单击**阻止服务的新会话**。</span><span class="sxs-lookup"><span data-stu-id="73f39-120">Click **Prevent new sessions for service**.</span></span>
    
9. <span data-ttu-id="73f39-121">单击“关闭”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="73f39-121">Click **Close**.</span></span>
    


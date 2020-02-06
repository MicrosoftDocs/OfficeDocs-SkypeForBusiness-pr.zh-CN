---
title: 配置受信任应用程序服务器
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
description: 在混合环境中，如果你创建新的受信任的应用程序服务器，则必须将下一个跃点池设置为 Skype for business Server 2019 池。 在混合环境中，旧版池和 Skype for business Server 2019 池都将显示在下拉列表中。 不支持选择旧版池。
ms.openlocfilehash: a853065c8888ce9e160b34d182ec8bde6f4569f3
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41813770"
---
# <a name="configure-trusted-application-servers"></a><span data-ttu-id="0c3c9-105">配置受信任应用程序服务器</span><span class="sxs-lookup"><span data-stu-id="0c3c9-105">Configure trusted application servers</span></span>

<span data-ttu-id="0c3c9-106">在混合环境中，如果你创建新的受信任的应用程序服务器，则必须将下一个跃点池设置为 Skype for business Server 2019 池。</span><span class="sxs-lookup"><span data-stu-id="0c3c9-106">In a mixed environment, if you create a new trusted application server, you must set the next hop pool to be a Skype for Business Server 2019 pool.</span></span> <span data-ttu-id="0c3c9-107">在混合环境中，旧版池和 Skype for business Server 2019 池都将显示在下拉列表中。</span><span class="sxs-lookup"><span data-stu-id="0c3c9-107">In a mixed environment, both the legacy pool and the Skype for Business Server 2019 pool appear in the drop-down list.</span></span> <span data-ttu-id="0c3c9-108">不支持选择旧版池。</span><span class="sxs-lookup"><span data-stu-id="0c3c9-108">Selecting the legacy pool is not supported.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="0c3c9-109">如果要迁移受信任的应用程序服务器，还应更新正在使用的 UCMA 版本。</span><span class="sxs-lookup"><span data-stu-id="0c3c9-109">If you are migrating a trusted application server, you should also update the version of UCMA you are using.</span></span> <span data-ttu-id="0c3c9-110">如果为 Skype for business Server 2019 创建新的受信任的应用程序池，则应将 UCMA 更新为 Skype for Business Server 2019 附带的版本或可用的最新版本。</span><span class="sxs-lookup"><span data-stu-id="0c3c9-110">If you create a new Trusted Application Pool for Skype for Business Server 2019, you should update UCMA to the version that is included with Skype for Business Server 2019 or the latest version available.</span></span> 
  
### <a name="select-skype-for-business-server-2019-as-next-hop-when-creating-a-trusted-application-server"></a><span data-ttu-id="0c3c9-111">创建受信任的应用服务器时，选择 "Skype for Business 服务器 2019" 作为下一个跃点</span><span class="sxs-lookup"><span data-stu-id="0c3c9-111">Select Skype for Business Server 2019 as next hop when creating a Trusted application server</span></span>

1. <span data-ttu-id="0c3c9-112">打开拓扑生成器。</span><span class="sxs-lookup"><span data-stu-id="0c3c9-112">Open Topology Builder.</span></span>
    
2. <span data-ttu-id="0c3c9-113">在左窗格中，右键单击 "**受信任的应用程序服务器**"，然后单击 "**新建受信任应用程序池**"。</span><span class="sxs-lookup"><span data-stu-id="0c3c9-113">In the left pane, right-click **Trusted application servers** and click **New Trusted Application Pool**.</span></span>
    
3. <span data-ttu-id="0c3c9-114">输入受信任的应用程序池的**池 FQDN** ，并选择是单服务器还是多服务器。</span><span class="sxs-lookup"><span data-stu-id="0c3c9-114">Enter the **Pool FQDN** of the trusted application pool and select whether it will be single-server or multiple-server.</span></span> 
    
4. <span data-ttu-id="0c3c9-115">单击" **下一步**"。</span><span class="sxs-lookup"><span data-stu-id="0c3c9-115">Click **Next**.</span></span>
    
5. <span data-ttu-id="0c3c9-116">在 "**选择下一个跃点**" 页面上，从列表中选择 Skype For business Server 2019 前端池。</span><span class="sxs-lookup"><span data-stu-id="0c3c9-116">On the **Select the next hop** page, from the list, select the Skype for Business Server 2019 Front End pool.</span></span> 
    
6. <span data-ttu-id="0c3c9-117">单击“**完成**”。</span><span class="sxs-lookup"><span data-stu-id="0c3c9-117">Click **Finish**.</span></span>
    
7. <span data-ttu-id="0c3c9-118">选择顶部节点**Skype for Business 服务器**，然后从 "**操作**" 菜单中选择 "**发布**"。</span><span class="sxs-lookup"><span data-stu-id="0c3c9-118">Select the top node **Skype for Business Server**, and from the **Action** menu select **Publish**.</span></span>
    
    <span data-ttu-id="0c3c9-119">验证**受信任的应用程序池**已成功创建且与正确的前端池关联。</span><span class="sxs-lookup"><span data-stu-id="0c3c9-119">Verify that the **Trusted Application Pool** has been created successfully and is associated with the correct Front End pool.</span></span> 
    


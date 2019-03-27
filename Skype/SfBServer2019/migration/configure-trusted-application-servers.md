---
title: 配置受信任应用程序服务器
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 在混合环境中，如果您创建一个新的受信任应用程序服务器，必须设置为 Skype 业务服务器 2019年池的下一个跃点池。 在混合环境中，旧池和业务服务器 2019年池 Skype 显示在下拉列表。 不支持选择旧池。
ms.openlocfilehash: 79f4de527008d2d9bf295fcb82eee433d04a1691
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/27/2019
ms.locfileid: "30890886"
---
# <a name="configure-trusted-application-servers"></a><span data-ttu-id="881c4-105">配置受信任应用程序服务器</span><span class="sxs-lookup"><span data-stu-id="881c4-105">Configure trusted application servers</span></span>

<span data-ttu-id="881c4-106">在混合环境中，如果您创建一个新的受信任应用程序服务器，必须设置为 Skype 业务服务器 2019年池的下一个跃点池。</span><span class="sxs-lookup"><span data-stu-id="881c4-106">In a mixed environment, if you create a new trusted application server, you must set the next hop pool to be a Skype for Business Server 2019 pool.</span></span> <span data-ttu-id="881c4-107">在混合环境中，旧池和业务服务器 2019年池 Skype 显示在下拉列表中。</span><span class="sxs-lookup"><span data-stu-id="881c4-107">In a mixed environment, both the legacy pool and the Skype for Business Server 2019 pool appear in the drop-down list.</span></span> <span data-ttu-id="881c4-108">不支持选择旧池。</span><span class="sxs-lookup"><span data-stu-id="881c4-108">Selecting the legacy pool is not supported.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="881c4-109">如果您要迁移的受信任应用程序服务器，则还应该更新的 UCMA 您使用的版本。</span><span class="sxs-lookup"><span data-stu-id="881c4-109">If you are migrating a trusted application server, you should also update the version of UCMA you are using.</span></span> <span data-ttu-id="881c4-110">如果您在为业务服务器 2019年的 Skype 创建一个新的受信任应用程序池，您应更新到附带的业务服务器 2019 Skype 的版本或最新版本的 UCMA。</span><span class="sxs-lookup"><span data-stu-id="881c4-110">If you create a new Trusted Application Pool for Skype for Business Server 2019, you should update UCMA to the version that is included with Skype for Business Server 2019 or the latest version available.</span></span> 
  
### <a name="select-skype-for-business-server-2019-as-next-hop-when-creating-a-trusted-application-server"></a><span data-ttu-id="881c4-111">Skype 的业务服务器 2019年时选择作为下一个跃点创建受信任应用程序服务器</span><span class="sxs-lookup"><span data-stu-id="881c4-111">Select Skype for Business Server 2019 as next hop when creating a Trusted application server</span></span>

1. <span data-ttu-id="881c4-112">打开拓扑生成器。</span><span class="sxs-lookup"><span data-stu-id="881c4-112">Open Topology Builder.</span></span>
    
2. <span data-ttu-id="881c4-113">在左窗格中，右键单击**受信任应用程序服务器**，然后单击**新建受信任应用程序池**。</span><span class="sxs-lookup"><span data-stu-id="881c4-113">In the left pane, right-click **Trusted application servers** and click **New Trusted Application Pool**.</span></span>
    
3. <span data-ttu-id="881c4-114">输入受信任应用程序池的**池 FQDN** ，并选择该池是单服务器还是多服务器。</span><span class="sxs-lookup"><span data-stu-id="881c4-114">Enter the **Pool FQDN** of the trusted application pool and select whether it will be single-server or multiple-server.</span></span> 
    
4. <span data-ttu-id="881c4-115">单击" **下一步**"。</span><span class="sxs-lookup"><span data-stu-id="881c4-115">Click **Next**.</span></span>
    
5. <span data-ttu-id="881c4-116">在**选择下一个跃点**页上，从列表中，选择 Business Server 2019 前端池的 Skype。</span><span class="sxs-lookup"><span data-stu-id="881c4-116">On the **Select the next hop** page, from the list, select the Skype for Business Server 2019 Front End pool.</span></span> 
    
6. <span data-ttu-id="881c4-117">单击“**完成**”。</span><span class="sxs-lookup"><span data-stu-id="881c4-117">Click **Finish**.</span></span>
    
7. <span data-ttu-id="881c4-118">选择顶层节点**Skype 业务服务器**，并从**操作**菜单中，选择**发布**。</span><span class="sxs-lookup"><span data-stu-id="881c4-118">Select the top node **Skype for Business Server**, and from the **Action** menu select **Publish**.</span></span>
    
    <span data-ttu-id="881c4-119">验证**受信任应用程序池**已成功创建且与正确的前端池关联。</span><span class="sxs-lookup"><span data-stu-id="881c4-119">Verify that the **Trusted Application Pool** has been created successfully and is associated with the correct Front End pool.</span></span> 
    


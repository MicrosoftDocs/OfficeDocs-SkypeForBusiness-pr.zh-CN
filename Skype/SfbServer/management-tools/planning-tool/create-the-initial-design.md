---
title: 为 Skype for Business Server 2015 创建初始拓扑设计
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 4/5/2016
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: f3131153-de14-41be-b1e6-7d4bb0191af1
description: 安装完 Skype for Business Server 规划工具后，即可开始规划工具并开始设计建议的 Skype for Business Server 2015 基础结构。
ms.openlocfilehash: 756c59ce0598af186a5cedabe250f7f1e7ec323c
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51098678"
---
# <a name="create-the-initial-topology-design-for-skype-for-business-server-2015"></a><span data-ttu-id="b9195-103">为 Skype for Business Server 2015 创建初始拓扑设计</span><span class="sxs-lookup"><span data-stu-id="b9195-103">Create the initial topology design for Skype for Business Server 2015</span></span>

<span data-ttu-id="b9195-104">安装完 Skype for Business Server 规划工具后，即可开始规划工具并开始设计建议的 Skype for Business Server 2015 基础结构。</span><span class="sxs-lookup"><span data-stu-id="b9195-104">After you have finished installing the Skype for Business Server Planning Tool, you are ready to start the Planning Tool and begin designing the proposed Skype for Business Server 2015 infrastructure.</span></span>

> [!NOTE]
>  <span data-ttu-id="b9195-105">规划工具是一个向导驱动的工具，具有详细的指南，可告知您设计站点和拓扑时的决策流程。</span><span class="sxs-lookup"><span data-stu-id="b9195-105">The Planning Tool is a wizard-driven tool with detailed guides to inform your decision-making process in designing your sites and topology.</span></span> <span data-ttu-id="b9195-106">本主题并不作为详尽指南，而只是为了帮助您开始在设计会话中使用规划工具。</span><span class="sxs-lookup"><span data-stu-id="b9195-106">This topic is intended not as an exhaustive guide, but simply to help get you started using the Planning Tool in your design sessions.</span></span>

### <a name="to-get-started-using-the-planning-tool-and-create-the-initial-design"></a><span data-ttu-id="b9195-107">开始使用规划工具并创建初始设计</span><span class="sxs-lookup"><span data-stu-id="b9195-107">To get started using the Planning Tool and create the initial design</span></span>

1. <span data-ttu-id="b9195-108">启动 Skype for Business Server 2015规划工具：单击"开始"，单击"所有程序"，单击 **"Skype for Business Server 2015"，** 然后单击"**规划工具"。**</span><span class="sxs-lookup"><span data-stu-id="b9195-108">Start the Skype for Business Server 2015 Planning Tool: Click **Start**, click **All Programs**, click **Skype for Business Server 2015**, and then click **Planning Tool**.</span></span>

2. <span data-ttu-id="b9195-109">规划工具启动后，将显示 **"欢迎使用 Skype for Business Server 2015** 规划工具"页。</span><span class="sxs-lookup"><span data-stu-id="b9195-109">After the Planning Tool has started, the **Welcome to the Planning Tool for Skype for Business Server 2015** page appears.</span></span> <span data-ttu-id="b9195-110">选择以下选项之一开始设计：</span><span class="sxs-lookup"><span data-stu-id="b9195-110">Choose one of the following options to begin your design:</span></span>

   - <span data-ttu-id="b9195-111">**选项 1：入门** 单击 **"入门** "可提供一系列特定的访谈问题以及相关选择来定义条件。</span><span class="sxs-lookup"><span data-stu-id="b9195-111">**Option 1: Get Started** Clicking **Get Started** provides a specific series of interview questions with relevant selections to define the criteria.</span></span> <span data-ttu-id="b9195-112">完成初始的" **开始** "访谈部分后，继续进入"设计 **网站** "以定义网站体系结构。</span><span class="sxs-lookup"><span data-stu-id="b9195-112">After you have finished the initial **Get Started** interview section, you proceed into **Design Sites** to define your site architecture.</span></span> <span data-ttu-id="b9195-113">若要完成此选项，请继续执行步骤 3。</span><span class="sxs-lookup"><span data-stu-id="b9195-113">To complete this option, proceed to step 3.</span></span>

   - <span data-ttu-id="b9195-114">**选项 2：设计网站** 单击 **"欢迎"** 页上的"设计网站"将跳过"入门"部分介绍的 **访谈** 式问题。</span><span class="sxs-lookup"><span data-stu-id="b9195-114">**Option 2: Design Sites** Clicking **Design Sites** at the Welcome page bypasses the interview questions presented in the **Get Started** section.</span></span> <span data-ttu-id="b9195-115">此选项将"入门"部分中的访谈问题响应所收集的信息设置为默认值。 </span><span class="sxs-lookup"><span data-stu-id="b9195-115">The information that would have been gathered by responding to the interview questions in **Get Started** section is set to default values with this option.</span></span> <span data-ttu-id="b9195-116">通过单击 **"设计站点**"，有经验的设计人员可以绕过初始访谈并根据需要更改中央站点起始页上 **的** 默认值。</span><span class="sxs-lookup"><span data-stu-id="b9195-116">By clicking **Design Sites**, the experienced designer can bypass the initial interview and change the default values, as needed, on the **Central Sites** start page.</span></span> <span data-ttu-id="b9195-117">若要完成此选项，请跳过步骤 3-5，从步骤 6 开始。</span><span class="sxs-lookup"><span data-stu-id="b9195-117">To complete this option, skip over steps 3-5 and start at step 6.</span></span>

   - <span data-ttu-id="b9195-118">**选项 3：显示保存的拓扑** 如果已使用规划工具完成并保存了拓扑，可以跳过这些步骤中的大多数步骤，首先打开并显示拓扑。</span><span class="sxs-lookup"><span data-stu-id="b9195-118">**Option 3: Display Your Saved Topology** If you have already completed and saved a topology through previous use of the Planning Tool, you can skip over most of these steps and start by opening and displaying the topology.</span></span> <span data-ttu-id="b9195-119">还可以对拓扑进行更改和更新，重新保存拓扑，然后将它导出到 Microsoft Excel 或 Microsoft Visio。</span><span class="sxs-lookup"><span data-stu-id="b9195-119">You can also make changes and updates to the topology, resave it, and then export it to Microsoft Excel or Microsoft Visio.</span></span> <span data-ttu-id="b9195-120">若要完成此选项，请跳过步骤 3-12，从步骤 13 开始。</span><span class="sxs-lookup"><span data-stu-id="b9195-120">To complete this option, skip over steps 3-12 and start at step 13.</span></span>

3. <span data-ttu-id="b9195-121">单击 **"入门** "开始设计 Skype for Business Server 2015 拓扑。</span><span class="sxs-lookup"><span data-stu-id="b9195-121">Click **Get Started** to begin designing your Skype for Business Server 2015 topology.</span></span>

4. <span data-ttu-id="b9195-122">通过为设计选择相应的条件回答每部分的问题，然后单击 **“下一步”** 继续进入下一个向导页。</span><span class="sxs-lookup"><span data-stu-id="b9195-122">Answer each section by selecting the appropriate criteria for your design, and then click **Next** to proceed to the next Wizard page.</span></span> <span data-ttu-id="b9195-123">单击 **"上** 一步"对之前的页面进行更改。</span><span class="sxs-lookup"><span data-stu-id="b9195-123">Click **Back** to make changes on previous pages.</span></span>

    > [!TIP]
    > <span data-ttu-id="b9195-124">每个页面中都有对选择条件的说明以及基于首选做法和容量规划给出的建议。</span><span class="sxs-lookup"><span data-stu-id="b9195-124">Each page has a description of the selection criteria, and recommendations based on preferred practices and capacity planning.</span></span> <span data-ttu-id="b9195-125">如果需要其他详细信息，请单击" **了解详细信息** "阅读 Microsoft 网站上 Skype for Business Server 2015 规划文档中的详细信息。</span><span class="sxs-lookup"><span data-stu-id="b9195-125">If you require additional details, click **Learn more** to read detailed information from the Skype for Business Server 2015 Planning documentation on the Microsoft  website.</span></span> <span data-ttu-id="b9195-126">您必须具有 Internet 连接来访问 Microsoft 网站。</span><span class="sxs-lookup"><span data-stu-id="b9195-126">You must have Internet connectivity to access the Microsoft  website.</span></span>

5. <span data-ttu-id="b9195-127">为设计选择适当的选项。</span><span class="sxs-lookup"><span data-stu-id="b9195-127">Select the appropriate options for your design.</span></span> <span data-ttu-id="b9195-128">定义初始条件后，会出现一个页面，确认“功能概述”已完成。</span><span class="sxs-lookup"><span data-stu-id="b9195-128">After the initial criteria are defined, a page will confirm that your Features Overview is complete.</span></span>

6. <span data-ttu-id="b9195-129">单击 **"设计网站** "以定义中央站点。</span><span class="sxs-lookup"><span data-stu-id="b9195-129">Click **Design Sites** to define your central site.</span></span>

    > [!NOTE]
    > <span data-ttu-id="b9195-130">每个 Skype for Business Server 2015 拓扑将至少有一个中央站点。</span><span class="sxs-lookup"><span data-stu-id="b9195-130">Each Skype for Business Server 2015 topology will have at least one central site.</span></span> <span data-ttu-id="b9195-131">您的设计可能只有一个中央站点、一个中央站点（具有多个分支站点、多个中央站点）或多个中央站点（具有与每个中央站点关联的分支站点）。</span><span class="sxs-lookup"><span data-stu-id="b9195-131">Your design may have a single central site, a central site with a number of branch sites, a number of central sites, or a number of central sites with branch sites associated with each central site.</span></span>

7. <span data-ttu-id="b9195-132">在 **"网站** 名称"中，键入将标识此中央站点的名称。</span><span class="sxs-lookup"><span data-stu-id="b9195-132">In **Site Name**, type the name that will identify this central site.</span></span>

8. <span data-ttu-id="b9195-133">在 **"网站用户"** 中，键入将位于此中央站点的预期本地并发用户数。</span><span class="sxs-lookup"><span data-stu-id="b9195-133">In **Site Homed Users**, type the expected number of on-premises concurrent users who will be homed in this central site.</span></span>

9. <span data-ttu-id="b9195-134">在 **"云托管用户**"中，键入将托管在此中央站点的预期联机并发用户数。</span><span class="sxs-lookup"><span data-stu-id="b9195-134">In **Cloud Homed Users**, type the expected number of online concurrent users who will be homed in this central site.</span></span>

10. <span data-ttu-id="b9195-135">根据需要修改联机协作、用户、语音、其他部署选项或服务器应用程序的选择。</span><span class="sxs-lookup"><span data-stu-id="b9195-135">Modify the selections for Online Collaboration, Users, Voice, Additional Deployment Options, or Server Applications, as needed.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="b9195-136">在设计的这一阶段，只能选择或清除部署选项。</span><span class="sxs-lookup"><span data-stu-id="b9195-136">At this point in the design, you can only select or clear options for your deployment.</span></span> <span data-ttu-id="b9195-137">但是，您可以在规划工具的稍后阶段配置更多选项。</span><span class="sxs-lookup"><span data-stu-id="b9195-137">However, you can configure more options in a later phase of the Planning Tool.</span></span> <span data-ttu-id="b9195-138">还有一些选项不可用且无法清除。</span><span class="sxs-lookup"><span data-stu-id="b9195-138">There are also options that are unavailable and cannot be cleared.</span></span> <span data-ttu-id="b9195-139">此外，可能必须先清除一个选项后才能清除另一个。</span><span class="sxs-lookup"><span data-stu-id="b9195-139">In addition, you may have to clear one option in order to clear another.</span></span> <span data-ttu-id="b9195-140">例如，如果清除"语音"下的 企业语音 选项，则"服务器应用程序" (下的响应组、通知和呼叫企业语音) 选项也将清除。 </span><span class="sxs-lookup"><span data-stu-id="b9195-140">For example, if you clear the **Enterprise Voice** option under Voice, then the **Response Group**, **Announcement**, and **Call Park** options under Server Applications (all of which are features of Enterprise Voice) are also cleared.</span></span>

11. <span data-ttu-id="b9195-141">定义站点名称和用户数量后，单击 **“下一步”**。</span><span class="sxs-lookup"><span data-stu-id="b9195-141">After defining a site name and number of users, click **Next**.</span></span>

12. <span data-ttu-id="b9195-142">以下页面请求有关 SIP 域、会议设置、语音设置和基础结构、Exchange UM、外部用户访问、持久聊天设置、客户端设置、并置选项和分支站点的信息。</span><span class="sxs-lookup"><span data-stu-id="b9195-142">The following pages ask for information about SIP domains, conference settings, voice settings and infrastructure, Exchange UM, external user access, Persistent Chat settings, client settings, collocation options, and branch sites.</span></span> <span data-ttu-id="b9195-143">根据需要回答这些问题。</span><span class="sxs-lookup"><span data-stu-id="b9195-143">Answer these questions as appropriate.</span></span>

13. <span data-ttu-id="b9195-144">最后一个问题询问您是否要创建另一个中央站点。</span><span class="sxs-lookup"><span data-stu-id="b9195-144">The final question asks if you want to create another central site.</span></span> <span data-ttu-id="b9195-145">如果选择" **是"，** 则规划工具将返回到"中央站点"页。</span><span class="sxs-lookup"><span data-stu-id="b9195-145">If you select **Yes**, then the Planning Tool returns to the Central Sites page.</span></span> <span data-ttu-id="b9195-146">如果选择"否 **"，** 请单击"**下** 一步"，然后单击"绘制"以显示高级全局拓扑视图。 </span><span class="sxs-lookup"><span data-stu-id="b9195-146">If you select **No**, click **Next**, and then click **Draw** to display the high-level Global Topology view.</span></span>

14. <span data-ttu-id="b9195-147">若要查看现有拓扑，请单击"显示 **"。**</span><span class="sxs-lookup"><span data-stu-id="b9195-147">To view an existing topology, click **Display**.</span></span>

15. <span data-ttu-id="b9195-148">单击代表之前保存的拓扑的 .xml 文件，然后单击 **“打开”**。</span><span class="sxs-lookup"><span data-stu-id="b9195-148">Click the .xml file that represents the previously saved topology, and then click **Open**.</span></span>

16. <span data-ttu-id="b9195-149">规划工具显示"全局拓扑"页。</span><span class="sxs-lookup"><span data-stu-id="b9195-149">The Planning Tool displays the Global Topology page.</span></span> <span data-ttu-id="b9195-150">现在，可以使用规划工具中提供的工具开始编辑、更新或更改拓扑。</span><span class="sxs-lookup"><span data-stu-id="b9195-150">You can now begin editing, updating, or changing the topology by using the tools available in the Planning Tool.</span></span>

## <a name="see-also"></a><span data-ttu-id="b9195-151">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b9195-151">See also</span></span>

[<span data-ttu-id="b9195-152">编辑设计</span><span class="sxs-lookup"><span data-stu-id="b9195-152">Editing the Design</span></span>](/previous-versions/office/lync-server-2013/lync-server-2013-editing-the-design)
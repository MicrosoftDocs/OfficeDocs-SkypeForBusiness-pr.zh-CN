---
title: 为 Skype for Business Server 2015 创建初始拓扑设计
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 4/5/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: f3131153-de14-41be-b1e6-7d4bb0191af1
description: 安装 Business Server 规划工具 Skype 后，即可开始规划工具并开始设计建议的 Skype 业务服务器 2015年基础结构。
ms.openlocfilehash: 73fd6f4a83ec5aec6808124728c1c73419bcdd28
ms.sourcegitcommit: 08c6fe9955ea61dd9cded2210ae0153e06bdd8a6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/28/2018
ms.locfileid: "23246664"
---
# <a name="create-the-initial-topology-design-for-skype-for-business-server-2015"></a><span data-ttu-id="ee347-103">为 Skype for Business Server 2015 创建初始拓扑设计</span><span class="sxs-lookup"><span data-stu-id="ee347-103">Create the initial topology design for Skype for Business Server 2015</span></span>

<span data-ttu-id="ee347-104">安装 Business Server 规划工具 Skype 后，即可开始规划工具并开始设计建议的 Skype 业务服务器 2015年基础结构。</span><span class="sxs-lookup"><span data-stu-id="ee347-104">After you have finished installing the Skype for Business Server Planning Tool, you are ready to start the Planning Tool and begin designing the proposed Skype for Business Server 2015 infrastructure.</span></span>

> [!NOTE]
>  <span data-ttu-id="ee347-105">规划工具是带有详细指南，告知您的决策过程中设计网站和拓扑的向导式工具。</span><span class="sxs-lookup"><span data-stu-id="ee347-105">The Planning Tool is a wizard-driven tool with detailed guides to inform your decision-making process in designing your sites and topology.</span></span> <span data-ttu-id="ee347-106">本主题旨在不是详尽的指南，但只是为了帮助您入门设计会话中使用规划工具。</span><span class="sxs-lookup"><span data-stu-id="ee347-106">This topic is intended not as an exhaustive guide, but simply to help get you started using the Planning Tool in your design sessions.</span></span>

### <a name="to-get-started-using-the-planning-tool-and-create-the-initial-design"></a><span data-ttu-id="ee347-107">若要开始使用规划工具并创建初始设计</span><span class="sxs-lookup"><span data-stu-id="ee347-107">To get started using the Planning Tool and create the initial design</span></span>

1. <span data-ttu-id="ee347-108">为业务 Server 2015 规划工具启动 Skype： 单击**开始**，单击**所有程序**、 都单击**业务服务器 2015年的 Skype**，，然后都单击**规划工具**。</span><span class="sxs-lookup"><span data-stu-id="ee347-108">Start the Skype for Business Server 2015 Planning Tool: Click **Start**, click **All Programs**, click **Skype for Business Server 2015**, and then click **Planning Tool**.</span></span>

2. <span data-ttu-id="ee347-109">开始规划工具后，将显示**欢迎使用规划工具的业务服务器 2015 Skype**页。</span><span class="sxs-lookup"><span data-stu-id="ee347-109">After the Planning Tool has started, the **Welcome to the Planning Tool for Skype for Business Server 2015** page appears.</span></span> <span data-ttu-id="ee347-110">选择以下选项之一，开始你的设计：</span><span class="sxs-lookup"><span data-stu-id="ee347-110">Choose one of the following options to begin your design:</span></span>

   - <span data-ttu-id="ee347-111">**选项 1： 开始**单击**开始**提供一系列特定面试使用相关选区定义的条件的问题。</span><span class="sxs-lookup"><span data-stu-id="ee347-111">**Option 1: Get Started** Clicking **Get Started** provides a specific series of interview questions with relevant selections to define the criteria.</span></span> <span data-ttu-id="ee347-112">完成初始的“**开始**”访谈部分后，继续进入“**设计站点**”来定义站点体系结构。</span><span class="sxs-lookup"><span data-stu-id="ee347-112">After you have finished the initial **Get Started** interview section, you proceed into **Design Sites** to define your site architecture.</span></span> <span data-ttu-id="ee347-113">要完成该选项，请继续执行步骤 3。</span><span class="sxs-lookup"><span data-stu-id="ee347-113">To complete this option, proceed to step 3.</span></span>

   - <span data-ttu-id="ee347-114">**选项 2： 设计网站**在欢迎页上单击**设计网站**绕过**入门**部分中呈现的面试问题。</span><span class="sxs-lookup"><span data-stu-id="ee347-114">**Option 2: Design Sites** Clicking **Design Sites** at the Welcome page bypasses the interview questions presented in the **Get Started** section.</span></span> <span data-ttu-id="ee347-115">此选项会将本应通过响应“**开始**”部分中的访谈式问题而收集到的信息设置为默认值。</span><span class="sxs-lookup"><span data-stu-id="ee347-115">The information that would have been gathered by responding to the interview questions in **Get Started** section is set to default values with this option.</span></span> <span data-ttu-id="ee347-116">经验丰富的设计师可以通过单击“**设计站点**”跳过初始访谈，并根据需要更改“**中央站点**”开始页上的默认值。</span><span class="sxs-lookup"><span data-stu-id="ee347-116">By clicking **Design Sites**, the experienced designer can bypass the initial interview and change the default values, as needed, on the **Central Sites** start page.</span></span> <span data-ttu-id="ee347-117">要完成该选项，请跳过步骤 3-5，从步骤 6 开始。</span><span class="sxs-lookup"><span data-stu-id="ee347-117">To complete this option, skip over steps 3-5 and start at step 6.</span></span>

   - <span data-ttu-id="ee347-118">**选项 3： 显示已保存的拓扑**如果您已完成并保存通过以前使用规划工具的拓扑，可以跳过这些步骤，首先打开并显示拓扑结构。</span><span class="sxs-lookup"><span data-stu-id="ee347-118">**Option 3: Display Your Saved Topology** If you have already completed and saved a topology through previous use of the Planning Tool, you can skip over most of these steps and start by opening and displaying the topology.</span></span> <span data-ttu-id="ee347-119">你也可更改和更新拓扑，重新保存，然后将其导出到 Microsoft Excel 或 Microsoft Visio。</span><span class="sxs-lookup"><span data-stu-id="ee347-119">You can also make changes and updates to the topology, resave it, and then export it to Microsoft Excel or Microsoft Visio.</span></span> <span data-ttu-id="ee347-120">要完成该选项，请跳过步骤 3-12，从步骤 13 开始。</span><span class="sxs-lookup"><span data-stu-id="ee347-120">To complete this option, skip over steps 3-12 and start at step 13.</span></span>

3. <span data-ttu-id="ee347-121">单击**开始**开始设计您 Skype 业务服务器 2015年拓扑。</span><span class="sxs-lookup"><span data-stu-id="ee347-121">Click **Get Started** to begin designing your Skype for Business Server 2015 topology.</span></span>

4. <span data-ttu-id="ee347-p106">通过选择适合你的设计的条件回答每部分的问题，然后单击“**下一步**”继续进入下一个向导页。单击“**上一步**”可更改之前的页面。</span><span class="sxs-lookup"><span data-stu-id="ee347-p106">Answer each section by selecting the appropriate criteria for your design, and then click **Next** to proceed to the next Wizard page. Click **Back** to make changes on previous pages.</span></span>

    > [!TIP]
    > <span data-ttu-id="ee347-124">每个页面中都有对选择条件的说明以及基于首选做法和容量规划给出的建议。</span><span class="sxs-lookup"><span data-stu-id="ee347-124">Each page has a description of the selection criteria, and recommendations based on preferred practices and capacity planning.</span></span> <span data-ttu-id="ee347-125">如果您需要的其他详细信息，请单击**详细了解**从 Microsoft 网站上的业务 Server 2015 规划文档 Skype 读取的详细的信息。</span><span class="sxs-lookup"><span data-stu-id="ee347-125">If you require additional details, click **Learn more** to read detailed information from the Skype for Business Server 2015 Planning documentation on the Microsoft  website.</span></span> <span data-ttu-id="ee347-126">您必须具有 Internet 连接访问 Microsoft 网站。</span><span class="sxs-lookup"><span data-stu-id="ee347-126">You must have Internet connectivity to access the Microsoft  website.</span></span>

5. <span data-ttu-id="ee347-p108">为设计选择适当的选项。定义初始条件后，会出现一个页面，确认“功能概述”已完成。</span><span class="sxs-lookup"><span data-stu-id="ee347-p108">Select the appropriate options for your design. After the initial criteria are defined, a page will confirm that your Features Overview is complete.</span></span>

6. <span data-ttu-id="ee347-129">单击**设计网站**定义您的中央站点。</span><span class="sxs-lookup"><span data-stu-id="ee347-129">Click **Design Sites** to define your central site.</span></span>

    > [!NOTE]
    > <span data-ttu-id="ee347-130">业务服务器 2015年拓扑的每个 Skype 将具有至少一个中央站点。</span><span class="sxs-lookup"><span data-stu-id="ee347-130">Each Skype for Business Server 2015 topology will have at least one central site.</span></span> <span data-ttu-id="ee347-131">您的设计可能具有单个中央站点，具有多个分支站点、 多个中央站点或使用与每个中央站点关联的分支站点的中央站点的号码的中心网站。</span><span class="sxs-lookup"><span data-stu-id="ee347-131">Your design may have a single central site, a central site with a number of branch sites, a number of central sites, or a number of central sites with branch sites associated with each central site.</span></span>

7. <span data-ttu-id="ee347-132">在**网站名称**框中，键入将标识此中央站点的名称。</span><span class="sxs-lookup"><span data-stu-id="ee347-132">In **Site Name**, type the name that will identify this central site.</span></span>

8. <span data-ttu-id="ee347-133">在**网站托管用户**中，键入的预期将驻留在此中央站点-本地并发用户数。</span><span class="sxs-lookup"><span data-stu-id="ee347-133">In **Site Homed Users**, type the expected number of on-premises concurrent users who will be homed in this central site.</span></span>

9. <span data-ttu-id="ee347-134">在**云托管的用户**中，键入预期的数量的联机并发用户将驻留在此中央站点。</span><span class="sxs-lookup"><span data-stu-id="ee347-134">In **Cloud Homed Users**, type the expected number of online concurrent users who will be homed in this central site.</span></span>

10. <span data-ttu-id="ee347-135">根据需要修改“联机协作”、“用户”、“语音”、“其他部署选项”或“服务器应用程序”的相关选项。</span><span class="sxs-lookup"><span data-stu-id="ee347-135">Modify the selections for Online Collaboration, Users, Voice, Additional Deployment Options, or Server Applications, as needed.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="ee347-136">在设计的这个阶段，只能选择或清除适用于你的部署的选项。</span><span class="sxs-lookup"><span data-stu-id="ee347-136">At this point in the design, you can only select or clear options for your deployment.</span></span> <span data-ttu-id="ee347-137">但是，您可以更高版本的规划工具阶段配置更多选项。</span><span class="sxs-lookup"><span data-stu-id="ee347-137">However, you can configure more options in a later phase of the Planning Tool.</span></span> <span data-ttu-id="ee347-138">还有一些选项不可用且无法清除。</span><span class="sxs-lookup"><span data-stu-id="ee347-138">There are also options that are unavailable and cannot be cleared.</span></span> <span data-ttu-id="ee347-139">此外，可能必须先清除一个选项后才能清除另一个。</span><span class="sxs-lookup"><span data-stu-id="ee347-139">In addition, you may have to clear one option in order to clear another.</span></span> <span data-ttu-id="ee347-140">例如，如果清除“语音”下的“**企业语音**”选项，那么“服务器应用程序”下的“**响应组**”、“**公告**”和“**呼叫寄存**”选项（均属于企业语音的功能）也将一并清除。</span><span class="sxs-lookup"><span data-stu-id="ee347-140">For example, if you clear the **Enterprise Voice** option under Voice, then the **Response Group**, **Announcement**, and **Call Park** options under Server Applications (all of which are features of Enterprise Voice) are also cleared.</span></span>

11. <span data-ttu-id="ee347-141">定义站点名称和用户数量后，单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="ee347-141">After defining a site name and number of users, click **Next**.</span></span>

12. <span data-ttu-id="ee347-142">以下页面请求提供有关 SIP 域、 会议设置、 语音设置和基础结构、 Exchange UM、 外部用户访问、 持久聊天设置、 客户端设置、 并置选项和分支站点的信息。</span><span class="sxs-lookup"><span data-stu-id="ee347-142">The following pages ask for information about SIP domains, conference settings, voice settings and infrastructure, Exchange UM, external user access, Persistent Chat settings, client settings, collocation options, and branch sites.</span></span> <span data-ttu-id="ee347-143">根据需要回答这些问题。</span><span class="sxs-lookup"><span data-stu-id="ee347-143">Answer these questions as appropriate.</span></span>

13. <span data-ttu-id="ee347-144">最后一个问题询问您是否想要创建另一个中央站点。</span><span class="sxs-lookup"><span data-stu-id="ee347-144">The final question asks if you want to create another central site.</span></span> <span data-ttu-id="ee347-145">如果选择**是**，然后规划工具返回到管理中心网站页。</span><span class="sxs-lookup"><span data-stu-id="ee347-145">If you select **Yes**, then the Planning Tool returns to the Central Sites page.</span></span> <span data-ttu-id="ee347-146">如果选择“**否**”，请单击“**下一步**”，然后单击“**绘制**”，此时将显示高级“全局拓扑”视图。</span><span class="sxs-lookup"><span data-stu-id="ee347-146">If you select **No**, click **Next**, and then click **Draw** to display the high-level Global Topology view.</span></span>

14. <span data-ttu-id="ee347-147">要查看现有拓扑，请单击“**显示**”。</span><span class="sxs-lookup"><span data-stu-id="ee347-147">To view an existing topology, click **Display**.</span></span>

15. <span data-ttu-id="ee347-148">单击代表之前保存的拓扑的 .xml 文件，然后单击“**打开**”。</span><span class="sxs-lookup"><span data-stu-id="ee347-148">Click the .xml file that represents the previously saved topology, and then click **Open**.</span></span>

16. <span data-ttu-id="ee347-149">规划工具显示全局拓扑页。</span><span class="sxs-lookup"><span data-stu-id="ee347-149">The Planning Tool displays the Global Topology page.</span></span> <span data-ttu-id="ee347-150">您现在可以开始编辑、 更新或更改拓扑使用规划工具中可用的工具。</span><span class="sxs-lookup"><span data-stu-id="ee347-150">You can now begin editing, updating, or changing the topology by using the tools available in the Planning Tool.</span></span>

## <a name="see-also"></a><span data-ttu-id="ee347-151">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ee347-151">See also</span></span>

[<span data-ttu-id="ee347-152">编辑设计</span><span class="sxs-lookup"><span data-stu-id="ee347-152">Editing the Design</span></span>](https://technet.microsoft.com/library/08f639ba-0e5f-4ae7-9191-c3d96c25b169.aspx)
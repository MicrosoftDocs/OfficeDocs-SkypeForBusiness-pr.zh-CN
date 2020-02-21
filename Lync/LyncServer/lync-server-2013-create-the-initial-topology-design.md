---
title: Lync Server 2013：创建初始拓扑设计
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create the initial design
ms:assetid: f3131153-de14-41be-b1e6-7d4bb0191af1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615047(v=OCS.15)
ms:contentKeyID: 51541530
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 71ccdec2c39839674c6304000680ec611a48c016
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42179719"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="create-the-initial-topology-design-for-lync-server-2013"></a><span data-ttu-id="b170b-102">为 Lync Server 2013 创建初始拓扑设计</span><span class="sxs-lookup"><span data-stu-id="b170b-102">Create the initial topology design for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b170b-103">_**上次修改的主题：** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="b170b-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="b170b-104">安装完 Lync Server 2013 （规划工具）后，即可启动规划工具并开始设计建议的 Lync Server 2013 基础结构。</span><span class="sxs-lookup"><span data-stu-id="b170b-104">After you have finished installing the Lync Server 2013, Planning Tool, you are ready to start the Planning Tool and begin designing the proposed Lync Server 2013 infrastructure.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="b170b-105">规划工具是一个向导驱动的工具，其中包含详细指南，可在设计网站和拓扑时向决策过程发出通知。</span><span class="sxs-lookup"><span data-stu-id="b170b-105">The Planning Tool is a wizard-driven tool with detailed guides to inform your decision-making process in designing your sites and topology.</span></span> <span data-ttu-id="b170b-106">本主题不是一种详尽的指南，只是为了帮助您在设计会话中开始使用规划工具。</span><span class="sxs-lookup"><span data-stu-id="b170b-106">This topic is intended not as an exhaustive guide, but simply to help get you started using the Planning Tool in your design sessions.</span></span>



</div>

<div>

## <a name="to-get-started-using-the-planning-tool-and-create-the-initial-design"></a><span data-ttu-id="b170b-107">开始使用规划工具并创建初始设计</span><span class="sxs-lookup"><span data-stu-id="b170b-107">To get started using the Planning Tool and create the initial design</span></span>

1.  <span data-ttu-id="b170b-108">启动 Lync Server 2013，规划工具：依次单击 "**开始**"、"**所有程序**"、" **Microsoft Lync Server 2013**" 和 "**规划工具**"。</span><span class="sxs-lookup"><span data-stu-id="b170b-108">Start the Lync Server 2013, Planning Tool: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Planning Tool**.</span></span>

2.  <span data-ttu-id="b170b-109">在规划工具启动之后，将显示 "**欢迎使用 Microsoft Lync Server 2013 的规划工具**" 页。</span><span class="sxs-lookup"><span data-stu-id="b170b-109">After the Planning Tool has started, the **Welcome to the Planning Tool for Microsoft Lync Server 2013** page appears.</span></span> <span data-ttu-id="b170b-110">选择下列选项之一以开始您的设计：</span><span class="sxs-lookup"><span data-stu-id="b170b-110">Choose one of the following options to begin your design:</span></span>
    
      - <span data-ttu-id="b170b-111">**选项1：开始**   **单击 "入门"** 提供了一系列针对相关选择的调查问题，以定义条件。</span><span class="sxs-lookup"><span data-stu-id="b170b-111">**Option 1: Get Started**   Clicking **Get Started** provides a specific series of interview questions with relevant selections to define the criteria.</span></span> <span data-ttu-id="b170b-112">完成最初的 "**开始**访谈" 部分之后，您将继续**设计网站**以定义网站体系结构。</span><span class="sxs-lookup"><span data-stu-id="b170b-112">After you have finished the initial **Get Started** interview section, you proceed into **Design Sites** to define your site architecture.</span></span> <span data-ttu-id="b170b-113">若要完成此选项，请继续执行步骤3。</span><span class="sxs-lookup"><span data-stu-id="b170b-113">To complete this option, proceed to step 3.</span></span>
    
      - <span data-ttu-id="b170b-114">**选项2：设计网站**   单击 "欢迎" 页面上的 "**设计网站**" 可绕过 "**入门**" 部分中介绍的访谈问题。</span><span class="sxs-lookup"><span data-stu-id="b170b-114">**Option 2: Design Sites**   Clicking **Design Sites** at the Welcome page bypasses the interview questions presented in the **Get Started** section.</span></span> <span data-ttu-id="b170b-115">通过响应 "**入门**" 部分中的 "会见问题" 部分收集的信息将使用此选项设置为 "默认值"。</span><span class="sxs-lookup"><span data-stu-id="b170b-115">The information that would have been gathered by responding to the interview questions in **Get Started** section is set to default values with this option.</span></span> <span data-ttu-id="b170b-116">通过单击 "**设计网站**"，经验丰富的设计人员可以绕过初始访谈，并根据需要在 "**中心网站**起始页" 上更改默认值。</span><span class="sxs-lookup"><span data-stu-id="b170b-116">By clicking **Design Sites**, the experienced designer can bypass the initial interview and change the default values, as needed, on the **Central Sites** start page.</span></span> <span data-ttu-id="b170b-117">若要完成此选项，请跳过步骤3-5 并从步骤6开始。</span><span class="sxs-lookup"><span data-stu-id="b170b-117">To complete this option, skip over steps 3-5 and start at step 6.</span></span>
    
      - <span data-ttu-id="b170b-118">**选项3：显示已保存的拓扑**   如果已通过以前使用规划工具完成并保存了拓扑，则可以跳过这些步骤，并首先打开并显示拓扑。</span><span class="sxs-lookup"><span data-stu-id="b170b-118">**Option 3: Display Your Saved Topology**   If you have already completed and saved a topology through previous use of the Planning Tool, you can skip over most of these steps and start by opening and displaying the topology.</span></span> <span data-ttu-id="b170b-119">您还可以对拓扑进行更改和更新，重新保存它，然后将其导出到 Microsoft Excel 或 Microsoft Visio。</span><span class="sxs-lookup"><span data-stu-id="b170b-119">You can also make changes and updates to the topology, resave it, and then export it to Microsoft Excel or Microsoft Visio.</span></span> <span data-ttu-id="b170b-120">若要完成此选项，请跳过步骤3-12 并从步骤13开始。</span><span class="sxs-lookup"><span data-stu-id="b170b-120">To complete this option, skip over steps 3-12 and start at step 13.</span></span>

3.  <span data-ttu-id="b170b-121">单击 "**开始**" 开始设计 Lync Server 2013 拓扑。</span><span class="sxs-lookup"><span data-stu-id="b170b-121">Click **Get Started** to begin designing your Lync Server 2013 topology.</span></span>

4.  <span data-ttu-id="b170b-122">通过为设计选择相应的条件回答每部分的问题，然后单击 **“下一步”** 继续进入下一个向导页。</span><span class="sxs-lookup"><span data-stu-id="b170b-122">Answer each section by selecting the appropriate criteria for your design, and then click **Next** to proceed to the next Wizard page.</span></span> <span data-ttu-id="b170b-123">单击 "**上一步**"，在以前的页面上进行更改。</span><span class="sxs-lookup"><span data-stu-id="b170b-123">Click **Back** to make changes on previous pages.</span></span>
    
    <div>
    

    > [!TIP]  
    > <span data-ttu-id="b170b-124">每个页面中都有对选择条件的说明以及基于首选做法和容量规划给出的建议。</span><span class="sxs-lookup"><span data-stu-id="b170b-124">Each page has a description of the selection criteria, and recommendations based on preferred practices and capacity planning.</span></span> <span data-ttu-id="b170b-125">如果需要更多详细信息，请单击 Microsoft TechNet 网站上的 "<STRONG>了解详细</STRONG>信息"，以阅读 Lync Server 2013 规划文档中的详细信息。</span><span class="sxs-lookup"><span data-stu-id="b170b-125">If you require additional details, click <STRONG>Learn more</STRONG> to read detailed information from the Lync Server 2013 Planning documentation on the Microsoft TechNet website.</span></span> <span data-ttu-id="b170b-126">要访问 Microsoft TechNet 网站，必须具有 Internet 连接。</span><span class="sxs-lookup"><span data-stu-id="b170b-126">You must have Internet connectivity to access the Microsoft TechNet website.</span></span>

    
    </div>

5.  <span data-ttu-id="b170b-127">为设计选择适当的选项。</span><span class="sxs-lookup"><span data-stu-id="b170b-127">Select the appropriate options for your design.</span></span> <span data-ttu-id="b170b-128">定义初始条件后，会出现一个页面，确认“功能概述”已完成。</span><span class="sxs-lookup"><span data-stu-id="b170b-128">After the initial criteria are defined, a page will confirm that your Features Overview is complete.</span></span>

6.  <span data-ttu-id="b170b-129">单击 "**设计网站**" 以定义您的中心网站。</span><span class="sxs-lookup"><span data-stu-id="b170b-129">Click **Design Sites** to define your central site.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="b170b-130">每个 Lync Server 2013 拓扑都至少有一个中央站点。</span><span class="sxs-lookup"><span data-stu-id="b170b-130">Each Lync Server 2013 topology will have at least one central site.</span></span> <span data-ttu-id="b170b-131">您的设计可能有一个中央站点、一个包含多个分支站点的中央站点、多个中央站点，或者具有与每个中心站点相关联的分支站点的多个中央站点。</span><span class="sxs-lookup"><span data-stu-id="b170b-131">Your design may have a single central site, a central site with a number of branch sites, a number of central sites, or a number of central sites with branch sites associated with each central site.</span></span>

    
    </div>

7.  <span data-ttu-id="b170b-132">在 "**网站名称**" 中，键入将标识此中心网站的名称。</span><span class="sxs-lookup"><span data-stu-id="b170b-132">In **Site Name**, type the name that will identify this central site.</span></span>

8.  <span data-ttu-id="b170b-133">在 "**网站托管用户**" 中，键入将驻留在此中央站点中的本地并发用户的预期数量。</span><span class="sxs-lookup"><span data-stu-id="b170b-133">In **Site Homed Users**, type the expected number of on-premises concurrent users who will be homed in this central site.</span></span>

9.  <span data-ttu-id="b170b-134">在 "**云托管用户**" 中，键入将托管在此中央站点中的联机并发用户的预期数量。</span><span class="sxs-lookup"><span data-stu-id="b170b-134">In **Cloud Homed Users**, type the expected number of online concurrent users who will be homed in this central site.</span></span>

10. <span data-ttu-id="b170b-135">根据需要修改联机协作、用户、语音、其他部署选项或服务器应用程序的选择。</span><span class="sxs-lookup"><span data-stu-id="b170b-135">Modify the selections for Online Collaboration, Users, Voice, Additional Deployment Options, or Server Applications, as needed.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="b170b-136">在设计的这一时刻，只能选择或清除部署的选项。</span><span class="sxs-lookup"><span data-stu-id="b170b-136">At this point in the design, you can only select or clear options for your deployment.</span></span> <span data-ttu-id="b170b-137">但是，您可以在规划工具的后续阶段中配置更多选项。</span><span class="sxs-lookup"><span data-stu-id="b170b-137">However, you can configure more options in a later phase of the Planning Tool.</span></span> <span data-ttu-id="b170b-138">还有一些选项不可用且无法清除。</span><span class="sxs-lookup"><span data-stu-id="b170b-138">There are also options that are unavailable and cannot be cleared.</span></span> <span data-ttu-id="b170b-139">此外，可能必须先清除一个选项后才能清除另一个。</span><span class="sxs-lookup"><span data-stu-id="b170b-139">In addition, you may have to clear one option in order to clear another.</span></span> <span data-ttu-id="b170b-140">例如，如果清除 "语音" 下的 "<STRONG>企业语音</STRONG>" 选项，则还会清除 "服务器应用程序（所有这些都是企业语音的功能）" 下的 "<STRONG>响应组</STRONG>"、"<STRONG>通知</STRONG>" 和 "<STRONG>呼叫寄存</STRONG>" 选项。</span><span class="sxs-lookup"><span data-stu-id="b170b-140">For example, if you clear the <STRONG>Enterprise Voice</STRONG> option under Voice, then the <STRONG>Response Group</STRONG>, <STRONG>Announcement</STRONG>, and <STRONG>Call Park</STRONG> options under Server Applications (all of which are features of Enterprise Voice) are also cleared.</span></span>

    
    </div>

11. <span data-ttu-id="b170b-141">定义站点名称和用户数量后，单击 **“下一步”**。</span><span class="sxs-lookup"><span data-stu-id="b170b-141">After defining a site name and number of users, click **Next**.</span></span>

12. <span data-ttu-id="b170b-142">以下页面要求提供有关 SIP 域、会议设置、语音设置和基础结构、Exchange UM、外部用户访问、持久聊天设置、客户端设置、并置选项和分支站点的信息。</span><span class="sxs-lookup"><span data-stu-id="b170b-142">The following pages ask for information about SIP domains, conference settings, voice settings and infrastructure, Exchange UM, external user access, Persistent Chat settings, client settings, collocation options, and branch sites.</span></span> <span data-ttu-id="b170b-143">根据需要回答这些问题。</span><span class="sxs-lookup"><span data-stu-id="b170b-143">Answer these questions as appropriate.</span></span>

13. <span data-ttu-id="b170b-144">最后一个问题询问您是否要创建另一个中心站点。</span><span class="sxs-lookup"><span data-stu-id="b170b-144">The final question asks if you want to create another central site.</span></span> <span data-ttu-id="b170b-145">如果选择 **"是**"，则规划工具将返回到 "中央站点" 页面。</span><span class="sxs-lookup"><span data-stu-id="b170b-145">If you select **Yes**, then the Planning Tool returns to the Central Sites page.</span></span> <span data-ttu-id="b170b-146">如果选择 "**否**"，请单击 "**下一步**"，然后单击 "**绘图**" 显示高级别全局拓扑视图。</span><span class="sxs-lookup"><span data-stu-id="b170b-146">If you select **No**, click **Next**, and then click **Draw** to display the high-level Global Topology view.</span></span>

14. <span data-ttu-id="b170b-147">若要查看现有拓扑，请单击 "**显示**"。</span><span class="sxs-lookup"><span data-stu-id="b170b-147">To view an existing topology, click **Display**.</span></span>

15. <span data-ttu-id="b170b-148">单击代表之前保存的拓扑的 .xml 文件，然后单击 **“打开”**。</span><span class="sxs-lookup"><span data-stu-id="b170b-148">Click the .xml file that represents the previously saved topology, and then click **Open**.</span></span>

16. <span data-ttu-id="b170b-149">规划工具将显示 "全局拓扑" 页面。</span><span class="sxs-lookup"><span data-stu-id="b170b-149">The Planning Tool displays the Global Topology page.</span></span> <span data-ttu-id="b170b-150">您现在可以使用规划工具中提供的工具开始编辑、更新或更改拓扑。</span><span class="sxs-lookup"><span data-stu-id="b170b-150">You can now begin editing, updating, or changing the topology by using the tools available in the Planning Tool.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="b170b-151">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b170b-151">See Also</span></span>


[<span data-ttu-id="b170b-152">在 Lync Server 2013 中编辑设计</span><span class="sxs-lookup"><span data-stu-id="b170b-152">Editing the design in Lync Server 2013</span></span>](lync-server-2013-editing-the-design.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


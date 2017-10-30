---
title: "在 Microsoft Teams 中使用内置选项卡和自定义选项卡 | Microsoft 支持"
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/25/2017
ms.topic: article
ms.service: msteams
description: "了解如何使用内置选项卡和自定义选项卡来包括对话、文件、地图等功能。"
Set_Free_Tag: Strat_MT_TeamsAdmin
ms.openlocfilehash: 2ba0e5d8897b7c77aa4fd9c319c9a77fcf2129b9
ms.sourcegitcommit: 2e557e90b4e30fe99ff9df3897b8e54f38ea2f2e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/22/2017
---
<a name="use-built-in-and-custom-tabs-in-microsoft-teams"></a><span data-ttu-id="61aa4-103">在 Microsoft Teams 中使用内置选项卡和自定义选项卡</span><span class="sxs-lookup"><span data-stu-id="61aa4-103">Use built-in and custom tabs in Microsoft Teams</span></span>
==================================================

<span data-ttu-id="61aa4-104">团队成员通过选项卡可以访问频道内专用画布上的服务。</span><span class="sxs-lookup"><span data-stu-id="61aa4-104">Tabs allow team members to access services on a dedicated canvas within a channel.</span></span> <span data-ttu-id="61aa4-105">这样，团队可以在频道的上下文中直接使用你提供的工具和数据，并就它们展开对话。</span><span class="sxs-lookup"><span data-stu-id="61aa4-105">This lets the team work directly with the tools and data you provide, and to have conversations about them, in the channel’s context.</span></span> <span data-ttu-id="61aa4-106">对于每个新频道，默认预配两个选项卡，如下文所列和下图所示：</span><span class="sxs-lookup"><span data-stu-id="61aa4-106">With every new channel, two tabs are provisioned by default, as listed and shown in the image, below:</span></span>

-   <span data-ttu-id="61aa4-107">对话</span><span class="sxs-lookup"><span data-stu-id="61aa4-107">Conversations</span></span>

-   <span data-ttu-id="61aa4-108">文件</span><span class="sxs-lookup"><span data-stu-id="61aa4-108">Files</span></span>

![](media/Use_built-in_and_custom_tabs_in_Microsoft_Teams_image1.png)

1.  <span data-ttu-id="61aa4-109">所有者和团队成员可以向每个频道添加其他选项卡，以帮助集成其云服务。</span><span class="sxs-lookup"><span data-stu-id="61aa4-109">Owners and team members can add additional tabs, to each channel, to help integrate their cloud services.</span></span>

2.  <span data-ttu-id="61aa4-110">Excel、PowerPoint、Word 和 PDF 必须先上载到**“文件”选项卡**，然后才能转换为选项卡。</span><span class="sxs-lookup"><span data-stu-id="61aa4-110">Excel, PowerPoint, Word and PDF files must be uploaded to the **Files tab** before they can be converted to tabs.</span></span> <span data-ttu-id="61aa4-111">此外，只需单击一次即可将已上载的任何现有文件转换为选项卡，如下所示。</span><span class="sxs-lookup"><span data-stu-id="61aa4-111">Alternatively, any existing uploaded, files can be converted into tabs with a single click, as shown below.</span></span>

    ![](media/Use_built-in_and_custom_tabs_in_Microsoft_Teams_image2.png)

3.  <span data-ttu-id="61aa4-112">要添加网站，URL 必须以 **https 前缀**开头，以使交换的任何信息保持安全。</span><span class="sxs-lookup"><span data-stu-id="61aa4-112">To add a website, the URL must start with an **https prefix,** so that any information exchanged remains secure.</span></span>

4.  <span data-ttu-id="61aa4-113">团队成员尝试向其频道添加自定义选项卡时，系统会提供详细说明。</span><span class="sxs-lookup"><span data-stu-id="61aa4-113">Detailed instructions are provided when a team member attempts to add a custom tab into their channel.</span></span>

5.  <span data-ttu-id="61aa4-114">向频道添加自定义选项卡时，系统会创建一个**选项卡对话**，允许团队成员就内容展开重点讨论。</span><span class="sxs-lookup"><span data-stu-id="61aa4-114">When a Custom tab is added into a channel, a **Tab conversation** is created that allows team members to have focused discussions about the content.</span></span>

    ![](media/Use_built-in_and_custom_tabs_in_Microsoft_Teams_image3.png)

6.  <span data-ttu-id="61aa4-115">可以向频道添加其他选项卡，以帮助用户轻松访问和管理其所需的数据或通过最新方式进行交互。</span><span class="sxs-lookup"><span data-stu-id="61aa4-115">Additional tabs can be added to channels to help users easily access and manage the data they need or interact with the most.</span></span> <span data-ttu-id="61aa4-116">这可以是 Power BI 报表、仪表板，甚至可以是 [Microsoft Stream](https://go.microsoft.com/fwlink/?linkid=855785) 视频频道，你可以在此发布培训视频。</span><span class="sxs-lookup"><span data-stu-id="61aa4-116">This can be a Power BI report, a dashboard, or even a [Microsoft Stream](https://go.microsoft.com/fwlink/?linkid=855785) video channel where you publish training videos.</span></span>

    ![](media/Use_built-in_and_custom_tabs_in_Microsoft_Teams_image4.png)

<a name="develop-custom-tabs"></a><span data-ttu-id="61aa4-117">开发自定义选项卡</span><span class="sxs-lookup"><span data-stu-id="61aa4-117">Develop custom tabs</span></span>
-------------------

<span data-ttu-id="61aa4-118">除了内置选项卡外，组织可以轻松设计和开发自己的选项卡，这些选项卡可以集成到 Microsoft Teams 中，也可以与社区的其他人共享。</span><span class="sxs-lookup"><span data-stu-id="61aa4-118">In addition to the built-in tabs, organizations can easily design and develop their own tabs, that can be integrated into Microsoft Teams, or shared with the rest of the community.</span></span>

<span data-ttu-id="61aa4-119">Microsoft Developer Network 提供了[详细说明](https://go.microsoft.com/fwlink/?linkid=855786)来指导如何设计和构建你自己的选项卡，以及下载和部署 Microsoft 开发的[示例选项卡](https://go.microsoft.com/fwlink/?linkid=855787)。</span><span class="sxs-lookup"><span data-stu-id="61aa4-119">The Microsoft Developer Network provides [detailed instructions](https://go.microsoft.com/fwlink/?linkid=855786) to design and build your own tabs; and download and deploy [sample tabs](https://go.microsoft.com/fwlink/?linkid=855787) developed by Microsoft.</span></span>

![](media/Use_built-in_and_custom_tabs_in_Microsoft_Teams_image5.png)

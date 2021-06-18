## <a name="integration-models-for-solution-providers"></a><span data-ttu-id="ad238-101">解决方案提供商的集成模型</span><span class="sxs-lookup"><span data-stu-id="ad238-101">Integration models for solution providers</span></span>

<a name="steps"></a>

<span data-ttu-id="ad238-102">作为联系中心解决方案提供商，有三种模型可供选择，将连接的联系中心解决方案集成到 Teams 中：</span><span class="sxs-lookup"><span data-stu-id="ad238-102">As a contact center solution provider, there are three models to choose from to integrate your connected contact center solution into Teams:</span></span>

- <span data-ttu-id="ad238-103">如果要使用经过认证的 SDC 和直接路由将联系中心解决方案连接到 Teams，请参阅 [连接模型](?tabs=connect#steps)。</span><span class="sxs-lookup"><span data-stu-id="ad238-103">If you want to use certified SBCs and Direct Routing to connect a contact center solution to Teams, see the [Connect model](?tabs=connect#steps).</span></span>

- <span data-ttu-id="ad238-104">若要使用 Azure 机器人和 Microsoft Graph 通信 API 使解决方案提供商能够创建 Teams 应用，请参阅 [扩展模型](?tabs=extend#steps)。</span><span class="sxs-lookup"><span data-stu-id="ad238-104">If you want to use Azure bots and the Microsoft Graph Communication APIs to enable solution providers to create Teams apps, see the [Extend model](?tabs=extend#steps).</span></span>

- <span data-ttu-id="ad238-105">如果要使用 SDK，使解决方案提供商能够将本机 Teams 体验 imbed 到其应用中，请参阅 [Power 模型](?tabs=power#steps)。</span><span class="sxs-lookup"><span data-stu-id="ad238-105">If you want to use an SDK that enables solution providers to imbed native Teams experiences in their App, see the [Power model](?tabs=power#steps).</span></span> <span data-ttu-id="ad238-106">当 SDK 可用时（到 2021 年底）时，可以使用电源解决方案。</span><span class="sxs-lookup"><span data-stu-id="ad238-106">Power solutions will be possible when the SDK is available, towards the end of 2021.</span></span>

### <a name="the-connect-model"></a>[<span data-ttu-id="ad238-107">**连接模型**</span><span class="sxs-lookup"><span data-stu-id="ad238-107">**The Connect model**</span></span>](#tab/connect)

<span data-ttu-id="ad238-108">Connect 模型使用 Microsoft 认证的 SDC 和直接路由将联系中心解决方案连接到 Teams 电话系统基础结构，实现增强的路由、配置和系统见解。</span><span class="sxs-lookup"><span data-stu-id="ad238-108">The Connect model uses Microsoft certified SBCs and Direct Routing to connect contact center solutions to Teams phone system infrastructure, enabling enhanced routing, configuration, and system insights.</span></span>

<span data-ttu-id="ad238-109">代理可以设置自动化虚拟助手和基于技能的路由队列，以收集信息并与客户主题专家联系。</span><span class="sxs-lookup"><span data-stu-id="ad238-109">Agents can set up automated virtual assistants and skill-based routing queues to gather information and connect customers with subject matter experts.</span></span>

<span data-ttu-id="ad238-110">**功能亮点：**</span><span class="sxs-lookup"><span data-stu-id="ad238-110">**Feature highlights:**</span></span>

<span data-ttu-id="ad238-111">虽然这些功能不是此集成模型的功能综合列表，但关注领域包括：</span><span class="sxs-lookup"><span data-stu-id="ad238-111">While these features aren't a comprehensive list of feature capabilities for this model of integration, the focus areas include:</span></span>

  - <span data-ttu-id="ad238-112">Office 365 身份验证，使代理能够从集成的 CCaaS 客户端连接到其 Microsoft 租户</span><span class="sxs-lookup"><span data-stu-id="ad238-112">Office 365 authN for agents to connect to their Microsoft tenant from their integrated CCaaS client</span></span> 

  - <span data-ttu-id="ad238-113">查看 Teams 何时提供代理</span><span class="sxs-lookup"><span data-stu-id="ad238-113">See when agents are available with Teams</span></span>

  - <span data-ttu-id="ad238-114">Teams 的转接和群组通话支持</span><span class="sxs-lookup"><span data-stu-id="ad238-114">Transfers and group call support with Teams</span></span> 

  - <span data-ttu-id="ad238-115">用于与 Teams 集成的 Teams Graph API 和云通信 API</span><span class="sxs-lookup"><span data-stu-id="ad238-115">Teams Graph APIs and Cloud Communication APIs for integration with Teams</span></span> 

  - <span data-ttu-id="ad238-116">多租户 SIP 中继，支持解决方案提供商 SBC 上的多个客户。</span><span class="sxs-lookup"><span data-stu-id="ad238-116">Multi-tenant SIP trunking to support several customers on solution provider’s SBC.</span></span>  

  - <span data-ttu-id="ad238-117">解决方案提供商使用 [<span class="underline">Microsoft 认证的会话边界控制器 (SBC) </span>](../direct-routing-border-controllers.md)</span><span class="sxs-lookup"><span data-stu-id="ad238-117">Solution providers to use [<span class="underline">Microsoft certified session border controller (SBC)</span>](../direct-routing-border-controllers.md)</span></span>


### <a name="the-extend-model"></a>[<span data-ttu-id="ad238-118">**扩展模型**</span><span class="sxs-lookup"><span data-stu-id="ad238-118">**The Extend model**</span></span>](#tab/extend)

<span data-ttu-id="ad238-119">扩展模型使用 Microsoft Graph 中的 [Teams](/microsoftteams/platform/overview)客户端平台 [、Teams Graph API](/graph/api/resources/teams-api-overview?view=graph-rest-1.0) 和 [云通信 API](/graph/api/resources/communications-api-overview?view=graph-rest-1.0)与 Teams 客户端集成。</span><span class="sxs-lookup"><span data-stu-id="ad238-119">The Extend model integrates with the Teams client using the [Teams client platform](/microsoftteams/platform/overview), [Teams Graph APIs](/graph/api/resources/teams-api-overview?view=graph-rest-1.0) and [Cloud Communications API in Microsoft Graph](/graph/api/resources/communications-api-overview?view=graph-rest-1.0).</span></span> <span data-ttu-id="ad238-120">扩展模型还针对所有联系中心呼叫和呼叫控制体验使用 Teams 电话系统，并且联系中心解决方案提供商与 Microsoft 365 一起充当电话运营商。</span><span class="sxs-lookup"><span data-stu-id="ad238-120">The Extend model also uses the Teams phone system for all contact center calls and call control experiences, and the contact center solution provider acts as a telephony carrier alongside Microsoft 365.</span></span>

<span data-ttu-id="ad238-121">代理可以使用 Teams 进行内部协作和外部通信，并且可以在开始参与之前从多个系统关联数据的动态上下文笔记受益，避免进行代价高昂的上下文切换。</span><span class="sxs-lookup"><span data-stu-id="ad238-121">Agents can use Teams for internal collaboration and external communication and can benefit from dynamic, contextual notes correlating data from multiple systems prior to starting an engagement and then avoid costly context switching.</span></span>

<span data-ttu-id="ad238-122">组织可以设计工作流和高级路由配置（向下到个人）并测量其系统和交互的质量。</span><span class="sxs-lookup"><span data-stu-id="ad238-122">Organizations can design workflows and advanced routing configurations down to the individual and measure the quality of their system and interactions.</span></span>

<span data-ttu-id="ad238-123">**功能亮点：**</span><span class="sxs-lookup"><span data-stu-id="ad238-123">**Feature highlights:**</span></span>

<span data-ttu-id="ad238-124">虽然这些功能不是此集成模型的功能综合列表，但关注领域包括：</span><span class="sxs-lookup"><span data-stu-id="ad238-124">While these features aren't a comprehensive list of feature capabilities for this model of integration, the focus areas include:</span></span>

  - <span data-ttu-id="ad238-125">用于与 Teams 集成的 Teams Graph API 和云通信 API</span><span class="sxs-lookup"><span data-stu-id="ad238-125">Teams Graph APIs and Cloud Communication APIs for integration with Teams</span></span> 

  - <span data-ttu-id="ad238-126">用于代理体验的基于 Teams 的应用</span><span class="sxs-lookup"><span data-stu-id="ad238-126">Teams-based app for agent experiences</span></span> 

  - <span data-ttu-id="ad238-127">Teams 作为代理的主要调用终结点</span><span class="sxs-lookup"><span data-stu-id="ad238-127">Teams as the primary calling endpoint for the agents</span></span> 

  - <span data-ttu-id="ad238-128">用于所有呼叫控件的 Teams 客户端呼叫</span><span class="sxs-lookup"><span data-stu-id="ad238-128">Teams client calling for all the call controls</span></span>

  - <span data-ttu-id="ad238-129">适用于 Teams Web 客户端和移动客户端的代理体验应用</span><span class="sxs-lookup"><span data-stu-id="ad238-129">Agent experience app for both Teams web and mobile client</span></span>

  - <span data-ttu-id="ad238-130">Teams 中 CCaaS 应用中代理的分析、工作流管理、基于角色的体验</span><span class="sxs-lookup"><span data-stu-id="ad238-130">Analytics, workflow management, role-based experiences for agents in the CCaaS app in Teams</span></span>

  - <span data-ttu-id="ad238-131">与 Teams 客户端集成的聊天和协作体验</span><span class="sxs-lookup"><span data-stu-id="ad238-131">Chat and collaboration experiences integrated with Teams clients</span></span> 

  - <span data-ttu-id="ad238-132">在所有应用中保留 Teams 客户端体验的性能和质量</span><span class="sxs-lookup"><span data-stu-id="ad238-132">Preserve performance and quality of Teams client experiences in all apps</span></span>  

### <a name="the-power-model"></a>[<span data-ttu-id="ad238-133">**电源模型**</span><span class="sxs-lookup"><span data-stu-id="ad238-133">**The Power model**</span></span>](#tab/power)

<span data-ttu-id="ad238-134">借助 Power 模型，解决方案提供商能够使用 Teams 呼叫基础结构和客户端平台创建基于本机 Azure 的语音应用程序，为协作客户和代理连接提供现代智能解决方案。</span><span class="sxs-lookup"><span data-stu-id="ad238-134">The Power model enables solution providers to create native Azure-based voice applications using the Teams calling infrastructure and client platform to deliver modern, intelligent solutions for collaborative customer and agent connection.</span></span> <span data-ttu-id="ad238-135">Power 模型的目标是提供单应用、单屏幕联系中心体验。</span><span class="sxs-lookup"><span data-stu-id="ad238-135">The goal of the Power model is to provide a one-app, one-screen contact center experience.</span></span>

<span data-ttu-id="ad238-136">**功能亮点：**</span><span class="sxs-lookup"><span data-stu-id="ad238-136">**Feature highlights:**</span></span>

<span data-ttu-id="ad238-137">虽然这些功能不是此集成模型的功能综合列表，但关注领域包括：</span><span class="sxs-lookup"><span data-stu-id="ad238-137">While these features aren't a comprehensive list of feature capabilities for this model of integration, the focus areas include:</span></span>

  - <span data-ttu-id="ad238-138">通过 Teams SDK 以本机方式为全渠道通信启用正式代理体验</span><span class="sxs-lookup"><span data-stu-id="ad238-138">Formal agent experiences natively enabled for omni-channel communication via Teams SDK</span></span> 

  - <span data-ttu-id="ad238-139">使用 Teams 协作服务进行代理协作和客户交互</span><span class="sxs-lookup"><span data-stu-id="ad238-139">Use Teams collaboration services for agent collaboration and customer interactions</span></span>  

  - <span data-ttu-id="ad238-140">快速预配云服务，随时随地部署</span><span class="sxs-lookup"><span data-stu-id="ad238-140">Rapid provisioning of cloud services, deploy anywhere</span></span> 

  - <span data-ttu-id="ad238-141">在 Teams 对话期间直接进行对话控制和与用户交互</span><span class="sxs-lookup"><span data-stu-id="ad238-141">Direct conversation control and interaction with users during Teams conversations</span></span> 

>[!NOTE]
> <span data-ttu-id="ad238-142">Power 模型将在 2021 年底可用。</span><span class="sxs-lookup"><span data-stu-id="ad238-142">The Power model will be available towards the end of 2021.</span></span>

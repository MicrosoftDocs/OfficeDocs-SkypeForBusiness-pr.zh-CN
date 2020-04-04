---
title: 为一线工作人员大规模预配 Microsoft Teams
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: keschm
description: 关于使用脚本为一线工作人员部署或预配 Microsoft Teams 的指南。
localization_priority: Priority
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- Teams_ITAdmin_RemoteWorkers
- remotework
appliesto:
- Microsoft Teams
ms.openlocfilehash: 4bb1250fd3cc02599fafa37ab6ac694403e33df9
ms.sourcegitcommit: f0f2fa999c1ca4a1118377c7938a247f79217609
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/02/2020
ms.locfileid: "43106829"
---
# <a name="how-to-provisions-teams-at-scale-for-firstline-workers"></a><span data-ttu-id="4262a-103">如何为一线工作人员预配 Teams</span><span class="sxs-lookup"><span data-stu-id="4262a-103">How to provisions Teams at scale for Firstline Workers</span></span>

<span data-ttu-id="4262a-104">是否需要快速将大量用户加入到 Microsoft Teams 并为他们配置精简体验？</span><span class="sxs-lookup"><span data-stu-id="4262a-104">Do you need to rapidly onboard a large number of users to Microsoft Teams and configure a streamlined experience for them?</span></span> <span data-ttu-id="4262a-105">可按以下说明操作，快速预配标识、预配团队，并分配所有相关策略来控制最终用户体验。</span><span class="sxs-lookup"><span data-stu-id="4262a-105">You can quickly provision identities, provision teams, and assign all relevant policies to control the end user experience by walking through the following instructions.</span></span>

<span data-ttu-id="4262a-106">在本演练中，你将学习如何：</span><span class="sxs-lookup"><span data-stu-id="4262a-106">In this walkthrough, you'll learn how to:</span></span>

- <span data-ttu-id="4262a-107">创建大量用户。</span><span class="sxs-lookup"><span data-stu-id="4262a-107">Create a large number of users.</span></span>
- <span data-ttu-id="4262a-108">创建大量团队并设置适当的频道。</span><span class="sxs-lookup"><span data-stu-id="4262a-108">Create a large number of teams and set up the appropriate channels.</span></span>
- <span data-ttu-id="4262a-109">大规模分配许可。</span><span class="sxs-lookup"><span data-stu-id="4262a-109">Assign licensing at scale.</span></span>
- <span data-ttu-id="4262a-110">创建相应的 Teams 消息传递策略、应用设置策略和应用权限策略。</span><span class="sxs-lookup"><span data-stu-id="4262a-110">Create appropriate Teams Messaging Policies, App Setup Policies, and App Permission Policies.</span></span>
- <span data-ttu-id="4262a-111">将这些策略大规模应用至用户。</span><span class="sxs-lookup"><span data-stu-id="4262a-111">Apply those policies to users at scale.</span></span>
- <span data-ttu-id="4262a-112">向指定团队分配大量用户。</span><span class="sxs-lookup"><span data-stu-id="4262a-112">Assign a large number of users into a designated team.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="4262a-113">先决条件</span><span class="sxs-lookup"><span data-stu-id="4262a-113">Prerequisites</span></span>

<span data-ttu-id="4262a-114">从[此位置](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/FLWTeamsScale.zip?raw=true)下载资产。</span><span class="sxs-lookup"><span data-stu-id="4262a-114">Download the assets from [this location](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/FLWTeamsScale.zip?raw=true).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="4262a-115">上面提供的链接中的脚本是由 Microsoft 按原样提供的，必须根据你的个人需求进行修改。</span><span class="sxs-lookup"><span data-stu-id="4262a-115">The scripts in the link provided above are provided as-is by Microsoft, and must be modified for your individual needs.</span></span>

## <a name="technical-requirements"></a><span data-ttu-id="4262a-116">技术要求</span><span class="sxs-lookup"><span data-stu-id="4262a-116">Technical requirements</span></span>

- <span data-ttu-id="4262a-117">租户必须具有相应数量的可用许可证，包括 Microsoft Teams。</span><span class="sxs-lookup"><span data-stu-id="4262a-117">Your tenant must have the appropriate number of licenses available that include Microsoft Teams.</span></span> <span data-ttu-id="4262a-118">如果你还没有此类许可证，请按照此处的说明激活 [ Office 365 E1 免费试用版](e1-trial-license.md)。</span><span class="sxs-lookup"><span data-stu-id="4262a-118">If you do not already have these licenses, follow the instructions here to activate the [Office 365 E1 Free Trial](e1-trial-license.md).</span></span>
- <span data-ttu-id="4262a-119">执行这些步骤的用户必须在 Azure AD 中具有全局管理员或用户管理员角色。</span><span class="sxs-lookup"><span data-stu-id="4262a-119">The user taking these steps must do so in the role of Global Admin or User Admin in Azure AD.</span></span>
- <span data-ttu-id="4262a-120">用户必须具有在其本地计算机上安装和配置软件的权限。</span><span class="sxs-lookup"><span data-stu-id="4262a-120">User must have the rights to install and configure software on their local machine.</span></span>

## <a name="step-by-step-process-overview"></a><span data-ttu-id="4262a-121">分步流程概述</span><span class="sxs-lookup"><span data-stu-id="4262a-121">Step-by-step process overview</span></span>

1. <span data-ttu-id="4262a-122">**设置环境**</span><span class="sxs-lookup"><span data-stu-id="4262a-122">**Setup Your Environment**</span></span>
    1. <span data-ttu-id="4262a-123">下载包含示例 PowerShell 脚本和文档的 ZIP 文件</span><span class="sxs-lookup"><span data-stu-id="4262a-123">Download the ZIP file containing the sample PowerShell scripts and documentation</span></span>
    1. <span data-ttu-id="4262a-124">设置凭据</span><span class="sxs-lookup"><span data-stu-id="4262a-124">Setup credentials</span></span>
    1. <span data-ttu-id="4262a-125">配置本地环境</span><span class="sxs-lookup"><span data-stu-id="4262a-125">Configure local environment</span></span>
    1. <span data-ttu-id="4262a-126">配置 PowerShell 模块和环境变量</span><span class="sxs-lookup"><span data-stu-id="4262a-126">Configure PowerShell Modules and Environmental Variables</span></span>
    1. <span data-ttu-id="4262a-127">创建应用注册</span><span class="sxs-lookup"><span data-stu-id="4262a-127">Create App Registration</span></span>
1. <span data-ttu-id="4262a-128">**创建和设置团队**</span><span class="sxs-lookup"><span data-stu-id="4262a-128">**Create and Setup Teams**</span></span>
    1. <span data-ttu-id="4262a-129">创建团队</span><span class="sxs-lookup"><span data-stu-id="4262a-129">Create Teams</span></span>
    1. <span data-ttu-id="4262a-130">为团队创建频道</span><span class="sxs-lookup"><span data-stu-id="4262a-130">Create Channels for Teams</span></span>
1. <span data-ttu-id="4262a-131">**创建 Teams 策略**</span><span class="sxs-lookup"><span data-stu-id="4262a-131">**Create Teams Policies**</span></span>
    1. <span data-ttu-id="4262a-132">创建 Teams 消息传递策略。</span><span class="sxs-lookup"><span data-stu-id="4262a-132">Create Teams Messaging Policies</span></span>
    1. <span data-ttu-id="4262a-133">创建 Teams 应用设置策略。</span><span class="sxs-lookup"><span data-stu-id="4262a-133">Create Teams App Setup Policies</span></span>
    1. <span data-ttu-id="4262a-134">创建 Teams 应用权限策略。</span><span class="sxs-lookup"><span data-stu-id="4262a-134">Create Teams App Permission Policies</span></span>
1. <span data-ttu-id="4262a-135">**创建和设置用户**</span><span class="sxs-lookup"><span data-stu-id="4262a-135">**Create and Setup Users**</span></span>
    1. <span data-ttu-id="4262a-136">创建用户和安全组</span><span class="sxs-lookup"><span data-stu-id="4262a-136">Create users and security groups</span></span>
    1. <span data-ttu-id="4262a-137">通过基于组的许可向用户分配许可</span><span class="sxs-lookup"><span data-stu-id="4262a-137">Assign licensing to users via group-based licensing</span></span>
1. <span data-ttu-id="4262a-138">**分配用户和策略**</span><span class="sxs-lookup"><span data-stu-id="4262a-138">**Assign Users and Policies**</span></span>
    1. <span data-ttu-id="4262a-139">向团队分配用户</span><span class="sxs-lookup"><span data-stu-id="4262a-139">Assign users to Teams</span></span>
    1. <span data-ttu-id="4262a-140">向用户和组分配策略</span><span class="sxs-lookup"><span data-stu-id="4262a-140">Assign policies to User and Groups</span></span>
1. <span data-ttu-id="4262a-141">**测试和验证**</span><span class="sxs-lookup"><span data-stu-id="4262a-141">**Test and Validate**</span></span>
    1. <span data-ttu-id="4262a-142">检查错误</span><span class="sxs-lookup"><span data-stu-id="4262a-142">Check for errors</span></span>
    1. <span data-ttu-id="4262a-143">以测试用户身份登录 Teams</span><span class="sxs-lookup"><span data-stu-id="4262a-143">Login to Teams with a test user</span></span>

## <a name="set-up-your-environment"></a><span data-ttu-id="4262a-144">设置环境</span><span class="sxs-lookup"><span data-stu-id="4262a-144">Set up your environment</span></span>

<span data-ttu-id="4262a-145">可以通过以下步骤设置环境：</span><span class="sxs-lookup"><span data-stu-id="4262a-145">The following steps will allow you to set up your environment:</span></span>

### <a name="download-zip-file-containing-sample-powershell-scripts"></a><span data-ttu-id="4262a-146">下载包含示例 PowerShell 脚本的 .zip 文件</span><span class="sxs-lookup"><span data-stu-id="4262a-146">Download .zip file containing sample PowerShell scripts</span></span>

<span data-ttu-id="4262a-147">在继续操作前，你需要在[此位置](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/FLWTeamsScale.zip?raw=true)下载脚本。</span><span class="sxs-lookup"><span data-stu-id="4262a-147">Before you can proceed, you'll need to download the scripts at [this location](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/FLWTeamsScale.zip?raw=true).</span></span>

### <a name="setup-credentials"></a><span data-ttu-id="4262a-148">设置凭据</span><span class="sxs-lookup"><span data-stu-id="4262a-148">Setup Credentials</span></span>

<span data-ttu-id="4262a-149">在本文档和示例脚本中，我们选择创建一个包含凭据的引用文件以简化操作。</span><span class="sxs-lookup"><span data-stu-id="4262a-149">In this document and the sample scripts we've chosen to create a reference file that contains your credentials in order to make things easier.</span></span> <span data-ttu-id="4262a-150">这种技术使你无需在将凭据保留在本地存储的同时对所有不同的服务终结点进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="4262a-150">This technique removes the need for you to authenticate to all the various service endpoints while maintaining the credentials in a local store.</span></span> <span data-ttu-id="4262a-151">为了运行后续脚本，你需要使用你和你的环境特有的凭据更新该引用文件。</span><span class="sxs-lookup"><span data-stu-id="4262a-151">In order to run the subsequent scripts, you'll need to update that reference file with the credentials that are unique to you and your environment.</span></span> <span data-ttu-id="4262a-152">在随后的每个脚本中，使用我们在 **GetCreds** 中调用的 helper 函数读取相应的凭据，这些凭据用于连接到各种服务。</span><span class="sxs-lookup"><span data-stu-id="4262a-152">From within each subsequent script, the appropriate credentials are read with the helper function  we've called **GetCreds**, and those credentials are used to connect to the various services.</span></span>

<span data-ttu-id="4262a-153">不同服务要求不同凭据的情况并不常见。</span><span class="sxs-lookup"><span data-stu-id="4262a-153">It's not uncommon for different services to require different credentials.</span></span> <span data-ttu-id="4262a-154">例如，你可能对 MicrosoftTeams、AzureAD 和 MSonline 使用不同的凭据，在这种情况下，你可以运行 SetCred，使用有意义的名称保存每个凭据文件。</span><span class="sxs-lookup"><span data-stu-id="4262a-154">For example you might have different credentials for MicrosoftTeams, AzureAD, and MSonline, in which case you can run SetCred saving each credential file with its own meaningful name.</span></span>

<span data-ttu-id="4262a-155">例如：SetCreds msol-cred.xml SetCreds azuread-cred.xml SetCreds teams-cred.xml</span><span class="sxs-lookup"><span data-stu-id="4262a-155">Examples: SetCreds msol-cred.xml SetCreds azuread-cred.xml SetCreds teams-cred.xml</span></span>

> [!NOTE]
> <span data-ttu-id="4262a-156">用于凭据的帐户不能要求提供 MFA。</span><span class="sxs-lookup"><span data-stu-id="4262a-156">The account used for the credentials cannot require MFA.</span></span>

<span data-ttu-id="4262a-157">以下是说明各种脚本如何使用保存的凭据进行身份验证的示例：</span><span class="sxs-lookup"><span data-stu-id="4262a-157">Here is an example of how the various scripts then use the saved credentials to authenticate:</span></span>

```azurepowershell
# Connect to MicrosoftTeams
$teams_cred = GetCreds teams-cred.xml
Connect-MicrosoftTeams -Credential $teams_cred
```

<span data-ttu-id="4262a-158">要设置你的凭据，请完成以下操作：</span><span class="sxs-lookup"><span data-stu-id="4262a-158">In order to set your credentials, complete the following:</span></span>

1. <span data-ttu-id="4262a-159">在 .zip 文件资产中查找 **SetCreds.ps1**。</span><span class="sxs-lookup"><span data-stu-id="4262a-159">Find the **SetCreds.ps1** in the .zip file assets.</span></span>
1. <span data-ttu-id="4262a-160">在 PowerShell 中运行 **SetCreds.ps1** 脚本以保存你的凭据。</span><span class="sxs-lookup"><span data-stu-id="4262a-160">From PowerShell run the **SetCreds.ps1** script to save your credentials.</span></span>
    1. <span data-ttu-id="4262a-161">系统将提示你“正在执行操作‘Export-Clixml’...”，你需要输入“Y”以批准。</span><span class="sxs-lookup"><span data-stu-id="4262a-161">You'll be prompted with "Performing the operation "Export-Clixml"..." and you'll need to enter 'Y' to approve.</span></span>

### <a name="configure-the-local-environment"></a><span data-ttu-id="4262a-162">配置本地环境</span><span class="sxs-lookup"><span data-stu-id="4262a-162">Configure the local environment</span></span>

1. <span data-ttu-id="4262a-163">在.zip 文件资产中查找 **SetConfig.ps1**。</span><span class="sxs-lookup"><span data-stu-id="4262a-163">Find the **SetConfig.ps1** in the .zip file assets.</span></span>
1. <span data-ttu-id="4262a-164">在 PowerShell 中运行以下命令，将带括号的条目替换为你的特定信息。</span><span class="sxs-lookup"><span data-stu-id="4262a-164">From PowerShell run the following command, replacing the bracketed entries with your specific information.</span></span>
    1. <span data-ttu-id="4262a-165">**SetConfig.ps1** -tenantName [你的租户名称] -rootPath“[git 存储库根目录的完整路径]”</span><span class="sxs-lookup"><span data-stu-id="4262a-165">**SetConfig.ps1** -tenantName [your tenant name] -rootPath "[full path to the root of the git repo]"</span></span>

<span data-ttu-id="4262a-166">例如：`.\SetConfig.ps1 -tenantName contoso.onmicrosoft.com -rootPath "C:\data\source\FLWTeamsScale"`</span><span class="sxs-lookup"><span data-stu-id="4262a-166">For example: `.\SetConfig.ps1 -tenantName contoso.onmicrosoft.com -rootPath "C:\data\source\FLWTeamsScale"`</span></span>

### <a name="configure-powershell-modules-and-environmental-variables"></a><span data-ttu-id="4262a-167">配置 PowerShell 模块和环境变量</span><span class="sxs-lookup"><span data-stu-id="4262a-167">Configure PowerShell modules and environmental variables</span></span>

<span data-ttu-id="4262a-168">在继续之前，你需要安装并连接若干个 PowerShell 模块，包括 Azure AD、MSAL、MSCloudUtils 和 MicrosoftTeams。</span><span class="sxs-lookup"><span data-stu-id="4262a-168">Before you go further, you'll need to install and connect to several PowerShell modules, including Azure AD, MSAL, MSCloudUtils, and MicrosoftTeams.</span></span>

1. <span data-ttu-id="4262a-169">在 .zip 文件资产中查找 **ConfigurePowerShellModules.ps1**。</span><span class="sxs-lookup"><span data-stu-id="4262a-169">Find the **ConfigurePowerShellModules.ps1** in the .zip file assets.</span></span>
1. <span data-ttu-id="4262a-170">编辑并使用你的变量替换以下环境变量：</span><span class="sxs-lookup"><span data-stu-id="4262a-170">Edit and replace the following environmental variables with your variables:</span></span>
1. <span data-ttu-id="4262a-171">在 PowerShell 中运行 **ConfigurePowerShellModules.ps1** 脚本。</span><span class="sxs-lookup"><span data-stu-id="4262a-171">From PowerShell, run the **ConfigurePowerShellModules.ps1** script.</span></span>

## <a name="create-and-set-up-teams"></a><span data-ttu-id="4262a-172">创建和设置团队</span><span class="sxs-lookup"><span data-stu-id="4262a-172">Create and set up Teams</span></span>

<span data-ttu-id="4262a-173">为了与一线工作人员进行沟通和协作，首先需要建立一系列团队，并向这些团队添加标准频道，我们将在接下来介绍这些内容。</span><span class="sxs-lookup"><span data-stu-id="4262a-173">In order to communicate and collaborate with your Firstline Workers, you will first need to establish a series of Teams and add standard Channels to those teams, which we'll walk through next.</span></span>

### <a name="create-teams"></a><span data-ttu-id="4262a-174">创建团队</span><span class="sxs-lookup"><span data-stu-id="4262a-174">Create teams</span></span>

<span data-ttu-id="4262a-175">团队是组织内人员、内容和工具的集合。</span><span class="sxs-lookup"><span data-stu-id="4262a-175">Teams are a collection of people, content, and tools within your organization.</span></span> <span data-ttu-id="4262a-176">对于大多数以一线工作人为中心的组织，最佳做法是将团队固定在一个物理位置周围。</span><span class="sxs-lookup"><span data-stu-id="4262a-176">For most Firstline Worker-centric organizations, it is best practice to anchor a Team around a physical location.</span></span> <span data-ttu-id="4262a-177">例如，对以下每个位置设立团队：</span><span class="sxs-lookup"><span data-stu-id="4262a-177">For example, a Team for each of the following:</span></span>

- <span data-ttu-id="4262a-178">商店</span><span class="sxs-lookup"><span data-stu-id="4262a-178">Store</span></span>
- <span data-ttu-id="4262a-179">通讯组列表</span><span class="sxs-lookup"><span data-stu-id="4262a-179">Distribution Center</span></span>
- <span data-ttu-id="4262a-180">制造工厂</span><span class="sxs-lookup"><span data-stu-id="4262a-180">Manufacturing Plant</span></span>
- <span data-ttu-id="4262a-181">医院</span><span class="sxs-lookup"><span data-stu-id="4262a-181">Hospital</span></span>
- <span data-ttu-id="4262a-182">杂货店</span><span class="sxs-lookup"><span data-stu-id="4262a-182">Grocery Store</span></span>

<span data-ttu-id="4262a-183">*最佳实践讨论*：设计团队时，务必牢记[团队限制和规范](limits-specifications-teams.md)。</span><span class="sxs-lookup"><span data-stu-id="4262a-183">*Best Practice Discussion*: When designing your teams, it's important to keep in mind [Teams limits and specifications](limits-specifications-teams.md).</span></span> <span data-ttu-id="4262a-184">对于小型组织，可使用组织范围的团队来简化通信并对物理位置结构进行补充。</span><span class="sxs-lookup"><span data-stu-id="4262a-184">For smaller organizations, an org-wide team can be used to streamline communication and complement a physical location structure.</span></span> <span data-ttu-id="4262a-185">对于其他组织，结构化物理位置团队命名约定有助于企业轻松地同时向多个团队交叉发布通信。</span><span class="sxs-lookup"><span data-stu-id="4262a-185">For others, a structured physical location Team naming convention helps assist Corporate Communications with Cross Posting to multiple teams simultaneously with ease.</span></span> <span data-ttu-id="4262a-186">例如，可以搜索名称中带有 US 的所有团队并向其交叉发布通信，以定位所有 US 位置。</span><span class="sxs-lookup"><span data-stu-id="4262a-186">For example, you can search and cross-post to all Teams with US in the name to target all US locations.</span></span> <span data-ttu-id="4262a-187">有关交叉发布的详细信息，请参阅[此处](https://support.office.com/article/cross-post-a-channel-conversation-in-teams-9c1252a3-67ef-498e-a7c1-dd7147b3d295)。</span><span class="sxs-lookup"><span data-stu-id="4262a-187">More information on cross-posting can be found [here](https://support.office.com/article/cross-post-a-channel-conversation-in-teams-9c1252a3-67ef-498e-a7c1-dd7147b3d295).</span></span>

#### <a name="steps-to-create-teams"></a><span data-ttu-id="4262a-188">创建团队的步骤</span><span class="sxs-lookup"><span data-stu-id="4262a-188">Steps to create teams</span></span>

1. <span data-ttu-id="4262a-189">在资产中查找 **Teams Information.csv** 文件。</span><span class="sxs-lookup"><span data-stu-id="4262a-189">Find the **Teams Information.csv** file in the assets.</span></span>
1. <span data-ttu-id="4262a-190">使用组织的特定信息来更新 **Teams Information.csv** 文件中的信息。</span><span class="sxs-lookup"><span data-stu-id="4262a-190">Update the information in the **Teams Information.csv** file with your organization's specific information.</span></span> <span data-ttu-id="4262a-191">请牢记我们上面的最佳做法。</span><span class="sxs-lookup"><span data-stu-id="4262a-191">Keep in mind our best practices above.</span></span>
1. <span data-ttu-id="4262a-192">查找 **CreateTeams. ps1** 脚本。</span><span class="sxs-lookup"><span data-stu-id="4262a-192">Find the **CreateTeams.ps1** script.</span></span>
1. <span data-ttu-id="4262a-193">在 PowerShell 中运行 **CreateTeams.ps1** 脚本。</span><span class="sxs-lookup"><span data-stu-id="4262a-193">From PowerShell, run the **CreateTeams.ps1** script.</span></span>

### <a name="create-channels-for-teams"></a><span data-ttu-id="4262a-194">为团队创建频道</span><span class="sxs-lookup"><span data-stu-id="4262a-194">Create channels for teams</span></span>

<span data-ttu-id="4262a-195">频道是团队中专门的分区，用于按特定主题、项目、学科等整理对话。</span><span class="sxs-lookup"><span data-stu-id="4262a-195">Channels are dedicated sections within a team to keep conversations organized by specific topic, project, discipline, and more.</span></span> <span data-ttu-id="4262a-196">每个团队都将自动获得一个常规频道，但在那里，你可以根据业务需求自定义你的结构。</span><span class="sxs-lookup"><span data-stu-id="4262a-196">Every Team automatically gets a General channel, but from there you can customize your structure according to the needs of your business.</span></span> <span data-ttu-id="4262a-197">例如，你的附加频道结构可能包括：</span><span class="sxs-lookup"><span data-stu-id="4262a-197">For example, your additional channel structure could include:</span></span>

- <span data-ttu-id="4262a-198">**制造** - 安全、第 1 行、第 2 行、企业沟通、培训</span><span class="sxs-lookup"><span data-stu-id="4262a-198">**Manufacturing** - Safety, Line 1, Line 2, Corporate Communications, Training</span></span>
- <span data-ttu-id="4262a-199">**杂货** - 面包店、农产品、肉类、企业沟通、培训</span><span class="sxs-lookup"><span data-stu-id="4262a-199">**Grocery** - Bakery, Produce, Meat, Corporate Communications, Training</span></span>
- <span data-ttu-id="4262a-200">**医疗保健** - 护士、医生、危症监护病房 1、危症监护病房 2</span><span class="sxs-lookup"><span data-stu-id="4262a-200">**Healthcare** - Nurses, Doctors, Critical Care Unit 1, Critical Care Unit 2</span></span>
- <span data-ttu-id="4262a-201">**宾馆** - 前台、维修、客房服务、代客泊车和行李运送、企业沟通、培训</span><span class="sxs-lookup"><span data-stu-id="4262a-201">**Hospitality** - Front Desk, Maintenance, Housekeeping, Valet and Baggage, Corporate Communications, Training</span></span>
- <span data-ttu-id="4262a-202">**零售** - 商店前门、商店后门、企业沟通、培训</span><span class="sxs-lookup"><span data-stu-id="4262a-202">**Retail** - Front of Store, Back of Store, Corporate Communications, Training</span></span>

> [!NOTE]
> <span data-ttu-id="4262a-203">不应将频道视为安全边界。</span><span class="sxs-lookup"><span data-stu-id="4262a-203">Channels should not be thought of as a security boundary.</span></span> <span data-ttu-id="4262a-204">它们是组织工作人员进行协作的一种手段。</span><span class="sxs-lookup"><span data-stu-id="4262a-204">They are a means of organizing your workers for the purposes of collaboration.</span></span>

<span data-ttu-id="4262a-205">*最佳实践讨论*：在设计频道结构时，请务必保持简单，尤其是在你希望许多用户加入的情况下。</span><span class="sxs-lookup"><span data-stu-id="4262a-205">*Best Practice Discussion*: When designing your channel structure, it's important to keep things simple, especially when you're looking to onboard a lot of users.</span></span> <span data-ttu-id="4262a-206">为了最大程度地降低培训需求，请抑制住为每种情况、角色或主题创建频道的冲动。</span><span class="sxs-lookup"><span data-stu-id="4262a-206">Resist the urge to create channels for every situation, role, or topic in order to minimize the need for training.</span></span> <span data-ttu-id="4262a-207">最多选择 3-5 个频道开始体验。</span><span class="sxs-lookup"><span data-stu-id="4262a-207">Pick 3-5 channels at most to get started.</span></span> <span data-ttu-id="4262a-208">可在需要时轻松创建其他频道。</span><span class="sxs-lookup"><span data-stu-id="4262a-208">Additional channels can easily be created as the need arises.</span></span> <span data-ttu-id="4262a-209">实际上，目前仅使用常规频道即可！</span><span class="sxs-lookup"><span data-stu-id="4262a-209">In fact, it's okay to just use the General channel alone for now!</span></span>

#### <a name="steps-to-create-channels-for-teams"></a><span data-ttu-id="4262a-210">为 Teams 创建频道的步骤</span><span class="sxs-lookup"><span data-stu-id="4262a-210">Steps to Create Channels for Teams</span></span>

1. <span data-ttu-id="4262a-211">在 .zip 文件资产中查找 **TeamsChannels.csv** 文件。</span><span class="sxs-lookup"><span data-stu-id="4262a-211">Find the **TeamsChannels.csv** file in the .zip file assets.</span></span>
1. <span data-ttu-id="4262a-212">使用组织的特定信息来更新 **TeamsChannels.csv** 文件。</span><span class="sxs-lookup"><span data-stu-id="4262a-212">Update the **TeamsChannels.csv** file with your organization's specific information.</span></span> <span data-ttu-id="4262a-213">请牢记我们上面的最佳做法。</span><span class="sxs-lookup"><span data-stu-id="4262a-213">Keep in mind our best practices above.</span></span>
1. <span data-ttu-id="4262a-214">在 .zip 文件资产中查找 **CreateTeamsChannels.ps1** 脚本。</span><span class="sxs-lookup"><span data-stu-id="4262a-214">Find the **CreateTeamsChannels.ps1** script in the .zip file assets.</span></span>
1. <span data-ttu-id="4262a-215">在 PowerShell 中运行 **TeamsChannels.ps1** 脚本。</span><span class="sxs-lookup"><span data-stu-id="4262a-215">From PowerShell, run the **TeamsChannels.ps1** script.</span></span>

## <a name="create-teams-policies"></a><span data-ttu-id="4262a-216">创建 Teams 策略</span><span class="sxs-lookup"><span data-stu-id="4262a-216">Create Teams policies</span></span>

<span data-ttu-id="4262a-217">作为管理员，你可以使用 Microsoft Teams 中的团队策略来控制组织中的用户能够看到的内容。</span><span class="sxs-lookup"><span data-stu-id="4262a-217">As an admin, you can use teams policies in Microsoft Teams to control what users in your organization see and can.</span></span> <span data-ttu-id="4262a-218">例如，可以控制将哪些应用程序固定到桌面或 Web 浏览器上的左边栏，或移动设备上的底部栏，以便在大量用户加入时简化最终用户体验。</span><span class="sxs-lookup"><span data-stu-id="4262a-218">For example, you can control which applications are pinned to the left rail on your Desktop or Web browser, or the bottom bar on mobile devices, in order to simplify the end user experience when onboarding a large amount of users.</span></span> <span data-ttu-id="4262a-219">这些策略中的一部分可使用 PowerShell 创建，另一些则必须在 Teams 管理控制台中手动创建。</span><span class="sxs-lookup"><span data-stu-id="4262a-219">Some of these policies can be created with PowerShell, and others have to be manually created in the Teams Admin Console.</span></span>

<span data-ttu-id="4262a-220">*最佳实践讨论*：对于下面的每个策略，我们将选择实际创建两个策略：一个用于一线工作人员，一个用于一线管理人员。</span><span class="sxs-lookup"><span data-stu-id="4262a-220">*Best Practice Discussion*: For each of the following policies, we're choosing to actually create two policies: one for Firstline Workers and one for Firstline Managers.</span></span> <span data-ttu-id="4262a-221">可以根据需要导入任意数目的联系人。</span><span class="sxs-lookup"><span data-stu-id="4262a-221">You can choose to create as many or as few as you like.</span></span> <span data-ttu-id="4262a-222">对于大多数客户来说，最好从两个联系人开始，即使你最初为每个组进行了相同的设置也不例外。</span><span class="sxs-lookup"><span data-stu-id="4262a-222">For most customers, two is a good place to start, even if you give the same settings to each group initially.</span></span> <span data-ttu-id="4262a-223">随着 Teams 体验的发展，你可以选择进一步区分自己的体验，创建两个单独的策略可简化这项工作。</span><span class="sxs-lookup"><span data-stu-id="4262a-223">As your experience with Teams grows, you may choose to differentiate their experience further and having the two separate policies already created can make that simpler.</span></span>

### <a name="create-teams-message-policies"></a><span data-ttu-id="4262a-224">创建 Teams 消息策略</span><span class="sxs-lookup"><span data-stu-id="4262a-224">Create Teams message policies</span></span>

<span data-ttu-id="4262a-225">消息传递策略用于控制为 Microsoft Teams 中的用户提供哪些聊天和频道消息功能。</span><span class="sxs-lookup"><span data-stu-id="4262a-225">Messaging policies are used to control which chat and channel messaging features are available to users in Microsoft Teams.</span></span>

<span data-ttu-id="4262a-226">*最佳实践讨论*：尽管可使用自动创建的默认全局策略，但我们选择了按照以下步骤创建自定义策略，为一线管理人员和一线工作人员提供更加锁定、简单和差异化的体验。</span><span class="sxs-lookup"><span data-stu-id="4262a-226">*Best Practice Discussion*: While you can use the default Global policy that is created automatically, we have opted to create a custom policy using the steps below to provide a more locked down, simple, and differentiated experience for Firstline Managers and Firstline Workers.</span></span>

#### <a name="steps-to-create-teams-message-policies"></a><span data-ttu-id="4262a-227">创建 Teams 消息策略的步骤</span><span class="sxs-lookup"><span data-stu-id="4262a-227">Steps to Create Teams Message Policies</span></span>

1. <span data-ttu-id="4262a-228">在 .zip 文件资产中查找 **TeamsMessagingPolicies.csv** 文件。</span><span class="sxs-lookup"><span data-stu-id="4262a-228">Find the **TeamsMessagingPolicies.csv** file in the .zip file assets.</span></span>
1. <span data-ttu-id="4262a-229">使用组织的特定信息来更新 **TeamsMessagingPolicies.csv** 文件。</span><span class="sxs-lookup"><span data-stu-id="4262a-229">Update the **TeamsMessagingPolicies.csv** file with your organization's specific information.</span></span> <span data-ttu-id="4262a-230">有关各选项的详细信息，请参阅[此处](https://docs.microsoft.com/microsoftteams/messaging-policies-in-teams#messaging-policy-settings)。</span><span class="sxs-lookup"><span data-stu-id="4262a-230">Additional information on some of the various options can be found [here](https://docs.microsoft.com/microsoftteams/messaging-policies-in-teams#messaging-policy-settings).</span></span>
1. <span data-ttu-id="4262a-231">在资产中查找 **CreateTeamsMessagePolicies.ps1** 脚本。</span><span class="sxs-lookup"><span data-stu-id="4262a-231">Find the **CreateTeamsMessagePolicies.ps1** script in the assets.</span></span>
1. <span data-ttu-id="4262a-232">在 PowerShell 中运行 **TeamsMessagePolicies.ps1** 脚本。</span><span class="sxs-lookup"><span data-stu-id="4262a-232">From PowerShell, run the **TeamsMessagePolicies.ps1** script.</span></span>

### <a name="create-teams-app-setup-policies"></a><span data-ttu-id="4262a-233">创建 Teams 应用设置策略</span><span class="sxs-lookup"><span data-stu-id="4262a-233">Create Teams app setup policies</span></span>

<span data-ttu-id="4262a-234">作为管理员，你可以使用应用设置策略执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="4262a-234">As an admin, you can use app setup policies to do the following:</span></span>

- <span data-ttu-id="4262a-235">自定义 Teams 以突出显示对用户最为重要的应用。</span><span class="sxs-lookup"><span data-stu-id="4262a-235">Customize Teams to highlight the apps that are most important for your users.</span></span> <span data-ttu-id="4262a-236">选择要固定的应用并设置其显示顺序。</span><span class="sxs-lookup"><span data-stu-id="4262a-236">You choose the apps to pin and set the order in which they appear.</span></span> <span data-ttu-id="4262a-237">通过固定应用，可展示组织中的用户所需的应用，包括由第三方或组织中的开发人员构建的应用。</span><span class="sxs-lookup"><span data-stu-id="4262a-237">Pinning apps lets you showcase apps that users in your organization need, including those built by third parties or by developers in your organization.</span></span>
- <span data-ttu-id="4262a-238">控制用户是否可以将应用固定到 Teams。</span><span class="sxs-lookup"><span data-stu-id="4262a-238">Control whether users can pin apps to Teams.</span></span>

<span data-ttu-id="4262a-239">将应用程序固定到应用栏。</span><span class="sxs-lookup"><span data-stu-id="4262a-239">Apps are pinned to the app bar.</span></span> <span data-ttu-id="4262a-240">这是 Teams 桌面客户端的侧边栏和 Teams 移动客户端（iOS 和 Android）的底边栏。</span><span class="sxs-lookup"><span data-stu-id="4262a-240">This is the bar on the side of the Teams desktop client and at the bottom of the Teams mobile clients (iOS and Android).</span></span>

|<span data-ttu-id="4262a-241">Teams 桌面客户端</span><span class="sxs-lookup"><span data-stu-id="4262a-241">Teams Desktop Client</span></span>  |         |<span data-ttu-id="4262a-242">Teams 移动客户端</span><span class="sxs-lookup"><span data-stu-id="4262a-242">Teams Mobile Client</span></span>  |
|---------|---------|---------|
|![Teams 桌面客户端的屏幕截图，其中应用已固定到 *应用* 栏。](media/FLW-Teams-Desktop-Client.png)         |         |![Teams 桌面客户端的屏幕截图，其中应用已固定到 *底部* 栏。](media/FLW-Teams-Mobile-Client.png) |

<span data-ttu-id="4262a-245">*最佳实践讨论*：在 Microsoft Teams 管理中心管理应用设置策略。</span><span class="sxs-lookup"><span data-stu-id="4262a-245">*Best Practice Discussion*: You manage app setup policies in the Microsoft Teams admin center.</span></span> <span data-ttu-id="4262a-246">无法使用 PowerShell 创建它们。</span><span class="sxs-lookup"><span data-stu-id="4262a-246">They aren't able to be created with PowerShell.</span></span> <span data-ttu-id="4262a-247">可使用全局（组织范围的默认）策略，或者创建自定义策略并将其分配给用户。</span><span class="sxs-lookup"><span data-stu-id="4262a-247">You can use the global (Org-wide default) policy or create custom policies and assign them to users.</span></span> <span data-ttu-id="4262a-248">除非你创建并分配了自定义策略，否则你组织中的用户将自动分配到全局策略。</span><span class="sxs-lookup"><span data-stu-id="4262a-248">Users in your organization will automatically be assigned to the global policy unless you create and assign a custom policy.</span></span> <span data-ttu-id="4262a-249">出于我们的目的，我们将为一线工作人员和一线管理人员创建两个新策略，以便为他们提供更简单、更精简的体验，从而轻松地同时加入大量用户。</span><span class="sxs-lookup"><span data-stu-id="4262a-249">For our purposes, we are creating two new policies for Firstline Workers and Firstline Managers, in order to provide them a simpler and more streamlined experience to ease onboarding a large number of users simultaneously.</span></span> <span data-ttu-id="4262a-250">你可以选择根据业务需求自定义体验。</span><span class="sxs-lookup"><span data-stu-id="4262a-250">You can choose to customize the experience as your business needs.</span></span>

#### <a name="create-the-firstline-manager-app-setup-policy"></a><span data-ttu-id="4262a-251">创建一线管理人员应用设置策略</span><span class="sxs-lookup"><span data-stu-id="4262a-251">Create the Firstline Manager app setup policy</span></span>

<span data-ttu-id="4262a-252">可以自定义以下设置以满足你的业务需求。</span><span class="sxs-lookup"><span data-stu-id="4262a-252">The following settings can be customized to meet your business needs.</span></span> <span data-ttu-id="4262a-253">我们已根据最佳实践选择了一些推荐的选项，并提高了大规模加入新用户的轻松度。</span><span class="sxs-lookup"><span data-stu-id="4262a-253">We have chosen some recommended options based on best practices and to improve the ease of onboarding new users at scale.</span></span> <span data-ttu-id="4262a-254">有关详细信息，请单击[此处](https://docs.microsoft.com/MicrosoftTeams/teams-app-setup-policies#create-a-custom-app-setup-policy)。</span><span class="sxs-lookup"><span data-stu-id="4262a-254">For more information, click [here](https://docs.microsoft.com/MicrosoftTeams/teams-app-setup-policies#create-a-custom-app-setup-policy).</span></span>

1. <span data-ttu-id="4262a-255">在 Microsoft Teams 管理中心的左侧导航中，转到“ **Teams 应用**” >“ **设置策略**”。</span><span class="sxs-lookup"><span data-stu-id="4262a-255">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Setup policies**.</span></span>
2. <span data-ttu-id="4262a-256">单击“ **添加**”。</span><span class="sxs-lookup"><span data-stu-id="4262a-256">Click **Add**.</span></span>  
3. <span data-ttu-id="4262a-257">输入策略的名称和说明。</span><span class="sxs-lookup"><span data-stu-id="4262a-257">Enter a name and description for the policy.</span></span> <span data-ttu-id="4262a-258">例如，**一线管理人员应用设置策略**。</span><span class="sxs-lookup"><span data-stu-id="4262a-258">As an example: **Firstline Manager App Setup Policy**.</span></span>
<span data-ttu-id="4262a-259">![一线管理人员应用设置策略图像。](media/FLW-FLM-App-Setup-Policy.png)</span><span class="sxs-lookup"><span data-stu-id="4262a-259">![Firstline manager app setup policy image.](media/FLW-FLM-App-Setup-Policy.png)</span></span>

4. <span data-ttu-id="4262a-260">关闭“**上载自定义应用**”。</span><span class="sxs-lookup"><span data-stu-id="4262a-260">Turn off **Upload custom apps**.</span></span>
5. <span data-ttu-id="4262a-261">关闭“**允许用户固定**”。</span><span class="sxs-lookup"><span data-stu-id="4262a-261">Turn off **Allow user pinning**.</span></span>
<span data-ttu-id="4262a-262">![允许用户固定切换图像。](media/FLW-Allow-User-Pinning.png)</span><span class="sxs-lookup"><span data-stu-id="4262a-262">![Allow user pinning switch image.](media/FLW-Allow-User-Pinning.png)</span></span>

6. <span data-ttu-id="4262a-263">如果尚未列出**班次**应用，请添加。</span><span class="sxs-lookup"><span data-stu-id="4262a-263">If it's not already listed, add the **Shifts** app.</span></span> <span data-ttu-id="4262a-264">有关**班次**的更多信息，请单击[此处](expand-teams-across-your-org/shifts/manage-the-shifts-app-for-your-organization-in-teams.md)。</span><span class="sxs-lookup"><span data-stu-id="4262a-264">For more information about **Shifts**, click [here](expand-teams-across-your-org/shifts/manage-the-shifts-app-for-your-organization-in-teams.md).</span></span>
<span data-ttu-id="4262a-265">![“添加固定的应用”屏幕，显示班次应用（列在“添加”按钮旁边）。](media/FLW-Add-Pinned-Apps.png)</span><span class="sxs-lookup"><span data-stu-id="4262a-265">![Add pinned apps screen, showing the Shifts app listed next to an Add button.](media/FLW-Add-Pinned-Apps.png)</span></span>

7. <span data-ttu-id="4262a-266">删除显示的呼叫</span><span class="sxs-lookup"><span data-stu-id="4262a-266">Remove Calling, if it appears.</span></span> <span data-ttu-id="4262a-267">注意：删除此功能不会针对用户禁用它，但会阻止它出现在应用栏，从而简化最终用户体验。</span><span class="sxs-lookup"><span data-stu-id="4262a-267">Note: removing this feature will not disable it for the user, but will prevent it from appearing on the app bar to simplify the end user experience.</span></span>
8. <span data-ttu-id="4262a-268">按以下顺序排列应用以指定其在 Teams 应用栏中的顺序，然后单击“ **保存**”。</span><span class="sxs-lookup"><span data-stu-id="4262a-268">Arrange the apps in the following order to dictate their order in the Teams App Bar, and then click **Save**.</span></span>
    1. <span data-ttu-id="4262a-269">活动</span><span class="sxs-lookup"><span data-stu-id="4262a-269">Activity</span></span>
    1. <span data-ttu-id="4262a-270">聊天</span><span class="sxs-lookup"><span data-stu-id="4262a-270">Chat</span></span>
    1. <span data-ttu-id="4262a-271">团队</span><span class="sxs-lookup"><span data-stu-id="4262a-271">Teams</span></span>
    1. <span data-ttu-id="4262a-272">日历</span><span class="sxs-lookup"><span data-stu-id="4262a-272">Calendar</span></span>
    1. <span data-ttu-id="4262a-273">班次 ![按顺序显示的管理人员应用程序列表的屏幕截图](media/FLW-Manager-Pinned-Apps.png)</span><span class="sxs-lookup"><span data-stu-id="4262a-273">Shifts ![Screenshot of the manager apps list in order.](media/FLW-Manager-Pinned-Apps.png)</span></span>

#### <a name="create-the-firstline-worker-app-setup-policy"></a><span data-ttu-id="4262a-274">创建一线工作人员应用设置策略</span><span class="sxs-lookup"><span data-stu-id="4262a-274">Create the Firstline Worker app setup policy</span></span>

<span data-ttu-id="4262a-275">可以自定义以下设置以满足你的业务需求。</span><span class="sxs-lookup"><span data-stu-id="4262a-275">The following settings can be customized to meet your business needs.</span></span> <span data-ttu-id="4262a-276">我们已根据最佳实践选择了一些推荐的选项，并提高了大规模加入新用户的轻松度。</span><span class="sxs-lookup"><span data-stu-id="4262a-276">We have chosen some recommended options based on best practices and to improve the ease of onboarding new users at scale.</span></span> <span data-ttu-id="4262a-277">有关详细信息，请单击[此处](https://docs.microsoft.com/MicrosoftTeams/teams-app-setup-policies#create-a-custom-app-setup-policy)。</span><span class="sxs-lookup"><span data-stu-id="4262a-277">For more information, click [here](https://docs.microsoft.com/MicrosoftTeams/teams-app-setup-policies#create-a-custom-app-setup-policy).</span></span>

1. <span data-ttu-id="4262a-278">在 Microsoft Teams 管理中心的左侧导航中，转到“ **Teams 应用**” >“ **设置策略**”。</span><span class="sxs-lookup"><span data-stu-id="4262a-278">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Setup policies**.</span></span>
2. <span data-ttu-id="4262a-279">单击“ **添加**”。</span><span class="sxs-lookup"><span data-stu-id="4262a-279">Click **Add**.</span></span>
3. <span data-ttu-id="4262a-280">输入策略的名称和说明。</span><span class="sxs-lookup"><span data-stu-id="4262a-280">Enter a name and description for the policy.</span></span> <span data-ttu-id="4262a-281">例如：**一线工作人员应用设置策略**。</span><span class="sxs-lookup"><span data-stu-id="4262a-281">As an example: **Firstline Worker App Setup Policy**.</span></span>
<span data-ttu-id="4262a-282">![一线工作人员应用设置策略图像。](media/FLW-FLW-App-Setup-Policy.png)</span><span class="sxs-lookup"><span data-stu-id="4262a-282">![Firstline worker app setup policy image.](media/FLW-FLW-App-Setup-Policy.png)</span></span>

4. <span data-ttu-id="4262a-283">关闭“**上载自定义应用**”。</span><span class="sxs-lookup"><span data-stu-id="4262a-283">Turn off **Upload custom apps**.</span></span>
5. <span data-ttu-id="4262a-284">关闭“**允许用户固定**”。</span><span class="sxs-lookup"><span data-stu-id="4262a-284">Turn off **Allow user pinning**.</span></span>
<span data-ttu-id="4262a-285">![允许用户固定切换图像。](media/FLW-Allow-User-Pinning.png)</span><span class="sxs-lookup"><span data-stu-id="4262a-285">![Allow user pinning switch image.](media/FLW-Allow-User-Pinning.png)</span></span>

6. <span data-ttu-id="4262a-286">如果尚未列出**班次**应用，请添加。</span><span class="sxs-lookup"><span data-stu-id="4262a-286">If it's not already listed, add the **Shifts** app.</span></span> <span data-ttu-id="4262a-287">有关**班次**的详细信息，请单击此处。</span><span class="sxs-lookup"><span data-stu-id="4262a-287">For more information about **Shifts**, click here.</span></span>
<span data-ttu-id="4262a-288">![“添加固定的应用”屏幕，显示班次应用（列在“添加”按钮旁边）。](media/FLW-Add-Pinned-Apps.png)</span><span class="sxs-lookup"><span data-stu-id="4262a-288">![Add pinned apps screen, showing the Shifts app listed next to an Add button.](media/FLW-Add-Pinned-Apps.png)</span></span>

7. <span data-ttu-id="4262a-289">删除显示的会议和呼叫</span><span class="sxs-lookup"><span data-stu-id="4262a-289">Remove Meetings and Calling, if they appear.</span></span> <span data-ttu-id="4262a-290">注意：删除这些功能不会针对用户禁用它们，但会阻止它们出现在应用栏，从而简化最终用户体验。</span><span class="sxs-lookup"><span data-stu-id="4262a-290">Note: removing these features will not disable them for the user, but will prevent them from appearing on the app bar to simplify the end user experience.</span></span>
8. <span data-ttu-id="4262a-291">按以下顺序排列应用以指定其在 Teams 应用栏中的顺序，然后单击“ **保存**”。</span><span class="sxs-lookup"><span data-stu-id="4262a-291">Arrange the apps in the following order to dictate their order in the Teams App Bar, and then click **Save**.</span></span>
    1. <span data-ttu-id="4262a-292">活动</span><span class="sxs-lookup"><span data-stu-id="4262a-292">Activity</span></span>
    1. <span data-ttu-id="4262a-293">聊天</span><span class="sxs-lookup"><span data-stu-id="4262a-293">Chat</span></span>
    1. <span data-ttu-id="4262a-294">Teams</span><span class="sxs-lookup"><span data-stu-id="4262a-294">Teams</span></span>
    1. <span data-ttu-id="4262a-295">班次 ![按顺序显示的工作人员应用的屏幕截图。](media/FLW-Worker-Pinned-Apps.png)</span><span class="sxs-lookup"><span data-stu-id="4262a-295">Shifts ![Screenshot of the worker apps list in order.](media/FLW-Worker-Pinned-Apps.png)</span></span>

### <a name="create-app-permission-policies"></a><span data-ttu-id="4262a-296">创建应用权限策略</span><span class="sxs-lookup"><span data-stu-id="4262a-296">Create app permission policies</span></span>

<span data-ttu-id="4262a-297">作为管理员，你可以使用应用权限策略来控制适用于组织中的 Microsoft Teams 用户的应用。</span><span class="sxs-lookup"><span data-stu-id="4262a-297">As an admin, you can use app permission policies to control what apps are available to Microsoft Teams users in your organization.</span></span> <span data-ttu-id="4262a-298">你可以允许或阻止 Microsoft、第三方和你的组织发布的所有应用或特定应用。</span><span class="sxs-lookup"><span data-stu-id="4262a-298">You can allow or block all apps, or specific apps published by Microsoft, third-parties, and your organization.</span></span> <span data-ttu-id="4262a-299">阻止某个应用后，具有该策略的用户将无法从 Teams 应用商店安装它。</span><span class="sxs-lookup"><span data-stu-id="4262a-299">When you block an app, users who have the policy are unable to install it from the Teams app store.</span></span> <span data-ttu-id="4262a-300">必须是全局管理员或 Teams 服务管理员才能管理这些策略。</span><span class="sxs-lookup"><span data-stu-id="4262a-300">You must be a global admin or Teams service admin to manage these policies.</span></span>

<span data-ttu-id="4262a-301">*最佳实践讨论*：在 Microsoft Teams 管理中心管理应用设置策略。</span><span class="sxs-lookup"><span data-stu-id="4262a-301">*Best Practice Discussion*: You manage app setup policies in the Microsoft Teams admin center.</span></span> <span data-ttu-id="4262a-302">无法使用 PowerShell 创建它们。</span><span class="sxs-lookup"><span data-stu-id="4262a-302">They aren't able to be created with PowerShell.</span></span> <span data-ttu-id="4262a-303">可使用全局（组织范围的默认）策略，或者创建自定义策略并将其分配给用户。</span><span class="sxs-lookup"><span data-stu-id="4262a-303">You can use the global (Org-wide default) policy or create custom policies and assign them to users.</span></span> <span data-ttu-id="4262a-304">除非你创建并分配了自定义策略，你组织中的用户将自动获取全局策略。</span><span class="sxs-lookup"><span data-stu-id="4262a-304">Users in your organization will automatically get the global policy unless you create and assign a custom policy.</span></span> <span data-ttu-id="4262a-305">出于我们的目的，我们将为一线工作人员和一线管理人员创建了两个新策略，以便为他们提供更安全、更精简的体验，从而轻松地同时加入大量用户。</span><span class="sxs-lookup"><span data-stu-id="4262a-305">For our purposes, we are creating two new policies for Firstline Workers and Firstline Managers in order to provide a secure and more streamlined experience to ease onboarding a large number of users simultaneously.</span></span> <span data-ttu-id="4262a-306">当然，你也可以选择根据业务需求自定义体验。</span><span class="sxs-lookup"><span data-stu-id="4262a-306">You can of course choose to customize the experience as your business needs.</span></span>

#### <a name="create-the-firstline-manager-app-permission-policy"></a><span data-ttu-id="4262a-307">创建一线管理人员应用权限策略</span><span class="sxs-lookup"><span data-stu-id="4262a-307">Create the Firstline Manager app permission policy</span></span>

<span data-ttu-id="4262a-308">可以自定义以下设置以满足你的业务需求。</span><span class="sxs-lookup"><span data-stu-id="4262a-308">The following settings can be customized to meet your business needs.</span></span> <span data-ttu-id="4262a-309">这些是基于最佳实践的一些推荐选项，可以提高新用户大规模登录的便利性。</span><span class="sxs-lookup"><span data-stu-id="4262a-309">These are some recommended options based on best practices that can improve the ease of onboarding new users at scale.</span></span> <span data-ttu-id="4262a-310">有关详细信息，请单击[此处](teams-app-permission-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="4262a-310">For more information, click [here](teams-app-permission-policies.md).</span></span>

1. <span data-ttu-id="4262a-311">在 Microsoft Teams 管理中心的左侧导航中，转到“ **Teams 应用**” >“ **权限策略**”。</span><span class="sxs-lookup"><span data-stu-id="4262a-311">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Permission policies**.</span></span>
2. <span data-ttu-id="4262a-312">单击“ **添加**”。</span><span class="sxs-lookup"><span data-stu-id="4262a-312">Click **Add**.</span></span>
<span data-ttu-id="4262a-313">![显示添加应用权限策略页面，包含针对 Microsoft、第三方和租户应用的部分。](media/FLW-add-app-permission-policy.png)</span><span class="sxs-lookup"><span data-stu-id="4262a-313">![Shows the add app permission policy page, with sections for Microsoft, third-party, and tenant apps.](media/FLW-add-app-permission-policy.png)</span></span>

3. <span data-ttu-id="4262a-314">输入策略的名称和说明。</span><span class="sxs-lookup"><span data-stu-id="4262a-314">Enter a name and description for the policy.</span></span> <span data-ttu-id="4262a-315">例如，一线管理人员应用权限策略。</span><span class="sxs-lookup"><span data-stu-id="4262a-315">As an example: Firstline Manager App Permission Policy.</span></span>
4. <span data-ttu-id="4262a-316">在 Microsoft 应用下，选择“**允许所有应用**”。</span><span class="sxs-lookup"><span data-stu-id="4262a-316">Under Microsoft apps, select **Allow all apps**.</span></span>
5. <span data-ttu-id="4262a-317">在第三方应用下，选择“**允许所有应用**”。</span><span class="sxs-lookup"><span data-stu-id="4262a-317">Under Third-party apps, select **Allow all apps**.</span></span>
6. <span data-ttu-id="4262a-318">在租户应用下，选择“**允许所有应用**”。</span><span class="sxs-lookup"><span data-stu-id="4262a-318">Under Tenant apps, select **Allow all apps**.</span></span>
7. <span data-ttu-id="4262a-319">单击“ **保存**”。</span><span class="sxs-lookup"><span data-stu-id="4262a-319">Click **Save**.</span></span>

#### <a name="create-the-firstline-worker-app-permission-policy"></a><span data-ttu-id="4262a-320">创建一线员工应用权限策略</span><span class="sxs-lookup"><span data-stu-id="4262a-320">Create the Firstline Worker App Permission Policy</span></span>

<span data-ttu-id="4262a-321">可以自定义以下设置以满足你的业务需求。</span><span class="sxs-lookup"><span data-stu-id="4262a-321">The following settings can be customized to meet your business needs.</span></span> <span data-ttu-id="4262a-322">这些是基于最佳实践的一些推荐选项，可以提高新用户大规模登录的便利性。</span><span class="sxs-lookup"><span data-stu-id="4262a-322">These are some recommended options based on best practices that can improve the ease of onboarding new users at scale.</span></span> <span data-ttu-id="4262a-323">有关详细信息，请单击[此处](teams-app-permission-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="4262a-323">For more information, click [here](teams-app-permission-policies.md).</span></span>

1. <span data-ttu-id="4262a-324">在 Microsoft Teams 管理中心的左侧导航中，转到“ **Teams 应用**” >“ **权限策略**”。</span><span class="sxs-lookup"><span data-stu-id="4262a-324">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Permission policies**.</span></span>
2. <span data-ttu-id="4262a-325">单击“ **添加**”。</span><span class="sxs-lookup"><span data-stu-id="4262a-325">Click **Add**.</span></span>
<span data-ttu-id="4262a-326">![显示添加应用权限策略页面，包含针对 Microsoft、第三方和租户应用的部分。](media/FLW-add-app-permission-policy.png)</span><span class="sxs-lookup"><span data-stu-id="4262a-326">![Shows the add app permission policy page, with sections for Microsoft, third-party, and tenant apps.](media/FLW-add-app-permission-policy.png)</span></span>

3. <span data-ttu-id="4262a-327">输入策略的名称和说明。</span><span class="sxs-lookup"><span data-stu-id="4262a-327">Enter a name and description for the policy.</span></span> <span data-ttu-id="4262a-328">例如，一线员工应用权限策略。</span><span class="sxs-lookup"><span data-stu-id="4262a-328">As an example: Firstline Worker App Permission Policy.</span></span>
4. <span data-ttu-id="4262a-329">在 Microsoft 应用下，选择“**允许所有应用**”。</span><span class="sxs-lookup"><span data-stu-id="4262a-329">Under Microsoft apps, select **Allow all apps**.</span></span>
5. <span data-ttu-id="4262a-330">在第三方应用下，选择“**阻止所有应用**”。</span><span class="sxs-lookup"><span data-stu-id="4262a-330">Under Third-party apps, select **Block all apps**.</span></span>
6. <span data-ttu-id="4262a-331">在租户应用下，选择“**允许所有应用**”。</span><span class="sxs-lookup"><span data-stu-id="4262a-331">Under Tenant apps, select **Allow all apps**.</span></span>
7. <span data-ttu-id="4262a-332">单击“ **保存**”。</span><span class="sxs-lookup"><span data-stu-id="4262a-332">Click **Save**.</span></span>

## <a name="create-and-set-up-users"></a><span data-ttu-id="4262a-333">创建和设置用户</span><span class="sxs-lookup"><span data-stu-id="4262a-333">Create and set up users</span></span>

### <a name="create-user-and-security-groups"></a><span data-ttu-id="4262a-334">创建用户和安全组</span><span class="sxs-lookup"><span data-stu-id="4262a-334">Create user and security groups</span></span>

<span data-ttu-id="4262a-335">要在 Teams 中处理大量用户，你首先需要在 Azure AD 中创建用户。</span><span class="sxs-lookup"><span data-stu-id="4262a-335">To work with a large amount of users in Teams you first need to have the users created in Azure AD.</span></span> <span data-ttu-id="4262a-336">有很多方法可以预配大量用户，但我们要强调以下几点：</span><span class="sxs-lookup"><span data-stu-id="4262a-336">There are many ways to provision a large number of users, but we're going to highlight the following:</span></span>

- <span data-ttu-id="4262a-337">如果这些用户已存在于下面其中一个 HR 系统只中，请使用以下链接设置用户预配：</span><span class="sxs-lookup"><span data-stu-id="4262a-337">If these users already exist in one of the following HR systems, use the following links to set up user provisioning:</span></span>
  - <span data-ttu-id="4262a-338">SAP Success Factors - [教程：配置 Active Directory 用户预配的 SAP SuccessFactors](https://docs.microsoft.com/azure/active-directory/saas-apps/sap-successfactors-inbound-provisioning-tutorial)。</span><span class="sxs-lookup"><span data-stu-id="4262a-338">SAP Success Factors - [Tutorial: Configure SAP SuccessFactors to Active Directory user provisioning](https://docs.microsoft.com/azure/active-directory/saas-apps/sap-successfactors-inbound-provisioning-tutorial).</span></span>
  - <span data-ttu-id="4262a-339">Workday - [教程：针对自动用户预配配置 Workday](https://docs.microsoft.com/azure/active-directory/saas-apps/workday-inbound-tutorial)。</span><span class="sxs-lookup"><span data-stu-id="4262a-339">Workday - [Tutorial: Configure Workday for automatic user provisioning](https://docs.microsoft.com/azure/active-directory/saas-apps/workday-inbound-tutorial).</span></span>
- <span data-ttu-id="4262a-340">如果你的用户信息存在于其他系统中，请继续执行以下步骤。</span><span class="sxs-lookup"><span data-stu-id="4262a-340">If you have your user information in other systems, proceed with the following steps.</span></span>

<span data-ttu-id="4262a-341">为了更高效地管理这些用户，你需要为一线工作人员和一线管理人员创建两个安全组，并按照以下步骤直接将这些用户预配到安全组：</span><span class="sxs-lookup"><span data-stu-id="4262a-341">In order to manage these users at scale more effectively, you need to create two security groups for Firstline Workers and Firstline Managers, and provision those users into the security groups directly, following these steps:</span></span>

1. <span data-ttu-id="4262a-342">在 .zip 文件资产中查找 **SecurityGroups.csv** 文件。</span><span class="sxs-lookup"><span data-stu-id="4262a-342">Find the **SecurityGroups.csv** file in the .zip file assets.</span></span>
1. <span data-ttu-id="4262a-343">使用组织的特定信息来更新 **SecurityGroups.csv** 文件。</span><span class="sxs-lookup"><span data-stu-id="4262a-343">Update the **SecurityGroups.csv** file with your organization's specific information.</span></span>
    1. <span data-ttu-id="4262a-344">务必更新 **MessagePolicy**、**AppPermissionPolicy** 和 **AppSetupPolicy** 的字段，以映射到先前创建的相应策略。</span><span class="sxs-lookup"><span data-stu-id="4262a-344">Make sure to update the **MessagePolicy**, **AppPermissionPolicy**, and **AppSetupPolicy** fields to map to the appropriate policies you created earlier.</span></span>
    1. <span data-ttu-id="4262a-345">务必更新 **LicensePlan** 字段，以反映你打算为每个用户提供的许可证。</span><span class="sxs-lookup"><span data-stu-id="4262a-345">Make sure to update the **LicensePlan** field to reflect the licensing that you intend to give each of these users.</span></span> <span data-ttu-id="4262a-346">有关产品名称和服务计划标识符的详细信息，请参阅[此处](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-service-plan-reference)的文档。</span><span class="sxs-lookup"><span data-stu-id="4262a-346">For more information on product names and service plan identifiers, review the documentation [here](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-service-plan-reference).</span></span>
1. <span data-ttu-id="4262a-347">在 .zip 文件资产中查找 **Users.csv** 文件。</span><span class="sxs-lookup"><span data-stu-id="4262a-347">Find the **Users.csv** file in the .zip file assets.</span></span>
1. <span data-ttu-id="4262a-348">使用组织的特定信息来更新 **Users.csv** 文件。</span><span class="sxs-lookup"><span data-stu-id="4262a-348">Update the **Users.csv** file with your organization's specific information.</span></span>
    1. <span data-ttu-id="4262a-349">默认情况下，我们提供的脚本将创建一个用户，其中临时密码必须在首次登录时更改。</span><span class="sxs-lookup"><span data-stu-id="4262a-349">By default, the script we've provided will create a user with a temporary password that must be changed on first login.</span></span> <span data-ttu-id="4262a-350">如果你不想使用默认密码，请编辑 **CreateUsers.ps1** 脚本以满足你的需求。</span><span class="sxs-lookup"><span data-stu-id="4262a-350">If you don't want to use the default password, edit the **CreateUsers.ps1** script to meet your requirements.</span></span>
    1. <span data-ttu-id="4262a-351">请确保更新“SecurityGroup”字段以反映先前创建的相应名称。</span><span class="sxs-lookup"><span data-stu-id="4262a-351">Make sure to update the SecurityGroup field to reflect the appropriate name created earlier.</span></span>
1. <span data-ttu-id="4262a-352">在 PowerShell 中，运行资产中的 **CreateUsers.ps1**。</span><span class="sxs-lookup"><span data-stu-id="4262a-352">From PowerShell, run the script **CreateUsers.ps1** from assets.</span></span>

### <a name="assign-licensing-to-users-by-group-based-licensing"></a><span data-ttu-id="4262a-353">通过基于组的许可向用户分配许可</span><span class="sxs-lookup"><span data-stu-id="4262a-353">Assign licensing to users by Group-Based licensing</span></span>

<span data-ttu-id="4262a-354">Microsoft 付费的云服务（如 Office 365、企业移动性 + 安全性、Dynamics 365 和其他类似产品）需要许可证。</span><span class="sxs-lookup"><span data-stu-id="4262a-354">Microsoft paid cloud services, such as Office 365, Enterprise Mobility + Security, Dynamics 365, and other similar products, require licenses.</span></span> <span data-ttu-id="4262a-355">这些许可证将分配给需要访问这些服务的每个用户。</span><span class="sxs-lookup"><span data-stu-id="4262a-355">These licenses are assigned to each user who needs access to these services.</span></span> <span data-ttu-id="4262a-356">为管理许可证，管理员将使用其中一个管理门户（Office 或 Azure）和 PowerShell cmdlet。</span><span class="sxs-lookup"><span data-stu-id="4262a-356">To manage licenses, administrators use one of the management portals (Office or Azure) and PowerShell cmdlets.</span></span> <span data-ttu-id="4262a-357">Azure Active Directory (Azure AD) 是支持所有 Microsoft 云服务标识管理的基础结构。</span><span class="sxs-lookup"><span data-stu-id="4262a-357">Azure Active Directory (Azure AD) is the underlying infrastructure that supports identity management for all Microsoft cloud services.</span></span> <span data-ttu-id="4262a-358">Azure AD 存储有关用户许可证分配状态的信息。</span><span class="sxs-lookup"><span data-stu-id="4262a-358">Azure AD stores information about license assignment states for users.</span></span>

<span data-ttu-id="4262a-359">为了大规模启用许可，Azure AD 现在包含基于组的许可，因此我们在本文前面创建了安全组。</span><span class="sxs-lookup"><span data-stu-id="4262a-359">In order to enable licensing at scale, Azure AD now includes group-based licensing, and for this reason we created the security groups earlier in this article.</span></span> <span data-ttu-id="4262a-360">可向组分配一个或多个产品许可证。</span><span class="sxs-lookup"><span data-stu-id="4262a-360">You can assign one or more product licenses to a group.</span></span> <span data-ttu-id="4262a-361">Azure AD 可确保许可证分配给组的所有成员。</span><span class="sxs-lookup"><span data-stu-id="4262a-361">Azure AD ensures that the licenses are assigned to all members of the group.</span></span> <span data-ttu-id="4262a-362">任何加入该组的新成员都获得了相应的许可证。</span><span class="sxs-lookup"><span data-stu-id="4262a-362">Any new members who join the group are assigned the appropriate licenses.</span></span> <span data-ttu-id="4262a-363">离开组的成员的许可证将被删除。</span><span class="sxs-lookup"><span data-stu-id="4262a-363">Licenses are removed from members who leave the group.</span></span> <span data-ttu-id="4262a-364">此许可管理无需通过 PowerShell 自动执行许可证管理，以根据用户的具体情况反映组织中的变化和部门结构。</span><span class="sxs-lookup"><span data-stu-id="4262a-364">This licensing management eliminates the need for automating license management via PowerShell to reflect changes in the organization and departmental structure on a per-user basis.</span></span>

## <a name="assign-users-and-policies"></a><span data-ttu-id="4262a-365">分配用户和策略</span><span class="sxs-lookup"><span data-stu-id="4262a-365">Assign Users and Policies</span></span>

### <a name="assigning-users-to-teams"></a><span data-ttu-id="4262a-366">向团队分配用户</span><span class="sxs-lookup"><span data-stu-id="4262a-366">Assigning users to teams</span></span>

<span data-ttu-id="4262a-367">现在你已创建用户并创建团队，可将所有用户放在适当的团队中。</span><span class="sxs-lookup"><span data-stu-id="4262a-367">Now that you've created the users and created the Teams, it's time to put all the users in the appropriate Teams.</span></span>

1. <span data-ttu-id="4262a-368">在 .zip 文件资产中查找 **Users.csv** 文件，并确保你能准确映射到此文件中的团队。</span><span class="sxs-lookup"><span data-stu-id="4262a-368">Find the **Users.csv** file in the .zip file assets and make sure you have accurate mapping to Teams in this file.</span></span>
1. <span data-ttu-id="4262a-369">在 PowerShell 中运行 .zip 文件资产中的 **AssignUserstoTeams.ps1** 文件。</span><span class="sxs-lookup"><span data-stu-id="4262a-369">From PowerShell, run the script **AssignUserstoTeams.ps1** from the .zip file assets.</span></span>

### <a name="assign-teams-policies-to-users"></a><span data-ttu-id="4262a-370">向用户分配 Teams 策略</span><span class="sxs-lookup"><span data-stu-id="4262a-370">Assign Teams policies to users</span></span>

<span data-ttu-id="4262a-371">你已创建用户和策略来修改 Teams 中的体验，现在可以将这些策略分配给合适的用户了。</span><span class="sxs-lookup"><span data-stu-id="4262a-371">Now that you've created the users and the policies to modify their experience in Teams, it's time to assign those policies to the correct users.</span></span>

1. <span data-ttu-id="4262a-372">在 .zip 文件资产中查找 **SecurityGroups.csv** 文件，并确保你能将策略准确映射到组。</span><span class="sxs-lookup"><span data-stu-id="4262a-372">Find the **SecurityGroups.csv** file in the .zip file assets and make sure you have accurate mapping of the policies to the groups.</span></span>
1. <span data-ttu-id="4262a-373">从 PowerShell 中运行 .zip 资产中的 **AssignPoliciestoUsers.ps1**。</span><span class="sxs-lookup"><span data-stu-id="4262a-373">From PowerShell, run the script **AssignPoliciestoUsers.ps1** from the .zip file assets.</span></span>

## <a name="test-and-validate"></a><span data-ttu-id="4262a-374">测试和验证</span><span class="sxs-lookup"><span data-stu-id="4262a-374">Test and validate</span></span>

### <a name="check-for-errors"></a><span data-ttu-id="4262a-375">检查错误</span><span class="sxs-lookup"><span data-stu-id="4262a-375">Check for errors</span></span>

<span data-ttu-id="4262a-376">运行早期版本的脚本时，将向位于 .zip 文件资产的日志文件夹中的 .csv 文件写入错误或异常。</span><span class="sxs-lookup"><span data-stu-id="4262a-376">As you ran the earlier scripts, errors or exceptions were written to a .csv file located in the logs folder of the .zip file assets.</span></span> <span data-ttu-id="4262a-377">此文件可用于调查可能发生的任何问题。</span><span class="sxs-lookup"><span data-stu-id="4262a-377">This file can be used to investigate any issues that may have occurred.</span></span>

<span data-ttu-id="4262a-378">异常的一个示例是，你试图创建一个租户中已经存在的团队。</span><span class="sxs-lookup"><span data-stu-id="4262a-378">An example of an exception could be if you tried to create a team that already existed in your tenant.</span></span>

1. <span data-ttu-id="4262a-379">查找“**日志**”文件夹，并审查它可能包含的任何 .csv 文件。</span><span class="sxs-lookup"><span data-stu-id="4262a-379">Find the **Logs** folder and review any .csv file it may contain.</span></span> <span data-ttu-id="4262a-380">如果没有异常，则不会在这里找到异常文件。</span><span class="sxs-lookup"><span data-stu-id="4262a-380">If there are no exceptions, you may not find an exception file here.</span></span>

### <a name="login-to-teams-with-a-test-user"></a><span data-ttu-id="4262a-381">以测试用户身份登录 Teams</span><span class="sxs-lookup"><span data-stu-id="4262a-381">Login to Teams with a test user</span></span>

<span data-ttu-id="4262a-382">你已经完成所有步骤，现在可以验证已完成的工作了。</span><span class="sxs-lookup"><span data-stu-id="4262a-382">Now that you've completed all the steps, it's time to verify the work you've completed.</span></span>

1. <span data-ttu-id="4262a-383">从先前的列表中选择一个用户，并使用该用户的凭据登录到 Teams。</span><span class="sxs-lookup"><span data-stu-id="4262a-383">Select a user from your earlier list and log into Teams with that user's credentials.</span></span>
1. <span data-ttu-id="4262a-384">验证 Teams 的外观和风格是否符合你的预期。</span><span class="sxs-lookup"><span data-stu-id="4262a-384">Verify the look and feel of Teams is what you expected.</span></span> <span data-ttu-id="4262a-385">如果不符合，请查看**创建 Teams 策略**和**向用户分配 Teams 策略**部分。</span><span class="sxs-lookup"><span data-stu-id="4262a-385">If not, review the **Create Teams Policies** and the **Assign Teams Policies to Users** sections.</span></span>
1. <span data-ttu-id="4262a-386">验证用户是否在正确的团队中。</span><span class="sxs-lookup"><span data-stu-id="4262a-386">Verify the user is in the correct team.</span></span> <span data-ttu-id="4262a-387">如果不在，请查看**创建和设置用户**和**向团队分配用户**部分。</span><span class="sxs-lookup"><span data-stu-id="4262a-387">If not, review the **Create and Setup Users** and **Assign Users to Teams** sections.</span></span>

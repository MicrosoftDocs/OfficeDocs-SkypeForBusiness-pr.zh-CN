---
title: 分配会议策略以支持匿名用户
ms.reviewer: ''
ms:assetid: 662de022-1111-40f7-bad4-f2b686f30973
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg521007(v=OCS.15)
ms:contentKeyID: 48184333
mtps_version: v=OCS.15
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 你可以通过配置会议策略来控制哪些人可以邀请匿名用户，并将该会议策略应用于特定用户。
ms.openlocfilehash: b5427ec96d3593cf87656f562acf0afc183b92d6
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818413"
---
# <a name="assign-conferencing-policies-to-support-anonymous-users-in-skype-for-business-server"></a><span data-ttu-id="b4782-103">在 Skype for Business 服务器中分配会议策略以支持匿名用户</span><span class="sxs-lookup"><span data-stu-id="b4782-103">Assign conferencing policies to support anonymous users in Skype for Business Server</span></span> 


<span data-ttu-id="b4782-104">默认情况下，将阻止所有用户邀请匿名用户参与会议。</span><span class="sxs-lookup"><span data-stu-id="b4782-104">By default, all users are prevented from inviting anonymous users to participate in a meeting.</span></span> <span data-ttu-id="b4782-105">你可以通过配置会议策略来控制哪些人可以邀请匿名用户，并将该会议策略应用于特定用户。</span><span class="sxs-lookup"><span data-stu-id="b4782-105">You control who can invite anonymous users by configuring a conferencing policy to support anonymous users, and applying that conferencing policy to specific users.</span></span> <span data-ttu-id="b4782-106">有关如何配置会议策略以支持匿名用户的详细信息，请参阅[在 skype For Business 服务器中创建会议策略](../../conferencing/create-policies.md)和[管理对 Skype for business 服务器的联盟和外部访问](../managing-federation-and-external-access.md)。</span><span class="sxs-lookup"><span data-stu-id="b4782-106">For details about how to configure a conferencing policies to support anonymous users, see [Create conferencing policies in Skype for Business Server](../../conferencing/create-policies.md) and [Managing federation and external access to Skype for Business Server](../managing-federation-and-external-access.md).</span></span>

<span data-ttu-id="b4782-107">使用此部分中的过程将已创建的会议策略应用于一个或多个用户或用户组。</span><span class="sxs-lookup"><span data-stu-id="b4782-107">Use the procedure in this section to apply a conferencing policy that you have already created to one or more users or user groups.</span></span>

> [!NOTE]  
> <span data-ttu-id="b4782-108">除了配置和应用策略以允许用户邀请匿名用户之外，还必须为你的组织启用匿名用户支持。</span><span class="sxs-lookup"><span data-stu-id="b4782-108">In addition to configuring and applying a policy to enable users to invite anonymous users, you must also enable support for anonymous users for your organization.</span></span> <span data-ttu-id="b4782-109">有关详细信息，请参阅[在 Skype For Business 服务器中配置用于控制公共用户访问的策略](../external-access-policies/configure-policies-to-control-public-user-access.md)。</span><span class="sxs-lookup"><span data-stu-id="b4782-109">For details, see [Configure policies to control public user access in Skype for Business Server](../external-access-policies/configure-policies-to-control-public-user-access.md).</span></span>


## <a name="to-configure-a-user-policy-for-anonymous-participation-in-meetings"></a><span data-ttu-id="b4782-110">配置匿名参与会议的用户策略</span><span class="sxs-lookup"><span data-stu-id="b4782-110">To configure a user policy for anonymous participation in meetings</span></span>

1.  <span data-ttu-id="b4782-111">使用 RTCUniversalServerAdmins 组成员（或具有同等用户权限）的用户帐户，或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="b4782-111">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="b4782-112">打开一个浏览器窗口，然后输入管理员 URL 以打开 Skype for Business 服务器控制面板。</span><span class="sxs-lookup"><span data-stu-id="b4782-112">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="b4782-113">在左侧导航栏中，单击 "**会议**"，然后执行下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="b4782-113">In the left navigation bar, click **Conferencing**, and then do one of the following:</span></span>
    
    1.  <span data-ttu-id="b4782-114">若要创建新的用户策略，请单击 "**新建**"，然后单击 "**用户策略**"。</span><span class="sxs-lookup"><span data-stu-id="b4782-114">To create a new user policy, click **New**, and then click **User policy**.</span></span> <span data-ttu-id="b4782-115">在 "**名称**" 字段中创建一个唯一名称，用于指示用户策略所涉及的内容（例如， **EnableAnonymous**适用于启用与匿名用户的通信的用户策略）。</span><span class="sxs-lookup"><span data-stu-id="b4782-115">Create a unique name in the **Name** field that indicates what the user policy covers (for example, **EnableAnonymous** for a user policy that enables communications with anonymous users).</span></span>
    
    2.  <span data-ttu-id="b4782-116">若要配置现有用户策略，请单击表中列出的相应策略，单击 "**编辑**"，然后单击 "**显示详细信息**"。</span><span class="sxs-lookup"><span data-stu-id="b4782-116">To configure an existing user policy, click the appropriate policy listed in the table, click **Edit**, and then click **Show details**.</span></span>

4.  <span data-ttu-id="b4782-117">在 "**会议策略**" 对话框中，选中 "**允许参与者邀请匿名用户**" 复选框。</span><span class="sxs-lookup"><span data-stu-id="b4782-117">In the **Conferencing Policies** dialog box, select the **Allow participants to invite anonymous users** check box.</span></span>

5.  <span data-ttu-id="b4782-118">单击“**提交**”。</span><span class="sxs-lookup"><span data-stu-id="b4782-118">Click **Commit**.</span></span>

6.  <span data-ttu-id="b4782-119">在左侧导航栏中，单击 "**用户**"，搜索要配置的用户帐户。</span><span class="sxs-lookup"><span data-stu-id="b4782-119">In the left navigation bar, click **Users**, search on the user account that you want to configure.</span></span>

7.  <span data-ttu-id="b4782-120">在列出搜索结果的表中，单击相应的用户帐户，再单击“**编辑**”，然后单击“**显示详细信息**”。</span><span class="sxs-lookup"><span data-stu-id="b4782-120">In the table that lists the search results, click the user account, click **Edit**, and then click **Show details**.</span></span>

8.  <span data-ttu-id="b4782-121">在 "**会议策略**" 下的 "**编辑 Skype for Business 服务器" 用户**中，选择包含要应用于此用户的匿名用户访问配置的用户策略。</span><span class="sxs-lookup"><span data-stu-id="b4782-121">In **Edit Skype for Business Server User** under **Conferencing policy**, select the user policy with the anonymous user access configuration that you want to apply to this user.</span></span>  

    > [!NOTE]  
    > <span data-ttu-id="b4782-122">" <STRONG> &lt;自动&gt; </STRONG>设置" 应用默认服务器安装设置，并由服务器自动应用。</span><span class="sxs-lookup"><span data-stu-id="b4782-122">The <STRONG>&lt;Automatic&gt;</STRONG> settings apply the default server installation settings and are applied automatically by the server.</span></span>


<span data-ttu-id="b4782-123">若要使用户能够邀请匿名用户加入会议，还必须在组织中启用匿名用户支持。</span><span class="sxs-lookup"><span data-stu-id="b4782-123">To enable users to invite anonymous users to conferences, you must also enable support for anonymous users in your organization.</span></span> <span data-ttu-id="b4782-124">有关详细信息，请参阅[在 Skype For Business 服务器中配置用于控制公共用户访问的策略](../external-access-policies/configure-policies-to-control-public-user-access.md)。</span><span class="sxs-lookup"><span data-stu-id="b4782-124">For details, see [Configure policies to control public user access in Skype for Business Server](../external-access-policies/configure-policies-to-control-public-user-access.md).</span></span>


---
title: Microsoft Teams信息保护许可证报告
author: anandab-msft
ms.author: anandab
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: ''
f1.keywords:
- NOCSH
localization_priority: Normal
search.appverid: ''
ms.collection:
- M365-collaboration
description: 了解如何使用 Teams 管理中心中的Microsoft Teams信息保护许可证报告，了解组织中应用如何使用更改通知事件订阅 API。
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: f5652ee503d6810a11f1b152dc0ea2dad23cf4df
ms.sourcegitcommit: 5c68298474d1782e69bde8c0940be7150cb93f6e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/23/2021
ms.locfileid: "53096873"
---
# <a name="microsoft-teams-information-protection-license-report"></a><span data-ttu-id="dd5e0-103">Microsoft Teams信息保护许可证报告</span><span class="sxs-lookup"><span data-stu-id="dd5e0-103">Microsoft Teams information protection license report</span></span>

<span data-ttu-id="dd5e0-104">通过 Teams 信息保护许可证报告，可以深入了解订阅更改通知事件[](/graph/api/resources/subscription?view=graph-rest-1.0)以侦听在[](/graph/api/resources/webhooks?view=graph-rest-1.0)租户级别 (（即 /teams/getAllMessage 或 /chats/getAllMessages) ）创建、更新或删除的消息的应用。</span><span class="sxs-lookup"><span data-stu-id="dd5e0-104">The Teams information protection license report gives insight into apps that have [subscribed](/graph/api/resources/subscription?view=graph-rest-1.0) to [change notification](/graph/api/resources/webhooks?view=graph-rest-1.0) events to listen to created, updated, or deleted messages at tenant level (that is, /teams/getAllMessage or /chats/getAllMessages).</span></span> <span data-ttu-id="dd5e0-105">只有在用户具有所需的许可证时，才成功发送与消息 [对应的更改通知](/graph/teams-licenses)。</span><span class="sxs-lookup"><span data-stu-id="dd5e0-105">A change notification corresponding to the message is sent successfully only when the user has the [required license](/graph/teams-licenses).</span></span>  <span data-ttu-id="dd5e0-106">可以看到给定用户触发了多少个更改通知。</span><span class="sxs-lookup"><span data-stu-id="dd5e0-106">You can see how many change notifications was triggered by a given user.</span></span>


## <a name="view-the-information-protection-license-report"></a><span data-ttu-id="dd5e0-107">查看信息保护许可证报告</span><span class="sxs-lookup"><span data-stu-id="dd5e0-107">View the information protection license report</span></span>

<span data-ttu-id="dd5e0-108">必须是 Teams 服务管理员才能管理这些策略。</span><span class="sxs-lookup"><span data-stu-id="dd5e0-108">You must be a Teams service admin to make these changes.</span></span> <span data-ttu-id="dd5e0-109">请参阅 [Teams 管理员角色管理 Teams](../using-admin-roles.md) ，了解管理员角色和权限。</span><span class="sxs-lookup"><span data-stu-id="dd5e0-109">See [Use Teams administrator roles to manage Teams](../using-admin-roles.md) to read about getting admin roles and permissions.</span></span>

1. <span data-ttu-id="dd5e0-110">在管理中心左侧导航Microsoft Teams，选择 **"分析"&报告**  >  **"使用情况报告"。**</span><span class="sxs-lookup"><span data-stu-id="dd5e0-110">In the left navigation of the Microsoft Teams admin center, select **Analytics & reports** > **Usage reports**.</span></span> <span data-ttu-id="dd5e0-111">在"**查看报表"选项卡上的**"报表 **"下**，选择"**信息保护许可证"。**</span><span class="sxs-lookup"><span data-stu-id="dd5e0-111">On the **View reports** tab, under **Report**, select **Information Protection License**.</span></span>
2. <span data-ttu-id="dd5e0-112">在 **"日期范围"** 下，选择一个范围。</span><span class="sxs-lookup"><span data-stu-id="dd5e0-112">Under **Date range**, select a range.</span></span>
3. <span data-ttu-id="dd5e0-113">在 **"应用**"下，选择一个应用，然后选择"**运行报表"。**</span><span class="sxs-lookup"><span data-stu-id="dd5e0-113">Under **Apps**, select an app and then select **Run report**.</span></span>

    <span data-ttu-id="dd5e0-114">![屏幕截图：Teams管理中心中带标注Teams信息保护许可证报告](../media/teams-info-protection-license-report-with-callouts.png "屏幕截图：Teams管理中心中带标注Teams信息保护许可证报告")</span><span class="sxs-lookup"><span data-stu-id="dd5e0-114">![Screenshot of the Teams information protection license report in the Teams admin center with callouts](../media/teams-info-protection-license-report-with-callouts.png "Screenshot of the Teams information protection license report in the Teams admin center with callouts")</span></span>

## <a name="interpret-the-report"></a><span data-ttu-id="dd5e0-115">解释报告</span><span class="sxs-lookup"><span data-stu-id="dd5e0-115">Interpret the report</span></span>

|<span data-ttu-id="dd5e0-116">标注</span><span class="sxs-lookup"><span data-stu-id="dd5e0-116">Callout</span></span> |<span data-ttu-id="dd5e0-117">说明</span><span class="sxs-lookup"><span data-stu-id="dd5e0-117">Description</span></span>  |
|--------|-------------|
|<span data-ttu-id="dd5e0-118">**1**</span><span class="sxs-lookup"><span data-stu-id="dd5e0-118">**1**</span></span>   |<span data-ttu-id="dd5e0-119">可以查看信息保护许可证报告，了解过去 7 天、30 天或 90 天的趋势。</span><span class="sxs-lookup"><span data-stu-id="dd5e0-119">The information protection license report can be viewed for trends over the last 7 days, 30, or 90 days.</span></span> |
|<span data-ttu-id="dd5e0-120">**2**</span><span class="sxs-lookup"><span data-stu-id="dd5e0-120">**2**</span></span>   |<span data-ttu-id="dd5e0-121">应用名称将显示过去 n 天内已订阅更改消息通知事件的所有应用的列表，如日期范围内所选。</span><span class="sxs-lookup"><span data-stu-id="dd5e0-121">App name will display a list of all apps that have subscribed to change notification events of messages in the last n days as selected in the date range.</span></span> |
|<span data-ttu-id="dd5e0-122">**3**</span><span class="sxs-lookup"><span data-stu-id="dd5e0-122">**3**</span></span>   |<span data-ttu-id="dd5e0-123">下表提供了所选应用的每个用户使用情况的细分。</span><span class="sxs-lookup"><span data-stu-id="dd5e0-123">The table gives you a breakdown of usage per user for the selected app.</span></span><ul><li><span data-ttu-id="dd5e0-124">**显示** 名称显示名称用户的名称。</span><span class="sxs-lookup"><span data-stu-id="dd5e0-124">**Display name** is the display name of the user.</span></span> <span data-ttu-id="dd5e0-125">选择显示名称转到管理中心中用户的详细信息Microsoft Teams页面。</span><span class="sxs-lookup"><span data-stu-id="dd5e0-125">Select the display name to go to the user's details page in the Microsoft Teams admin center.</span></span></li><li><span data-ttu-id="dd5e0-126">**如果用户具有** 此处 [] 中定义的所需许可证之一，则" (许可证) https://docs.microsoft.com/en-us/graph/teams-licenses 为"是"</span><span class="sxs-lookup"><span data-stu-id="dd5e0-126">**Has Required License** is yes if the user has one of the required licenses as defined (here)[https://docs.microsoft.com/en-us/graph/teams-licenses].</span></span> <span data-ttu-id="dd5e0-127">如果用户没有所需的许可证，则会显示"分配许可证"链接，该链接导航到 Microsoft 管理中心中的用户许可证详细信息页 ("活动用户">选择用户名  >  ) 。</span><span class="sxs-lookup"><span data-stu-id="dd5e0-127">If the user does not have the required license, the _Assign license_ link is displayed which navigated to the user's license detail page in the Microsoft admin center (**Users** > **Active Users** > select username).</span></span></li><li><span data-ttu-id="dd5e0-128">**"许可证保护的事件** "是针对该用户创建、更新或删除的消息发送到应用的唯一更改通知事件数。</span><span class="sxs-lookup"><span data-stu-id="dd5e0-128">**License Protected Events** is the number of unique change notification events sent to the app against a message which was created, updated or deleted by that user.</span></span></li></ul> |
|<span data-ttu-id="dd5e0-129">**4**</span><span class="sxs-lookup"><span data-stu-id="dd5e0-129">**4**</span></span>   |<span data-ttu-id="dd5e0-130">将报表导出到 CSV 文件进行脱机分析。</span><span class="sxs-lookup"><span data-stu-id="dd5e0-130">Export the report to a CSV file for offline analysis.</span></span> <span data-ttu-id="dd5e0-131">选择 **"导出Excel"，** 然后选择"**下载"** 选项卡。选择 **"** 下载"，在报表准备就绪后下载报表。</span><span class="sxs-lookup"><span data-stu-id="dd5e0-131">Select **Export to Excel**, and then the **Downloads** tab. Select **Download** to download the report when it's ready.</span></span> |
|<span data-ttu-id="dd5e0-132">**5**</span><span class="sxs-lookup"><span data-stu-id="dd5e0-132">**5**</span></span>   |<span data-ttu-id="dd5e0-133">将报表导出到 CSV 文件进行脱机分析。</span><span class="sxs-lookup"><span data-stu-id="dd5e0-133">Export the report to a CSV file for offline analysis.</span></span> <span data-ttu-id="dd5e0-134">选择 **"导出Excel"，** 然后选择"**下载"** 选项卡。选择 **"** 下载"，在报表准备就绪后下载报表。</span><span class="sxs-lookup"><span data-stu-id="dd5e0-134">Select **Export to Excel**, and then the **Downloads** tab. Select **Download** to download the report when it's ready.</span></span> <span data-ttu-id="dd5e0-135">在报表视图中查看Excel，还将看到 **"ID"** 和"**电子邮件**"列，表示用户的用户 ID 和电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="dd5e0-135">When you view the report in Excel, you'll also see an **Id** and **email** column, which represents the User ID and email address of the user.</span></span> |

## <a name="make-the-user-specific-data-anonymous"></a><span data-ttu-id="dd5e0-136">使用户特定的数据匿名</span><span class="sxs-lookup"><span data-stu-id="dd5e0-136">Make the user-specific data anonymous</span></span>

<span data-ttu-id="dd5e0-137">若要使用户活动Teams数据匿名，你必须是全局管理员。</span><span class="sxs-lookup"><span data-stu-id="dd5e0-137">To make the data in the Teams user activity report anonymous, you have to be a global administrator.</span></span> <span data-ttu-id="dd5e0-138">这会在报表及其导出显示名称隐藏可识别信息，例如电子邮件、电子邮件和 Azure AD ID。</span><span class="sxs-lookup"><span data-stu-id="dd5e0-138">This will hide identifiable information such as display name, email, and Azure AD ID in reports and their exports.</span></span>

1. <span data-ttu-id="dd5e0-139">在Microsoft 365 管理中心，转到 **"设置** Org 设置"，在"服务" \> **选项卡** 下，选择"报表 **"。**</span><span class="sxs-lookup"><span data-stu-id="dd5e0-139">In the Microsoft 365 admin center, go to **Settings** \> **Org Settings**, and under the **Services** tab, choose **Reports**.</span></span>
    
2. <span data-ttu-id="dd5e0-140">选择 **"报告**"，然后选择"**显示匿名标识符"。**</span><span class="sxs-lookup"><span data-stu-id="dd5e0-140">Select **Reports**, and then choose to **Display anonymous identifiers**.</span></span> <span data-ttu-id="dd5e0-141">此设置同时应用于管理中心Microsoft 365 管理中心使用情况Teams报表。</span><span class="sxs-lookup"><span data-stu-id="dd5e0-141">This setting gets applied both to the usage reports in the Microsoft 365 admin center and the Teams admin center.</span></span>
  
3. <span data-ttu-id="dd5e0-142">选择"**保存更改"。**</span><span class="sxs-lookup"><span data-stu-id="dd5e0-142">Select **Save changes**.</span></span>

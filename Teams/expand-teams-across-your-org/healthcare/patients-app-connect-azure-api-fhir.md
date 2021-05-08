---
title: 将患者应用连接到 Azure API for FHIR
author: cichur
ms.author: v-cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
search.appverid: MET150
f1.keywords:
- NOCSH
localization_priority: Normal
MS.collection:
- M365-collaboration
- Teams_ITAdmin_Healthcare
appliesto:
- Microsoft Teams
ms.reviewer: anach
description: 了解如何将应用程序中的 Patients 应用Microsoft Teams Azure API for FHIR (快速医疗保健互操作性资源) 。
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: e06e422765c1d1d633414d24dff48e2801067f15
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51096264"
---
# <a name="connect-the-patients-app-to-azure-api-for-fhir"></a><span data-ttu-id="b0542-103">将患者应用连接到 Azure API for FHIR</span><span class="sxs-lookup"><span data-stu-id="b0542-103">Connect the Patients app to Azure API for FHIR</span></span>

> [!NOTE]
> <span data-ttu-id="b0542-104">从 2020 年 10 月 30 日起，"患者"应用已停用，并替换为 Teams [列表](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) 应用。</span><span class="sxs-lookup"><span data-stu-id="b0542-104">Effective October 30, 2020, the Patients app has been retired and replaced by the [Lists app](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) in Teams.</span></span> <span data-ttu-id="b0542-105">患者应用数据存储在支持团队的 Office 365 组的组邮箱中。</span><span class="sxs-lookup"><span data-stu-id="b0542-105">Patients app data is stored in the group mailbox of the Office 365 group that backs the team.</span></span> <span data-ttu-id="b0542-106">与该患者应用关联的所有数据将保留在该组，但无法再通过用户界面访问。</span><span class="sxs-lookup"><span data-stu-id="b0542-106">All data associated with the Patients app is retained in this group but can no longer be accessed through the user interface.</span></span> <span data-ttu-id="b0542-107">用户可通过"列表"应用或 [重新创建](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db)。</span><span class="sxs-lookup"><span data-stu-id="b0542-107">Users can re-create their lists using the [Lists app](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db).</span></span>
>
><span data-ttu-id="b0542-108">借助列表，医疗保健组织中的护理团队可针对各种方案创建患者列表，提供圆形和内联团队会议、常规患者监视等。</span><span class="sxs-lookup"><span data-stu-id="b0542-108">With Lists, care teams in your healthcare organization can create patient lists for scenarios ranging from rounds and interdisciplinary team meetings to general patient monitoring.</span></span> <span data-ttu-id="b0542-109">查看列表的"患者"模板以开始使用。</span><span class="sxs-lookup"><span data-stu-id="b0542-109">Check out the Patients template in Lists to get started.</span></span> <span data-ttu-id="b0542-110">若要深入了解如何在组织中管理列表应用，请参阅" [列表应用管理](../../manage-lists-app.md)。</span><span class="sxs-lookup"><span data-stu-id="b0542-110">To learn more about how to manage the Lists app in your organization, see [Manage the Lists app](../../manage-lists-app.md).</span></span>

<span data-ttu-id="b0542-111">按照以下步骤允许患者应用Microsoft Teams FHIR 实例的 Azure API。</span><span class="sxs-lookup"><span data-stu-id="b0542-111">Follow these steps to allow the Patients app in Microsoft Teams access to an Azure API for FHIR instance.</span></span> <span data-ttu-id="b0542-112">本文假设在租户中设置并配置 [了用于 FHIR](https://azure.microsoft.com/services/azure-api-for-fhir/) 实例的 Azure API。</span><span class="sxs-lookup"><span data-stu-id="b0542-112">This article assumes that you have an [Azure API for FHIR instance](https://azure.microsoft.com/services/azure-api-for-fhir/) set up and configured in your tenant.</span></span>  <span data-ttu-id="b0542-113">如果尚未在租户中创建适用于 FHIR 实例的 Azure API，请参阅快速 [入门：](/azure/healthcare-apis/fhir-paas-portal-quickstart)使用 Azure 门户部署适用于 FHIR 的 Azure API。</span><span class="sxs-lookup"><span data-stu-id="b0542-113">If you haven’t yet created an Azure API for FHIR instance in your tenant, see [Quickstart: Deploy Azure API for FHIR using Azure portal](/azure/healthcare-apis/fhir-paas-portal-quickstart).</span></span>

1. <span data-ttu-id="b0542-114">单击此处 [授予](https://login.microsoftonline.com/common/adminConsent?client_id=4aee3506-b263-43e0-ba31-1468fa7b2806) 患者应用的管理员许可。</span><span class="sxs-lookup"><span data-stu-id="b0542-114">Click [here](https://login.microsoftonline.com/common/adminConsent?client_id=4aee3506-b263-43e0-ba31-1468fa7b2806) to grant admin consent for the Patients app.</span></span> <span data-ttu-id="b0542-115">系统提示时，使用租户管理员或全局管理员凭据登录，然后单击"接受"以授予所需的权限。</span><span class="sxs-lookup"><span data-stu-id="b0542-115">When prompted, sign in using your tenant admin or global admin credentials, and then click **Accept** to grant the required permissions.</span></span>

    !["患者"应用的权限请求屏幕截图](../../media/patients-app-permissions-request.png)

    <span data-ttu-id="b0542-117">接受后，关闭窗口。</span><span class="sxs-lookup"><span data-stu-id="b0542-117">After you accept, close the window.</span></span> <span data-ttu-id="b0542-118">你将看到一个可能如下所示的页面。</span><span class="sxs-lookup"><span data-stu-id="b0542-118">You'll see a page that may look like this.</span></span> <span data-ttu-id="b0542-119">可以忽略页面上的错误消息。</span><span class="sxs-lookup"><span data-stu-id="b0542-119">You can ignore the error message on the page.</span></span> <span data-ttu-id="b0542-120">它是无危害的，表示已授予许可。</span><span class="sxs-lookup"><span data-stu-id="b0542-120">It's harmless and indicates that consent is granted.</span></span> <span data-ttu-id="b0542-121"> (我们正在努力为此 URL 创建一个用户友好的页面。</span><span class="sxs-lookup"><span data-stu-id="b0542-121">(We're working on a more user-friendly page for this URL.</span></span> <span data-ttu-id="b0542-122">敬请期待！) </span><span class="sxs-lookup"><span data-stu-id="b0542-122">Stay tuned!)</span></span>

    !["患者应用"权限请求的屏幕截图](../../media/patients-app-permissions-request-granted.png)

2. <span data-ttu-id="b0542-124">使用管理员凭据登录到 [Azure](https://portal.azure.com) 门户。</span><span class="sxs-lookup"><span data-stu-id="b0542-124">Sign in to the [Azure portal](https://portal.azure.com) with your admin credentials.</span></span>

3. <span data-ttu-id="b0542-125">在左侧导航栏中 **，选择**"Azure Active Directory"，然后选择"Enterprise **应用程序"。**</span><span class="sxs-lookup"><span data-stu-id="b0542-125">In the left navigation, select **Azure Active Directory**, and then select **Enterprise Applications**.</span></span>

    <span data-ttu-id="b0542-126">查找名为 **Patients (dev)** 行，然后将"对象 **ID"** 列中的值复制到剪贴板。</span><span class="sxs-lookup"><span data-stu-id="b0542-126">Look for a row named **Patients (dev)**, and then copy the value in the **Object ID** column to your clipboard.</span></span>

    ![Azure 门户中" (开发) 行的屏幕截图](../../media/patients-app-azure-portal-object-id.png)

4. <span data-ttu-id="b0542-128">转到要连接到 Patients 应用的 Azure API for FHIR 资源实例 (搜索它或浏览资源) ，然后打开该实例的设置。</span><span class="sxs-lookup"><span data-stu-id="b0542-128">Go to the Azure API for FHIR resource instance to which you want to connect the Patients app (either by searching for it or by browsing through your resources), and then open the settings for that instance.</span></span>

    ![Azure 门户中用于 FHIR 实例设置的 Azure API 的屏幕截图](../../media/patients-app-azure-portal-instance-settings.png)

5. <span data-ttu-id="b0542-130">单击 **"** 身份验证"，然后在步骤 3 中复制的对象 ID 粘贴到"允许 **的对象 ID"** 框中。</span><span class="sxs-lookup"><span data-stu-id="b0542-130">Click **Authentication**, and then paste the object ID that you copied in step 3 to the **Allowed object IDs** box.</span></span> <span data-ttu-id="b0542-131">这允许 Patients 应用访问 FHIR 服务器。</span><span class="sxs-lookup"><span data-stu-id="b0542-131">This allows the Patients app to access the FHIR server.</span></span> <span data-ttu-id="b0542-132">粘贴对象 ID 后，Azure Active Directory进行验证，旁边会显示一个绿色对号。</span><span class="sxs-lookup"><span data-stu-id="b0542-132">After you paste the object ID, Azure Active Directory validates it, and a green check mark appears next to it.</span></span>

    ![Azure 门户中身份验证设置的屏幕截图](../../media/patients-app-azure-portal-authentication.png)

6. <span data-ttu-id="b0542-134">单击“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="b0542-134">Click **Save**.</span></span> <span data-ttu-id="b0542-135">这会重新部署实例，这可能需要几分钟时间。</span><span class="sxs-lookup"><span data-stu-id="b0542-135">This redeploys the instance, which can take a few minutes.</span></span>

7. <span data-ttu-id="b0542-136">单击 **"概述**"，然后从 **FHIR 元数据终结点复制 URL。**</span><span class="sxs-lookup"><span data-stu-id="b0542-136">Click **Overview**, and then copy the URL from **FHIR metadata endpoint**.</span></span> <span data-ttu-id="b0542-137">删除元数据标记，获取 FHIR 服务器 URL。</span><span class="sxs-lookup"><span data-stu-id="b0542-137">Remove the metadata tag to get the FHIR server URL.</span></span> <span data-ttu-id="b0542-138">例如 `https://test02-teamshealth.azurehealthcareapis.com/` ，。</span><span class="sxs-lookup"><span data-stu-id="b0542-138">For example, `https://test02-teamshealth.azurehealthcareapis.com/`.</span></span>

    ![Azure 门户中的元数据终结点](../../media/patients-app-azure-portal-metadata-endpoint.png)

8. <span data-ttu-id="b0542-140">在Teams中，转到团队中加载的 Patients 应用实例，单击"设置"，**然后在**"链接"框中输入 FHIR服务器终结点 URL。</span><span class="sxs-lookup"><span data-stu-id="b0542-140">In Teams, go to the Patients app instance that's loaded in your team, click **Settings**, and then in the **Link** box, enter the FHIR server endpoint URL.</span></span> <span data-ttu-id="b0542-141">然后单击 **"连接"** 以建立连接并搜索患者，然后将患者添加到列表中。</span><span class="sxs-lookup"><span data-stu-id="b0542-141">Then, click **Connect** to establish a connection and search and add patients to your list.</span></span>  

    ![ <span data-ttu-id="b0542-142">病人应用中的"患者"Teams</span><span class="sxs-lookup"><span data-stu-id="b0542-142">Patients app settings in Teams</span></span>](../../media/patients-app-teams.png)

    <span data-ttu-id="b0542-143">如果在此步骤中连接到 Teams 时收到错误，请发送错误的详细屏幕截图、[来自 Fiddler](https://www.telerik.com/download/fiddler)的日志以及电子邮件中任何其他重现步骤，主题行为"Patients App – EMR 模式故障排除"到[teamsforhealthcare@service.microsoft.com。](mailto:teamsforhealthcare@service.microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="b0542-143">If you get an error when connecting to Teams during this step, send a detailed screenshot of the error, logs from [Fiddler](https://www.telerik.com/download/fiddler) and any other repro steps in an email with a subject line of “Patients App – EMR mode troubleshooting” to [teamsforhealthcare@service.microsoft.com](mailto:teamsforhealthcare@service.microsoft.com).</span></span>

## <a name="related-topics"></a><span data-ttu-id="b0542-144">相关主题</span><span class="sxs-lookup"><span data-stu-id="b0542-144">Related topics</span></span>

- [<span data-ttu-id="b0542-145">患者应用概述</span><span class="sxs-lookup"><span data-stu-id="b0542-145">Patients app overview</span></span>](patients-app-overview.md)
- [<span data-ttu-id="b0542-146">将电子医疗记录集成到 Microsoft Teams 中</span><span class="sxs-lookup"><span data-stu-id="b0542-146">Integrating Electronic Healthcare Records into Microsoft Teams</span></span>](patients-app.md)
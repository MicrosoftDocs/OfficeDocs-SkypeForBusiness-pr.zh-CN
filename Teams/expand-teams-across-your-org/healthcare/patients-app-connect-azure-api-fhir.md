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
description: 了解如何将 Microsoft Teams 中的 Patients 应用连接到 Azure API for FHIR (快速医疗保健互操作性资源) 。
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: 4e41b071ef1724043f45c3783b062108d29a5190
ms.sourcegitcommit: 67782296062528bbeade5cb9074143fee0536646
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/24/2020
ms.locfileid: "49731150"
---
# <a name="connect-the-patients-app-to-azure-api-for-fhir"></a><span data-ttu-id="4984d-103">将患者应用连接到 Azure API for FHIR</span><span class="sxs-lookup"><span data-stu-id="4984d-103">Connect the Patients app to Azure API for FHIR</span></span>

> [!NOTE]
> <span data-ttu-id="4984d-104">从 2020 年 10 月 30 日起，"患者"应用已停用，并替换为 Teams 中的 [列表](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) 应用。</span><span class="sxs-lookup"><span data-stu-id="4984d-104">Effective October 30, 2020, the Patients app has been retired and replaced by the [Lists app](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) in Teams.</span></span> <span data-ttu-id="4984d-105">患者应用数据存储在支持团队的 Office 365 组的组邮箱中。</span><span class="sxs-lookup"><span data-stu-id="4984d-105">Patients app data is stored in the group mailbox of the Office 365 group that backs the team.</span></span> <span data-ttu-id="4984d-106">与 Patients 应用关联的所有数据将保留在此组中，但无法再通过用户界面访问。</span><span class="sxs-lookup"><span data-stu-id="4984d-106">All data associated with the Patients app is retained in this group but can no longer be accessed through the user interface.</span></span> <span data-ttu-id="4984d-107">用户可以使用列表应用重新创建 [其列表](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db)。</span><span class="sxs-lookup"><span data-stu-id="4984d-107">Users can re-create their lists using the [Lists app](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db).</span></span>
>
><span data-ttu-id="4984d-108">借助列表，医疗保健组织的护理团队可以创建从轮次和内部团队会议到常规患者监视等场景的患者列表。</span><span class="sxs-lookup"><span data-stu-id="4984d-108">With Lists, care teams in your healthcare organization can create patient lists for scenarios ranging from rounds and interdisciplinary team meetings to general patient monitoring.</span></span> <span data-ttu-id="4984d-109">请查看"列表"中的"患者"模板以开始使用。</span><span class="sxs-lookup"><span data-stu-id="4984d-109">Check out the Patients template in Lists to get started.</span></span> <span data-ttu-id="4984d-110">若要详细了解如何在组织中管理列表应用，请参阅" [管理列表"应用](../../manage-lists-app.md)。</span><span class="sxs-lookup"><span data-stu-id="4984d-110">To learn more about how to manage the Lists app in your organization, see [Manage the Lists app](../../manage-lists-app.md).</span></span>

<span data-ttu-id="4984d-111">按照以下步骤操作，允许 Microsoft Teams 中的 Patients 应用访问用于 FHIR 实例的 Azure API。</span><span class="sxs-lookup"><span data-stu-id="4984d-111">Follow these steps to allow the Patients app in Microsoft Teams access to an Azure API for FHIR instance.</span></span> <span data-ttu-id="4984d-112">本文假设在租户中设置并配置 [了用于 FHIR](https://azure.microsoft.com/services/azure-api-for-fhir/) 实例的 Azure API。</span><span class="sxs-lookup"><span data-stu-id="4984d-112">This article assumes that you have an [Azure API for FHIR instance](https://azure.microsoft.com/services/azure-api-for-fhir/) set up and configured in your tenant.</span></span>  <span data-ttu-id="4984d-113">如果尚未在租户中创建适用于 FHIR 实例的 Azure API，请参阅快速入门：使用 Azure 门户部署适用于 FHIR 的[Azure API。](https://docs.microsoft.com/azure/healthcare-apis/fhir-paas-portal-quickstart)</span><span class="sxs-lookup"><span data-stu-id="4984d-113">If you haven’t yet created an Azure API for FHIR instance in your tenant, see [Quickstart: Deploy Azure API for FHIR using Azure portal](https://docs.microsoft.com/azure/healthcare-apis/fhir-paas-portal-quickstart).</span></span>

1. <span data-ttu-id="4984d-114">单击此处 [授予](https://login.microsoftonline.com/common/adminConsent?client_id=4aee3506-b263-43e0-ba31-1468fa7b2806) "患者"应用的管理员许可。</span><span class="sxs-lookup"><span data-stu-id="4984d-114">Click [here](https://login.microsoftonline.com/common/adminConsent?client_id=4aee3506-b263-43e0-ba31-1468fa7b2806) to grant admin consent for the Patients app.</span></span> <span data-ttu-id="4984d-115">系统提示时，使用租户管理员或全局管理员凭据登录，然后单击"接受"以授予所需的权限。</span><span class="sxs-lookup"><span data-stu-id="4984d-115">When prompted, sign in using your tenant admin or global admin credentials, and then click **Accept** to grant the required permissions.</span></span>

    !["患者"应用的权限请求屏幕截图](../../media/patients-app-permissions-request.png)

    <span data-ttu-id="4984d-117">接受后，关闭窗口。</span><span class="sxs-lookup"><span data-stu-id="4984d-117">After you accept, close the window.</span></span> <span data-ttu-id="4984d-118">你将看到一个可能如下所示的页面。</span><span class="sxs-lookup"><span data-stu-id="4984d-118">You'll see a page that may look like this.</span></span> <span data-ttu-id="4984d-119">可以忽略页面上的错误消息。</span><span class="sxs-lookup"><span data-stu-id="4984d-119">You can ignore the error message on the page.</span></span> <span data-ttu-id="4984d-120">这是没有危害的，表示已授予许可。</span><span class="sxs-lookup"><span data-stu-id="4984d-120">It's harmless and indicates that consent is granted.</span></span> <span data-ttu-id="4984d-121"> (我们正在努力为此 URL 创建一个用户友好的页面。</span><span class="sxs-lookup"><span data-stu-id="4984d-121">(We're working on a more user-friendly page for this URL.</span></span> <span data-ttu-id="4984d-122">敬请期待！) </span><span class="sxs-lookup"><span data-stu-id="4984d-122">Stay tuned!)</span></span>

    !["患者"应用的权限请求屏幕截图](../../media/patients-app-permissions-request-granted.png)

2. <span data-ttu-id="4984d-124">使用管理员凭据登录到 [Azure](https://portal.azure.com) 门户。</span><span class="sxs-lookup"><span data-stu-id="4984d-124">Sign in to the [Azure portal](https://portal.azure.com) with your admin credentials.</span></span>

3. <span data-ttu-id="4984d-125">在左侧导航栏中，选择 **"Azure Active Directory"，** 然后选择"**企业应用程序"。**</span><span class="sxs-lookup"><span data-stu-id="4984d-125">In the left navigation, select **Azure Active Directory**, and then select **Enterprise Applications**.</span></span>

    <span data-ttu-id="4984d-126">查找名为 **Patients (dev)** 行，然后将"对象 **ID"** 列中的值复制到剪贴板。</span><span class="sxs-lookup"><span data-stu-id="4984d-126">Look for a row named **Patients (dev)**, and then copy the value in the **Object ID** column to your clipboard.</span></span>

    ![Azure 门户中" (开发) 行的屏幕截图](../../media/patients-app-azure-portal-object-id.png)

4. <span data-ttu-id="4984d-128">转到要连接到 Patients 应用的 Azure API for FHIR 资源实例 (搜索它或浏览资源) ，然后打开该实例的设置。</span><span class="sxs-lookup"><span data-stu-id="4984d-128">Go to the Azure API for FHIR resource instance to which you want to connect the Patients app (either by searching for it or by browsing through your resources), and then open the settings for that instance.</span></span>

    ![Azure 门户中用于 FHIR 实例设置的 Azure API 的屏幕截图](../../media/patients-app-azure-portal-instance-settings.png)

5. <span data-ttu-id="4984d-130">单击 **"** 身份验证"，然后在步骤 3 中复制的对象 ID 粘贴到"允许 **的对象 ID"** 框中。</span><span class="sxs-lookup"><span data-stu-id="4984d-130">Click **Authentication**, and then paste the object ID that you copied in step 3 to the **Allowed object IDs** box.</span></span> <span data-ttu-id="4984d-131">这允许 Patients 应用访问 FHIR 服务器。</span><span class="sxs-lookup"><span data-stu-id="4984d-131">This allows the Patients app to access the FHIR server.</span></span> <span data-ttu-id="4984d-132">粘贴对象 ID 后，Azure Active Directory 会验证它，旁边会显示一个绿色的选中标记。</span><span class="sxs-lookup"><span data-stu-id="4984d-132">After you paste the object ID, Azure Active Directory validates it, and a green check mark appears next to it.</span></span>

    ![Azure 门户中身份验证设置的屏幕截图](../../media/patients-app-azure-portal-authentication.png)

6. <span data-ttu-id="4984d-134">单击“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="4984d-134">Click **Save**.</span></span> <span data-ttu-id="4984d-135">这会重新部署实例，这可能需要几分钟时间。</span><span class="sxs-lookup"><span data-stu-id="4984d-135">This redeploys the instance, which can take a few minutes.</span></span>

7. <span data-ttu-id="4984d-136">单击 **"** 概述"，然后从 FHIR 元数据终结点 **复制 URL。**</span><span class="sxs-lookup"><span data-stu-id="4984d-136">Click **Overview**, and then copy the URL from **FHIR metadata endpoint**.</span></span> <span data-ttu-id="4984d-137">删除元数据标记，获取 FHIR 服务器 URL。</span><span class="sxs-lookup"><span data-stu-id="4984d-137">Remove the metadata tag to get the FHIR server URL.</span></span> <span data-ttu-id="4984d-138">例如 `https://test02-teamshealth.azurehealthcareapis.com/` ，</span><span class="sxs-lookup"><span data-stu-id="4984d-138">For example, `https://test02-teamshealth.azurehealthcareapis.com/`.</span></span>

    ![Azure 门户中的元数据终结点](../../media/patients-app-azure-portal-metadata-endpoint.png)

8. <span data-ttu-id="4984d-140">在 Teams 中，转到团队中加载的 Patients 应用实例，单击"设置"，然后在"链接"框中输入 FHIR 服务器终结点 URL。</span><span class="sxs-lookup"><span data-stu-id="4984d-140">In Teams, go to the Patients app instance that's loaded in your team, click **Settings**, and then in the **Link** box, enter the FHIR server endpoint URL.</span></span> <span data-ttu-id="4984d-141">然后， **单击"连接** "建立连接并搜索患者，然后将患者添加到列表中。</span><span class="sxs-lookup"><span data-stu-id="4984d-141">Then, click **Connect** to establish a connection and search and add patients to your list.</span></span>  

    ![ <span data-ttu-id="4984d-142">Teams 中的患者应用设置</span><span class="sxs-lookup"><span data-stu-id="4984d-142">Patients app settings in Teams</span></span>](../../media/patients-app-teams.png)

    <span data-ttu-id="4984d-143">如果在此步骤中连接到 Teams 时收到错误，请将错误的详细屏幕截图、[来自 Fiddler](https://www.telerik.com/download/fiddler)的日志以及电子邮件中任何其他重现步骤的屏幕截图，主题行为"Patients App – EMR mode troubleshooting"（患者应用 - EMR 模式故障排除）发送给[teamsforhealthcare@service.microsoft.com。](mailto:teamsforhealthcare@service.microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="4984d-143">If you get an error when connecting to Teams during this step, send a detailed screenshot of the error, logs from [Fiddler](https://www.telerik.com/download/fiddler) and any other repro steps in an email with a subject line of “Patients App – EMR mode troubleshooting” to [teamsforhealthcare@service.microsoft.com](mailto:teamsforhealthcare@service.microsoft.com).</span></span>

## <a name="related-topics"></a><span data-ttu-id="4984d-144">相关主题</span><span class="sxs-lookup"><span data-stu-id="4984d-144">Related topics</span></span>

- [<span data-ttu-id="4984d-145">患者应用概述</span><span class="sxs-lookup"><span data-stu-id="4984d-145">Patients app overview</span></span>](patients-app-overview.md)
- [<span data-ttu-id="4984d-146">将电子医疗记录集成到 Microsoft Teams 中</span><span class="sxs-lookup"><span data-stu-id="4984d-146">Integrating Electronic Healthcare Records into Microsoft Teams</span></span>](patients-app.md)

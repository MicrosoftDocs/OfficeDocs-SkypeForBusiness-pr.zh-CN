---
title: 将患者应用连接到 Azure API for FHIR
author: lanachin
ms.author: v-lanac
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
description: 了解如何将 Microsoft 团队中的患者应用连接到 FHIR (快速医疗保健互操作性资源) 的 Azure API。
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: e3ff2f42953d59d1eecbc96179759f2ad9024f82
ms.sourcegitcommit: 18b5e3487ba1350c5d2e6d676a4ab582b5b638d4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "48772253"
---
# <a name="connect-the-patients-app-to-azure-api-for-fhir"></a><span data-ttu-id="bfe77-103">将患者应用连接到 Azure API for FHIR</span><span class="sxs-lookup"><span data-stu-id="bfe77-103">Connect the Patients app to Azure API for FHIR</span></span>

> [!NOTE]
> <span data-ttu-id="bfe77-104">2020年10月30日，患者应用已停用，并已由团队中的 " [列表" 应用](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) 取代。</span><span class="sxs-lookup"><span data-stu-id="bfe77-104">Effective October 30, 2020, the Patients app has been retired and replaced by the [Lists app](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) in Teams.</span></span> <span data-ttu-id="bfe77-105">利用 "列表"，医疗保健组织中的 "护理团队" 可以创建各种方案的患者列表，包括从倒圆角和 interdisciplinary 团队会议到常规患者监控。</span><span class="sxs-lookup"><span data-stu-id="bfe77-105">With Lists, care teams in your healthcare organization can create patient lists for scenarios ranging from rounds and interdisciplinary team meetings to general patient monitoring.</span></span> <span data-ttu-id="bfe77-106">查看列表中的患者模板以开始使用。</span><span class="sxs-lookup"><span data-stu-id="bfe77-106">Check out the Patients template in Lists to get started.</span></span> <span data-ttu-id="bfe77-107">若要了解有关如何管理组织中的列表应用的详细信息，请参阅 [管理列表应用](../../manage-lists-app.md)</span><span class="sxs-lookup"><span data-stu-id="bfe77-107">To learn more about how to manage the Lists app in your organization, see [Manage the Lists app](../../manage-lists-app.md)</span></span>

<span data-ttu-id="bfe77-108">按照以下步骤，允许 Microsoft 团队中的患者应用访问 FHIR 实例的 Azure API。</span><span class="sxs-lookup"><span data-stu-id="bfe77-108">Follow these steps to allow the Patients app in Microsoft Teams access to an Azure API for FHIR instance.</span></span> <span data-ttu-id="bfe77-109">本文假定你在租户中设置和配置了 [FHIR 实例的 AZURE API](https://azure.microsoft.com/services/azure-api-for-fhir/) 。</span><span class="sxs-lookup"><span data-stu-id="bfe77-109">This article assumes that you have an [Azure API for FHIR instance](https://azure.microsoft.com/services/azure-api-for-fhir/) set up and configured in your tenant.</span></span>  <span data-ttu-id="bfe77-110">如果尚未在租户中为 FHIR 实例创建 Azure API，请参阅 [快速入门：使用 azure 门户部署 FHIR 的 AZURE api](https://docs.microsoft.com/azure/healthcare-apis/fhir-paas-portal-quickstart)。</span><span class="sxs-lookup"><span data-stu-id="bfe77-110">If you haven’t yet created an Azure API for FHIR instance in your tenant, see [Quickstart: Deploy Azure API for FHIR using Azure portal](https://docs.microsoft.com/azure/healthcare-apis/fhir-paas-portal-quickstart).</span></span>


1. <span data-ttu-id="bfe77-111">单击 [此处](https://login.microsoftonline.com/common/adminConsent?client_id=4aee3506-b263-43e0-ba31-1468fa7b2806) 授予对患者应用的管理员同意。</span><span class="sxs-lookup"><span data-stu-id="bfe77-111">Click [here](https://login.microsoftonline.com/common/adminConsent?client_id=4aee3506-b263-43e0-ba31-1468fa7b2806) to grant admin consent for the Patients app.</span></span> <span data-ttu-id="bfe77-112">出现提示时，使用租户管理员或全局管理员凭据登录，然后单击 " **接受** " 以授予所需的权限。</span><span class="sxs-lookup"><span data-stu-id="bfe77-112">When prompted, sign in using your tenant admin or global admin credentials, and then click **Accept** to grant the required permissions.</span></span>

    ![患者应用的权限请求的屏幕截图](../../media/patients-app-permissions-request.png)

    <span data-ttu-id="bfe77-114">接受后，关闭窗口。</span><span class="sxs-lookup"><span data-stu-id="bfe77-114">After you accept, close the window.</span></span> <span data-ttu-id="bfe77-115">你将看到一个可能如下所示的页面。</span><span class="sxs-lookup"><span data-stu-id="bfe77-115">You'll see a page that may look like this.</span></span> <span data-ttu-id="bfe77-116">你可以忽略页面上的错误消息。</span><span class="sxs-lookup"><span data-stu-id="bfe77-116">You can ignore the error message on the page.</span></span> <span data-ttu-id="bfe77-117">这是无害的，表明授予同意。</span><span class="sxs-lookup"><span data-stu-id="bfe77-117">It's harmless and indicates that consent is granted.</span></span> <span data-ttu-id="bfe77-118"> (我们正在处理此 URL 的用户更友好的页面。</span><span class="sxs-lookup"><span data-stu-id="bfe77-118">(We're working on a more user-friendly page for this URL.</span></span> <span data-ttu-id="bfe77-119">请继续关注！ ) </span><span class="sxs-lookup"><span data-stu-id="bfe77-119">Stay tuned!)</span></span>

    ![患者应用的权限请求的屏幕截图](../../media/patients-app-permissions-request-granted.png)
    
2. <span data-ttu-id="bfe77-121">通过管理员凭据登录到 [Azure 门户](https://portal.azure.com) 。</span><span class="sxs-lookup"><span data-stu-id="bfe77-121">Sign in to the [Azure portal](https://portal.azure.com) with your admin credentials.</span></span>

3. <span data-ttu-id="bfe77-122">在左侧导航中，选择 " **Azure Active Directory** "，然后选择 " **企业应用程序** "。</span><span class="sxs-lookup"><span data-stu-id="bfe77-122">In the left navigation, select **Azure Active Directory** , and then select **Enterprise Applications** .</span></span>

    <span data-ttu-id="bfe77-123">查找名为 " **病人 (dev")** 的行，然后将 " **对象 ID** " 列中的值复制到剪贴板。</span><span class="sxs-lookup"><span data-stu-id="bfe77-123">Look for a row named **Patients (dev)** , and then copy the value in the **Object ID** column to your clipboard.</span></span>
    
    ![Azure 门户中患者 (开发人员) 行的屏幕截图](../../media/patients-app-azure-portal-object-id.png)
    
4. <span data-ttu-id="bfe77-125">转到要通过其连接患者应用的 FHIR 资源实例的 Azure API，方法是通过搜索它或浏览) 的资源来 (，然后打开该实例的设置。</span><span class="sxs-lookup"><span data-stu-id="bfe77-125">Go to the Azure API for FHIR resource instance to which you want to connect the Patients app (either by searching for it or by browsing through your resources), and then open the settings for that instance.</span></span>

    ![Azure API for Azure 门户中的 FHIR 实例设置的屏幕截图](../../media/patients-app-azure-portal-instance-settings.png)

5. <span data-ttu-id="bfe77-127">单击 " **身份验证** "，然后将您在步骤3中复制的对象 ID 粘贴到 " **允许的对象 id** " 框中。</span><span class="sxs-lookup"><span data-stu-id="bfe77-127">Click **Authentication** , and then paste the object ID that you copied in step 3 to the **Allowed object IDs** box.</span></span> <span data-ttu-id="bfe77-128">这允许患者应用访问 FHIR 服务器。</span><span class="sxs-lookup"><span data-stu-id="bfe77-128">This allows the Patients app to access the FHIR server.</span></span> <span data-ttu-id="bfe77-129">粘贴对象 ID 后，Azure Active Directory 将对其进行验证，旁边会显示一个绿色复选标记。</span><span class="sxs-lookup"><span data-stu-id="bfe77-129">After you paste the object ID, Azure Active Directory validates it, and a green check mark appears next to it.</span></span>

    ![Azure 门户中身份验证设置的屏幕截图](../../media/patients-app-azure-portal-authentication.png)

6. <span data-ttu-id="bfe77-131">单击“ **保存** ”。</span><span class="sxs-lookup"><span data-stu-id="bfe77-131">Click **Save** .</span></span> <span data-ttu-id="bfe77-132">此示例 redeploys 实例，这可能需要几分钟时间。</span><span class="sxs-lookup"><span data-stu-id="bfe77-132">This redeploys the instance, which can take a few minutes.</span></span>

7. <span data-ttu-id="bfe77-133">单击 " **概述** "，然后从 **FHIR metadata 终结点** 复制 URL。</span><span class="sxs-lookup"><span data-stu-id="bfe77-133">Click **Overview** , and then copy the URL from **FHIR metadata endpoint** .</span></span> <span data-ttu-id="bfe77-134">删除元数据标记以获取 FHIR 服务器 URL。</span><span class="sxs-lookup"><span data-stu-id="bfe77-134">Remove the metadata tag to get the FHIR server URL.</span></span> <span data-ttu-id="bfe77-135">例如， https://test02-teamshealth.azurehealthcareapis.com/ 。</span><span class="sxs-lookup"><span data-stu-id="bfe77-135">For example, https://test02-teamshealth.azurehealthcareapis.com/.</span></span> 

    ![Azure 门户中的元数据终结点的屏幕截图](../../media/patients-app-azure-portal-metadata-endpoint.png)

8. <span data-ttu-id="bfe77-137">在 "团队" 中，转到团队中加载的患者应用实例，单击 " **设置** "，然后在 " **链接** " 框中，输入 FHIR 服务器终结点 URL。</span><span class="sxs-lookup"><span data-stu-id="bfe77-137">In Teams, go to the Patients app instance that's loaded in your team, click **Settings** , and then in the **Link** box, enter the FHIR server endpoint URL.</span></span> <span data-ttu-id="bfe77-138">然后，单击 " **连接** " 建立连接并搜索 "病人" 并将其添加到您的列表。</span><span class="sxs-lookup"><span data-stu-id="bfe77-138">Then, click **Connect** to establish a connection and search and add patients to your list.</span></span>  

    ![团队中的患者应用设置的屏幕截图](../../media/patients-app-teams.png)
    
    <span data-ttu-id="bfe77-140">如果在此步骤中连接到团队时收到错误，请从 [Fiddler](https://www.telerik.com/download/fiddler) 中发送详细的屏幕截图，并使用 "患者应用– EMR 模式疑难解答" 主题行的电子邮件中的任何其他再现步骤进行 [teamsforhealthcare@service.microsoft.com](mailto:teamsforhealthcare@service.microsoft.com)。</span><span class="sxs-lookup"><span data-stu-id="bfe77-140">If you get an error when connecting to Teams during this step, send a detailed screenshot of the error, logs from [Fiddler](https://www.telerik.com/download/fiddler) and any other repro steps in an email with a subject line of “Patients App – EMR mode troubleshooting” to [teamsforhealthcare@service.microsoft.com](mailto:teamsforhealthcare@service.microsoft.com).</span></span>

## <a name="related-topics"></a><span data-ttu-id="bfe77-141">相关主题</span><span class="sxs-lookup"><span data-stu-id="bfe77-141">Related topics</span></span>

- [<span data-ttu-id="bfe77-142">患者应用概述</span><span class="sxs-lookup"><span data-stu-id="bfe77-142">Patients app overview</span></span>](patients-app-overview.md)
- [<span data-ttu-id="bfe77-143">将电子医疗记录集成到 Microsoft Teams 中</span><span class="sxs-lookup"><span data-stu-id="bfe77-143">Integrating Electronic Healthcare Records into Microsoft Teams</span></span>](patients-app.md)

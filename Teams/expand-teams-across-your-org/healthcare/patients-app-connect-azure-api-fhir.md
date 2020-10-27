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
ms.openlocfilehash: 1f137f7cbe90304620bb0fc5c919c0861fca9d7e
ms.sourcegitcommit: 0a51738879b13991986a3a872445daa8bd20533d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "48766985"
---
# <a name="connect-the-patients-app-to-azure-api-for-fhir"></a><span data-ttu-id="fedad-103">将患者应用连接到 Azure API for FHIR</span><span class="sxs-lookup"><span data-stu-id="fedad-103">Connect the Patients app to Azure API for FHIR</span></span>

> [!IMPORTANT]
> <span data-ttu-id="fedad-104">**2020年10月30日生效，患者应用将被否决，用户将无法再从团队应用商店安装。我们鼓励你立即开始使用团队中的 " [列表" 应用](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) 。**</span><span class="sxs-lookup"><span data-stu-id="fedad-104">**Effective October 30, 2020, the Patients app will be deprecated and users will no longer be able to install it from the Teams app store. We encourage you to start using the [Lists app](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) in Teams today.**</span></span>
>
><span data-ttu-id="fedad-105">患者应用数据存储在支持团队的 Office 365 组的组邮箱中。</span><span class="sxs-lookup"><span data-stu-id="fedad-105">Patients app data is stored in the group mailbox of the Office 365 group that backs the team.</span></span> <span data-ttu-id="fedad-106">当患者应用停用时，与之关联的所有数据将保留在此组中，但不能再通过用户界面进行访问。</span><span class="sxs-lookup"><span data-stu-id="fedad-106">When the Patients app is retired, all data associated with it will be retained in this group but can no longer be accessed through the user interface.</span></span> <span data-ttu-id="fedad-107">当前用户可以使用 " [列表" 应用](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db)重新创建其列表。</span><span class="sxs-lookup"><span data-stu-id="fedad-107">Current users can re-create their lists using the [Lists app](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db).</span></span>
>
><span data-ttu-id="fedad-108">" [列表" 应用](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) 为所有团队用户预安装，可在每个团队和频道中用作选项卡。</span><span class="sxs-lookup"><span data-stu-id="fedad-108">The [Lists app](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) is pre-installed for all Teams users and is available as a tab in every team and channel.</span></span> <span data-ttu-id="fedad-109">使用列表，运行状况团队可以使用内置患者模板、从头开始或通过将数据导入 Excel 来创建患者列表。</span><span class="sxs-lookup"><span data-stu-id="fedad-109">With Lists, health teams can create patient lists using the built-in Patients template, from scratch, or by importing data to Excel.</span></span> <span data-ttu-id="fedad-110">若要了解有关如何管理组织中的列表应用的详细信息，请参阅 [管理列表应用](../../manage-lists-app.md)。</span><span class="sxs-lookup"><span data-stu-id="fedad-110">To learn more about how to manage the Lists app in your organization, see [Manage the Lists app](../../manage-lists-app.md).</span></span>

<span data-ttu-id="fedad-111">按照以下步骤，允许 Microsoft 团队中的患者应用访问 FHIR 实例的 Azure API。</span><span class="sxs-lookup"><span data-stu-id="fedad-111">Follow these steps to allow the Patients app in Microsoft Teams access to an Azure API for FHIR instance.</span></span> <span data-ttu-id="fedad-112">本文假定你在租户中设置和配置了 [FHIR 实例的 AZURE API](https://azure.microsoft.com/services/azure-api-for-fhir/) 。</span><span class="sxs-lookup"><span data-stu-id="fedad-112">This article assumes that you have an [Azure API for FHIR instance](https://azure.microsoft.com/services/azure-api-for-fhir/) set up and configured in your tenant.</span></span>  <span data-ttu-id="fedad-113">如果尚未在租户中为 FHIR 实例创建 Azure API，请参阅 [快速入门：使用 azure 门户部署 FHIR 的 AZURE api](https://docs.microsoft.com/azure/healthcare-apis/fhir-paas-portal-quickstart)。</span><span class="sxs-lookup"><span data-stu-id="fedad-113">If you haven’t yet created an Azure API for FHIR instance in your tenant, see [Quickstart: Deploy Azure API for FHIR using Azure portal](https://docs.microsoft.com/azure/healthcare-apis/fhir-paas-portal-quickstart).</span></span>


1. <span data-ttu-id="fedad-114">单击 [此处](https://login.microsoftonline.com/common/adminConsent?client_id=4aee3506-b263-43e0-ba31-1468fa7b2806) 授予对患者应用的管理员同意。</span><span class="sxs-lookup"><span data-stu-id="fedad-114">Click [here](https://login.microsoftonline.com/common/adminConsent?client_id=4aee3506-b263-43e0-ba31-1468fa7b2806) to grant admin consent for the Patients app.</span></span> <span data-ttu-id="fedad-115">出现提示时，使用租户管理员或全局管理员凭据登录，然后单击 " **接受** " 以授予所需的权限。</span><span class="sxs-lookup"><span data-stu-id="fedad-115">When prompted, sign in using your tenant admin or global admin credentials, and then click **Accept** to grant the required permissions.</span></span>

    ![患者应用的权限请求的屏幕截图](../../media/patients-app-permissions-request.png)

    <span data-ttu-id="fedad-117">接受后，关闭窗口。</span><span class="sxs-lookup"><span data-stu-id="fedad-117">After you accept, close the window.</span></span> <span data-ttu-id="fedad-118">你将看到一个可能如下所示的页面。</span><span class="sxs-lookup"><span data-stu-id="fedad-118">You'll see a page that may look like this.</span></span> <span data-ttu-id="fedad-119">你可以忽略页面上的错误消息。</span><span class="sxs-lookup"><span data-stu-id="fedad-119">You can ignore the error message on the page.</span></span> <span data-ttu-id="fedad-120">这是无害的，表明授予同意。</span><span class="sxs-lookup"><span data-stu-id="fedad-120">It's harmless and indicates that consent is granted.</span></span> <span data-ttu-id="fedad-121"> (我们正在处理此 URL 的用户更友好的页面。</span><span class="sxs-lookup"><span data-stu-id="fedad-121">(We're working on a more user-friendly page for this URL.</span></span> <span data-ttu-id="fedad-122">请继续关注！ ) </span><span class="sxs-lookup"><span data-stu-id="fedad-122">Stay tuned!)</span></span>

    ![患者应用的权限请求的屏幕截图](../../media/patients-app-permissions-request-granted.png)
    
2. <span data-ttu-id="fedad-124">通过管理员凭据登录到 [Azure 门户](https://portal.azure.com) 。</span><span class="sxs-lookup"><span data-stu-id="fedad-124">Sign in to the [Azure portal](https://portal.azure.com) with your admin credentials.</span></span>

3. <span data-ttu-id="fedad-125">在左侧导航中，选择 " **Azure Active Directory** "，然后选择 " **企业应用程序** "。</span><span class="sxs-lookup"><span data-stu-id="fedad-125">In the left navigation, select **Azure Active Directory** , and then select **Enterprise Applications** .</span></span>

    <span data-ttu-id="fedad-126">查找名为 " **病人 (dev")** 的行，然后将 " **对象 ID** " 列中的值复制到剪贴板。</span><span class="sxs-lookup"><span data-stu-id="fedad-126">Look for a row named **Patients (dev)** , and then copy the value in the **Object ID** column to your clipboard.</span></span>
    
    ![Azure 门户中患者 (开发人员) 行的屏幕截图](../../media/patients-app-azure-portal-object-id.png)
    
4. <span data-ttu-id="fedad-128">转到要通过其连接患者应用的 FHIR 资源实例的 Azure API，方法是通过搜索它或浏览) 的资源来 (，然后打开该实例的设置。</span><span class="sxs-lookup"><span data-stu-id="fedad-128">Go to the Azure API for FHIR resource instance to which you want to connect the Patients app (either by searching for it or by browsing through your resources), and then open the settings for that instance.</span></span>

    ![Azure API for Azure 门户中的 FHIR 实例设置的屏幕截图](../../media/patients-app-azure-portal-instance-settings.png)

5. <span data-ttu-id="fedad-130">单击 " **身份验证** "，然后将您在步骤3中复制的对象 ID 粘贴到 " **允许的对象 id** " 框中。</span><span class="sxs-lookup"><span data-stu-id="fedad-130">Click **Authentication** , and then paste the object ID that you copied in step 3 to the **Allowed object IDs** box.</span></span> <span data-ttu-id="fedad-131">这允许患者应用访问 FHIR 服务器。</span><span class="sxs-lookup"><span data-stu-id="fedad-131">This allows the Patients app to access the FHIR server.</span></span> <span data-ttu-id="fedad-132">粘贴对象 ID 后，Azure Active Directory 将对其进行验证，旁边会显示一个绿色复选标记。</span><span class="sxs-lookup"><span data-stu-id="fedad-132">After you paste the object ID, Azure Active Directory validates it, and a green check mark appears next to it.</span></span>

    ![Azure 门户中身份验证设置的屏幕截图](../../media/patients-app-azure-portal-authentication.png)

6. <span data-ttu-id="fedad-134">单击“ **保存** ”。</span><span class="sxs-lookup"><span data-stu-id="fedad-134">Click **Save** .</span></span> <span data-ttu-id="fedad-135">此示例 redeploys 实例，这可能需要几分钟时间。</span><span class="sxs-lookup"><span data-stu-id="fedad-135">This redeploys the instance, which can take a few minutes.</span></span>

7. <span data-ttu-id="fedad-136">单击 " **概述** "，然后从 **FHIR metadata 终结点** 复制 URL。</span><span class="sxs-lookup"><span data-stu-id="fedad-136">Click **Overview** , and then copy the URL from **FHIR metadata endpoint** .</span></span> <span data-ttu-id="fedad-137">删除元数据标记以获取 FHIR 服务器 URL。</span><span class="sxs-lookup"><span data-stu-id="fedad-137">Remove the metadata tag to get the FHIR server URL.</span></span> <span data-ttu-id="fedad-138">例如， https://test02-teamshealth.azurehealthcareapis.com/ 。</span><span class="sxs-lookup"><span data-stu-id="fedad-138">For example, https://test02-teamshealth.azurehealthcareapis.com/.</span></span> 

    ![Azure 门户中的元数据终结点的屏幕截图](../../media/patients-app-azure-portal-metadata-endpoint.png)

8. <span data-ttu-id="fedad-140">在 "团队" 中，转到团队中加载的患者应用实例，单击 " **设置** "，然后在 " **链接** " 框中，输入 FHIR 服务器终结点 URL。</span><span class="sxs-lookup"><span data-stu-id="fedad-140">In Teams, go to the Patients app instance that's loaded in your team, click **Settings** , and then in the **Link** box, enter the FHIR server endpoint URL.</span></span> <span data-ttu-id="fedad-141">然后，单击 " **连接** " 建立连接并搜索 "病人" 并将其添加到您的列表。</span><span class="sxs-lookup"><span data-stu-id="fedad-141">Then, click **Connect** to establish a connection and search and add patients to your list.</span></span>  

    ![团队中的患者应用设置的屏幕截图](../../media/patients-app-teams.png)
    
    <span data-ttu-id="fedad-143">如果在此步骤中连接到团队时收到错误，请从 [Fiddler](https://www.telerik.com/download/fiddler) 中发送详细的屏幕截图，并使用 "患者应用– EMR 模式疑难解答" 主题行的电子邮件中的任何其他再现步骤进行 [teamsforhealthcare@service.microsoft.com](mailto:teamsforhealthcare@service.microsoft.com)。</span><span class="sxs-lookup"><span data-stu-id="fedad-143">If you get an error when connecting to Teams during this step, send a detailed screenshot of the error, logs from [Fiddler](https://www.telerik.com/download/fiddler) and any other repro steps in an email with a subject line of “Patients App – EMR mode troubleshooting” to [teamsforhealthcare@service.microsoft.com](mailto:teamsforhealthcare@service.microsoft.com).</span></span>

## <a name="related-topics"></a><span data-ttu-id="fedad-144">相关主题</span><span class="sxs-lookup"><span data-stu-id="fedad-144">Related topics</span></span>

- [<span data-ttu-id="fedad-145">患者应用概述</span><span class="sxs-lookup"><span data-stu-id="fedad-145">Patients app overview</span></span>](patients-app-overview.md)
- [<span data-ttu-id="fedad-146">将电子医疗记录集成到 Microsoft Teams 中</span><span class="sxs-lookup"><span data-stu-id="fedad-146">Integrating Electronic Healthcare Records into Microsoft Teams</span></span>](patients-app.md)

---
title: 将患者应用连接到 Azure API for FHIR
author: lanachin
ms.author: v-lanac
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
search.appverid: MET150
localization_priority: Normal
MS.collection:
- M365-collaboration
- Teams_ITAdmin_Healthcare
appliesto:
- Microsoft Teams
ms.reviewer: anach
description: 了解如何将 Microsoft 团队中的患者应用连接到 FHIR （快速医疗保健互操作性资源）的 Azure API。
ms.openlocfilehash: e532aa9f9fbecb472db63a1ddad4cd71518a8041
ms.sourcegitcommit: d7fab927e96954f294f28dfb33c0889f736b3ab5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/22/2020
ms.locfileid: "41259079"
---
# <a name="connect-the-patients-app-to-azure-api-for-fhir"></a><span data-ttu-id="1e780-103">将患者应用连接到 Azure API for FHIR</span><span class="sxs-lookup"><span data-stu-id="1e780-103">Connect the Patients app to Azure API for FHIR</span></span>

<span data-ttu-id="1e780-104">按照以下步骤，允许 Microsoft 团队中的患者应用访问 FHIR 实例的 Azure API。</span><span class="sxs-lookup"><span data-stu-id="1e780-104">Follow these steps to allow the Patients app in Microsoft Teams access to an Azure API for FHIR instance.</span></span> <span data-ttu-id="1e780-105">本文假定你在租户中设置和配置了[FHIR 实例的 AZURE API](https://azure.microsoft.com/services/azure-api-for-fhir/) 。</span><span class="sxs-lookup"><span data-stu-id="1e780-105">This article assumes that you have an [Azure API for FHIR instance](https://azure.microsoft.com/services/azure-api-for-fhir/) set up and configured in your tenant.</span></span>  <span data-ttu-id="1e780-106">如果尚未在租户中为 FHIR 实例创建 Azure API，请参阅[快速入门：使用 azure 门户部署 FHIR 的 AZURE api](https://docs.microsoft.com/azure/healthcare-apis/fhir-paas-portal-quickstart)。</span><span class="sxs-lookup"><span data-stu-id="1e780-106">If you haven’t yet created an Azure API for FHIR instance in your tenant, see [Quickstart: Deploy Azure API for FHIR using Azure portal](https://docs.microsoft.com/azure/healthcare-apis/fhir-paas-portal-quickstart).</span></span>


1. <span data-ttu-id="1e780-107">单击[此处](https://login.microsoftonline.com/common/adminConsent?client_id=4aee3506-b263-43e0-ba31-1468fa7b2806)授予对患者应用的管理员同意。</span><span class="sxs-lookup"><span data-stu-id="1e780-107">Click [here](https://login.microsoftonline.com/common/adminConsent?client_id=4aee3506-b263-43e0-ba31-1468fa7b2806) to grant admin consent for the Patients app.</span></span> <span data-ttu-id="1e780-108">出现提示时，使用租户管理员或全局管理员凭据登录，然后单击 "**接受**" 以授予所需的权限。</span><span class="sxs-lookup"><span data-stu-id="1e780-108">When prompted, sign in using your tenant admin or global admin credentials, and then click **Accept** to grant the required permissions.</span></span>

    ![患者应用的权限请求的屏幕截图](../../media/patients-app-permissions-request.png)

    <span data-ttu-id="1e780-110">接受后，关闭窗口。</span><span class="sxs-lookup"><span data-stu-id="1e780-110">After you accept, close the window.</span></span> <span data-ttu-id="1e780-111">你将看到一个可能如下所示的页面。</span><span class="sxs-lookup"><span data-stu-id="1e780-111">You'll see a page that may look like this.</span></span> <span data-ttu-id="1e780-112">你可以忽略页面上的错误消息。</span><span class="sxs-lookup"><span data-stu-id="1e780-112">You can ignore the error message on the page.</span></span> <span data-ttu-id="1e780-113">这是无害的，表明授予同意。</span><span class="sxs-lookup"><span data-stu-id="1e780-113">It's harmless and indicates that consent is granted.</span></span> <span data-ttu-id="1e780-114">（我们正在为此 URL 的用户提供更友好的页面。</span><span class="sxs-lookup"><span data-stu-id="1e780-114">(We're working on a more user-friendly page for this URL.</span></span> <span data-ttu-id="1e780-115">继续关注！）</span><span class="sxs-lookup"><span data-stu-id="1e780-115">Stay tuned!)</span></span>

    ![患者应用的权限请求的屏幕截图](../../media/patients-app-permissions-request-granted.png)
2. <span data-ttu-id="1e780-117">通过管理员凭据登录到[Azure 门户](https://portal.azure.com)。</span><span class="sxs-lookup"><span data-stu-id="1e780-117">Sign in to the [Azure portal](https://portal.azure.com) with your admin credentials.</span></span>
3. <span data-ttu-id="1e780-118">在左侧导航中，选择 " **Azure Active Directory**"，然后选择 "**企业应用程序**"。</span><span class="sxs-lookup"><span data-stu-id="1e780-118">In the left navigation, select **Azure Active Directory**, and then select **Enterprise Applications**.</span></span>
    <span data-ttu-id="1e780-119">查找名为 "**病人（开发人员）**" 的行，然后将 "**对象 ID** " 列中的值复制到剪贴板。</span><span class="sxs-lookup"><span data-stu-id="1e780-119">Look for a row named **Patients (dev)**, and then copy the value in the **Object ID** column to your clipboard.</span></span>
    <span data-ttu-id="1e780-120">![Azure 门户中的患者（开发）行的屏幕截图](../../media/patients-app-azure-portal-object-id.png)</span><span class="sxs-lookup"><span data-stu-id="1e780-120">![Screenshot of Patients (dev) row in Azure portal](../../media/patients-app-azure-portal-object-id.png)</span></span>
4. <span data-ttu-id="1e780-121">转到要连接到患者应用的 FHIR 资源实例的 Azure API （通过搜索或浏览资源），然后打开该实例的设置。</span><span class="sxs-lookup"><span data-stu-id="1e780-121">Go to the Azure API for FHIR resource instance to which you want to connect the Patients app (either by searching for it or by browsing through your resources), and then open the settings for that instance.</span></span>

    ![Azure API for Azure 门户中的 FHIR 实例设置的屏幕截图](../../media/patients-app-azure-portal-instance-settings.png)

5. <span data-ttu-id="1e780-123">单击 "**身份验证**"，然后将您在步骤3中复制的对象 ID 粘贴到 "**允许的对象 id** " 框中。</span><span class="sxs-lookup"><span data-stu-id="1e780-123">Click **Authentication**, and then paste the object ID that you copied in step 3 to the **Allowed object IDs** box.</span></span> <span data-ttu-id="1e780-124">这允许患者应用访问 FHIR 服务器。</span><span class="sxs-lookup"><span data-stu-id="1e780-124">This allows the Patients app to access the FHIR server.</span></span> <span data-ttu-id="1e780-125">粘贴对象 ID 后，Azure Active Directory 将对其进行验证，旁边会显示一个绿色复选标记。</span><span class="sxs-lookup"><span data-stu-id="1e780-125">After you paste the object ID, Azure Active Directory validates it, and a green check mark appears next to it.</span></span>

    ![Azure 门户中身份验证设置的屏幕截图](../../media/patients-app-azure-portal-authentication.png)

6. <span data-ttu-id="1e780-127">单击“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="1e780-127">Click **Save**.</span></span> <span data-ttu-id="1e780-128">此示例 redeploys 实例，这可能需要几分钟时间。</span><span class="sxs-lookup"><span data-stu-id="1e780-128">This redeploys the instance, which can take a few minutes.</span></span>
7. <span data-ttu-id="1e780-129">单击 "**概述**"，然后从**FHIR metadata 终结点**复制 URL。</span><span class="sxs-lookup"><span data-stu-id="1e780-129">Click **Overview**, and then copy the URL from **FHIR metadata endpoint**.</span></span> <span data-ttu-id="1e780-130">删除元数据标记以获取 FHIR 服务器 URL。</span><span class="sxs-lookup"><span data-stu-id="1e780-130">Remove the metadata tag to get the FHIR server URL.</span></span> <span data-ttu-id="1e780-131">例如， https://test02-teamshealth.azurehealthcareapis.com/。</span><span class="sxs-lookup"><span data-stu-id="1e780-131">For example, https://test02-teamshealth.azurehealthcareapis.com/.</span></span> 

    ![Azure 门户中的元数据终结点的屏幕截图](../../media/patients-app-azure-portal-metadata-endpoint.png)

8. <span data-ttu-id="1e780-133">在 "团队" 中，转到团队中加载的患者应用实例，单击 "**设置**"，然后在 "**链接**" 框中，输入 FHIR 服务器终结点 URL。</span><span class="sxs-lookup"><span data-stu-id="1e780-133">In Teams, go to the Patients app instance that's loaded in your team, click **Settings**, and then in the **Link** box, enter the FHIR server endpoint URL.</span></span> <span data-ttu-id="1e780-134">然后，单击 "**连接**" 建立连接并搜索 "病人" 并将其添加到您的列表。</span><span class="sxs-lookup"><span data-stu-id="1e780-134">Then, click **Connect** to establish a connection and search and add patients to your list.</span></span>  

    ![团队中的患者应用设置的屏幕截图](../../media/patients-app-teams.png)
    
    <span data-ttu-id="1e780-136">如果在此步骤中连接到团队时收到错误，请从[Fiddler](https://www.telerik.com/download/fiddler)中发送详细的屏幕截图，并使用 "患者应用– EMR 模式疑难解答" 主题行的电子邮件中的任何其他再现步骤进行[teamsforhealthcare@service.microsoft.com](mailto:teamsforhealthcare@service.microsoft.com)。</span><span class="sxs-lookup"><span data-stu-id="1e780-136">If you get an error when connecting to Teams during this step, send a detailed screenshot of the error, logs from [Fiddler](https://www.telerik.com/download/fiddler) and any other repro steps in an email with a subject line of “Patients App – EMR mode troubleshooting” to [teamsforhealthcare@service.microsoft.com](mailto:teamsforhealthcare@service.microsoft.com).</span></span>

## <a name="related-topics"></a><span data-ttu-id="1e780-137">相关主题</span><span class="sxs-lookup"><span data-stu-id="1e780-137">Related topics</span></span>

- [<span data-ttu-id="1e780-138">患者应用概述</span><span class="sxs-lookup"><span data-stu-id="1e780-138">Patients app overview</span></span>](patients-app-overview.md)
- [<span data-ttu-id="1e780-139">将电子医疗记录集成到 Microsoft Teams 中</span><span class="sxs-lookup"><span data-stu-id="1e780-139">Integrating Electronic Healthcare Records into Microsoft Teams</span></span>](patients-app.md)

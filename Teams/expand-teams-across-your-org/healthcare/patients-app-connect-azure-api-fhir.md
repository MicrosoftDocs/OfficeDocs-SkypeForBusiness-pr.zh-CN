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
# <a name="connect-the-patients-app-to-azure-api-for-fhir"></a>将患者应用连接到 Azure API for FHIR

> [!NOTE]
> 从 2020 年 10 月 30 日起，"患者"应用已停用，并替换为 Teams [列表](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) 应用。 患者应用数据存储在支持团队的 Office 365 组的组邮箱中。 与该患者应用关联的所有数据将保留在该组，但无法再通过用户界面访问。 用户可通过"列表"应用或 [重新创建](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db)。
>
>借助列表，医疗保健组织中的护理团队可针对各种方案创建患者列表，提供圆形和内联团队会议、常规患者监视等。 查看列表的"患者"模板以开始使用。 若要深入了解如何在组织中管理列表应用，请参阅" [列表应用管理](../../manage-lists-app.md)。

按照以下步骤允许患者应用Microsoft Teams FHIR 实例的 Azure API。 本文假设在租户中设置并配置 [了用于 FHIR](https://azure.microsoft.com/services/azure-api-for-fhir/) 实例的 Azure API。  如果尚未在租户中创建适用于 FHIR 实例的 Azure API，请参阅快速 [入门：](/azure/healthcare-apis/fhir-paas-portal-quickstart)使用 Azure 门户部署适用于 FHIR 的 Azure API。

1. 单击此处 [授予](https://login.microsoftonline.com/common/adminConsent?client_id=4aee3506-b263-43e0-ba31-1468fa7b2806) 患者应用的管理员许可。 系统提示时，使用租户管理员或全局管理员凭据登录，然后单击"接受"以授予所需的权限。

    !["患者"应用的权限请求屏幕截图](../../media/patients-app-permissions-request.png)

    接受后，关闭窗口。 你将看到一个可能如下所示的页面。 可以忽略页面上的错误消息。 它是无危害的，表示已授予许可。  (我们正在努力为此 URL 创建一个用户友好的页面。 敬请期待！) 

    !["患者应用"权限请求的屏幕截图](../../media/patients-app-permissions-request-granted.png)

2. 使用管理员凭据登录到 [Azure](https://portal.azure.com) 门户。

3. 在左侧导航栏中 **，选择**"Azure Active Directory"，然后选择"Enterprise **应用程序"。**

    查找名为 **Patients (dev)** 行，然后将"对象 **ID"** 列中的值复制到剪贴板。

    ![Azure 门户中" (开发) 行的屏幕截图](../../media/patients-app-azure-portal-object-id.png)

4. 转到要连接到 Patients 应用的 Azure API for FHIR 资源实例 (搜索它或浏览资源) ，然后打开该实例的设置。

    ![Azure 门户中用于 FHIR 实例设置的 Azure API 的屏幕截图](../../media/patients-app-azure-portal-instance-settings.png)

5. 单击 **"** 身份验证"，然后在步骤 3 中复制的对象 ID 粘贴到"允许 **的对象 ID"** 框中。 这允许 Patients 应用访问 FHIR 服务器。 粘贴对象 ID 后，Azure Active Directory进行验证，旁边会显示一个绿色对号。

    ![Azure 门户中身份验证设置的屏幕截图](../../media/patients-app-azure-portal-authentication.png)

6. 单击“**保存**”。 这会重新部署实例，这可能需要几分钟时间。

7. 单击 **"概述**"，然后从 **FHIR 元数据终结点复制 URL。** 删除元数据标记，获取 FHIR 服务器 URL。 例如 `https://test02-teamshealth.azurehealthcareapis.com/` ，。

    ![Azure 门户中的元数据终结点](../../media/patients-app-azure-portal-metadata-endpoint.png)

8. 在Teams中，转到团队中加载的 Patients 应用实例，单击"设置"，**然后在**"链接"框中输入 FHIR服务器终结点 URL。 然后单击 **"连接"** 以建立连接并搜索患者，然后将患者添加到列表中。  

    ![ 病人应用中的"患者"Teams](../../media/patients-app-teams.png)

    如果在此步骤中连接到 Teams 时收到错误，请发送错误的详细屏幕截图、[来自 Fiddler](https://www.telerik.com/download/fiddler)的日志以及电子邮件中任何其他重现步骤，主题行为"Patients App – EMR 模式故障排除"到[teamsforhealthcare@service.microsoft.com。](mailto:teamsforhealthcare@service.microsoft.com)

## <a name="related-topics"></a>相关主题

- [患者应用概述](patients-app-overview.md)
- [将电子医疗记录集成到 Microsoft Teams 中](patients-app.md)
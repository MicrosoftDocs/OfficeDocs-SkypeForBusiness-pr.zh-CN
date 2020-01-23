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
# <a name="connect-the-patients-app-to-azure-api-for-fhir"></a>将患者应用连接到 Azure API for FHIR

按照以下步骤，允许 Microsoft 团队中的患者应用访问 FHIR 实例的 Azure API。 本文假定你在租户中设置和配置了[FHIR 实例的 AZURE API](https://azure.microsoft.com/services/azure-api-for-fhir/) 。  如果尚未在租户中为 FHIR 实例创建 Azure API，请参阅[快速入门：使用 azure 门户部署 FHIR 的 AZURE api](https://docs.microsoft.com/azure/healthcare-apis/fhir-paas-portal-quickstart)。


1. 单击[此处](https://login.microsoftonline.com/common/adminConsent?client_id=4aee3506-b263-43e0-ba31-1468fa7b2806)授予对患者应用的管理员同意。 出现提示时，使用租户管理员或全局管理员凭据登录，然后单击 "**接受**" 以授予所需的权限。

    ![患者应用的权限请求的屏幕截图](../../media/patients-app-permissions-request.png)

    接受后，关闭窗口。 你将看到一个可能如下所示的页面。 你可以忽略页面上的错误消息。 这是无害的，表明授予同意。 （我们正在为此 URL 的用户提供更友好的页面。 继续关注！）

    ![患者应用的权限请求的屏幕截图](../../media/patients-app-permissions-request-granted.png)
2. 通过管理员凭据登录到[Azure 门户](https://portal.azure.com)。
3. 在左侧导航中，选择 " **Azure Active Directory**"，然后选择 "**企业应用程序**"。
    查找名为 "**病人（开发人员）**" 的行，然后将 "**对象 ID** " 列中的值复制到剪贴板。
    ![Azure 门户中的患者（开发）行的屏幕截图](../../media/patients-app-azure-portal-object-id.png)
4. 转到要连接到患者应用的 FHIR 资源实例的 Azure API （通过搜索或浏览资源），然后打开该实例的设置。

    ![Azure API for Azure 门户中的 FHIR 实例设置的屏幕截图](../../media/patients-app-azure-portal-instance-settings.png)

5. 单击 "**身份验证**"，然后将您在步骤3中复制的对象 ID 粘贴到 "**允许的对象 id** " 框中。 这允许患者应用访问 FHIR 服务器。 粘贴对象 ID 后，Azure Active Directory 将对其进行验证，旁边会显示一个绿色复选标记。

    ![Azure 门户中身份验证设置的屏幕截图](../../media/patients-app-azure-portal-authentication.png)

6. 单击“**保存**”。 此示例 redeploys 实例，这可能需要几分钟时间。
7. 单击 "**概述**"，然后从**FHIR metadata 终结点**复制 URL。 删除元数据标记以获取 FHIR 服务器 URL。 例如， https://test02-teamshealth.azurehealthcareapis.com/。 

    ![Azure 门户中的元数据终结点的屏幕截图](../../media/patients-app-azure-portal-metadata-endpoint.png)

8. 在 "团队" 中，转到团队中加载的患者应用实例，单击 "**设置**"，然后在 "**链接**" 框中，输入 FHIR 服务器终结点 URL。 然后，单击 "**连接**" 建立连接并搜索 "病人" 并将其添加到您的列表。  

    ![团队中的患者应用设置的屏幕截图](../../media/patients-app-teams.png)
    
    如果在此步骤中连接到团队时收到错误，请从[Fiddler](https://www.telerik.com/download/fiddler)中发送详细的屏幕截图，并使用 "患者应用– EMR 模式疑难解答" 主题行的电子邮件中的任何其他再现步骤进行[teamsforhealthcare@service.microsoft.com](mailto:teamsforhealthcare@service.microsoft.com)。

## <a name="related-topics"></a>相关主题

- [患者应用概述](patients-app-overview.md)
- [将电子医疗记录集成到 Microsoft Teams 中](patients-app.md)

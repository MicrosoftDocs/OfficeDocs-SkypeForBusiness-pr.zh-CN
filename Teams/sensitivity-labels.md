---
title: Microsoft Teams 的敏感度标签
ms.author: mikeplum
author: cabailey
manager: laurawi
ms.reviewer: abgupta
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
localization_priority: Normal
search.appverid: MET150
description: 了解如何使用敏感度标签在 Microsoft Teams 中保护团队。
ms.openlocfilehash: 461daf6e91f9ba276dceef1929601d1188563931
ms.sourcegitcommit: f223b5f3735f165d46bb611a52fcdfb0f4b88f66
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/06/2021
ms.locfileid: "51593860"
---
# <a name="sensitivity-labels-for-microsoft-teams"></a>Microsoft Teams 的敏感度标签

[敏感度标签](/microsoft-365/compliance/sensitivity-labels) 允许 Teams 管理员保护和管理对在团队内协作期间创建的敏感组织内容的访问。 在 [Microsoft](/microsoft-365/compliance/go-to-the-securitycompliance-center)合规性中心中配置敏感度标签及其关联策略后，这些标签可以应用于组织的团队。

对于使用 Teams 教育 SKUS 的客户，课堂团队目前不支持敏感度标签。 若要详细了解许可，请参阅 Microsoft [Teams 服务说明](/office365/servicedescriptions/teams-service-description)。

## <a name="whats-the-difference-between-sensitivity-labels-and-teams-classification-labels"></a>敏感度标签和 Teams 分类标签之间有什么区别？

敏感度标签不同于分类标签，也称为 Azure AD 组分类。 分类标签是可与 Microsoft 365 组关联的文本字符串，但没有任何与之关联的实际策略。 使用分类标签作为元数据，然后必须使用其他方法（例如内部工具和脚本）来强制实施策略。

使用敏感度标签的好处是，通过 Microsoft 365 组平台、合规性中心和 Teams 服务的组合，自动端到端地强制实施其策略。 敏感度标签提供强大的基础结构支持，用于保护组织的敏感数据并确保符合内部策略或法规。

如果当前使用分类标签，请参阅以下文档，详细了解如何将它们迁移到敏感度标签： [经典 Azure AD 组分类](/microsoft-365/compliance/sensitivity-labels-teams-groups-sites#classic-azure-ad-group-classification)。

## <a name="example-scenarios-for-sensitivity-labels"></a>敏感度标签的示例方案

如何对组织中 Teams 使用敏感度标签的示例方案：

- [为团队设置 (隐私级别) 隐私级别](#set-the-privacy-level-for-teams)
- [控制来宾对团队的访问](#control-guest-access-to-teams)

### <a name="set-the-privacy-level-for-teams"></a>设置团队的隐私级别

可以创建和配置敏感度标签，在团队创建期间应用该标签时，允许用户创建具有特定隐私性 (公共或) 设置。

例如，创建并发布名为"机密"的敏感度标签，该标签隐私选项配置为"私密 **"。** 因此，使用此标签创建的任何团队都必须是专用团队。 

当用户创建新团队并选择"机密"标签时，可供用户使用的唯一隐私选项是"专用 **"。** 用户无法选择其他隐私选项，例如"公共"和"组织范围"：

![机密敏感度标签的屏幕截图](media/sensitivity-labels-confidential-example.png)

同样，创建并发布名为"常规"的敏感度标签，该标签隐私选项配置为"**公共"。** 当用户创建新团队时，他们只能在选择此标签时创建公共团队或组织范围的团队：

![常规敏感度标签的屏幕截图](media/sensitivity-labels-general-example.png)

创建团队时，敏感度标签显示在团队中频道的右上角。 

> [!NOTE]
> 如果使用分层父子标签（如"Confidential\Finance"），则频道标头中只会显示父标签。

![团队频道中敏感度标签的屏幕截图](media/sensitivity-labels-channel.png)

团队所有者可以通过访问团队，然后单击"编辑团队"，随时更改该团队的敏感度标签和 **隐私设置**。

![团队属性中敏感度标签的屏幕截图](media/sensitivity-labels-edit-team.png)

### <a name="control-guest-access-to-teams"></a>控制来宾对团队的访问

可以使用敏感度标签来控制来宾对团队的访问。 使用不允许来宾访问的标签创建的团队仅对贵组织的用户可用。 无法将组织外部人员添加到团队。

## <a name="microsoft-teams-admin-center"></a>Microsoft Teams 管理中心

在 Microsoft Teams 管理中心创建或编辑团队时，可以应用敏感度标签。 

敏感度标签在团队属性和 Microsoft Teams 管理中心的"管理团队 **"** 页面上的"分类"列中也可见。

## <a name="limitations"></a>限制

为 Teams 使用敏感度标签之前，请注意以下限制：

- **子标签不显示父标签名称**
    
    Teams 支持子标签，但不显示父标签的名称。 例如，"**机密** \\ **所有员工"** 显示为"**所有员工"。**

- **Teams Graph API、PowerShell cmdlet 和模板不支持敏感度标签**
    
    用户无法通过 Teams Graph API、Teams PowerShell cmdlet 和 Teams 模板直接创建团队时指定敏感度标签。 但是，新式组图形 API 和 PowerShell cmdlet 允许创建具有标签的组。 因此，用户可以首先使用组图形 API 或 PowerShell cmdlet 创建带标签的组，然后将这些组转换为 Teams。

- **支持专用频道**
    
    在团队中创建的专用频道将继承应用于团队的敏感度标签。 该标签会自动应用于专用频道的 SharePoint 网站集。
    
    但是，如果用户直接更改专用频道的 SharePoint 网站上敏感度标签，该标签更改不会反映在 Teams 客户端中。 在此方案中，用户继续在专用频道标题中看到应用于团队的原始敏感度标签。

## <a name="how-to-create-and-configure-sensitivity-labels-for-teams"></a>如何为 Teams 创建和配置敏感度标签

使用 Microsoft 365 文档中的说明为 Teams 创建和配置敏感度标签： 

- [使用敏感度标签保护 Microsoft Teams、Microsoft 365 组和 SharePoint 网站中的内容](/microsoft-365/compliance/sensitivity-labels-teams-groups-sites)。

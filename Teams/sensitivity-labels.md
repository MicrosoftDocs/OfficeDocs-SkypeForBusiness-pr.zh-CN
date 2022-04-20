---
title: Microsoft Teams的敏感度标签
ms.author: cabailey
author: cabailey
manager: laurawi
ms.reviewer: shubjain
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
ms.localizationpriority: medium
search.appverid: MET150
description: 了解如何使用敏感度标签来保护Microsoft Teams中的团队。
ms.openlocfilehash: fab5ad4e3be3da5afc6ee373aa6bebe2afae819e
ms.sourcegitcommit: 1d990582e2deb5f55ba9adada3e17377f792a141
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/19/2022
ms.locfileid: "64922693"
---
# <a name="sensitivity-labels-for-microsoft-teams"></a>Microsoft Teams的敏感度标签

[敏感度标签](/microsoft-365/compliance/sensitivity-labels)允许Teams管理员保护和规范对团队内协作期间创建的敏感组织内容的访问。 在 [Microsoft Purview 合规性门户](/microsoft-365/compliance/go-to-the-securitycompliance-center)中使用其关联的策略配置敏感度标签后，这些标签可以应用于组织中的团队。

对于使用 Teams Education SKU 的客户，当前在类团队中不支持敏感度标签。 若要了解有关许可的详细信息，[请参阅Microsoft Teams服务说明](/office365/servicedescriptions/teams-service-description)。

## <a name="whats-the-difference-between-sensitivity-labels-and-teams-classification"></a>敏感度标签和Teams分类有什么区别？

敏感度标签不同于Teams分类，也称为Azure AD组分类。 分类是可与Microsoft 365组关联但没有任何实际策略关联的文本字符串。 将分类用作元数据，然后必须使用其他方法（例如内部工具和脚本）来强制实施策略。

使用敏感度标签的好处是，通过Microsoft 365 组平台、合规中心和Teams服务的组合，自动端到端强制实施其策略。 敏感度标签为保护组织的敏感数据并确保符合内部策略或法规提供了强大的基础结构支持。

如果当前使用Teams分类，请参阅以下文档，了解有关如何将这些值转换为敏感度标签的详细信息和说明：[经典Azure AD组分类](/microsoft-365/compliance/sensitivity-labels-teams-groups-sites#classic-azure-ad-group-classification)。

## <a name="example-scenarios-for-sensitivity-labels"></a>敏感度标签的示例方案

有关如何在组织中将敏感度标签与Teams配合使用的示例方案：

- [为团队设置公共或私人)  (隐私级别](#set-the-privacy-level-for-teams)
- [控制对团队的来宾访问](#control-guest-access-to-teams)

### <a name="set-the-privacy-level-for-teams"></a>设置团队的隐私级别

可以创建和配置敏感度标签，该标签在创建团队期间应用时，允许用户创建具有特定隐私 (公共或专用) 设置的团队。

例如，创建并发布名为“机密”的敏感度标签，该标签隐私选项配置为 **“专用**”。 因此，使用此标签创建的任何团队都必须是私人团队。 

当用户创建新团队并选择 **“机密** ”标签时，用户唯一可用的隐私选项是 **“专用**”。 其他隐私选项（如公共和组织范围）不可用于用户选择：

![机密敏感度标签的屏幕截图。](media/sensitivity-labels-confidential-example.png)

同样，你创建并发布名为“常规”的敏感度标签，该标签隐私选项配置为 **“公共**”。 当用户创建新团队时，他们只能在选择此标签时创建公共组织范围的团队：

![常规敏感度标签的屏幕截图。](media/sensitivity-labels-general-example.png)

创建团队后，敏感度标签对团队中频道右上角的用户可见。 

![团队频道中敏感度标签的屏幕截图。](media/sensitivity-labels-channel.png)

团队所有者可以通过转到团队随时更改团队的敏感度标签和隐私设置，然后单击 **“编辑团队**”。

![团队属性中敏感度标签的屏幕截图。](media/sensitivity-labels-edit-team.png)

### <a name="control-guest-access-to-teams"></a>控制对团队的来宾访问

可以使用敏感度标签来控制来宾对团队的访问。 使用不允许来宾访问的标签创建的Teams仅对组织中的用户可用。 无法将组织外部的人员添加到团队。

## <a name="microsoft-teams-admin-center"></a>Microsoft Teams管理中心

在Microsoft Teams管理中心创建或编辑团队时，可以应用敏感度标签。 

敏感度标签在团队属性和Microsoft Teams管理中心的 **“管理团队**”页上的“**分类**”列中也可见。

## <a name="limitations"></a>限制

在将敏感度标签用于Teams之前，请注意以下限制：

- **Teams Graph API 和 PowerShell cmdlet 不支持敏感度标签**
    
    用户无法通过 Teams Graph API 或 Teams PowerShell cmdlet 直接创建团队时指定敏感度标签。 但是，新式组Graph API 和 PowerShell cmdlet 确实允许创建具有敏感度标签的组。 这意味着可以使用这些方法创建具有敏感度标签的组，然后将这些组转换为团队。

- **对专用频道的支持**
    
    在团队中创建的专用频道继承了在团队中应用的敏感度标签。 同一标签会自动应用于专用频道的SharePoint网站集。
    
    但是，如果用户直接更改专用通道的SharePoint网站上的敏感度标签，则该标签更改不会反映在Teams客户端中。 在此方案中，用户继续看到在专用频道标头的团队中应用的原始敏感度标签。

## <a name="how-to-create-and-configure-sensitivity-labels-for-teams"></a>如何为Teams创建和配置敏感度标签

使用Microsoft 365文档中的说明为Teams创建和配置敏感度标签： 

- [使用敏感度标签保护Microsoft Teams、Microsoft 365组和SharePoint网站中的内容](/microsoft-365/compliance/sensitivity-labels-teams-groups-sites)。

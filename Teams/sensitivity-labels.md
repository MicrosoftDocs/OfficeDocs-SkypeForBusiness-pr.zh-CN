---
title: Microsoft Teams 的敏感度标签
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
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
description: 了解如何在 Microsoft Teams 中定义和使用敏感度标签。
ms.openlocfilehash: d021954a32cc2d93fb7b17726720396e66b4fd39
ms.sourcegitcommit: b68a7b5100fc2b47ae81f465d48d1ac2348c1744
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/11/2021
ms.locfileid: "49795768"
---
# <a name="sensitivity-labels-for-microsoft-teams"></a>Microsoft Teams 的敏感度标签

[敏感度标签](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels) 允许 Teams 管理员管理对在团队内协作期间创建的敏感组织内容的访问。 可以在合规性中心定义敏感度标签及其关联的 [策略](https://docs.microsoft.com/microsoft-365/compliance/go-to-the-securitycompliance-center)。 这些标签和策略会自动应用于组织中团队。  

## <a name="whats-the-difference-between-sensitivity-labels-and-teams-classification-labels"></a>敏感度标签和 Teams 分类标签之间有什么区别？

敏感度标签不同于分类标签。 分类标签是可与 Microsoft 365 组关联的文本字符串，但没有任何与之关联的实际策略。 使用分类标签作为元数据，通过内部工具和脚本手动强制实施策略。

另一方面，敏感度标签及其策略是通过组平台、安全与合规中心与 Teams 服务的组合&端到端强制实施的。 敏感度标签提供强大的基础结构支持，用于保护组织的敏感数据。  

若要将现有组从使用分类标签迁移到使用敏感度标签，请使用 Azure Active [Directory 分类和 Microsoft 365](https://docs.microsoft.com/microsoft-365/compliance/migrate-aad-classification-sensitivity-labels)组的敏感度标签中的说明。

## <a name="create-manage-and-publish-sensitivity-labels-for-teams"></a>为 Teams 创建、管理和发布敏感度标签

若要了解如何为 Teams 启用、创建和发布敏感度标签，请参阅"使用敏感度标签保护 [Microsoft Teams、Microsoft 365](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites)组和 SharePoint 网站中的内容"。

>[!IMPORTANT]
>创建、更新和删除敏感度标签需要谨慎排序，将标签发布给用户。 序列中出现任何偏差都可能导致所有用户持续出现团队创建错误。 因此，创建和发布标签、修改和删除已发布的标签<a href="#createpublishlabels"></a>以及管理团队创建错误时<a href="#modifydeletelabels"></a>，必须<a href="#manageerrors">执行以下操作</a>。

**创建和发布标签**<a name="createpublishlabels"></a>

在合规性中心中创建和发布标签时，可能需要 10 分钟才能在团队创建界面中显示该标签。 使用以下步骤发布租户中所有用户的标签：
1. 创建标签，并针对租户中的几个选定用户帐户发布该标签。
2. 发布标签后，请等待 10 分钟。
3. 10 分钟后，尝试使用有权访问标签的用户帐户之一创建具有标签的团队。
4. 如果团队在步骤 3 中成功创建，则继续操作并发布租户中其余用户的标签。

**修改和删除已发布的标签**<a name="modifydeletelabels"></a>

在标签与敏感度策略关联时删除或修改标签可能会导致整个租户的团队创建失败。 因此，在删除或修改标签之前，必须先取消标签与其关联策略的关联。 使用以下步骤  
删除或修改标签：
1. 从使用该标签的所有策略中删除标签。 或者，也可以删除策略本身。
2. 从策略中删除标签或删除策略本身时，请等待 10 分钟，然后继续下一步。
3. 10 分钟后，启动团队创建界面，并确保该标签不再对租户中任何用户可见。
4. 现在，可以安全地删除或修改标签。

**管理团队创建错误**<a name="manageerrors"></a>

如果团队创建在公共预览版期间的任何时间点开始失败，有两个选项：
 - 确保在创建团队期间，任何用户都不需要使用敏感度标签。
 - 使用"启用此预览"中的脚本 [关闭敏感度标签](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites#enable-this-preview)。

请注意，EnableMIPLabels 设置必须设置为 false，如下所示：

```console
$setting["EnableMIPLabels"] = "False"
```

## <a name="using-sensitivity-labels-with-teams"></a>将敏感度标签与 Teams 一起使用

下面是一些示例方案，演示了如何在组织中将敏感度标签与 Teams 一同使用。

### <a name="privacy-setting-of-teams"></a>团队的隐私设置

你可以创建一个敏感度标签，在团队创建期间应用该标签时，允许用户创建具有特定隐私性 (公共或专用) 设置。

例如，在安全中心创建名为"机密"的标签&配置 Teams，以便使用此标签创建的任何团队都必须是专用团队。 当用户创建新团队并选择"机密"标签时，可供用户使用的唯一隐私选项是 **"专用"。** 用户禁用了其他隐私选项，例如"公共"和"组织范围"。

![机密敏感度标签的屏幕截图](media/sensitivity-labels-confidential-example.png)

同样，如果用户在创建新 **团队时选择了** "常规"，则他们只能创建公共团队或组织范围的团队。

![常规敏感度标签的屏幕截图](media/sensitivity-labels-general-example.png)

创建团队后，敏感度标签显示在团队中频道的右上角。

![团队频道中敏感度标签的屏幕截图](media/sensitivity-labels-channel.png)

团队所有者可以通过访问团队，然后单击"编辑团队"随时更改该团队的敏感度标签和 **隐私设置**。

![团队属性中敏感度标签的屏幕截图](media/sensitivity-labels-edit-team.png)

### <a name="guest-access-to-teams"></a>团队的来宾访问权限

可以指定使用特定标签创建的团队是否允许来宾访问。 使用不允许来宾访问的标签创建的团队仅适用于您的组织中的用户。 不能将组织外部人员添加到团队。

### <a name="sensitivity-labels-in-the-microsoft-teams-admin-center"></a>Microsoft Teams 管理中心中的敏感度标签

可以在 Microsoft Teams 管理中心创建或编辑团队时设置敏感度标签。 敏感度标签在团队属性和 Microsoft Teams 管理中心的"管理团队"页面上的"分类"列中也可见。

## <a name="known-issues"></a>已知问题

**支持 Teams Graph API、PowerShell cmdlet 和模板中的敏感度标签**

目前，用户无法对通过图形 API、PowerShell cmdlet 和模板直接创建的团队应用敏感度标签。

**支持 Teams EDU SU 中的敏感度标签**

使用 Teams 教育 SK 的客户提供敏感度标签目前不受支持。

**直接在 SharePoint 网站集上编辑专用频道的敏感度标签**

在团队中创建的专用频道将继承应用于团队的敏感度标签。 此外，同一标签会自动应用于专用频道的 SharePoint 网站集。

如果用户直接更新专用频道的 SharePoint 网站集上的敏感度标签，该标签不会在 Teams 客户端中更新。 在此方案中，用户将继续在专用频道标题中看到应用于团队的敏感度标签。

**应用于 Teams 应用外部敏感度标签的更改传播时间**

在 Teams 应用外部对敏感度标签所做的更改最多可能需要 24 小时才能反映在 Teams 应用中。 这适用于为租户启用或禁用标签而做出的任何更改、对标签名称、设置和策略的更改。

此外，对直接对支持团队的组或 SharePoint 网站集的标签进行的任何更改最多可能需要 24 小时才能传播到 Teams 应用。

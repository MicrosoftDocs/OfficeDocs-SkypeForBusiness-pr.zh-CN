---
title: Microsoft 团队的灵敏度标签
author: lanachin
ms.author: v-lanac
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
description: 了解如何在 Microsoft 团队中定义和使用敏感度标签。
ms.openlocfilehash: 446bd222ce29ed627eb3229b244228665bbff6c0
ms.sourcegitcommit: ed3d7ebb193229cab9e0e5be3dc1c28c3f622c1b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41838112"
---
# <a name="sensitivity-labels-for-microsoft-teams"></a>Microsoft 团队的灵敏度标签

[!INCLUDE [preview-feature](includes/preview-feature.md)]

[敏感度标签](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels)允许团队管理员控制在团队内协作期间创建的敏感组织内容的访问权限。 你可以在[安全 & 合规中心](https://docs.microsoft.com/microsoft-365/compliance/go-to-the-securitycompliance-center)中定义灵敏度标签及其关联的策略。 这些标签和策略将自动应用于你的组织中的团队。  

## <a name="whats-the-difference-between-sensitivity-labels-and-teams-classification-labels"></a>灵敏度标签和团队分类标签之间有何区别？

敏感度标签不同于需要使用 PowerShell 创建的分类标签。 分类标签是可与组相关联但没有任何相关联的实际策略的文本字符串。 将分类标签用作元数据以通过内部工具和脚本手动强制实施策略。

另一方面，灵敏度标签和其策略通过组平台、安全 & 合规中心和团队服务的组合自动实施端到端。 灵敏度标签提供强大的基础结构支持以保护组织的敏感数据。  

## <a name="create-manage-and-publish-sensitivity-labels-for-teams"></a>为团队创建、管理和发布灵敏度标签

有关如何为团队启用、创建和发布敏感度标签的详细说明，请参阅[将敏感度标签与 Microsoft 团队、Office 365 组和 SharePoint 网站结合使用](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites)。

>[!IMPORTANT]
>创建、更新和删除灵敏度标签需要对用户发布标签的仔细排序。 序列中的任何偏差都可能会导致所有用户的持久团队创建错误。 因此，在<a href="#createpublishlabels">创建和发布标签</a>、<a href="#modifydeletelabels">修改和删除已发布标签</a>以及<a href="#manageerrors">管理团队创建错误</a>时，执行以下操作非常重要。

**创建和发布标签** <a name="createpublishlabels"></a>

在安全 & 合规中心创建和发布标签时，该标签最多可能需要24小时才能在团队创建界面中变为可见。 使用以下步骤为租户中的所有用户发布标签：
1. 创建标签并将其发布到租户中的几个选择用户帐户。
2. 当标签发布时，请等待24小时。
3. 24小时后，请尝试使用有权访问标签的用户帐户创建带有标签的团队。
4. 如果团队在步骤3中成功创建，则继续并为租户中的其余用户发布标签。

**修改和删除已发布的标签** <a name="modifydeletelabels"></a>

删除或修改与灵敏度策略相关联的标签可能会导致整个租户中的团队创建失败。 因此，在删除或修改标签之前，必须首先解除标签与其关联的策略的关联。 使用以下步骤  
要删除或修改标签，请执行以下操作：
1. 从使用该标签的所有策略中删除标签。 或者，也可以删除策略本身。
2. 当从策略中删除标签或策略本身被删除时，请等待48小时，然后再继续。
3. 48小时后，启动团队创建界面并确保该标签对于租户中的任何用户不再可见。
4. 现在，您可以安全地删除或修改标签。

**管理团队创建错误** <a name="manageerrors"></a>

如果团队创建在公共预览版中的任何时候开始失败，您有两种选择：
 - 确保在创建团队期间对任何用户不强制使用灵敏度标签。
 - 使用 "[启用此预览](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites#enable-this-preview)" 中的脚本关闭灵敏度标签。

请注意，EnableMIPLabels 设置必须设置为 false，如下所示：

```
$setting["EnableMIPLabels"] = "False"
 ```

## <a name="using-sensitivity-labels-with-teams"></a>将灵敏度标签与团队配合使用

下面是一些有关如何将敏感度标签与组织中的团队配合使用的示例方案。

### <a name="privacy-setting-of-teams"></a>团队的隐私设置

你可以创建在团队创建期间应用的敏感度标签，以允许用户使用特定隐私（公共或专用）设置创建团队。

例如，在安全 & 合规中心创建名为 "保密" 的标签，并配置团队，以便使用此标签创建的任何团队都必须是专用团队。 当用户创建新团队并选择 "**机密**" 标签时，用户可用的唯一隐私选项是 "**专用**"。 用户已禁用其他隐私选项，如公共和组织范围。

![机密敏感度标签的屏幕截图](media/sensitivity-labels-confidential-example.png)

同样，如果用户在创建新团队时选择 "**常规**"，则他们只能创建公共团队或组织级团队。

![常规灵敏度标签的屏幕截图](media/sensitivity-labels-general-example.png)

创建团队时，灵敏度标签显示在团队频道的右上角。

![团队频道中灵敏度标签的屏幕截图](media/sensitivity-labels-channel.png)

团队所有者可以随时更改团队的敏感度标签和隐私设置，方法是转到团队，然后单击 "**编辑团队**"。

![团队频道中灵敏度标签的屏幕截图](media/sensitivity-labels-edit-team.png)

### <a name="guest-access-to-teams"></a>对团队的来宾访问

你可以指定使用特定标签创建的团队是否允许来宾访问。 使用不允许来宾访问的标签创建的团队仅对您的组织中的用户可用。 无法将组织外部的人员添加到团队。

## <a name="known-issues"></a>已知问题

**Microsoft 团队管理中心中对灵敏度标签的支持**

目前，Microsoft 团队管理中心不支持敏感性标签。 如果使用灵敏度标签，则在创建或编辑团队时将无法设置灵敏度标签。 灵敏度标签在团队属性中也不可见，并且在 Microsoft 团队管理中心的 "**分类**" 列中不可见。

**对团队图形 Api、Powershell cmdlet 和模板中的灵敏度标签的支持**

当前，用户无法对直接通过图形 Api、Powershell cmdlet 和模板创建的团队应用敏感度标签。

**直接在专用频道的 SharePoint 网站集上编辑灵敏度标签**

在团队中创建的专用频道将继承应用于团队的灵敏度标签。 此外，将在专用频道的 SharePoint 网站集上自动应用相同的标签。

如果用户在专用频道的 SharePoint 网站集上直接更新灵敏度标签，则不会在团队客户端中更新该标签。 在这种情况下，用户将继续在专用信道标题中看到团队中应用的灵敏度标签。

**应用于团队应用外的灵敏度标签的更改的传播时间**

对 "团队" 应用外的灵敏度标签所做的更改最多需要24小时才能反映在 "团队" 应用中。 这适用于为租户启用或禁用标签、更改标签名称、设置和策略所做的任何更改。

此外，直接对支持团队的组或 SharePoint 网站集直接更改标签的任何更改最多可能需要24小时才能传播到团队应用。

---
title: '适用于团队管理员的患者应用 '
author: dstrome
ms.author: dstrome
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
description: 适用于团队管理员的患者应用
ms.openlocfilehash: 1b6db686be1acbc7ee23be555c9794c644e5c5cc
ms.sourcegitcommit: f4f5ad1391b472d64390180c81c2680f011a8a10
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2020
ms.locfileid: "48367582"
---
# <a name="patients-app-overview"></a>患者应用概述

> [!IMPORTANT]
> **2020年10月30日生效，患者应用将被否决，用户将无法再从团队应用商店安装。我们鼓励你立即开始使用团队中的 " [列表" 应用](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) 。**
>
>患者应用数据存储在支持团队的 Office 365 组的组邮箱中。 当患者应用停用时，与之关联的所有数据将保留在此组中，但不能再通过用户界面进行访问。 当前用户可以使用 " [列表" 应用](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db)重新创建其列表。
>
>" [列表" 应用](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) 为所有团队用户预安装，可在每个团队和频道中用作选项卡。 使用 "列表"，"护理团队" 可以使用内置患者模板、从头开始或通过将数据导入 Excel 来创建患者列表。 若要了解有关如何管理组织中的列表应用的详细信息，请参阅 [管理列表应用](../../manage-lists-app.md)。

患者应用程序是适用于所有团队用户的 Microsoft 团队应用商店应用程序。 该应用支持由临床工作者组成的患者护理团队 (例如，护士、医生、社会工作者) 可以策展和查看患者的列表，包括从倒圆角和 interdisciplinary 团队会议到常规患者监控的情形。

应用具有两种模式：

- 通过 FHIR 连接到 EMRs 的 EMR 连接模式。 EMR 连接模式应用保留在私人预览版中，并且感兴趣的客户或管理员可能会通过在 [teamsforhealthcare@service.microsoft.com](mailto:teamsforhealthcare@service.microsoft.com) 中删除 microsoft 电子邮件，获取有关其 Microsoft 365 组织的信息，从而请求对应用的访问权限。
- 允许护理团队手动添加/添加患者信息的手动模式。 应用程序位于团队应用商店中，最终用户可在私人预览版中下载。 可使用团队中的 [应用设置策略](../../teams-app-setup-policies.md) 将应用限制到特定部分的用户。 若要获取对应用的访问权限，你的租户需要参与技术采纳计划 (点击 ") "。 请在 [teamsforhealthcare@service.microsoft.com](mailto:teamsforhealthcare@service.microsoft.com) 上向我们发送电子邮件，以启动请求访问的流程。

## <a name="usage-example"></a>用法示例

在医疗 wards 中每个班次的舍入期内，临床医生在 nursing 工作站上进行收集，以便在拖动中讨论患者的最新更新。  他们突出显示关键指标， (不一定是医疗的，或者它在病人的医疗记录) 上是明确的，确保患者基于其诊断的 glide 途径。 为了围绕这些患者，"费用" 护士在一个团队中设置患者应用，其中添加了所有临床医生，并将患者添加到患者列表。 在舍入期间，护士和其他护理 givers 在其移动设备上的患者 access Microsoft 团队和患者应用，并在其设备上更新相关的患者信息，并且在护理团队中的其他人可以看到这些更新和注释并保持同步。一天两次，在班次的开始和结束时间，他们也有多个专业的团队会议可以通过患者列表，并使用患者应用在大型显示屏上使用患者应用共享有关每个患者的信息。 通常情况下，某些临床医生可能还会远程拨入这些团队会议，并且仍是讨论的一部分。

## <a name="configure-patients-app"></a>配置患者应用

有关如何准备您的环境以使用 EMR 模式患者应用的信息，请参阅将 [电子医疗保健记录集成到 Microsoft 团队](patients-app.md)。 你还需要查看 [Microsoft 团队中的 "管理应用设置策略"](../../teams-app-setup-policies.md) 以为你的组织启用患者应用。

有关最终用户如何才能访问患者应用并将其安装到他们拥有或管理的团队的信息，请参阅 [Microsoft 团队患者入门](https://support.office.com/article/get-started-with-microsoft-teams-patients-aa7daebe-706a-4a65-8ce9-b9b79233f393)。

<!-- add link out to client doc, doesn't seem to be available yet, Grant is finalizing -->

## <a name="frequently-asked-questions-faq"></a>常见问题 (常见问题) 

**患者应用数据存储在何处？**

最终用户输入到患者应用中的所有数据，包括列/字段架构、输入到列表中的实际数据和列表项 (（即患者) ）存储在安全和合规的 Exchange Online 基础结构中。 所有数据都存储在与团队相关联的组邮箱中。 此体系结构使患者应用能够轻松完成数据派驻、政府云支持 (未来) 以及电子数据展示支持等其他合规性/信息保护功能。 患者应用在团队范围内运行。 你将需要为每个团队安装应用的实例。

<!-- add link to eDiscovery article for the Patients app, Mark Johnson will finalize soon -->

**从哪里可以获取患者应用？**

如果患者应用由其管理员启用，则任何最终用户都可以转到 "团队" 应用商店，并将患者应用添加到他们所属的团队。 有关详细信息，请参阅 [管理 Microsoft 团队中的应用设置策略](../../teams-app-setup-policies.md)。

**我是否可以在团队中拥有患者应用的多个实例，因为这是我的拖动/单元的运营方式？**

目前，您只能为给定团队安装一个患者应用实例，并且仅在 "常规" 频道中安装。 但是，在应用内，可以创建多个列表来处理多通道或隔离/隔离方案。 默认情况下，团队的所有成员都将有权访问常规频道中的 "患者" 选项卡。 

**是否可以导出患者应用中的所有数据？**
目前尚不能，但此功能即将推出。 

**由于此应用适用于 PHI，因此是否有审核来防止未经授权的访问或遵守管理法规？**

是的，有。 Microsoft 团队用户在患者应用上执行的每个单个 UI 操作都会在安全和合规中心进行审核和使用。 在 [患者应用的审核日志](patients-audit.md)中介绍了详细信息。

## <a name="related-topics"></a>相关主题

[将电子医疗记录集成到 Microsoft Teams 中](patients-app.md)

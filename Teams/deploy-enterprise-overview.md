---
title: Microsoft Teams 企业版部署概述
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
description: 了解如何部署 Microsoft Teams 的企业功能。
ms.localizationpriority: high
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- m365initiative-deployteams
appliesto:
- Microsoft Teams
ms.openlocfilehash: f6e6a2835df6f00bc9103594b1cfe5ae011c6960
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/26/2021
ms.locfileid: "58617418"
---
# <a name="teams-enterprise-deployment-overview"></a>Teams 企业部署概述

如果是中型或大型企业，则需要考虑如何向用户推出服务、如何将 Microsoft Teams 客户端部署到用户、网络设计如何影响实时通信的质量等。请查看以下部分，获取指向可帮助你在组织中规划 Teams 的文章的指针。

> [!NOTE]
> 若尚未进行部署，强烈建议通过试点开始 Teams 部署。 试点将允许你和一些早期采用者在规划和推出之前熟悉 Teams 及其功能。若要详细了解如何开始进行试点，请参阅 [Microsoft Teams](get-started-with-teams-quick-start.md)。

阅读以下部分并准备好开始在组织中部署 Teams 之后，请参阅 [企业部署中的 Microsoft Teams](deploy-enterprise-setup.md)。

## <a name="architecture"></a>体系结构

团队紧密集成到 Microsoft 365 中，并使用多种功能支持聊天、文件共享、会议、电话、视频流等。 推出 Teams 之前，请查看 [Microsoft Teams IT 体系结构和电话解决方案海报](teams-architecture-solutions-posters.md) 以便熟悉 Teams 如何与 Microsoft 365 其余部分协作，为用户创建完整的协作体验。

## <a name="workloads"></a>工作负载

团队有三个工作负载，可独立部署： **聊天、团队和**; **会议和会议**;和 **电话系统和 PSTN（公用电话交换网络）连接**。 每个工作负载在我们的文档中都有其自己的部分，以便更容易找到有关该工作负载的信息。 这包括部署规划信息。

若要查看要部署的工作负荷的部署规划信息，请参阅下列文章：

- [聊天、团队和渠道](deploy-chat-teams-channels-microsoft-teams-landing-page.md)
- [会话和会议](deploy-meetings-microsoft-teams-landing-page.md)
- [电话系统和 PSTN 连接](cloud-voice-landing-page.md)

## <a name="network-planner"></a>Network Planner

如果用户众多或同时具有复杂的网络，则 Teams 的网络规划非常重要。 Teams 支持语音呼叫和视频会议，这两者均依赖于实时通信，为用户提供最佳体验。 网络必须：

- 有足够的带宽容量，容纳并发语音呼叫数、视频会议、会议、屏幕共享等。
- 具有支持实时通信协议的网络硬件。
- 允许网络上各设备之间的所需网络端口、Microsoft 365 服务和外部用户。

请参阅以下文章，帮助了解 Teams 网络要求：

- [为 Microsoft Teams 准备组织的网络](prepare-network.md)
- [Teams 或 Skype for Business Online 的代理服务器](proxy-servers-for-skype-for-business-online.md)

为帮助你进行规划，Teams 包括网络规划器。 网络规划器将询问有关你拥有的用户数和类型、组织拥有的网站数、网络链接带宽容量等的问题。 使用此信息，网络规划器将创建一个报表，显示每项活动的带宽要求和建议。

 > [!div class="nextstepaction"]
> [转到网络规划器](https://admin.teams.microsoft.com/networkplanner/organization)

（只有 Microsoft 365 [管理员才能](/microsoft-365/admin/add-users/about-admin-roles#commonly-used-microsoft-365-admin-center-roles) 网络规划器。）

有关网络规划器工作方式的详细信息，请参阅 [使用 Microsoft Teams 网络规划器](network-planner.md)。

若要了解网络规划器可如何规划网络的示例，请参阅["使用网络规划“ 的示例方案](tutorial-network-planner-example.yml)。

## <a name="teams-advisor"></a>Teams 顾问

Teams 顾问是团队内解决方案，将团队、频道、文件共享和 Planner 结合起来，为组织创建部署项目。 Teams 顾问创建特定于您选择的工作负荷（例如聊天、团队和频道）的项目计划，其中包括在部署期间应执行的建议任务。 每个任务包含说明、建议和相关文章的链接，引导你完成该过程。 可以轻松将任务分配给一个或多个人员，并为每个任务指定开始日期和结束日期。

> [!TIP]
> 请参阅如何使用 Teams 顾问来帮助你规划团队部署，方法可以是完成 [Microsoft Learn 上的 Teams 顾问](/learn/modules/m365-teams-rollout-using-advisor/) 模块。

> [!div class="nextstepaction"]
> [转到 Teams 顾问](https://admin.teams.microsoft.com/teams-deployment)

（必须是 Microsoft 365 [管理员才能](/microsoft-365/admin/add-users/about-admin-roles#commonly-used-microsoft-365-admin-center-roles) Teams 顾问。）

有关 Teams 顾问工作方式的详细信息，请参阅 [使用 Teams 顾问来帮助你推出 Microsoft Teams](use-advisor-teams-roll-out.md)。

## <a name="lifecycle-and-governance-planning"></a>生命周期和管理规划

规划团队部署时，需要考虑组织中团队的生命周期、频道、文件等。 还你应该考虑将存储在其中的信息类型。 可能会为特定项目创建团队、为部门创建团队，或者将团队用作整个组织的集中资源。 每个用法具有不同的要求，这进一步提出类似问题：

- 团队持续活动会持续多久？
- 谁应拥有和管理团队及其频道？
- 某些合规性要求应该适用于某些团队，而不适用于其他团队？
- 是否有可帮助用户识别合适团队的命名策略？

创建策略和准则作为初始部署的一部分，有助于确保你的用户能够找到所需的信息。 但最重要的是，适当的策略可帮助防止组织信息泄露，帮助你符合法规要求，并根据需要保留信息以用于存档。

若要深入了解 Teams 中的生命周期管理和管理，请参阅以下内容：

- [在 Teams 中规划生命周期管理](plan-teams-lifecycle.md)
- [在 Teams 中规划管理](plan-teams-governance.md)

## <a name="adoption"></a>采用

为确保你的组织和用户获取最多使用 Teams，需要采用计划。 有效的采用计划可以提前采用者，他们可：

- 向同事以及业务或组领导阐明 Teams 的好处。
- 看到 Teams 如何改善协作并更轻松地相互联系时，为其他人激发热情。
- 帮助评估现有业务流程，并针对团队如何集成到其中提出建议。
- 向部署团队报告成功和难题，帮助改进采用过程。

有关设置采用计划的详细信息，请参阅 [采用 Microsoft Teams](adopt-microsoft-teams-landing-page.md)。
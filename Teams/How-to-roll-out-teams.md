---
title: 如何部署 Microsoft Teams
author: lolajacobsen
ms.author: lolaj
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: LolaJ
audience: admin
description: 找到在组织中部署 Microsoft Teams 的正确途径。
localization_priority: Priority
search.appverid: MET150
ms.collection:
- M365-collaboration
- Teams_ITAdmin_RemoteWorkers
- remotework
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.dashboard.helparticle.rolloutteams
appliesto:
- Microsoft Teams
ms.openlocfilehash: bb11c6a7386abb9a83e178692a84cef1dfe8bd05
ms.sourcegitcommit: f96d66d08a9d6993edbb9554738dc8236d901933
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/30/2020
ms.locfileid: "43053555"
---
# <a name="how-to-roll-out-microsoft-teams"></a>如何部署 Microsoft Teams

## <a name="start-here"></a>从这里开始
不管是小型企业还是跨国企业，都可以通过[入门](get-started-with-teams-quick-start.md)来开始部署 Teams。 它将指导你小规模地部署 Teams，如果你是一家小型企业，或者要快速部署 Teams 作为你的第一个 Office 365 工作负载以支持**远程工作者**，那么你可能只需这样做即可。 如果是较大的组织，请使用[入门](get-started-with-teams-quick-start.md)让一小部分早期采用者试用 Teams，以便能够了解 Teams，并开始规划在组织范围内部署。 

## <a name="recommended-path-to-teams"></a>建议的 Teams 部署途径


我们建议在组织做好准备时按工作负载分阶段部署 Teams。 **不必等到完成了一个步骤才开始下一个步骤。** 某些组织可能想要一次性部署所有 Teams 功能，而另一些组织则可能更喜欢分阶段方法。 下面是按我们的建议部署顺序列出的 Teams 工作负载：

- [入门](get-started-with-teams-quick-start.md)
- [聊天、团队、频道和应用](deploy-chat-teams-channels-microsoft-teams-landing-page.md)
- [会议](deploy-meetings-microsoft-teams-landing-page.md)
- [云语音](cloud-voice-landing-page.md)

[采用中心](adopt-microsoft-teams-landing-page.md)：在整个 Teams 部署过程中，一定要利用这些资源来帮助推动 Teams 的采用。

![说明 Teams 部署途径的图示](media/how-to-roll-out-teams-image1.png)


## <a name="if-youre-starting-from-skype-for-business-on-premises-or-hybrid-deployments"></a>如果从 Skype for Business（本地或混合部署）开始

如果从 Skype for Business（联机或本地）转换到 Teams，或者需要混合配置，则你仍然可能采用上面的 Teams [建议部署途径](#recommended-path-to-teams)，但首先需要进行一些额外的规划。 首先查看下表中适用于贵组织情况的指引。



|  |贵组织的情况|指引  |
|---------|---------|---------|
|<IMG src="https://docs.microsoft.com/office/media/icons/migration-teams.svg" alt="Migration arrow symbol" height="50" width="50">|我当前正在使用 Skype for Business Online，并准备转移到 Teams。 |转到[升级到 Teams](upgrade-start-here.md)。        |
|<IMG SRC="https://docs.microsoft.com/office/media/icons/hybrid-teams.svg" alt="Hybrid symbol" height="50" width="50">|我的组织正在运行 Skype for Business Server，并且我想要部署 Teams。 |为了全面部署 Teams，首先你需要在本地环境和 Microsoft 365 环境之间配置混合连接。 请先阅读[在 Skype for Business Server 和 Office 365之间规划混合连接](https://docs.microsoft.com/skypeforbusiness/hybrid/plan-hybrid-connectivity)。 <br><br>你还应查看[升级到 Teams](upgrade-start-here.md)。   |
|<IMG src="https://docs.microsoft.com/office/media/icons/on-premises-teams.svg" alt="On premises symbol" height="50" width="50">|我没有 Skype for Business Server，但有本地 PSTN 解决方案。 我想要部署 Teams，但希望保留本地 PSTN 解决方案。 |按照上面的[建议途径](#recommended-path-to-teams)部署 Teams。<br><br>然后阅读[规划直接路由](direct-routing-plan.md)，了解如何使用电话系统直接路由将本地 PSTN 解决方案连接到 Teams。|
|



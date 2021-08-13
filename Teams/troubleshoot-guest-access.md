---
title: 排查 Microsoft Teams 中的来宾访问问题
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
ms.reviewer: corbinm
search.appverid: MET150
description: 获取排查并解决 Microsoft Teams 中来宾访问问题方面的帮助。
f1.keywords:
- NOCSH
localization_priority: Normal
appliesto:
- Microsoft Teams
ms.openlocfilehash: aaca5da3140761a4a0fc9194c8acb31325d0aceaa9463ab7517779865aa479cf
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2021
ms.locfileid: "54296439"
---
# <a name="troubleshoot-problems-with-guest-access-in-microsoft-teams"></a>排查 Microsoft Teams 中的来宾访问问题

- 若要了解我们是否了解你的问题，请查看[Teams的支持人员。](/MicrosoftTeams/troubleshoot/teams-welcome)
- 若要查看与 Teams 中来宾访问相关的现有支持问题，请转到 [Teams 故障排除](/MicrosoftTeams/troubleshoot/)。
- 来宾是组织外部人员。 如果你组织内部的某人（包括员工、现场合同工或现场代理），则不能添加为来宾。 这同样适用于你的关联公司。
- 有关即将发布的新推出或更新后的来宾访问功能，请访问 [Teams 路线图](https://aka.ms/teamsroadmap)。
- 请在 [Teams UserVoice](https://aka.ms/TeamsUserVoice) 中告诉我们你想要的功能。

[!INCLUDE [uservoice-disclaimer-note](includes/uservoice-disclaimer-note.md)]

## <a name="if-your-guests-are-seeing-license-errors"></a>如果来宾看到许可证错误

Teams 中的来宾访问功能使用 Azure Active Directory (Azure AD) 企业对企业 (B2B) 及其许可模式。 所有 Microsoft 365 商业标准版、Office 365 企业版和 Office 365 教育版订阅均包含来宾访问功能。 无需额外的 Microsoft 365 或 Office 365 许可证。

> [!NOTE]
> Teams来宾的住宅租户上启用订阅，来宾才能登录并使用 Teams 作为另一资源租户上的 () 租户。

如果看到许可错误，请务必阅读 [Azure AD](/azure/active-directory/external-identities/external-identities-pricing) 外部标识的计费模型，以确定满足组织中来宾访问需求的许可要求。

- 来宾许可证计入邀请组织。 在计算所需的许可证数量时，请注意这一点。
- 无论是受邀来宾来自另一个组织Microsoft 365还是使用其个人电子邮件地址，许可证都计入组织。

## <a name="support-for-b2b-user-types"></a>支持 B2B 用户类型

目前，Teams 只支持 [Azure B2B 定义的](/azure/active-directory/b2b/user-properties)状态 1 和状态 2 类型来宾用户。

## <a name="related-topics"></a>相关主题

[Teams 中的来宾访问](guest-access.md)

[Teams 疑难解答](/MicrosoftTeams/troubleshoot/teams)
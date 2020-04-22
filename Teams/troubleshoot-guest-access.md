---
title: 排查 Microsoft Teams 中的来宾访问问题
author: LolaJacobsen
ms.author: lolaj
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
appliesto:
- Microsoft Teams
localization_priority: Normal
ms.openlocfilehash: 52d3922bc68e942ad1cd58e40861fa8820ee6614
ms.sourcegitcommit: ea54990240fcdde1fb061489468aadd02fb4afc7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/22/2020
ms.locfileid: "43778398"
---
<a name="troubleshoot-problems-with-guest-access-in-microsoft-teams"></a>排查 Microsoft Teams 中的来宾访问问题
======================================================

> [!IMPORTANT]
> 最长可能需要等待 24 小时，更改才会生效。 


- 若要查看与 Teams 中来宾访问相关的现有支持问题，请转到 [Teams 故障排除](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/)。
- 若要确定你的问题是否已顺利反馈，请查看 [Microsoft Teams 已知问题](Known-issues.md)。
- 来宾是你组织外部的用户。 如果你组织内部的某人（包括员工、现场合同工或现场代理），则不能添加为来宾。 这同样适用于你的关联公司。
- 有关即将发布的新推出或更新后的来宾访问功能，请访问 [Teams 路线图](https://aka.ms/teamsroadmap)。
- 请在 [Teams UserVoice](https://aka.ms/TeamsUserVoice) 中告诉我们你想要的功能。

## <a name="if-your-guests-are-seeing-license-errors"></a>如果来宾看到许可证错误

Teams 中的来宾访问功能使用 Azure Active Directory (Azure AD) 企业对企业 (B2B) 及其许可模式。 来宾访问包括在所有 Microsoft 365 商业标准、Office 365 企业版和 Office 365 教育版订阅中。 无需额外的 Office 365 许可证。

> [!NOTE]
> 必须在来宾的家庭租户上启用团队，来宾才能以其他（资源）租户的来宾身份登录和使用团队。

如果您看到 "授权错误"，请确保阅读[Azure Active DIRECTORY B2B 授权指南](https://docs.microsoft.com/azure/active-directory/b2b/licensing-guidance)以确定授权要求以满足您的组织中的来宾访问要求。


- 来宾许可证计入邀请组织。 在计算所需的许可证数量时，请注意这一点。
- 根据您的组织统计许可证，无论受邀的来宾来自其他 Office 365 组织还是使用其个人电子邮件地址。

## <a name="support-for-b2b-user-types"></a>支持 B2B 用户类型
目前，Teams 只支持 [Azure B2B 定义的](https://docs.microsoft.com/azure/active-directory/b2b/user-properties)状态 1 和状态 2 类型来宾用户。

## <a name="related-topics"></a>相关主题

[Teams 中的来宾访问](guest-access.md)



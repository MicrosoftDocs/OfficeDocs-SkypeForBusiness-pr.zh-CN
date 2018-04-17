---
title: 登录到 Microsoft 小组
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 03/23/2018
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: ''
description: 有关通过使用现代的身份验证登录到 Microsoft 小组指导。
localization_priority: Normal
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 443f20b1ecd8295acc4f731211c69d23a79f28dd
ms.sourcegitcommit: dea27df69d948b7b9cc017b7023c4013cee8e4d1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/16/2018
---
<a name="sign-in-to-microsoft-teams"></a>登录到 Microsoft 小组
==========================

Microsoft 的小组使用现代身份验证来保持简单和安全的登录体验。

## <a name="how-modern-authentication-works"></a>现代如何验证的工作原理

现代身份验证是一个过程，它使工作组知道用户已经在其他地方，输入其凭据 （如工作电子邮件和密码），并且不应要求他们输入他们再次启动该应用程序。 经验有所不同取决于一些因素，像如果用户在使用 Windows 或 mac。 也将因您的组织是否已启用一元身份验证或多因素身份验证 (多因素身份验证通常涉及到验证凭据通过电话，提供一个唯一的代码，并输入 PIN，或显示缩略图）。 下面是每个现代的身份验证方案的简要介绍。

### <a name="windows-users"></a>Windows 用户 

- 如果用户已登录到其他 Office 应用程序通过其 Office 365 企业帐户，当他们开始他们正在采取直接到应用程序的团队。 没有必要为他们输入其凭据。

- 如果用户未登录到其他任何地方，其 Office 365 企业帐户在启动团队时，被要求提供单因素或多因素身份验证 （SFA 或 MFA），这取决于什么您的组织决定他们想要以所需要的过程。

- 如果用户已登录到加入域的计算机，在启动团队，他们可能需要经过一个身份验证步骤，具体取决于您的组织选择是否要求 MFA 或如果他们的计算机已要求 MFA 登录时。 如果他们的计算机已经要求 MFA 登录，当他们打开团队，应用程序自动启动。

### <a name="mac-users"></a>Mac 的用户 

当用户启动团队时，他们的计算机不能将他们从他们的 Office 365 企业帐户或任何其他 Office 应用程序的凭据。 相反，他们将看到一个提示，询问他们对于 SFA 或 MFA （具体取决于您的组织的设置）。 一旦用户输入其凭据，它们不需要再次提供它们。 从那一刻开始，团队自动启动时在同一台计算机上工作。

## <a name="switching-accounts-after-completing-modern-authentication"></a>在完成新型身份验证后切换帐户

如果用户正在加入域的计算机 （例如，如果其租户已经启用了 Kerberos） 上，他们不能切换用户帐户，一旦他们完成了现代的身份验证。 如果用户不使用加入域的计算机上，则可以切换帐户。

## <a name="signing-out-of-microsoft-teams-after-completing-modern-authentication"></a>现代身份验证完成后退出 Microsoft 小组

若要退出团队，用户可以单击顶部的应用程序，其个人资料图片，然后选择**退出**。他们可以应用程序图标在任务栏上，右键单击，然后选择**注销**。一旦他们已经超出团队的符号，它们需要输入其凭据再次启动应用程序。

## <a name="troubleshooting-modern-authentication"></a>故障排除的现代身份验证

现代身份验证即可供使用团队，因此如果用户都不能完成此过程，可能会出现错您的域或您的组织的 Office 365 企业帐户每个组织。 

有关详细信息，请参阅[为什么时遇到无法登录到 Microsoft 小组？](https://support.office.com/en-US/article/why-am-i-having-trouble-signing-in-to-microsoft-teams-a02f683b-61a3-4008-9447-ee60c5593b0f)。


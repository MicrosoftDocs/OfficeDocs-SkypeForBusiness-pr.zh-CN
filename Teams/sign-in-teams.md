---
title: 登录到 Microsoft 团队
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 03/23/2018
audience: Admin
ms.topic: article
ms.service: msteams
search.appverid: MET150
ms.reviewer: ''
description: 使用现代身份验证登录到 Microsoft 团队的指南。
localization_priority: Priority
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 5899d002ff6492f06b42f824e8799dfc30b9f42f
ms.sourcegitcommit: 2a6e499165424fe2d189ad140951e222c8ba9c81
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2018
ms.locfileid: "23849880"
---
<a name="sign-in-to-microsoft-teams"></a>登录到 Microsoft 团队
==========================

Microsoft 团队使用现代身份验证以保持登录体验简单和安全。

## <a name="how-modern-authentication-works"></a>如何现代验证的工作原理

现代身份验证是一个过程，可让团队知道用户已经输入其凭据 （如其工作电子邮件和密码中） 到其他位置，并且他们不应需要输入其再次启动应用程序。 体验异几个因素，如如果用户正在在 Windows 或 mac。 它还将有所不同，具体取决于您的组织是否已启用单双因素身份验证或多因素身份验证 (多因素身份验证通常需要验证凭据的电话，提供一个唯一的代码，输入 PIN，通过或演示指纹）。 以下是一个每种现代身份验证方案。

### <a name="windows-users"></a>Windows 用户 

- 如果用户具有已登录到其 Office 365 企业版帐户，通过其他 Office 应用程序启动团队时他们正在执行直线的应用程序。 则无需为他们输入其凭据。

- 如果用户未登录到其他任何位置，其 Office 365 企业版帐户启动团队时，需要提供一元或多因素身份验证 （SFA 或 MFA），具体取决于什么您的组织已决定他们希望伴有过程。

- 如果用户要登录到加入域的计算机上，启动团队，它们可能会要求穿过一个多个身份验证的步骤，具体取决于您的组织选择是否加入需要 MFA 或如果其计算机已需要 MFA 登录时。 如果其计算机已要求 MFA 登录，当其打开团队，应用程序自动启动。

### <a name="mac-users"></a>Mac 用户 

当用户启动团队时，其计算机不能以打开其 Office 365 企业版客户或任何其他 Office 应用程序从其凭据。 相反，他们将看到一个提示，询问他们 SFA 或 MFA （具体取决于组织的设置）。 一旦用户输入凭据，它们不需要再次将它们提供。 从上的点，团队自动启动时正在同一台计算机上。

## <a name="switching-accounts-after-completing-modern-authentication"></a>切换后完成现代身份验证的帐户

如果用户正在 （例如，如果其租户已启用 Kerberos） 的加入域的计算机上，他们不能在他们已完成现代身份验证之后切换用户帐户。 如果用户加入域的计算机上不工作，他们可以切换帐户。

## <a name="signing-out-of-microsoft-teams-after-completing-modern-authentication"></a>注销完成现代身份验证后的 Microsoft 团队

要注销团队，用户可以单击顶部的应用程序，其配置文件图片，然后选择**注销**。它们可以右键单击其任务栏上，在应用程序图标，然后选择**注销**。一旦他们已超出团队登录，他们需要输入其凭据重新启动应用程序。

## <a name="troubleshooting-modern-authentication"></a>疑难解答现代的身份验证

现代身份验证是适用于每个组织使用团队，因此如果用户不是能够完成此过程，可能有错与您的域或组织的 Office 365 企业版帐户。 

有关详细信息，请参阅[为什么我不能登录到 Microsoft 团队？](https://support.office.com/article/why-am-i-having-trouble-signing-in-to-microsoft-teams-a02f683b-61a3-4008-9447-ee60c5593b0f)。


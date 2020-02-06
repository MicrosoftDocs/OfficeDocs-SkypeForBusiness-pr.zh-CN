---
title: 使用新式验证登录 Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 11/15/2018
audience: Admin
ms.topic: conceptual
ms.service: msteams
search.appverid: MET150
ms.reviewer: ''
description: 如何使用新式身份验证登录到 Microsoft 团队。
localization_priority: Normal
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 9911a014fe3bd3e3ede151e2a85e8181c399e463
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41790610"
---
<a name="sign-in-to-microsoft-teams-using-modern-authentication"></a>使用新式验证登录 Microsoft Teams
==========================

Microsoft 团队使用新式身份验证来保持登录体验简单而又安全。 若要查看用户如何登录到团队，请阅读[登录团队](https://support.office.com/article/sign-in-to-teams-ea4b1443-d11b-4791-8ae1-9977e7723055)。

## <a name="how-modern-authentication-works"></a>新式身份验证的工作原理

新式验证是让团队知道用户已在其他位置输入其凭据（如工作电子邮件和密码）的过程，并且不需要再次输入它们来启动应用。 根据几个因素（如用户在 Windows 或在 Mac 上工作），体验会有所不同。 它还会根据你的组织是否已启用单因素身份验证或多重身份验证而有所不同（多重身份验证通常涉及通过电话验证凭据、提供唯一代码、输入 PIN 或演示指纹）。 下面是每个新式身份验证方案的一个断开。

### <a name="windows-users"></a>Windows 用户 

- 如果用户已通过其 Office 365 企业帐户登录到其他 Office 应用，则当用户启动团队时，他们将直接转到该应用。 无需他们输入其凭据。

- 如果用户未登录到任何其他位置的 Office 365 企业帐户，则当用户启动团队时，系统会要求他们提供单因素或多重身份验证（SFA 或 MFA），具体取决于你的组织决定需要的流程。

- 如果用户登录到加入域的计算机，则当用户启动团队时，可能会要求他们执行一个更多身份验证步骤，具体取决于你的组织选择是需要 MFA 还是计算机已要求进行 MFA 登录。 如果其计算机已要求进行 MFA 登录，则当用户打开团队时，应用会自动启动。

- 如果用户登录到加入域的计算机，并且不希望其用户名预填充到团队登录屏幕上，则管理员可以将以下 Windows 注册表设置为关闭用户名的预填充：计算机 \ HKEY_CURRENT_USER \Software\Microsoft\Office\Teams DisableUpnSuffixCheck （REG_DWORD）0x00000001 （1）

  注意：在默认情况下，跳过以 "本地" 或 "corp" 结尾的用户名的用户名预填。因此无需设置注册表项即可将其关闭。 


### <a name="mac-users"></a>Mac 用户 

用户启动团队时，其计算机将无法从其 Office 365 企业帐户或任何其他 Office 应用程序中提取其凭据。 他们将看到一条提示，要求他们提供 SFA 或 MFA （具体取决于您的组织的设置）。 用户输入其凭据后，不需要再次提供它们。 从此时起，团队会在它们在同一台计算机上工作时自动启动。

## <a name="switching-accounts-after-completing-modern-authentication"></a>完成新式身份验证后切换帐户

如果用户正在使用加入域的计算机（例如，如果其租户已启用 Kerberos），则他们在完成新式身份验证后无法切换用户帐户。 如果用户不在已加入域的计算机上工作，则他们可以切换帐户。

## <a name="signing-out-of-microsoft-teams-after-completing-modern-authentication"></a>在完成新式身份验证后注销 Microsoft 团队
若要注销团队，用户可以单击应用顶部的个人资料图片，然后选择 "**注销**"。他们还可以右键单击任务栏中的应用程序图标，然后选择 "**注销**"。注销团队后，他们需要再次输入其凭据以启动该应用。

## <a name="urls-and-ip-address-ranges"></a>Url 和 IP 地址范围
团队需要连接到 Internet。 若要了解在 Office 365 计划、政府和其他云中使用团队的客户应可访问的终结点，请阅读[此处的指南](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges)。 此外，你还需要允许访问https://ssl.gstatic.com。

## <a name="troubleshooting-modern-authentication"></a>新式验证疑难解答

现代身份验证适用于使用团队的每个组织，因此，如果用户无法完成此过程，则您的域或组织的 Office 365 企业帐户可能有问题。 

有关详细信息，请参阅[为什么我在登录 Microsoft 团队时遇到问题？](https://support.office.com/article/why-am-i-having-trouble-signing-in-to-microsoft-teams-a02f683b-61a3-4008-9447-ee60c5593b0f)。


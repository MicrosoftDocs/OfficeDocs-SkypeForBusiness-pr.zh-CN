---
title: 使用新式验证登录 Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
search.appverid: MET150
ms.reviewer: ''
description: 如何使用新式验证登录 Microsoft Teams。
localization_priority: Priority
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.openlocfilehash: 7bb74338a3e46bb4e3a65fcbf2a69d56558dad61
ms.sourcegitcommit: f859843003b34feab18a3d2df34fdbb9858e7148
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/11/2020
ms.locfileid: "41889435"
---
<a name="sign-in-to-microsoft-teams-using-modern-authentication"></a>使用新式验证登录 Microsoft Teams
==========================

Microsoft Teams 使用新式验证保持登录体验简单而安全。 若要了解用户如何登录 Teams，请阅读[登录 Teams](https://support.office.com/article/sign-in-to-teams-ea4b1443-d11b-4791-8ae1-9977e7723055)。

## <a name="how-modern-authentication-works"></a>新式验证的工作原理

新式验证是一种使 Teams 知道用户已在其他位置输入凭据（如工作电子邮件和密码）而不再需要再次输入凭据即可启动应用的过程。 体验将因几个因素（如用户在 Windows 上还是在 Mac 上工作）而异。 具体将取决于你的组织启用了单重身份验证还是多重身份验证（多重身份验证通常涉及通过手机验证凭据、提供唯一代码、输入 PIN 或提供指纹）。 下面是每个新式身份验证应用场景的描述。

### <a name="windows-users"></a>Windows 用户 

- 如果用户已通过其 Office 365 企业版帐户登录到其他 Office 应用，则当他们启动 Teams 时，会直接转到该应用。 他们无需输入凭据。

- 如果用户未在任何其他位置登录其 Office 365 企业版帐户，则当他们启动 Teams 时，系统会要求他们提供单重或多重身份验证（SFA 或 MFA），具体验证方式取决于你的组织已决定采用的必要验证过程。

- 如果用户登录到了加入域的计算机，则当他们启动 Teams 时，系统可能会要求他们多执行一个身份验证步骤，具体取决于你的组织选择了需要 MFA，还是用户的计算机已经要求进行 MFA 登录。 如果用户的计算机已经要求进行 MFA 登录，则当他们打开 Teams 时，该应用会自动启动。

- 如果用户登录到了加入域的计算机，并且你不希望他们的用户名预填充在 Teams 登录屏幕上，则管理员可以设置以下 Windows 注册表来关闭用户名预填充 (UPN)：

  Computer\HKEY_CURRENT_USER\Software\Microsoft\Office\Teams<br/>
  SkipUpnPrefill(REG_DWORD)<br/>
  0x00000001 (1)

    > [!NOTE]
    > 默认情况下会忽略以“.local”或“.corp”结尾的用户名的用户名预填充，因此无需设置注册表项来关闭该功能。 


### <a name="mac-users"></a>Mac 用户 

用户启动 Teams 后，其计算机将无法从其 Office 365 企业版帐户或任何其他 Office 应用程序中拉取凭据。 事实上，他们将看到一条提示，要求他们进行 SFA 或 MFA 验证（具体取决于组织的设置）。 用户输入其凭据后，他们无需再次提供凭据。 此后，只要是在同一台计算机上工作，Teams 都将自动启动。

## <a name="switching-accounts-after-completing-modern-authentication"></a>完成新式验证后切换帐户

如果用户在加入域的计算机上工作（例如，如果他们的租户已启用 Kerberos），则他们在完成新式验证后无法切换用户帐户。 如果用户不在加入域的计算机上工作，则可以切换帐户。

## <a name="signing-out-of-teams-after-completing-modern-authentication"></a>完成新式验证后注销 Teams
若要注销 Teams，用户可以单击应用顶部的个人资料图片，然后选择“**注销**”。他们还可以右键单击任务栏中的应用图标，然后选择“**注销**”。注销 Teams 后，他们需要再次输入凭据才能启动该应用。

## <a name="urls-and-ip-address-ranges"></a>URL 和 IP 地址范围
Teams 需要连接到 Internet。 若要了解在 Office 365 计划、政府版和其他云中使用 Teams 的客户应该可以访问的终结点，请阅读 [Office 365 URL 和 IP 地址范围](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges)。 

> [!IMPORTANT]
> 目前，Teams 要求所有用户都能访问（TCP 端口 443）Google ssl.gstatic.com 服务 (https://ssl.gstatic.com)；即使你不使用 Gstatic，也是如此。 Teams 将很快取消此要求（2020 年初），届时我们将相应地更新此文章。

## <a name="troubleshooting-modern-authentication"></a>新式验证疑难解答

使用 Teams 的每个组织均可使用新式验证，因此如果用户无法完成该过程，则你的域或组织的 Office 365 企业版帐户可能存在问题。 

有关详细信息，请参阅[为什么我无法登录 Microsoft Teams？](https://support.office.com/article/why-am-i-having-trouble-signing-in-to-microsoft-teams-a02f683b-61a3-4008-9447-ee60c5593b0f)


---
title: 用于更安全消息传递的 Teams 安全最佳做法
author: MSFTTracyP
ms.author: tracyp
manager: dansimp
ms.date: 11/10/2021
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: pawa
description: 本文是有关如何安全使用 Teams 的快速参考，它是一般安全最佳做法的入门读物，也是培训用户安全信息的提示。
ms.localizationpriority: high
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- remotework
ms.custom:
- Security
appliesto:
- Microsoft Teams
ms.openlocfilehash: 61ba1607f2999ef56c3176d4ba8ed0aaebb82e50
ms.sourcegitcommit: 115e44f33fc7993f6eb1bc781f83eb02a506e29b
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/11/2021
ms.locfileid: "60909675"
---
# <a name="security-best-practices-for-microsoft-teams"></a>Microsoft Teams 的安全最佳做法

通过即时通讯和视频会议进行协作，使许多行业和学校在大流行病期间继续开展工作。 然而，如此大规模的在线实时协作也伴随着必须解决的 *风险*。 否则，不良参与者将利用工作和生活中的这种变化，进行 **网络钓鱼** 和 **垃圾邮件** 的宣传。 本文中的编号参考列表作为使用 Teams 给别人发信息时的一般安全入门知识，是对 Teams 新手或任何即时通讯安全的人的培训指导。

存在于电子邮件中的网络钓鱼风险同样存在于即时通讯和协作应用程序中，因此应采用同样的用户意识和指导来保护 Teams 用户。

在用户层面，有些措施可以很简单，并且用户应感到有权依赖它们。 用户不应单击以打开来自任何他们不认识的人或他们无法核实身份的人的链接，正如 [保护自己免受网络钓鱼](https://support.microsoft.com/en-us/windows/protect-yourself-from-phishing-0c7ea947-ba98-3bd9-7184-430e1f860a44) 一文所述。 为了防范外部攻击，租户管理员可以禁用或关闭企业联合身份验证以及 Teams for Life (TFL) 和 Skype 互操作性，关于 [管理外部访问 (联盟) - Microsoft Teams | Microsoft Docs](/microsoftteams/manage-external-access)。

Teams 协作功能集允许消息传送、文件协作、会议、白板以及许多其他连接机会。 这些功能适用于 Teams for Enterprise、Teams for Life、Skype、Skype for Business、Azure Communication Services (ACS) 等。 这也意味着有必要跨这些功能保护自己、对等方和客户。 在这里，应该为每个用户提供最安全的决策权限，以便他们自己、对等方和客户做出最安全的决策。

## <a name="just-as-with-email-online-safety-must-be-practiced-in-microsoft-teams-messaging"></a>与电子邮件一样，必须在 Microsoft Teams 消息传递中实施在线安全

在 Teams 中工作时，标准安全措施应已成习惯。

1. 请对来自组织外部的联系人和会议请求保持警惕。 陌生人可能是善意的。 而有些人可能暗地里有恶意。
2. 如果无法识别发件人，可以检查公司的已知全局地址列表中是否有其标识，并将无法验证的任何通信升级到更高级别进行处理。 如有疑问，请勿与未知和未经验证的用户交互。
3. 如果收到来自未知人员的链接或文件，请不要单击它。 同样，请为你自己的安全、其他用户以及客户的安全提供最佳判断。
4. 如果单击的链接导航将你转到阻止你导航的安全链接页上，请不要尝试绕过该页面 (对于任何可能以红色结尾、阻止安全附件页面的单击附件也是如此)。 如果你知道并信任目标站点，请将问题报告给 Microsoft 以及将你定向到其中的任何人。 但导致登陆阻塞页的原因有很多，应考虑使用红色标志，而不是绕行导航。
5. 切勿向任何未经请求的请求提供个人信息。 这也对个人安全存在风险。 攻击者可以利用你的例如生日这样简单的详细信息。
6. 扫描链接以查找拼写不正确、添加的数字或奇异字符。 你可能需要链接到 `www.litware.com/strategies/Metricsbreakout.xlsx` 但发现地址类似于 `www.litwre.com`、`www.litwarecom.com`，甚至`www.litwαre.com`。 如果无法识别链接，则十分可疑。 该地址 `www.litware.com` 与 `www.litware2021.com` 不同。

请务必保持你的警觉，而不要轻视你的安全性，以及你轻松使用或授予的那些人员的安全性。 作为单个用户，你应始终感到有权在信任之前通过验证来保护自己以及你的同行和客户。

最后，也必须认识到每个人都会犯错。 例如，用户在匆忙时或疲惫时可能容易点击。 管理员应确保组织中的用户清楚地知道要将问题链接单击和其他安全事件上报到的资源，以便在发生错误时，用户有追索权，并可以采取进一步的安全操作。

> [!TIP]
> 检查任何不确定的联系人的资料卡，特别是如果电子邮件是在公司以外 (例如，如果你的组织不是 *Litware*，则应检查以 *@litware.com* 结尾的账户)。 用户可以通过检查档案卡上的 **(GUEST)** 来确认他们不认识的人是否是会议的欢迎来宾。 明确邀请来宾参与。
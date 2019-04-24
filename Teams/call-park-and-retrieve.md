---
title: Microsoft Teams 中的呼叫寄存和取回
ms.author: lolaj
author: LolaJacobsen
manager: serdars
ms.date: 04/12/2019
ms.reviewer: srividhc
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- M365-voice
ms.audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Phone System
description: 使用呼叫寄存和取回呼叫置于保持状态，云中团队服务中。
ms.openlocfilehash: 798e53ef9a0638be659da8567419b7bd3d3c3555
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32211835"
---
# <a name="call-park-and-retrieve-in-microsoft-teams"></a>Microsoft Teams 中的呼叫寄存和取回

呼叫寄存和取回是一种功能，允许用户将呼叫置于保留在云中团队服务中。 驻留呼叫后，该服务将生成一个唯一的代码调用检索。 寄存呼叫或其他人的用户然后可以使用该代码和支持的应用程序或设备取回呼叫。 

下面是一些使用呼叫寄存的常见方案： 

- 前台接待员 parks 呼叫的人在执行出厂中工作。 接待员然后宣布呼叫和代码编号，通过公共地址系统。 被叫的用户可以拿起在工厂团队电话，然后输入代码以取回呼叫。
- 用户 parks 移动设备上的呼叫，因为设备电池不足电源。 然后，用户可以输入代码以从团队桌面电话取回该呼叫。
- 支持代表性公园客户呼叫和专家取回该呼叫并帮助客户团队通道上发送通知。 专家进入团队客户端取回呼叫中的代码

> [!IMPORTANT]
> 此功能才可用在仅团队部署模式下。 有关团队部署模式的详细信息，请参阅[了解 Microsoft 团队和 Skype 的业务共存及互操作性](teams-and-skypeforbusiness-coexistence-and-interoperability.md)

## <a name="license-required"></a>所需的许可证

若要寄存并取回呼叫，用户必须是企业语音的用户和管理员必须授予该用户的呼叫寄存策略。 有关许可模型的详细信息，请参阅[Office 365 许可的 Microsoft 团队](office-365-licensing.md)。

## <a name="call-park-and-retrieve-feature-availability"></a>呼叫驻留和检索功能可用性

呼叫寄存和取回是当前支持以下客户端和设备。 （支持在仅工作组模式中，使用或不 PSTN 连接。）

| 功能 | 团队桌面 | 团队 Mac 应用程序 | 工作组 Web 应用程序 （边缘） |团队移动 iOS/Android 应用程序 | 团队 IP 电话 | Skype 业务 IP 电话 |
|------------|---------------|---------------|----------------------|-----------------------------|----------------|-----------------------------|
| 驻留呼叫 | 是 | 是 | 是 | 是 | 即将提供| 否 |
| 取回驻留的呼叫 | 是 | 是 | 是 | 是 | 即将提供| 否 |
| 返回未检索的电话铃声 | 是 | 是 | 是 | 是 | 即将提供| 否 |

## <a name="configuring-call-park-and-retrieve"></a>配置呼叫寄存和取回

您必须是管理员能够配置呼叫寄存和取回，和默认情况下禁用此功能。 您可以为用户启用它，并创建使用呼叫寄存策略的用户组。 时为一组用户应用同一策略，他们可以寄存并取回呼叫之间本身。 若要配置呼叫寄存的用户和用户组创建呼叫寄存，按照下面的[分配呼叫寄存策略](#assign-a-call-park-policy)过程。

有关如何使用呼叫寄存和检索功能的信息，请参阅[寄存团队中的呼叫](https://support.office.com/article/park-a-call-in-teams-8538c063-d676-4e9a-8045-fc3b7299bb2f)。

### <a name="enable-a-call-park-policy"></a>启用呼叫寄存策略

请按照下列步骤来启用呼叫寄存策略：

1. 转到**Microsoft 团队管理中心** > **语音** > **呼叫寄存策略**。
2. 选择**新策略**。
3. 为策略指定名称，然后切换到**上**的**允许呼叫寄存**。
4. 选择**保存**。

### <a name="assign-a-call-park-policy"></a>分配呼叫寄存策略

按照以下步骤为一个或多个用户分配呼叫寄存策略：

1. 转到**Microsoft 团队管理中心** > **语音** > **呼叫寄存策略**。
2. 通过单击左侧的策略名称选择的策略。
3. 选择**管理用户**。
4. 在**管理用户**窗格中，搜索用户按显示名称或用户名称，选择名称，然后选择**添加**。 要添加的每个用户重复此步骤。
5. 添加完用户后，选择**保存**。
 
### <a name="configure-call-park-and-retrieve-with-powershell"></a>配置呼叫寄存和检索与 PowerShell

使用[新建 CsTeamsCallParkPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamscallparkpolicy?view=skype-ps) PowerShell cmdlet 创建呼叫寄存策略。

使用[授予 CsTeamsCallParkPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamscallparkpolicy?view=skype-ps) PowerShell cmdlet 授予的呼叫寄存策略。

您可以使用[集 CsTeamsCallParkPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamscallparkpolicy?view=skype-ps) ，如下所示更改默认设置：

`Set-CsTeamsCallParkPolicy -Identity Global -AllowCallPark $true`


## <a name="troubleshooting"></a>疑难解答

如果用户不能看到寄存或检索按钮： 

- 检查用户具有启用呼叫寄存策略。 

如果用户尝试检索呼叫，并且不成功，检查以下项目：

- 验证用户使用团队客户端或工作组启用设备/电话
- 分组 – 是呼叫寄存组的成员的用户？
- 岛模式 – 呼叫寄存和取回是团队岛模式中不可用。
- 已检索或终止呼叫。

## <a name="more-information"></a>更多信息

[寄存呼叫的团队](https://support.office.com/article/park-a-call-in-teams-8538c063-d676-4e9a-8045-fc3b7299bb2f)。
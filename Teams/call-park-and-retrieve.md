---
title: 呼叫驻留和检索中的 Microsoft 团队
ms.author: lolaj
author: lolaj
manager: serdars
ms.date: 12/13/2018
ms.reviewer: srividhc
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service:
- msteams
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
ms.audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Phone System
description: 使用呼叫寄存和取回呼叫置于保持状态，云中团队服务中。
ms.openlocfilehash: 02ec2b3af52cac65f82f5f0f0fc2b4b54ae61369
ms.sourcegitcommit: 5f7e078125f810a9e9a89052854ef63916afe7d3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/14/2018
ms.locfileid: "27283156"
---
# <a name="call-park-and-retrieve-in-microsoft-teams"></a>呼叫驻留和检索中的 Microsoft 团队

呼叫寄存和取回是一种功能，允许用户将呼叫置于保留在云中团队服务中。 驻留呼叫后，该服务将生成一个唯一的代码调用检索。 寄存呼叫或其他人的用户然后可以使用该代码和支持的应用程序或设备取回呼叫。 

下面是一些使用呼叫寄存的常见方案： 

- 前台接待员 parks 呼叫的人在执行出厂中工作。 接待员然后宣布呼叫和代码编号，通过公共地址系统。 被叫的用户可以拿起在工厂团队电话，然后输入代码以取回呼叫。
- 用户 parks 移动设备上的呼叫，因为设备电池不足电源。 然后，用户可以输入，然后代码从团队桌面电话取回该呼叫。
- 支持代表性公园客户呼叫和专家取回该呼叫并帮助客户团队通道上发送通知。 专家进入团队客户端取回呼叫中的代码

> [!IMPORTANT]
> 此功能才可用在仅团队部署模式下。 团队部署模式的详细信息，请参阅[了解 Microsoft 团队和 Skype 的业务共存及互操作性](teams-and-skypeforbusiness-coexistence-and-interoperability.md)

## <a name="license-required"></a>所需的许可证

若要寄存并取回呼叫，用户必须是企业语音的用户和管理员必须授予该用户的呼叫寄存策略。 有关许可模型的其他详细信息，请参阅[Office 365 许可的 Microsoft 团队](office-365-licensing.md)。

## <a name="call-park-and-retrieve-feature-availability"></a>呼叫驻留和检索功能可用性

呼叫寄存和取回是当前支持以下客户端和设备。 （支持在仅工作组模式中，使用或不 PSTN 连接。）

| 功能 | 团队桌面 | 团队 Mac 应用程序 | 工作组 Web 应用程序 （边缘） |团队移动 iOS/Android 应用程序 | 团队 IP 电话 | Skype 业务 IP 电话 |
|------------|---------------|---------------|----------------------|-----------------------------|----------------|-----------------------------|
| 驻留呼叫 | 是 | 是 | 是 | 即将提供 | 即将提供| 否 |
| 取回驻留的呼叫 | 是 | 是 | 是 | 即将提供 | 即将提供| 否 |
| 返回未检索到的呼叫拨打 | 是 | 是 | 是 | 即将提供 | 即将提供| 否 |

## <a name="configuring-call-park-and-retrieve"></a>配置呼叫寄存和取回

您必须是管理员能够配置呼叫寄存和取回，和默认情况下禁用此功能。 您可以为用户启用它，并创建使用呼叫寄存策略的用户组。 时为一组用户应用同一策略，他们将能够寄存和取回呼叫之间本身。 若要配置为用户的呼叫寄存和创建呼叫寄存用户组，请按照下面的过程。

有关如何使用呼叫寄存和检索功能的信息，请参阅[寄存团队中的呼叫](https://support.office.com/article/park-a-call-in-teams-8538c063-d676-4e9a-8045-fc3b7299bb2f)。

### <a name="configure-call-park-and-retrieve-with-powershell"></a>配置呼叫寄存和检索与 PowerShell

使用[新建 CsTeamsCallParkPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamscallparkpolicy?view=skype-ps) PowerShell cmdlet 创建呼叫寄存策略。

使用[授予 CsTeamsCallParkPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamscallparkpolicy?view=skype-ps) PowerShell cmdlet 授予的呼叫寄存策略。

## <a name="troubleshooting"></a>故障排除

如果用户不能看到寄存或检索按钮： 

- 检查用户具有启用呼叫寄存策略。 

如果用户尝试检索呼叫，并且不成功，检查以下项目：

- 验证用户使用团队客户端或工作组启用设备/电话
- 分组 – 是呼叫寄存组的成员的用户？
- 岛模式 – 呼叫寄存和取回是团队岛模式中不可用。
- 已检索或终止呼叫。

## <a name="more-information"></a>更多信息

[寄存呼叫的团队](https://support.office.com/article/park-a-call-in-teams-8538c063-d676-4e9a-8045-fc3b7299bb2f)。
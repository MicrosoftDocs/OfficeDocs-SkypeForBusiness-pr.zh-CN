---
title: 使用 Microsoft Teams 支持远程工作者
author: LolaJacobsen
ms.author: lolaj
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.collection:
- M365-collaboration
ms.reviewer: dansteve
localization_priority: Priority
search.appverid: MET150
description: 使用本指南可帮助组织中的远程工作者使用 Microsoft Teams 高效工作，尤其是当他们在家办公（WFH）来应对新型冠状病毒肺炎的爆发。
appliesto:
- Microsoft Teams
ms.openlocfilehash: 4fbdb875896ca07402d699f1ca2a28770cb46ee2
ms.sourcegitcommit: ae65fb089d98665c4b26e0345bb96241fb893f0b
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/29/2020
ms.locfileid: "42342899"
---
# <a name="support-remote-workers-using-microsoft-teams"></a>使用 Microsoft Teams 支持远程工作者

按照本文中的最佳做法为远程工作或在家办公的用户提供支持。

## <a name="technical"></a>技术

1.  请确保[已为所有人启用 Teams](assign-teams-licenses.md)
    
      - 请查看 [Teams 探索](teams-exploratory.md) 或 [Teams 免费版](https://support.office.com/article/Welcome-to-Microsoft-Teams-free-6d79a648-6913-4696-9237-ed13de64ae3c)，将 Teams 设为可供公司中的每个人使用。

      - 远程办公员工更大程度地依赖于会议和音频会议。 如果尚未推出这些工作负载，请查看“[在 Teams 中进行会议](deploy-meetings-microsoft-teams-landing-page.md)”。

2.  告知用户有关 Teams 的信息。 下载[Teams 客户成功套件](https://download.microsoft.com/download/A/E/9/AE984CD4-CF4B-41E7-9ABD-6735E3F01897/MicrosoftTeamsCustomerSuccessKit.zip)以获取演示文稿、示例电子邮件、海报和入门指南。


5.  确保员工可充分访问 Internet 并具有足够的带宽来使用 Teams。 使用“[为 Teams 准备组织的网络](prepare-network.md)”中的指南，了解如何进行此操作。
    - 带宽受限将会影响 Teams 会议的音质。 为确保在低带宽条件下获得最佳会议体验，鼓励用户限制视频，并使用 PSTN 进行通话和会议音频。 

    - 如果需要有关解决或修复通话或会议质量方面问题的帮助，请遵循本文底部“[已知问题：拨入 Skype for Business 或 Teams 会议 ID](#known-issue-dialing-into-skype-for-business-or-teams-conference-ids)”中的指南。

2.  [发送培训链接](enduser-training.md)，帮助你的员工充分利用 Teams。
    
3. 阅读有关远程工作的新内容并与用户共享：
        
      - Teams 博客（2020 年 2 月 28 日）： [使用 Microsoft Teams 在家工作的 4 个提示](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/4-tips-for-working-from-home-with-microsoft-teams-by-lola/ba-p/1202083)

      - [使用 Office 365 进行协作](https://support.office.com/article/Collaborate-with-Office-365-ac05a41e-0b49-4420-9ebc-190ee4e744f4)

      - [使用 Teams 和 Office 365 远程工作](https://support.microsoft.com/help/4549995/working-remotely-with-teams-and-office-365)

3.  鼓励所有人[安装](get-clients.md#mobile-clients)和使用移动应用：[iOS 版](https://go.microsoft.com/fwlink/?LinkId=835758)   [Android 版](https://go.microsoft.com/fwlink/p/?linkid=2102168)

    > [!NOTE]
    > 如果你在中国，请转到此处[获取适用于中国的 Teams for Android](get-teams-android-in-china.md)

4.  增设[支持人员](troubleshoot-installation.md)来处理用户查询。


## <a name="communications"></a>通讯

使用 Teams 与员工保持联系：
- [组织范围的团队](create-an-org-wide-team.md)和[Company Communicator](https://docs.microsoft.com/microsoftteams/platform/samples/app-templates#company-communicator)应用模板
    
- 发送有关组织的在家办公和健康安全策略信息。
    
- 通过[实时事件](teams-live-events/what-are-teams-live-events.md)进行全公司会议和跟进服务。 对于任何超过 250 个参与者的会议，请将其设置为实时事件。 

## <a name="personal-considerations"></a>个人注意事项

下面的一些提示可助你成功在家办公：

- 拥有具有良好照明和合理人体工学性能的实际工作空间。

- 设定明确的工作时间和工作任务，使用 Teams [当前状态](https://support.office.com/article/change-your-status-in-teams-ce36ed14-6bc9-4775-a33e-6629ba4ff78e)指示离开时间。

- 有意识地“往返”在家工作地点；不要将在家工作等同于在家就是工作。

- 定时起床和休息。 可以散步、舒展筋骨、给自己泡杯茶。

## <a name="known-issue-dialing-into-skype-for-business-or-teams-conference-ids"></a>已知问题：拨入 Skype for Business 或 Teams 会议 ID

下面是 2020 年 2 月 7 日消息中心帖子的摘要(MC203397)：

Microsoft 意识到，中国地区的部分用户在拨入到 Skype for Business 或 Teams 会议 ID 时会遇到问题。 多数情况下，这些问题是我们控制系统之外的问题。 通常，问题与本地移动设备和电话运营商有关。 

如果遇到音频会议问题，建议执行以下操作：

- 要求主叫方或会议组织者呼叫你的 PSTN 或手机号码
- 使用 VoIP，从桌面或移动客户端加入通话或会议

如果需要记录支持工单，请包含下列内容：
    
- 准确的通话时间
- 已拨打的会议网桥号码
- 主叫方电话网络
- 主叫方电话号码

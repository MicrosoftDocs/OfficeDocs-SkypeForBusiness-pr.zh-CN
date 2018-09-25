---
title: 为组织设置通信点数
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mikedav
ms.topic: article
ms.assetid: bb9f2a8d-f5be-41ed-9d19-25dea5ca9f52
ms.tgt.pltfrm: cloud
ms.service:
- skype-for-business-online
- msteams
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Licensing
description: 'Learn how to set up communication credits (PSTN Consumption) billing licenses for your users and organization. '
ms.openlocfilehash: f82788d34e492b6dd3fe54c60168b8d83b3c09e2
ms.sourcegitcommit: 9acf2f80cbd55ba2ff6aab034757cc053287485f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/25/2018
ms.locfileid: "25018006"
---
# <a name="set-up-communications-credits-for-your-organization"></a>为组织设置通信点数

您需要设置通信点数，如果您想要使用 Skype for Business 和 Microsoft Teams 的免费电话号码。 此外，我们建议您设置 Communications 字幕式调用计划 （国内或国际） 和音频会议用户需要拨出**任何目标**的能力。 多个国家/地区内包括在内，但某些目标不能包含在您调用规划或音频会议的订阅。 如果您不会设置 Communications 字幕式帐单且将**Communications 字幕式**许可证分配给用户，并且您运行出分钟，以便您的组织 （具体取决于您调用计划或音频会议中计划国家/地区），这些用户将无法发起呼叫或从音频会议拨出。 您可以获取详细信息，请通过读取资金数量，包括建议[Communications 字幕式是什么？](what-are-communications-credits.md)
  
> [!NOTE]
> 若要找出它的费用， [请参阅下面的价格](https://go.microsoft.com/fwlink/p/?LinkId=799523 )  。 
  
## <a name="step-1-assign-an-audio-conferencing-and-calling-plan-license-to-your-users"></a>步骤 1： 向用户分配音频会议和调用规划许可证

当您注册时，您将获取一定数量的分钟，具体取决于您的国家/地区。 您可以看到您将收到搜索的国家或地区的分钟数[此处](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)。 使用这些分钟后，呼叫将中断。 若要防止这种情况，您需要设置 Communications 字幕式。
  
这样，**您需要为音频会议或电话系统许可证分配**用户。
  
- 将**音频会议**许可证分配给用户。 请参阅[业务和 Microsoft 团队许可证分配 Skype](/SkypeForBusiness/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses)。
    
    指定此许可证后，您需要设置音频会议。 有关分步说明，请参阅[尝试或购买 Office 365 中的音频会议](/SkypeForBusiness/audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365)。
    
- 将**电话系统**和国内或国内和国际呼叫规划许可证分配给用户。 请参阅[业务和 Microsoft 团队许可证分配 Skype](/SkypeForBusiness/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses)。
    
    > [!NOTE]
    > 尽管不需要的通信字幕式，则仍需还分配**国内调用规划**或**国内和国际呼叫规划**许可证。
  
    分配这些许可证后，你需要获得贵组织的电话号码，然后将这些号码分配给组织中的人员。 有关分步说明，请参阅[Set up 调用计划](set-up-calling-plans.md)。
    
有关详细信息，请参阅[业务和 Microsoft 团队授权加载项的 Skype](/SkypeForBusiness/skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing)
  
## <a name="step-2-set-up-communications-credits-for-your-organization"></a>步骤 2： 为您的组织的通信字幕式设置

1. 使用你的工作或学校帐户登录 Office 365。
    
2. 在 Office 365 管理中心的左侧导航窗格中，转到**帐单** > **订阅** > **添加订阅**。

3. 展开**加载项订阅**，然后选择**Communications 字幕式** > **立即购买**。
    
4. 在**Communications 字幕式**订阅页中，填写您的信息，然后单击**下一步**:
    
  - **添加资金**输入要添加到您的帐户的金额。 如果您不启用自动充电，都用完这些资金，调用使用 Communications 字幕式启用的功能将会中断 （如入站免费电话服务）。 若要避免无需手动补充 Communications 字幕式平衡每次您平衡达到 0 （零），我们建议您启用自动充电功能。
    
  - **自动充值**：启用自动充值将在余额低于你设置的阈值时自动补充你的帐户余额。
    
    建议使用**自动充电**设置以避免服务的任何中断应 Communications 字幕式平衡达到 0 （零）。 充电事务成功，充电事务失败 （如信用卡过期），以及 Communications 字幕式平衡达到 0 （零） 时，您将会发送电子邮件。
    
  - **为充电量**在要添加到您的帐户下, 触发量到达的**为充电与**框中输入的金额。
    
  - **触发量**向*触发器*自动充电**平衡低于时**将使用的框中输入的金额。 一旦您平衡低于这个值，将自动将充电量添加到您的帐户。

      > [!NOTE]
    > 资金将仅可用于使用服务时，microsoft Communications 字幕式发布率。 自购买之日起的 12 个月内未使用的任何资金将过期并丢失。 
    
5. 输入您的付款信息并单击 **下订单** 。
    >[!IMPORTANT]
    >如果您是批量授权客户，则可以选择您的企业协议编号进行付款。 如果您有多个企业协议编号，您将能够选择要用于付款的企业协议。 您还将获得一个机会，指定要与企业协议编号关联的采购订单编号 （如果适用）。
    
每个组织会调用规划卷和要考虑的其他用法。 You will need to get this type of usage data from your current service provider. 已使用 Skype 业务 online 已作为其服务提供商的组织可以通过查看在**业务管理中心的 Skype**获取使用率数据 > **报告** > **PSTN 用法详细信息**报告。
  
设置 Communications 字幕式时，需要调查呼叫使用为您的组织，以确定您将需要置于的金额。 你可以通过查看" **PSTN 使用详细信息**"报告获取呼叫使用信息。 此报告可以将呼叫数据记录导出到 Excel 中，如果您想要导出的数据存储或创建自定义报告。 若要查看用法，请参阅[Skype 的业务 PSTN 使用率报告](/SkypeForBusiness/skype-for-business-online-reporting/pstn-usage-report)
  
## <a name="step-3-assign-a-communications-credits-license-to-users"></a>步骤 3： 将 Communications 字幕式许可证分配给用户

1. 使用你的工作或学校帐户登录 Office 365。
    
2. 在 Office 365 管理中心的左侧导航窗格中，转到**用户** > **活动用户**，然后从列表中选择一个用户。
    
3. 在"操作"窗格中的" **产品许可证**"下，单击" **编辑**"。
    
4. 在**产品许可证**页上，切换到**在上**分配此许可证， **Communications 字幕式**，然后单击**保存**。
    
    > [!NOTE]
    > 即使已经分配一个**企业 E5**许可证的用户，仍建议您这样做。
  
## <a name="want-to-know-about-plans-and-pricing"></a>想要了解计划和定价？

您可以看到计划和定价通过访问以下链接之一：
  
- [通话套餐](https://go.microsoft.com/fwlink/?LinkId=799761 )
    
- [音频会议计划](https://go.microsoft.com/fwlink/?LinkId=799762 )
    
- [电话系统计划](https://go.microsoft.com/fwlink/?LinkId=799763)
    
您还可以参见信息通过[登录到 Office 365 管理中心](https://portal.office.com/adminportal/home?add=sub&amp;adminportal=1#/catalog)，转到**帐单** > **订阅** > **添加订阅**。
  
若要查看使用许可证或许可证需要为每个功能的表，请参阅[业务和 Microsoft 团队授权加载项的 Skype](/SkypeForBusiness/skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing)。
  
## <a name="related-topics"></a>相关主题

- [设置 Skype for Business Online](/SkypeForBusiness/set-up-skype-for-business-online/set-up-skype-for-business-online)
    
- [设置电话系统语音邮件 - 管理员帮助](set-up-phone-system-voicemail.md)
    
- [设置通话套餐](set-up-calling-plans.md) 和 [Office 365 的通话套餐](calling-plans-for-office-365.md)
    
- [存入资金和管理通信点数](add-funds-and-manage-communications-credits.md)
    
- [配置云连接器](https://technet.microsoft.com/library/mt605228.aspx)和[下载云连接器](https://aka.ms/CloudConnectorInstaller)

  
 
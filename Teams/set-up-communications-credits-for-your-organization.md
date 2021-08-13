---
title: 设置组织的通信点数
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: mikedav
ms.topic: article
ms.assetid: bb9f2a8d-f5be-41ed-9d19-25dea5ca9f52
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- m365initiative-voice
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Licensing
- seo-marvel-apr2020
description: 'Learn how to set up communication credits (PSTN Consumption) billing licenses for your users and organization. '
ms.openlocfilehash: 3acb2dbb4029e7b530d556f6fa63bbdb9b329963160bd27113ea10bbd9e219d7
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2021
ms.locfileid: "54348627"
---
# <a name="set-up-communications-credits-for-your-organization"></a>设置组织的通信点数

您需要设置通信点数，如果您想要使用 Skype for Business 和 Microsoft Teams 的免费电话号码。 此外，我们建议你为需要拨出到任何目的地的呼叫计划 (或国际) 和音频会议用户设置通信 **积分**。 包括许多国家/地区，但某些目的地可能不包含在呼叫计划或音频会议订阅中。 如果未设置通信信用额度计费并将通信信用额度许可证分配给用户，并且你的组织 (根据你的呼叫计划或音频会议计划在你的国家/地区) 中用完了分钟数，则这些用户将无法进行呼叫或从音频会议会议拨出。 可以通过阅读什么是通信信用额度，获取更多信息，包括建议 [的金额？](what-are-communications-credits.md)
  
> [!NOTE]
> 若要找出它的费用， [请参阅下面的价格](https://go.microsoft.com/fwlink/p/?LinkId=799523 )  。 
  
## <a name="step-1-assign-an-audio-conferencing-or-calling-plan-license-to-your-users"></a>步骤 1：为用户分配音频会议或通话计划许可证

注册时，你获得特定分钟数，具体取决于你的国家/地区。 您可以在"音频会议"和"呼叫计划"[](./country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md#select-your-country-or-region-to-see-whats-available-for-your-organization)的"国家/地区可用性"列表中搜索您的国家/地区，以查看您将获得的分钟数。 使用这些分钟数后，通话将断开连接。 若要防止这种情况发生，需要设置通信信用额度。
  
为此，**你需要为用户分配** 音频电话系统许可证。
  
- 为 **用户分配** 音频会议许可证。 请参阅[分配Microsoft Teams附加许可证。](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md)
    
    分配此许可证后，需要设置音频会议。 有关分步说明，请参阅试用或购买音频会议（Microsoft 365[或Office 365）。](try-or-purchase-audio-conferencing-in-office-365-for-teams.md)
    
- 为 **电话系统** 分配国内 **或** 国内和国际呼叫计划许可证。 请参阅[分配Microsoft Teams附加许可证。](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md)
    
    > [!NOTE]
    > 虽然通信积分不需要，但您仍然需要分配国内呼叫计划或 **国内和国际呼叫计划** 许可证。 
  
    分配这些许可证后，你需要获得贵组织的电话号码，然后将这些号码分配给组织中的人员。 有关分步说明，请参阅 [设置呼叫计划](set-up-calling-plans.md)。
    
有关详细信息，请参阅Microsoft Teams[附加许可](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md)
  
## <a name="step-2-set-up-communications-credits-for-your-organization"></a>步骤 2：为组织设置通信信用额度

1. 使用工作[或Microsoft 365 管理中心](https://portal.office.com/Adminportal)登录帐户。
    
2. 在左侧导航栏中Microsoft 365 管理中心，转到"**计费**  >  **购买服务"。** 向下滚动并选择"**附加内容"。**

3. 选择 **"通信信用额度"。**
    
4. 在"**通信信用额度"** 订阅页上，填写你的信息，然后单击"下一步 **"：**
    
   - **添加资金** 输入要添加到帐户的金额。 如果未启用自动充值，这些资金耗尽后，使用通信信用额度启用的呼叫功能将中断 (如入站免费服务) 。 为了避免每次余额达到 0 或零 (，) 手动补充通信信用额度余额，我们建议您启用自动充值功能。
    
   - **自动充值**：启用自动充值将在余额低于你设置的阈值时自动补充你的帐户余额。
    
     建议你使用自动充值设置，以免在通信信用额度余额达到 0 或零时 (中断) 。 当充值交易成功、充值交易失败（例如 (信用卡) ）以及通信积分余额达到 0 (零时) 。
    
   - **充值金额** 在"充值金额 **"** 框中输入在达到以下触发金额后要添加到帐户的金额。
    
   - **触发量** 在将用于"**触发**"自动充值的"余额低于"框中输入金额。  余额低于此金额后，充值金额将自动添加到你的帐户。

      > [!NOTE]
     > 使用服务时，资金将仅应用于 Microsoft 发布的通信信用额度。 自购买之日起的 12 个月内未使用的任何资金将过期并丢失。 
     > 
     > 使用自动充值功能时，当达到触发金额并处理充值交易时，将生成通信积分的开票。 通信信用额度以先出先出的方式使用。 若要了解如何检查每月使用情况，请阅读[PSTN Skype for Business报告](/skypeforbusiness/skype-for-business-online-reporting/pstn-usage-report)
    
5. 输入您的付款信息并单击 **下订单** 。
    >[!IMPORTANT]
    >如果您是批量授权客户，则可以选择您的企业协议编号进行付款。 如果您有多个企业协议编号，您将能够选择要用于付款的企业协议。 您还将获得一个机会，指定要与企业协议编号关联的采购订单编号 （如果适用）。
    
每个组织都会考虑不同的呼叫计划数量和费率使用情况。 You will need to get this type of usage data from your current service provider. 已使用 Skype for Business Online 的组织可以通过在管理中心报告 PSTN 使用情况详细信息报告中查看Microsoft Teams  >    >  **获取使用情况** 数据。
  
设置通信信用额度时，需要调查组织的呼叫使用情况，以确定所需的金额。 你可以通过查看" **PSTN 使用详细信息**"报告获取呼叫使用信息。 如果需要存储数据或创建自定义报表，Excel此报告将呼叫数据记录导出到其他位置。 若要了解如何查看使用情况，请阅读 [PSTN 使用情况报告](/skypeforbusiness/skype-for-business-online-reporting/pstn-usage-report)。
  
## <a name="step-3-assign-a-communications-credits-license-to-users"></a>步骤 3：向用户分配通信信用额度许可证

1. 使用工作[或Microsoft 365 管理中心](https://portal.office.com/Adminportal)登录帐户。
    
2. 在左侧导航栏中Microsoft 365 管理中心，转到"**用户**  >  **""活动** 用户"，然后从列表中选择一个用户。
    
3. 选择 **"许可证和应用"。**
    
4. 将 **"通信信用额度"** 切换 **为"打开**"以分配此许可证，然后选择"保存 **"。**
    
    > [!NOTE]
    > 即使为用户分配了 **E5 Enterprise，** 仍建议这样做。

    > [!TIP]
    > 可以使用 [Powershell 通过](/powershell/module/skype/?view=skype-ps) 一个命令将许可证和应用分配给多个用户。
  
## <a name="want-to-know-about-plans-and-pricing"></a>想要了解计划和定价？

可以通过访问以下链接之一来查看计划和定价：
  
- [通话套餐](https://go.microsoft.com/fwlink/?LinkId=799761 )
    
- [音频会议计划](https://go.microsoft.com/fwlink/?LinkId=799762 )
    
- [电话系统计划](https://go.microsoft.com/fwlink/?LinkId=799763)
    
也可通过登录订阅并访问"计费订阅 [Microsoft 365 管理中心"添加订阅"来](https://portal.office.com/adminportal/home?add=sub&amp;adminportal=1#/catalog)  >    >  **查看信息**。
  
若要查看包含每个功能所需的许可证的表，请参阅Microsoft Teams[许可证。](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md)
  
## <a name="related-topics"></a>相关主题

- [设置 Skype for Business Online](/SkypeForBusiness/set-up-skype-for-business-online/set-up-skype-for-business-online)
    
- [设置云语音邮件 - 管理员帮助](set-up-phone-system-voicemail.md)
    
- [为呼叫或](set-up-calling-plans.md)通话[设置Microsoft 365和Office 365](calling-plans-for-office-365.md)
    
- [添加资金并管理通信点数](add-funds-and-manage-communications-credits.md)
    
  

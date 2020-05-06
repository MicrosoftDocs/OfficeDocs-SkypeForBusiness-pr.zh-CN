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
ms.openlocfilehash: 5fb963bbea97a41b6dbd6b68d5d7e0c162dc5a05
ms.sourcegitcommit: 09ff11f8e4f6a93cedc34a5d732a133163df79a0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/05/2020
ms.locfileid: "44042939"
---
# <a name="set-up-communications-credits-for-your-organization"></a>设置组织的通信点数

您需要设置通信点数，如果您想要使用 Skype for Business 和 Microsoft Teams 的免费电话号码。 此外，我们建议你为呼叫计划（国内或国际）和需要拨出到**任何目的地**的音频会议用户设置通讯信用点数。 包括许多国家/地区，但某些目的地可能不包括在您的通话计划或音频会议套餐中。 如果您不设置通讯信用帐单并为您的用户分配**通讯信用**许可证，而您的组织的分钟数（取决于您所在国家/地区的通话计划或音频会议计划），这些用户将无法通过音频会议会议进行呼叫或拨出。 您可以通过阅读[通讯信用点数](what-are-communications-credits.md)来获取详细信息（包括推荐的融资金额）？
  
> [!NOTE]
> 若要找出它的费用， [请参阅下面的价格](https://go.microsoft.com/fwlink/p/?LinkId=799523 )  。 
  
## <a name="step-1-assign-an-audio-conferencing-or-calling-plan-license-to-your-users"></a>步骤1：为用户分配音频会议或呼叫计划许可证

当您注册时，您将获得一定的分钟数，具体取决于您所在的国家/地区。 可以在 "[国家或地区" 列表中搜索音频会议和通话计划](https://docs.microsoft.com/microsoftteams/country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans#select-your-country-or-region-to-see-whats-available-for-your-organization)的国家或地区，以查看您将获得的分钟数。 使用这些分钟数后，通话将断开。 要防止这种情况发生，您需要设置通讯信用点数。
  
若要执行此操作，你需要为你的用户**分配音频会议或电话系统许可证**。
  
- 将**音频会议**许可证分配给你的用户。 请参阅[分配 Microsoft 团队附加设备许可证](teams-add-on-licensing/assign-teams-add-on-licenses.md)。
    
    分配此许可证后，你将需要设置音频会议。 有关分步说明，请参阅[在 Office 365 中试用或购买音频会议](try-or-purchase-audio-conferencing-in-office-365-for-teams.md)。
    
- 为你的用户分配**电话系统**和**国内或国内和国际**呼叫计划许可证。 请参阅[分配 Microsoft 团队附加设备许可证](teams-add-on-licensing/assign-teams-add-on-licenses.md)。
    
    > [!NOTE]
    > 虽然通信信用点数不是必需的，但您仍然需要分配**国内呼叫计划**或**国内和国际呼叫计划**许可证。
  
    分配这些许可证后，你需要获得贵组织的电话号码，然后将这些号码分配给组织中的人员。 有关分步说明，请参阅[设置呼叫计划](set-up-calling-plans.md)。
    
有关详细信息，请参阅[Microsoft 团队附加许可](teams-add-on-licensing/microsoft-teams-add-on-licensing.md)
  
## <a name="step-2-set-up-communications-credits-for-your-organization"></a>步骤2：为你的组织设置通讯信用点数

1. 使用你的工作或学校帐户登录到新的 Microsoft 365 管理中心。
    
2. 在 Microsoft 365 管理中心的左侧导航中，转到 "**帐单** > **购买服务**"。 向下滚动，然后选择 "**加载项**"。

3. 选择 "**通讯信用点数**"。
    
4. 在 "**通信信用点数**订阅" 页面上，填写您的信息，然后单击 "**下一步**"：
    
   - **添加资金**输入要添加到您的帐户的金额。 如果不启用自动重新充电，一旦这些资金耗尽，使用通信信用点数启用的呼叫功能将被中断（如传入免费服务）。 为避免每次余额达到0（零）时都必须手动补充您的通信点数余额，我们建议您启用自动重新充电功能。
    
   - **自动充值**：启用自动充值将在余额低于你设置的阈值时自动补充你的帐户余额。
    
     如果您的通讯信用点数达到0（零），建议使用**自动重新充电**设置以避免任何服务中断。 当您的交易失败时，您将收到一封电子邮件，在重新充电交易失败（如已过期的信用卡），以及通讯信用余额达到0（零）时，您将收到电子邮件。
    
   - 重新**充电金额**在 "重新**充电**" 框中输入您希望在您的帐户达到以下总金额后添加到该帐户的金额。
    
   - **触发金额**在 "**余额低于**" 框中输入将用于 "*触发*" 自动重新充电的金额。 余额低于此金额后，将自动向您的帐户添加重新充电金额。

      > [!NOTE]
     > 在使用服务时，资金将仅应用于 Microsoft 已发布费率的通信信用点数。 自购买之日起的 12 个月内未使用的任何资金将过期并丢失。 
     > 
     > 仅当使用 alloted 基金时，才会应用 "每月计费"，以了解如何查看每月使用情况，请阅读[Skype for BUSINESS PSTN 使用报告](https://docs.microsoft.com/skypeforbusiness/skype-for-business-online-reporting/pstn-usage-report)
    
5. 输入您的付款信息并单击 **下订单** 。
    >[!IMPORTANT]
    >如果您是批量授权客户，则可以选择您的企业协议编号进行付款。 如果您有多个企业协议编号，您将能够选择要用于付款的企业协议。 您还将获得一个机会，指定要与企业协议编号关联的采购订单编号 （如果适用）。
    
每个组织都将有不同的通话计划体积和费率的使用。 You will need to get this type of usage data from your current service provider. 已使用 skype for business Online 的组织已经在使用**skype for business 管理中心** > **报告** > **PSTN 使用详细信息**报告的服务提供商可以获得使用数据。
  
设置通讯信用点数时，您需要调查组织的通话使用情况以确定所需的金额。 你可以通过查看" **PSTN 使用详细信息**"报告获取呼叫使用信息。 如果需要存储数据或创建自定义报表，可通过此报表将调用数据记录导出到 Excel。 若要了解如何查看使用情况，请阅读[Skype for BUSINESS PSTN 使用报告](https://docs.microsoft.com/skypeforbusiness/skype-for-business-online-reporting/pstn-usage-report)。
  
## <a name="step-3-assign-a-communications-credits-license-to-users"></a>步骤3：为用户分配通讯信用许可证

1. 使用你的工作或学校帐户登录。
    
2. 在 Microsoft 365 管理中心的左侧导航中，转到 "**用户** > **活动用户**"，然后从列表中选择一个或一个用户。
    
3. 选择 "**许可证和应用**"。
    
4. 将**通讯信用点数**切换到 **"开"** 以分配此许可证，然后选择 "**保存**"。
    
    > [!NOTE]
    > 即使你有分配了**企业版 E5**许可证的用户，仍建议你执行此操作。
  
## <a name="want-to-know-about-plans-and-pricing"></a>想要了解计划和定价？

你可以通过访问以下链接之一来查看计划和定价：
  
- [通话套餐](https://go.microsoft.com/fwlink/?LinkId=799761 )
    
- [音频会议计划](https://go.microsoft.com/fwlink/?LinkId=799762 )
    
- [电话系统计划](https://go.microsoft.com/fwlink/?LinkId=799763)
    
您也可以通过[登录到 Microsoft 365 管理中心](https://portal.office.com/adminportal/home?add=sub&amp;adminportal=1#/catalog)并转到**帐单** > **订阅** > **添加订阅**来查看信息。
  
若要查看一个表，其中包含每个功能所需的许可证或许可证，请参阅[Microsoft 团队加载项许可](teams-add-on-licensing/microsoft-teams-add-on-licensing.md)。
  
## <a name="related-topics"></a>相关主题

- [设置 Skype for Business Online](/SkypeForBusiness/set-up-skype-for-business-online/set-up-skype-for-business-online)
    
- [设置云语音邮件 - 管理员帮助](set-up-phone-system-voicemail.md)
    
- [设置通话套餐](set-up-calling-plans.md) 和 [Office 365 的通话套餐](calling-plans-for-office-365.md)
    
- [添加资金并管理通信点数](add-funds-and-manage-communications-credits.md)
    
  
 

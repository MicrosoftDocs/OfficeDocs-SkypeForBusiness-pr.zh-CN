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
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Licensing
- seo-marvel-apr2020
description: 'Learn how to set up communication credits (PSTN Consumption) billing licenses for your users and organization. '
ms.openlocfilehash: 9cbd49ed35b3bd52c7b00decf67cab0e01d0a320
ms.sourcegitcommit: 2b1290b763c73f64c84c7568b16962e4ae48acf6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/01/2022
ms.locfileid: "65823593"
---
# <a name="set-up-communications-credits-for-your-organization"></a>设置组织的通信点数

您需要设置通信点数，如果您想要使用 Skype for Business 和 Microsoft Teams 的免费电话号码。 此外，建议为通话套餐设置通信额度， (国内或国际) ，音频会议需要拨打任何 **目标** 的用户。 包括许多国家/地区，但某些目标可能不包括在通话套餐或音频会议订阅中。 如果未设置通信信用额度计费并向用户分配 **通信信用额度** 许可证，并且组织 (会根据您的通话套餐或音频会议计划在您的国家/地区) 中运行几分钟，则这些用户将无法拨打电话或从音频会议会议拨打电话。 可以通过阅读[什么是通信额度](what-are-communications-credits.md)来获取详细信息，包括建议的资金金额？
  
> [!NOTE]
> 若要找出它的费用， [请参阅下面的价格](https://go.microsoft.com/fwlink/p/?LinkId=799523 )  。 
  
## <a name="step-1-assign-an-audio-conferencing-or-calling-plan-license-to-your-users"></a>步骤 1：为用户分配音频会议或呼叫计划许可证

注册时，可获得一定数目的分钟数，具体取决于你的国家/地区。 可以在[“国家/地区”或“区域”可用性列表中搜索你的国家/地区，以获取音频会议和通话套餐](./country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md#select-your-country-or-region-to-see-whats-available-for-your-organization)，以查看所获取的分钟数。 使用这些分钟后，呼叫将断开连接。 若要防止发生这种情况，需要设置通信额度。
  
为此，**需要向用户分配音频会议或电话系统许可证**。 可以为分配了这两个许可证或同时分配了这两个许可证的用户启用通信信用额度。
  
- 为用户分配 **音频会议** 许可证。 请参阅[分配Microsoft Teams加载项许可证](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md)。
    
    分配此许可证后，需要设置音频会议。 有关分步说明，请参阅[Microsoft 365或Office 365中的试用或购买音频会议](try-or-purchase-audio-conferencing-in-office-365-for-teams.md)。
    
- 为用户分配 **电话系统** 和 **国内或国内和国际** 通话套餐许可证。 请参阅[分配Microsoft Teams加载项许可证](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md)。
    
    > [!NOTE]
    > 虽然通信额度不需要，但仍需要分配 **国内通话套餐** 或 **国内和国际通话套餐** 许可证。
  
    分配这些许可证后，你需要获得贵组织的电话号码，然后将这些号码分配给组织中的人员。 有关分步说明，请参阅 [“设置呼叫计划](set-up-calling-plans.md)”。
    
有关详细信息，请参阅[Microsoft Teams加载项许可](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md)
  
## <a name="step-2-set-up-communications-credits-for-your-organization"></a>步骤 2：为组织设置通信额度

1. 使用工作或学校帐户登录到[Microsoft 365 管理中心](https://portal.office.com/Adminportal)。
    
2. 在Microsoft 365 管理中心的左侧导航栏中，转到 **计** > 费 **购买服务**。

3. 在 **加载项** 类别下查找 **通信信用额度**，或在“**搜索所有产品类别**”搜索框中搜索“通信额度”，然后选择 **“详细信息**”。
    
4. 查看服务信息并选择 **“购买**”。  (注意：按顺序自动选择固定数量的通信信用额度许可证。) 

5. 在“签出”页上，输入付款信息并填写所需的信息：
    
   - **添加资金** 输入要添加到帐户的金额。 如果不启用自动充值，这些资金耗尽后，使用通信额度启用的呼叫功能将中断 (，例如入站免费服务) 。 为了避免每次余额达到 0 (零) 时必须手动补充通信额度余额，建议启用自动充值功能。
    
   - **自动充值**：启用自动充值将在余额低于你设置的阈值时自动补充你的帐户余额。
    
     如果通信额度余额达到 0 (零) ，建议使用 **自动充值** 设置来避免服务中断。 当充值交易成功时，当充值事务失败 (（例如信用卡) 过期，以及通信额度余额达到 0 (零) 时，系统会向你发送电子邮件。
    
   - **充值量** 在 **“充值”** 中输入要在帐户达到以下触发量后添加到帐户的框中的金额。
    
   - **触发量** 输入当 **余额低于** 用于“ *触发*  ”自动充值的框中的金额。 余额低于此金额后，将自动将充值量添加到帐户。

      > [!NOTE]
     > 使用这些服务时，资金将仅以 Microsoft 发布的费率应用于通信信用额度。 自购买之日起的 12 个月内未使用的任何资金将过期并丢失。 
     > 
     > 使用自动充值函数时，当达到触发量并处理充值事务时，将生成通信额度的发票。 通信信用额度首先以现出方式使用。 若要了解如何检查每月使用情况，请阅读[Microsoft Teams PSTN 使用情况报告](/microsoftteams/teams-analytics-and-reports/pstn-usage-report)。
    
6. 选择 **“位置”顺序**。
    >[!IMPORTANT]
    >如果你是批量许可客户，你可能希望使用企业协议进行付款。 如果要执行此操作，请打开一个顶级支持案例以启用此功能。 如果您有多个企业协议编号，您将能够选择要用于付款的企业协议。 如果适用) 支持启用此操作，你还将有机会指定与企业协议编号 (关联的采购订单号。
    
每个组织将有不同的通话套餐量和费率的使用情况。 You will need to get this type of usage data from your current service provider. 已使用Skype for Business联机或Microsoft Teams作为服务提供商的组织可以通过在 **Microsoft Teams管理中心** > **分析&报告** 使用情况 **报告** >  > **PSTN 和短信 (预览) 使用** 情况报表中查看使用情况数据来获取使用情况数据。
  
设置通信额度时，需要调查组织的呼叫使用情况，以确定所需的金额。 可以通过查看 **PSTN 和短信 (预览) 使用** 情况报告来获取呼叫使用情况信息。 如果需要存储数据或创建自定义报表，此报表允许将调用数据记录导出到Excel。 若要了解如何查看使用情况，请阅读[Microsoft Teams PSTN 使用情况报告](/microsoftteams/teams-analytics-and-reports/pstn-usage-report)。
  
## <a name="step-3-assign-a-communications-credits-license-to-users"></a>步骤 3：向用户分配通信额度许可证

1. 使用工作或学校帐户登录到[Microsoft 365 管理中心](https://portal.office.com/Adminportal)。
    
2. 在Microsoft 365 管理中心的左侧导航中，转到 **用户** > **活动用户**，然后从列表中选择用户。
    
3. 选择 **“许可证”和“应用**”。
    
4. 将 **通信额度** 切换到 **“打开”** 以分配此许可证，然后选择 **“保存**”。
    
    > [!NOTE]
    > 即使已为用户分配 **了Enterprise E5** 许可证，仍建议执行此操作。

    > [!TIP]
    > 可以使用 [Powershell](/powershell/module/skype/?view=skype-ps&preserve-view=true) 通过一个命令将许可证和应用分配给多个用户。
  
## <a name="want-to-know-about-plans-and-pricing"></a>想要了解计划和定价？

可以通过访问以下链接之一来查看计划和定价：
  
- [通话套餐](https://go.microsoft.com/fwlink/?LinkId=799761 )
    
- [音频会议计划](https://go.microsoft.com/fwlink/?LinkId=799762 )
    
- [电话系统计划](https://go.microsoft.com/fwlink/?LinkId=799763)
    
还可以通过 [登录到Microsoft 365 管理中心](https://portal.office.com/adminportal/home?add=sub&amp;adminportal=1#/catalog)并转到计 **费** > **订阅** > **添加订阅** 来查看信息。
  
若要查看包含每个功能所需的许可证或许可证的表，请参阅[Microsoft Teams加载项许可](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md)。
  
## <a name="related-topics"></a>相关主题

- [设置 Skype for Business Online](/SkypeForBusiness/set-up-skype-for-business-online/set-up-skype-for-business-online)
    
- [设置云语音邮件 - 管理员帮助](set-up-phone-system-voicemail.md)
    
- 为[Microsoft 365或Office 365](calling-plans-for-office-365.md)[设置呼叫计划](set-up-calling-plans.md)和呼叫计划
    
- [添加资金并管理通信点数](add-funds-and-manage-communications-credits.md)
    
  

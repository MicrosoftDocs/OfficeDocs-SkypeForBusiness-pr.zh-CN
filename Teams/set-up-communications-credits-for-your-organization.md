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
description: Learn how to set up communication credits (PSTN Consumption) billing licenses for your users and organization.
ms.openlocfilehash: 8093b10d4918793c669f42b839999239d381a24a
ms.sourcegitcommit: 07761c26b53d92fc36b82cab7b3e38a6de4ff945
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/02/2022
ms.locfileid: "67156570"
---
# <a name="set-up-communications-credits-for-your-organization"></a>设置组织的通信点数

如果要在 Microsoft Teams 中使用免费号码，则需要设置通信额度。 Microsoft 建议为呼叫计划设置通信额度， (需要拨出到 **任何目标** 的国内、国际或即用即付) 和音频会议用户。 某些目标可能不包括在通话套餐或音频会议订阅中。

注册通话套餐和/或音频会议时，会根据你的国家/地区获得一定分钟数。 有关详细信息，请参阅 [音频会议和通话套餐的国家/地区可用性列表](./country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md#select-your-country-or-region-to-see-whats-available-for-your-organization)。

如果未设置通信额度，并且你的组织用完了几分钟，这些用户将无法拨打电话或从音频会议中拨打电话。 可以通过阅读[什么是通信额度](what-are-communications-credits.md)来获取详细信息，包括建议的资金金额？
  
> [!NOTE]
> 有关计划和定价的详细信息， [请参阅此处的费率](https://go.microsoft.com/fwlink/p/?LinkId=799523)。

若要为组织设置通信额度，请执行以下步骤：

1. [向用户分配具有通话套餐许可证的音频会议和/或电话系统](#step-1-assign-an-audio-conferencing-andor-phone-system-with-calling-plan-license-to-your-users)。

2. [为组织设置通信额度](#step-2-set-up-communications-credits-for-your-organization)。

3. [向用户分配通信额度许可证](#step-3-assign-a-communications-credits-license-to-users)。
  
## <a name="step-1-assign-an-audio-conferencing-andor-phone-system-with-calling-plan-license-to-your-users"></a>步骤 1：为用户分配具有通话套餐许可证的音频会议和/或电话系统
  
可以为拥有音频会议许可证、具有通话套餐许可证的电话系统或两者兼有的用户启用通信信用额度。
  
- 向用户分配 **音频会议** 许可证。 请参阅 [分配 Microsoft Teams 加载项许可证](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md)。

  分配此许可证后，需要设置音频会议。 有关分步说明，请参[阅在 Microsoft 365 或 Office 365 中试用或购买音频会议](try-or-purchase-audio-conferencing-in-office-365-for-teams.md)。

- 为用户分配 **电话系统** 和 **国内**、 **国际** 或即 **用即付** 呼叫计划许可证。 请参阅 [分配 Microsoft Teams 加载项许可证](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md)。

  > [!NOTE]
  > 尽管通信额度不需要此功能，但仍需要分配 **国内呼叫计划**、 **国际呼叫计划** 或即 **用即付** 许可证。
  
  分配这些许可证后，需要获取组织的电话号码，然后将这些号码分配给组织中的人员。 有关分步说明，请参阅 [“设置呼叫计划](set-up-calling-plans.md)”。

有关详细信息，请参阅 [Microsoft Teams 加载项许可](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md)。
  
## <a name="step-2-set-up-communications-credits-for-your-organization"></a>步骤 2：为组织设置通信额度

1. 使用工作或学校帐户登录到[Microsoft 365 管理中心](https://portal.office.com/Adminportal)。

2. 在Microsoft 365 管理中心的左侧导航栏中，转到 **计** > 费 **购买服务**。

3. 在 **加载项** 类别下查找 **通信信用** 额度，或在“**搜索所有产品类别**”搜索框中搜索 **通信信用额度**，然后选择 **“详细信息**”。

4. 查看服务信息并选择 **“购买**”。  (注意：按顺序自动选择固定数量的通信信用额度许可证。) 

5. 在“签出”页上，输入付款信息并填写所需的信息：

   - **添加资金** 输入要添加到帐户的金额。

   - **自动充值**：启用自动充值将在余额低于你设置的阈值时自动补充你的帐户余额。

     Microsoft 建议使用 **自动充值** 设置，以避免通信额度余额达到零时服务中断。 当充值交易成功时，当充值事务失败 (（如过期的信用卡) ，以及通信信用额度余额达到零时，系统会向你发送电子邮件。

   - **充值量** 在 **“充值”** 中输入要在帐户达到以下触发量后添加到帐户的框中的金额。

   - **触发量** 输入当 **余额低于** 用于“ *触发*  ”自动充值的框中的金额。 余额低于此金额后，将自动将充值量添加到帐户。

      > [!NOTE]
     > 使用这些服务时，资金将仅以 Microsoft 发布的费率应用于通信信用额度。 自购买之日起的 12 个月内未使用的任何资金将过期并丢失。
     >
     > 使用自动充值函数时，当达到触发量并处理充值事务时，将生成通信额度的发票。 通信信用额度首先以现出方式使用。 若要了解如何检查每月使用情况，请阅读 [Microsoft Teams PSTN 使用情况报告](/microsoftteams/teams-analytics-and-reports/pstn-usage-report)。

6. 选择 **“位置”顺序**。

    >[!IMPORTANT]
    >如果你是批量许可客户，你可能希望使用企业协议进行付款。 如果您有多个企业协议编号，您将能够选择要用于付款的企业协议。 如果适用) 支持启用此操作，你还将有机会指定与企业协议编号 (关联的采购订单号。

每个组织将有不同的通话套餐量和费率的使用情况。 需要从当前服务提供商获取此类型的使用情况数据。 已使用 Microsoft Teams 作为其服务提供商的组织可以通过在 **Microsoft Teams 管理中心** > **分析&报告** 使用情况 **报告** >  > **PSTN 和 SMS** 中查看使用情况数据来获取使用情况数据 (预览) 使用情况报告。
  
设置通信额度时，需要调查组织的呼叫使用情况，以确定所需的金额。 可以通过查看 **PSTN 和短信 (预览) 使用** 情况报告来获取呼叫使用情况信息。 如果需要存储数据或创建自定义报表，此报表允许将调用数据记录导出到 Excel。 若要了解如何查看使用情况，请阅读 [Microsoft Teams PSTN 使用情况报告](/microsoftteams/teams-analytics-and-reports/pstn-usage-report)。
  
## <a name="step-3-assign-a-communications-credits-license-to-users"></a>步骤 3：向用户分配通信额度许可证

1. 使用工作或学校帐户登录到[Microsoft 365 管理中心](https://portal.office.com/Adminportal)。

2. 在Microsoft 365 管理中心的左侧导航中，转到 **用户** > **活动用户**，然后从列表中选择用户。

3. 选择 **“许可证”和“应用**”。

4. 将 **通信额度** 切换到 **“打开”** 以分配此许可证，然后选择 **“保存**”。

    > [!NOTE]
    > 即使有分配有 **企业 E5** 许可证的用户，仍建议执行此操作。

    > [!TIP]
    > 可以使用 [Powershell](/powershell/module/skype/?view=skype-ps&preserve-view=true) 通过一个命令将许可证和应用分配给多个用户。
  
## <a name="for-more-information"></a>有关详细信息

- 可以通过 [登录到Microsoft 365 管理中心](https://portal.office.com/adminportal/home?add=sub&amp;adminportal=1#/catalog)并转到计 **费** > **订阅** > **添加订阅** 来查看详细信息。
  
- 有关许可证的详细信息，请参阅 [Microsoft Teams 加载项许可](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md)。

- 有关通话套餐的详细信息，请参阅为 [Microsoft 365](calling-plans-for-office-365.md) [设置呼叫计划](set-up-calling-plans.md)和呼叫计划。

- 有关添加资金和管理通信信用额度的详细信息，请 [参阅“添加资金和管理通信额度](add-funds-and-manage-communications-credits.md)”。

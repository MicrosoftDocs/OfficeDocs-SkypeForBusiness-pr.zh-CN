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
- highpri
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
ms.openlocfilehash: 0a6489b0c3e7591139421b418be52d6bfcd8f4fa
ms.sourcegitcommit: 0a13f96663c7466b08d654bedcb6206f302189a1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/22/2022
ms.locfileid: "69139126"
---
# <a name="set-up-communications-credits-for-your-organization"></a>设置组织的通信点数

如果要将免费号码与 Microsoft Teams 配合使用，需要设置通信点数。 Microsoft 建议为需要拨出 **任何目的地** 的 Microsoft Teams 通话套餐 (国内、国际或即用即付) 和音频会议用户设置通信额度。 某些目标可能未包含在通话套餐或音频会议订阅中。

当你注册通话套餐和/或音频会议时，你将获得一些时间，具体取决于你的国家/地区。 有关详细信息，请参阅 [音频会议和通话套餐的国家或地区可用性列表](./country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md#select-your-country-or-region-to-see-whats-available-for-your-organization)。

如果未设置通信点数，并且组织的分钟数不足，则这些用户将无法拨打电话或拨出音频会议。 你可以通过阅读[什么是通信额度](what-are-communications-credits.md)来获取详细信息，包括建议的资金金额？
  
有关计划和定价的详细信息， [请参阅此处的费率](https://go.microsoft.com/fwlink/p/?LinkId=799523)。

> [!IMPORTANT]
> **对于具有呼叫订阅的新商业体验的客户：**
>
> NCE)  (新的商业体验允许客户在使用服务后支付服务费用，也称为使用后计费。
>
> 由于通信额度是用于支持传出分钟数的预付费预算，因此无法使用 NCE 呼叫订阅的客户购买。
>
> 相反，NCE 客户将在使用超额传出几分钟后支付费用。 不需要通信点数池。
>
> 有关呼叫订阅的新商业体验的详细信息，请参阅 [为订阅启用即用即付](/microsoft-365/commerce/subscriptions/manage-pay-as-you-go-services) 和 [电信即用即付的新商业超额](/partner-center/new-commerce-telco-payg)。

若要为组织设置通信额度，请执行以下步骤：

1. [向用户分配具有通话套餐许可证的音频会议和/或电话系统](#step-1-assign-an-audio-conferencing-andor-phone-system-with-calling-plan-license-to-your-users)。

2. [为组织设置通信额度](#step-2-set-up-communications-credits-for-your-organization)。

3. [向用户分配通信点数许可证](#step-3-assign-a-communications-credits-license-to-users)。
  
## <a name="step-1-assign-an-audio-conferencing-andor-phone-system-with-calling-plan-license-to-your-users"></a>步骤 1：向用户分配具有通话套餐许可证的音频会议和/或电话系统
  
可以为具有音频会议许可证和/或具有通话套餐许可证的电话系统的用户启用通信点数。
  
- 向用户分配 **音频会议** 许可证。 请参阅 [分配 Microsoft Teams 附加许可证](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md)。

  分配此许可证后，需要设置音频会议。 有关分步说明，请参阅[在 Microsoft 365 或 Office 365 中试用或购买音频会议](try-or-purchase-audio-conferencing-in-office-365-for-teams.md)。

- 向用户分配 **电话系统和****国内**、**国际** 或 **即用即付** 通话套餐许可证。 请参阅 [分配 Microsoft Teams 附加许可证](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md)。

  > [!NOTE]
  > 虽然通信额度不需要它，但你仍然需要分配 **国内通话套餐**、 **国际通话套餐** 或 **即用即付** 许可证。
  
  分配这些许可证后，需要获取组织的电话号码，然后将这些号码分配给组织中的人员。 有关分步说明，请参阅 [设置通话套餐](set-up-calling-plans.md)。

有关详细信息，请参阅 [Microsoft Teams 附加许可](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md)。
  
## <a name="step-2-set-up-communications-credits-for-your-organization"></a>步骤 2：为组织设置通信额度

1. 使用工作或学校帐户登录到[Microsoft 365 管理中心](https://portal.office.com/Adminportal)。

2. 在Microsoft 365 管理中心的左侧导航栏中，转到 **“计费** > **购买服务**”。

3. 在 **“加载项**”类别下查找 **“通信额度**”，或在“**搜索所有产品类别**”搜索框中搜索 **“通信额度**”，然后选择“**详细信息**”。

4. 查看服务信息，然后选择“ **购买**”。  (注意：每个订单中都会自动选择固定数量的通信点数许可证。) 

5. 在“结帐”页上，输入你的付款信息并填写所需的信息：

   - **添加资金** 输入要添加到帐户的金额。

   - **自动充值**：启用自动充值将在余额低于你设置的阈值时自动补充你的帐户余额。

     Microsoft 建议使用 **自动充值** 设置，以避免在通信点数余额为零时中断服务。 充值交易成功、充值交易失败 (（例如信用卡) 过期）以及通信额度余额达到零时，将向你发送电子邮件。

   - **充值金额** 在“ **充值金额** ”框中，在达到以下触发金额后，输入要添加到帐户的金额。

   - **触发器金额** 在“ **当余额低于** ”框中输入金额，该金额将用于“ *触发*  ”自动充值。 余额低于此金额后，充值金额将自动添加到您的帐户。

      > [!NOTE]
     > 使用服务时，资金将仅应用于以 Microsoft 发布的费率计算的通信额度。 自购买之日起的 12 个月内未使用的任何资金将过期并丢失。
     >
     > 使用自动充值功能时，当达到触发金额并处理充值交易时，将生成通信额度的发票。 通信额度以先出先出的方式使用。 若要了解如何检查每月使用情况，请阅读 [Microsoft Teams PSTN 使用情况报告](/microsoftteams/teams-analytics-and-reports/pstn-usage-report)。

6. 选择“**下单**”。

    >[!IMPORTANT]
    >如果你是批量许可客户，你可能希望使用企业协议进行付款。 如果您有多个企业协议编号，您将能够选择要用于付款的企业协议。 在支持启用后，你还将有机会指定与企业协议编号关联的采购订单编号 (（如果适用) ）。

每个组织将有不同的通话套餐使用量和费率要考虑。 需要从当前服务提供商处获取此类使用情况数据。 已使用 Microsoft Teams 作为其服务提供商的组织可以在 **Microsoft Teams 管理中心** >  Analytics 中查看使用情况数据，**&报告** > **使用情况报告** > **PSTN 和 SMS (预览版) 使用情况** 报告来获取使用情况数据。
  
设置通信点数时，需要调查组织的呼叫使用情况，以确定所需的金额。 可以通过查看 **PSTN 和 SMS (预览版) 使用情况** 报告来获取呼叫使用情况信息。 如果需要存储数据或创建自定义报表，此报表允许您将呼叫数据记录导出到 Excel。 若要了解如何查看使用情况，请阅读 [Microsoft Teams PSTN 使用情况报告](/microsoftteams/teams-analytics-and-reports/pstn-usage-report)。
  
## <a name="step-3-assign-a-communications-credits-license-to-users"></a>步骤 3：向用户分配通信点数许可证

1. 使用工作或学校帐户登录到[Microsoft 365 管理中心](https://portal.office.com/Adminportal)。

2. 在Microsoft 365 管理中心的左侧导航栏中，转到 **“活动用户”** > ，然后从列表中选择一个用户。

3. 选择 **“许可证和应用**”。

4. 将 **“通信信用额度** ”切换为 **“开”** 以分配此许可证，然后选择“ **保存**”。

    > [!NOTE]
    > 即使你拥有分配有 **企业 E5** 许可证的用户，仍建议这样做。

    > [!TIP]
    > 可以使用 [Powershell](/powershell/module/skype/?view=skype-ps&preserve-view=true) 通过一个命令将许可证和应用分配给多个用户。
  
## <a name="for-more-information"></a>有关详细信息

- 可以通过 [登录到 Microsoft 365 管理中心](https://portal.office.com/adminportal/home?add=sub&amp;adminportal=1#/catalog)并转到 **“计费** > **订阅** > **”“添加订阅**”来查看详细信息。
  
- 有关许可证的详细信息，请参阅 [Microsoft Teams 附加许可](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md)。

- 有关通话套餐的详细信息，请参阅 [为](set-up-calling-plans.md) [Microsoft 365 设置通话套餐和通话套餐](calling-plans-for-office-365.md)。

- 有关添加资金和管理通信额度的详细信息，请参阅 [添加资金和管理通信额度](add-funds-and-manage-communications-credits.md)。

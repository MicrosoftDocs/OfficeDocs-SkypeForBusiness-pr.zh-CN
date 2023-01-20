---
title: 联系电话号码服务团队
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: mikedav, roykuntz, jastark
ms.topic: conceptual
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.voice.tnsservicedesk
- ms.teamsadmincenter.voice.contacttnssupport
- Calling Plans
ROBOTS: NOINDEX, NOFOLLOW
description: 当你为组织获取电话号码或端口 (转移) 号码时，可能需要在 TNS 服务台获取帮助和支持。
ms.openlocfilehash: 9984775a05458592fe1789c0dd8b173a08783220
ms.sourcegitcommit: fd56fb16ed60b027d3f8de96711d143825f9c184
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/20/2023
ms.locfileid: "69835555"
---
# <a name="telephone-number-services-tns---service-desk"></a>电话号码服务 (TNS) - 服务台

> [!NOTE]
> 截至 2021 年 7 月 22 日，以前联系 TNS 服务台的电子邮件系统已停用。

可通过新的电话号码服务中心与电话号码服务 (TNS) 服务台 **[进行交互。](https://pstnsd.powerappsportals.com)** 现在可以在与 Teams 管理中心集成的单个位置打开票证、查看票证和跟踪通信。 以下各节更详细地介绍了这些任务。


- **[创建新案例](#create-a-new-case)** - 提交新请求或常规查询。

- **[查看现有案例](#view-and-manage-existing-cases)** - 跟踪和监视现有案例 () 。

- **[查看我的公司案例](#view-and-manage-existing-cases)** - 跟踪和监视公司的现有案例 () 。 如果公司的同事已打开任何案例，则可在此视图中查找这些案例。

- **[提供反馈](#view-and-manage-existing-cases)** - 与我们分享你的反馈。

## <a name="create-a-new-case"></a>新建案例

> [!NOTE]
> 仅允许来自同一租户的人员创建案例。 例如，来自 @fabrikam.com 的人员无法代表 @contoso.com 创建案例。

若要创建新案例，请执行以下步骤：

1. 选择 **从以下位置之一创建新案例** ：

   - 在 **“电话号码服务中心** ”主页中，位于页面顶部或底部磁贴。

   - 从 **查看现有案例**  页。

   - 从 **查看我的公司案例** 页。

2. 提供案例详细信息，如[下一部分](#provide-case-details)中所述。

3. 输入所有值后，选择“ **提交**”。 你将看到一个新屏幕，可在其中查看案例编号。

### <a name="provide-case-details"></a>提供案例详细信息

为了了解案例详细信息，Microsoft 需要以下信息：

- [案例类别](#case-category)
- [国家或地区](#country-or-region)
- [案例类型](#case-type)
- [案例标题](#case-title)
- [其他通知联系人](#additional-contacts-for-notifications)
- [说明](#description)
- [其他支持文档](#additional-supporting-documents)

#### <a name="case-category"></a>案例类别

案例可以包含以下两个类别之一：

- **提交新请求**- 如果要提交新请求，请选择此选项。 例如，想要提交端口请求，或从 Microsoft 购买电话号码。

- **常规查询** - 如果存在有助于确定请求的问题，请选择此选项。 例如，需要知道是否可以将无线号码移植到 Microsoft，或者需要知道 Microsoft 是否支持虚免费号码。

#### <a name="country-or-region"></a>国家或地区

选择要提交此案例的国家/地区。 如果有对多个国家/地区的请求，则必须为每个国家/地区打开一个案例。

#### <a name="case-type"></a>案例类型

案例类型可以是下列类型之一：

- **自定义呼叫名称（仅限美国）** - 在 Microsoft 电话号码上设置自定义呼叫名称。 这仅适用于美国电话号码。

  - **要设置的自定义呼叫名称（仅限 15 个字符）** - 要设置的自定义呼叫名称。 名称的最大限制为 15 个字符。

  - **电话号码列表** - 要为其设置自定义呼叫名称值的电话号码列表。 上传包含电话号码列表的 csv 文件。

- **租户间端口**– 将电话号码从一个租户移动到另一个租户。 例如，Microsoft 中有两个不同的租户，并且希望将电话号码从一个租户移动到另一个租户。

  - **源租户域名** - 要将电话号码移到其他租户的租户。

  - **源租户唯一标识符** - 源租户的租户 ID。 这是可选字段。

  - **目标租户域名** - 要将电话号码移动到的租户。

  - **目标租户唯一标识符** - 目标租户的租户 ID。 这是可选字段。

  - **请求的日期时间*** - 要将号码从源租户移动到目标租户的日期和时间。 查看日期和时间。

  - **电话号码列表** - 要从源租户移动到目标租户的电话号码列表。 上传包含电话号码列表的 csv 文件。

- **清单类型更改**– 更改电话号码的类型。 例如，想要将 Microsoft 订阅者号码更改为服务号码。 有关 Microsoft 支持的电话号码类型的详细信息，请参阅 [电话号码类型](../different-kinds-of-phone-numbers-used-for-calling-plans.md)。

  - **转换为** - 选择此项可将数字转换为用户编号或服务号码。

  - **首选日期/时间*** - 要更改数字清单类型的日期和时间。 有关详细信息，请参阅日期和时间。

  - **复选框 - 我知道，为了能够更新清单类型，需要取消分配我的电话号码** - 除非未分配租户中的电话号码，否则 Microsoft 无法处理电话号码类型更改请求。 如果在将来的日期请求此更改，则需要确保在请求的日期和时间之前未分配数字。

  - **电话号码列表** - 要更改其类型的电话号码列表。 上传包含电话号码列表的 csv 文件。

- **新 TN 购置** – 从 Microsoft 购买新电话号码。

  - **数字类型** - 选择数字的类型。 请参阅[电话号码类型](../different-kinds-of-phone-numbers-used-for-calling-plans.md)。

  - **尝试从 Teams 管理员 中心门户获取电话号码** - 是否尝试从 Microsoft Teams 管理员中心购买这些电话号码？

  - **所需的电话号码数量 - 要购买的电话号码数量。**

  - **省/自治区/直辖市** - 要为其提供电话号码的国家/地区内的省/自治区/直辖市。

  - **城市** - 要为其提供电话号码的省/自治区/直辖市内的城市。

  - **Office 地址** - 此地址仅特定于特定国家/地区。 这是办公室的站点地址。

  - **目录列表** - 仅特定于特定国家/地区。 是否要使用电话号码发布公司信息？

- **端口** – 将现有电话号码从当前服务提供商移植到 Microsoft。

  - **将端口订单命名** - 为端口申请提供易于记住的名称。

  - **请求的移植日期/时间*** - 要将数字移植到 Microsoft 的日期和时间。 这不是有保证的移植日期，因为当前号码所有者必须先批准我们的转网请求。 查看日期和时间。

  - **移植号码列表** - 要移植到 Microsoft 的电话号码列表。 上传包含电话号码列表的 csv 文件。

  - **授权书 （LOA）** - 在此处附加已签名和填写的 LOA。 如果没有 LOA，Microsoft 无法处理端口请求。

    > [!NOTE]
    > 有关用于移植/转移现有电话号码的 LOA 和其他文档要求的详细信息，请参阅 [管理通话套餐的电话号码](/microsoftteams/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization)。
    >
    >若要为用户移植/转移 999 或更少的电话号码，请将已完成且已签名的 LOA 上传到 Microsoft Teams 管理中心以供进一步处理。
    >
    > 若要移植/转移超过 999 个电话号码，或者如果在 Microsoft Teams 管理中心的移植过程中遇到问题，可以 [手动将转网订单提交](/microsoftteams/phone-number-calling-plans/manually-submit-port-order) 到你区域的 TNS 服务台。

- **地址更新**– 更新紧急呼叫地址。 请注意，此字段仅适用于所选国家/地区。

  - **位置 ID** - 紧急地址的位置 ID。

  - **电话号码列表** - 要为其更改紧急地址的电话号码列表（在"说明"字段中输入所需的地址）。 上传包含电话号码列表的 csv 文件。

**日期和时间。** 如果选择国家/地区 = 法国，日期 = 2021/8/14，时间 = 上午 10 点，则请求将在 2021 年 8 月 14 日上午 10 点执行。 法语时间。

#### <a name="case-title"></a>案例标题

输入汇总请求的标题。

#### <a name="additional-contacts-for-notifications"></a>其他通知联系人

输入从 Microsoft 接收自动状态通知的人员列表。
例如，想要按端口顺序排列，并且希望除了自己之外的其他两个同事接收自动状态通知。 在 **通知电子邮件** 部分中提供同事的电子邮件地址。 此信息是可选的。

#### <a name="description"></a>说明

描述你尝试实现的目标，并列出有关 Microsoft 电话号码服务 (TNS) 服务台的问题。

#### <a name="additional-supporting-documents"></a>其他支持文档

上传案例的任何其他文档。

## <a name="view-and-manage-existing-cases"></a>查看和管理现有案例

可以通过选择 **查看现有案例** 和选择案例编号来查看案例。 选择案例编号会将重定向到案例详细信息。 （还可以通过选择 **查看公司案例** 查看公司案例。） 还可以：

- 通过选择 **打开案例**、**所有案例** 或 **已结案例** 来 **筛选案例**。

- 通过打开现有案例、向下滚动并选择“**添加注释**”，**与 TNS 服务台就** 你的案例进行通信。 将显示一个新窗口。 在批注框中输入消息。 附加任何支持文档 (（如果可用) ），然后选择“ **提交**”。

  **来自 TNS 服务台** 的响应将显示在同一时间线下。 当案例有更新时，将收到更新的自动电子邮件通知。

- 通过导航到现有案例、向下滚动并选择 **取消案例**，来 **取消案例**。 从下拉列表中选择取消的原因，然后选择 **取消**。

- **解决案例** - 如果认为请求已完成，则可以通过导航到现有案例、向下滚动并选择 **解决案例**。 选择 **关闭**；现在，该案例将显示为 **已解决– 问题已解决**。

## <a name="related-topics-and-additional-resources"></a>相关主题和其他资源

- 有关数字设置和配置、许可证、费用或计费的帮助，请参阅 [业务产品支持联系人 - 管理员帮助](/microsoft-365/admin/contact-support-for-business-products?tabs=online)。

- 若要了解所在国家或地区的可用功能，请参阅[音频会议和通话套餐的国家/地区可用情况](../country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)。

- 有关组织的电话号码的相应类型 () 的信息，请参阅 [不同类型的电话号码](../different-kinds-of-phone-numbers-used-for-calling-plans.md)。

- 有关管理组织电话号码的信息，请参阅 [管理组织的电话号码](manage-phone-numbers-for-your-organization.md)。

- 有关紧急呼叫条款和条件的信息，请参阅 [紧急呼叫条款和条件](../emergency-calling-terms-and-conditions.md)。

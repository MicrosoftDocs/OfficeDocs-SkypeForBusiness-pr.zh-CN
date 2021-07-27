---
title: 联系 PSTN 服务台
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
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.voice.pstnservicedesk
- ms.teamsadmincenter.voice.contactPSTNsupport
- Calling Plans
ROBOTS: NOINDEX, NOFOLLOW
description: 当你获得电话号码或转网 (为) 号码时，可能需要在 PSTN 服务台获取帮助和支持。
ms.openlocfilehash: b3925fbd473094b06133fb7cfe31479396434b80
ms.sourcegitcommit: 9879bc587382755d9a5cd63a75b0e7dc4e15574c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/21/2021
ms.locfileid: "53510273"
---
# <a name="pstn-service-desk"></a>PSTN 服务台 

有一个与 PSTN 服务台交互的新过程。 现在，可以在与管理中心集成的单个位置打开票证、查看票证和Teams通信。 本文介绍联系服务台所需的一切信息。

> [!NOTE]
> 截至 2021 年 7 月 22 日，当前电子邮件系统已停用。

若要联系服务台，请：

1. 登录到 Teams 管理中心 - admin.teams.microsoft.com。

2. 在左窗格中，选择 **"电话数字"。**

3. 在页面顶部，选择"获取 **电话号码支持"。** 你将看到"电话服务中心"。  

> [!NOTE]
> 仅允许来自同一租户的某人创建案例。 也就是说，来自 @fabrikam.com 的某人不能代表 @contoso.com。 

从电话"数字服务中心"中，可以创建新案例、查看现有事例、与服务台通信以及管理用户配置文件。 以下部分更详细地介绍了这些任务。

- **电话号码服务中心**  – 导航到门户主页。 

- **[创建新案例](#create-a-new-case)**  – 提交新请求或一般查询。 

- **[查看现有案例](#view-and-manage-existing-cases)** - 跟踪和监视现有 () 。 

- **[查看我的公司案例](#view-and-manage-existing-cases)**  - 跟踪和监视公司的现有案例 () 。 如果你的公司的同事打开了任何案例，你可以在此视图中查找这些案例。  

- **[提供反馈](#view-and-manage-existing-cases)**- 与我们分享你的反馈。 

- **[你的姓名]**  – 更新个人资料页面。 


## <a name="create-a-new-case"></a>创建新案例

若要创建一个新案例，请执行以下步骤：

1. 从 **以下位置之一选择** "创建新案例"：  

   - 从 **电话"** 数字服务中心"页的顶部或底部磁贴。

   - 从" **查看现有事例"页**  。

   - 从" **查看我的公司案例"** 页面。

2. 提供案例详细信息，如下一部分 [所述](#provide-case-details)。

3. 输入所有值后，选择"提交 **"。** 你将看到一个新屏幕，可在其中查看案例编号。  

### <a name="provide-case-details"></a>提供案例详细信息

若要了解案例详细信息，Microsoft 需要以下信息：

- [案例类别](#case-category)
- [国家或地区](#country-or-region)
- [案例类型](#case-type)
- [案例标题](#case-title)
- [通知的其他联系人](#additional-contacts-for-notifications)
- [说明](#description)
- [其他支持文档](#additional-supporting-documents)

#### <a name="case-category"></a>案例类别

一个案例可以有两个类别之一： 

- **提交新请求**- 如果要提交新请求，请选择此选项。 例如，你想要提交端口请求，或者想要从 Microsoft 购买电话号码。  

- **一般查询** - 如果有疑问，请选择此选项，以便确定你的请求。 例如，需要知道是否可以将无线号码移植到 Microsoft，或者需要知道 Microsoft 是否支持免费电话号码。 

#### <a name="country-or-region"></a>国家或地区

选择要提交此案例的国家/地区。 如果有针对多个国家/地区的请求，则必须按国家/地区创建一个案例。  

#### <a name="case-type"></a>案例类型

案例类型可以是下列类型之一：

- **自定义呼叫 (美国**) - 在 Microsoft 电话号码上设置自定义呼叫名称。 这仅适用于美国电话号码。 

  - **自定义呼叫名称， (15 个字符**) - 要设置的自定义呼叫名称。 名称的最大限制为 15 个字符。  

  - **电话号码列表** - 要设置其自定义呼叫名称值的电话号码列表。 Upload包含电话号码列表的 csv 文件。  

- **租户间端口** - 将电话号码从一个租户移到另一个租户。 例如，你在 Microsoft 中拥有两个不同的租户，并且希望将电话号码从一个租户移动到另一个租户。  

  - **源租户域名** - 要从其中将电话号码移动到其他租户的租户。  

  - **源租户唯一标识符** - 源租户的租户 ID。 这是一个可选字段。  

  - **目标租户域名** - 要将电话号码移动到的租户。  

  - **目标租户唯一标识符** - 目标租户的租户 ID。 这是一个可选字段。  

  - **请求的日期时间*** - 希望号码从源租户移动到目标租户的日期和时间。 请参阅日期和时间。

  - **电话号码列表** - 想要从源租户移动到目标租户的电话号码列表。 Upload包含电话号码列表的 csv 文件。 

- **清单类型** 更改 - 更改电话号码 (类型) 。 例如，想要将 Microsoft 订阅者号码更改为服务号码。 有关 Microsoft 支持的电话号码类型详细信息，请参阅 [电话号码的类型](../different-kinds-of-phone-numbers-used-for-calling-plans.md)。

  - **转换为** - 选择可将号码转换为用户号码或服务号码。 

  - **首选日期/** 时间 * - 要更改数字的库存类型的日期和时间。 有关详细信息，请参阅日期和时间。

  - **复选框 -** 我了解，为了能够更新库存类型，需要取消分配我的电话号码 - Microsoft 无法处理电话号码类型更改请求，除非未分配租户中的电话号码。 如果请求在将来的日期进行此更改，则需要确保在请求的日期和时间之前未分配号码。 

  - **电话号码列表** - 要更改其类型的电话号码列表。 Upload包含电话号码列表的 csv 文件。 

- **新 TN 购置** - 从 Microsoft 购买新电话号码。  

  - **数字类型** - 选择数字的类型。 请参阅 [电话号码的类型](../different-kinds-of-phone-numbers-used-for-calling-plans.md)。

  - **尝试从 Teams** 管理中心门户获取电话号码 - 您是否尝试从 Microsoft Teams 管理中心门户购买这些电话号码，可在何处自助？  

  - **所需的电话号码数量** - 要购买的电话号码的计数。  

  - **省/** 市/自治区 - 需要电话号码的国家/地区中的州/省。  

  - **城市** - 需要其电话号码的州/省内的城市。  

  - **Office地址**- 这仅适用于某些国家/地区。 这是办公室的网站地址。  

  - **目录列表** - 这仅适用于某些国家/地区。 是否要使用电话号码发布公司信息？  

- **移植到** - 将现有电话号码从当前服务提供商移植到 Microsoft。  

  - **为端口订单命名** - 为端口请求提供容易记住的名称。 

  -  **请求的移植日期/时间*** - 您希望号码移植到 Microsoft 的日期和时间。 请注意，这不是有保证的移植日期，因为当前号码所有者必须首先批准我们的端口请求。 请参阅日期和时间。 

  - **移植号码列表** - 要移植到 Microsoft 的电话号码列表。 Upload包含电话号码列表的 csv 文件。 

  - **LOA (授权)** - 在此处附加已签名和填写的 LOA。 没有 LOA，Microsoft 无法处理端口请求。  

- **地址更新** - 更新紧急呼叫地址。 请注意，此字段仅适用于选定国家/地区。 

  - **位置 ID** - 紧急地址的位置 ID。 

  - **电话号码列表** - 要更改紧急地址的电话号码列表， ("说明"字段中输入所需) 。 Upload包含电话号码列表的 csv 文件。 

***日期和时间。** 如果选择"国家/地区 = 法国，日期 = 2021 年 8 月 14 日，时间 = 上午 10 点"，则请求将在 2021 年 8 月 14 日上午 10 点执行。 法语时间。 

#### <a name="case-title"></a>案例标题

输入总结您的请求的标题。  

#### <a name="additional-contacts-for-notifications"></a>通知的其他联系人

输入将收到来自 Microsoft 的自动状态通知的人的列表。 例如，想要按顺序排列端口，并且希望除你自己外，其他两个同事接收自动状态通知。 在"通知电子邮件"部分中提供 **同事** 的电子邮件地址。 此信息是可选的。 

#### <a name="description"></a>说明

描述你尝试实现的目标，并列出你的 Microsoft PSTN 服务台问题。  

#### <a name="additional-supporting-documents"></a>其他支持文档

Upload案例添加任何其他文档。  

## <a name="view-and-manage-existing-cases"></a>查看和管理现有事例

可以通过选择"查看我的现有案例 **"并选择** 案例编号来查看案例。 选择案例编号会将你重定向到案例详细信息。  (您也可以通过选择"查看公司案例"来查看公司案例) 您也可以：

- **通过选择"打开事例****"、"****所有事例**"或"已关闭 **事例"筛选事例**。

- **通过打开现有案例、向下滚动并选择** "添加注释"，与 PSTN 服务台就 **你的案例进行沟通**。 将出现一个新窗口。 在批注框中输入邮件。 附加任何支持文档 (（如果) 可帮助你提出请求，然后选择"提交 **"。**  

  来自 PSTN 服务台的响应将在同一时间线下显示。 当你的情况有更新时，你将收到更新的自动电子邮件通知。 

- **通过导航到** 现有案例、向下滚动并选择"取消案例"来 **取消案例。** 从下拉列表中选择取消的原因，然后选择"取消 **"。**  

- **解决案例** - 如果认为请求已完成，可以通过导航到现有案例、向下滚动并选择"解决案例" **来解决案例**。 选择"**关闭";** 现在，该案例将显示为"已 **解决 – 已解决问题"。**  


## <a name="related-topics-and-additional-resources"></a>相关主题和其他资源

- 有关与数字设置和配置、许可证、费用或计费相关的帮助，请参阅支持联系人商业版产品 [- 管理员帮助](/microsoft-365/admin/contact-support-for-business-products?tabs=online&view=o365-worldwide)。

- 有关在你的国家/地区可用的呼叫计划的信息，请参阅音频会议和呼叫计划的国家和地区 [可用性](../country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)。

- 有关可帮助你为组织选择 (类型) 的信息，请参阅不同类型的 [电话号码](../different-kinds-of-phone-numbers-used-for-calling-plans.md)。

- 有关为组织管理电话号码的信息，请参阅 [管理组织的电话号码](manage-phone-numbers-for-your-organization.md)。

- 有关紧急呼叫条款和条件的信息，请参阅 [紧急呼叫条款和条件](../emergency-calling-terms-and-conditions.md)。

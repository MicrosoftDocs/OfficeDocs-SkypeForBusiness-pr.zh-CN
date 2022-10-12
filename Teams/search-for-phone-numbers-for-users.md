---
title: 搜索用户的电话号码
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: davlick, roykuntz, jastark
ms.topic: article
ms.assetid: cc22c49a-c644-4151-a2fc-a1474148f8ba
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
- Calling Plans
description: 了解如何搜索可按国家或地区和城市分配给用户的电话号码，并指定所需的号码数量。
ms.openlocfilehash: fce7c59ba1d680ca6e364713f611833773111648
ms.sourcegitcommit: 179713dd2b22736c0d63060a6351eb69ec4abff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/12/2022
ms.locfileid: "68551506"
---
# <a name="search-for-telephone-numbers-for-users"></a>搜索用户的电话号码

当你在组织中设置用户以使用 Microsoft 提供的电话号码拨打和接听电话时，必须先使用 **Microsoft Teams 管理中心** 并获取要分配给用户的电话号码。 分配给用户的电话号码将是以前为组织获取的电话号码：编辑用户的属性并单击 **“分配**”时，该数字将列在下拉列表中。
  
在向用户分配 Microsoft 提供的电话号码之前，必须使用 **“获取新号码** ”页来搜索可用的电话号码。 可以按 **国家/地区 (市场)**、 **数字类型** 和 **位置** 进行搜索。 然后，你将看到在该国家/地区提供数字的运算符列表。

如果选择 Microsoft 作为操作员，可以通过输入用户所需的电话号码数量从 Teams 管理中心获取号码。 该页面将根据你仍可获取的数量自动限制数量。 如果选择运算符连接运算符，将定向到所选运算符的登陆页以完成编号顺序。

获取和管理电话号码的方式因 PSTN 连接选项而异：Microsoft 呼叫计划、运营商连接、Teams Phone Mobile 或直接路由。

本文适用于 [Microsoft 通话套餐](#search-for-telephone-numbers-for-microsoft-calling-plans)、 [运营商连接](#search-for-telephone-numbers-for-operator-connect-or-teams-phone-mobile)和 [Teams Phone Mobile](#search-for-telephone-numbers-for-operator-connect-or-teams-phone-mobile)。 有关所有选项的详细信息，请参阅 [管理组织的电话号码](/microsoftteams/manage-phone-numbers-landing-page)。

## <a name="search-for-telephone-numbers-for-microsoft-calling-plans"></a>搜索 Microsoft 通话套餐的电话号码

若要为用户搜索电话号码，请执行以下操作：
  
1. 转到 **Microsoft Teams 管理中心**。

2. 在左侧导航栏中选择 **“语音** > **电话号码** > **获取新号码**”。
  
    > [!IMPORTANT]
    > 若要在 Teams 管理中心左侧导航中看到 **“语音** ”选项，必须先购买至少一个 **企业 E5 或 E3 许可证**、一个 **电话系统** 加载项许可证或一个 **音频会议** 加载项许可证。  

3. 在 **“选择位置和数量** ”页上，从 **国家/地区 (市场)** 下拉列表中选择一个位置。

4. 从 **“数字”类型** 下拉列表中选择 **“用户**”。

5. 根据你选择的国家/地区 (市场) ，现在将有不同的选项可用于查找所需的电话号码。  

6. 在 **“数量**”下，输入组织所需的电话号码数，然后单击 **“下一步**”。 [!警告] 你有 10 分钟的时间选择电话号码。 如果花费超过 10 分钟，号码将返回到电话号码池。

    > [!NOTE]
    > 可以查看 (可用的电话号码，具体取决于数量旁边列出的) 许可证 **数。**
  
7. 在 **“获取号码”** 页上，选择所需的电话号码，单击 **“获取号码**”，然后单击 **“下一步**”。

    > [!IMPORTANT]
    > 可以获取的电话号码比拥有 Microsoft 许可证的电话号码多。 若要确定可以获取的电话号码数，请获取你的 Microsoft 呼叫计划许可证数，添加许可证数的 10%，然后添加 10，然后删除你已获取的号码。 例如，如果你有 100 个 Microsoft **国内呼叫计划** 和/或 **国际呼叫计划** 许可证，则可以保留 120 个电话号码，假设你尚未为这 100 个用户获取一些电话号码。 有关更多详细信息，请参阅[可以获取多少个电话号码？](./how-many-phone-numbers-can-you-get.md)

8. 在 **“确认** ”页上，验证你的选择，然后单击 **“放置顺序**”。

9. 返回到 **“电话号码** ”页时，选择要分配的电话号码或号码，然后单击 **“编辑** ”将其分配给用户。

## <a name="search-for-telephone-numbers-for-operator-connect-or-teams-phone-mobile"></a>搜索操作员连接或 Teams Phone Mobile 的电话号码

1. 转到 **Microsoft Teams 管理中心**。

2. 在左侧导航栏中选择 **“语音** > **电话号码** > **获取新号码**”。
  
    > [!IMPORTANT]
    > 若要在 Teams 管理中心左侧导航中看到 **“语音** ”选项，必须先购买至少一个 **企业 E5 或 E3 许可证**、一个 **电话系统** 加载项许可证或一个 **音频会议** 加载项许可证。  

3. 在 **“选择位置和数量** ”页上，从 **国家/地区 (市场)** 下拉列表中选择一个位置。

4. 从 **“数字”类型** 下拉列表中选择 **“用户**”。

5. 根据你选择的国家/地区 (市场) ，现在将有不同的选项可用于查找所需的电话号码。 可以通过选择 **“显示我的运** 算符”来筛选以仅显示已添加的运算符。

6. 如果已向操作员提供许可，则会将你定向到操作员的登陆页以完成订单过程。

7. 如果尚未向操作员提供许可，系统会指示你在 Teams 管理中心所选的运算符页上启用操作员。 有关详细信息，请参阅 [“启用运算符](operator-connect-configure.md#enable-an-operator)”。

8. 订单完成后，操作员会将电话号码上传到租户，你可以将其分配给用户。  

## <a name="related-topics"></a>相关主题

[管理组织的电话号码](manage-phone-numbers-landing-page.md)

[紧急呼叫条款和条件](./emergency-calling-terms-and-conditions.md)

[紧急呼叫免责声明标签](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)

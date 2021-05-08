---
title: 设置"公共区域"电话许可证
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 12/13/2018
ms.reviewer: kponnus
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Phone System
- seo-marvel-mar2020
description: '了解如何为大厅、接收区和会议室设置公用区域电话 '
ms.openlocfilehash: bb17b21eac262c160abc3e16a4b552fb32b97d00
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117110"
---
# <a name="set-up-the-common-area-phone-license-for-microsoft-teams"></a>为 Microsoft Teams 设置公共区域电话许可证
> [!NOTE]
> 公用区域电话不支持语音邮件。

公用区域电话通常放置在大厅等区域，或者供许多人进行呼叫的另一区域;例如，前台区域、大厅或会议电话。 常用区域电话使用与公用区域服务许可证绑定电话登录。 还必须适当设置 TeamsIPPhone 策略，使手机具有共同的区域用户体验。

在以下步骤中，我们将帮助你设置一个帐户电话系统为组织部署公用区域电话。 为获得更完整的会议室体验（包括音频会议），请考虑购买具有会议室设备的专用会议许可证。 

首先，需要购买公共区域电话 (CAP) 许可证，并确保拥有经过认证的电话。 若要搜索并了解有关认证电话的信息，请转到["Microsoft Teams设备"。](https://products.office.com/microsoft-teams/across-devices?ms.url=officecomteamsdevices&rtc=1) 

## <a name="step-1---buy-the-licenses"></a>第 1 步 - 购买许可证

1. 在Microsoft 365中心，转到"**计费**  >  **购买服务**"，然后展开"**其他计划"。**

    ![显示"公共区域"磁贴电话屏幕截图](media/set-up-common-area-phone-image1.png)

2. 选择 **"公共区域电话**  >  **立即购买"。**

3. 在"结帐"页面上，单击"**立即购买"。**

4. 展开 **附加内容订阅，** 然后单击购买通话套餐。 选择"国内 **呼叫计划"或****"国内和国际呼叫计划"。**

> [!NOTE]
> 如果使用 Microsoft 电话直接路由，则不需要呼叫计划许可证。

> [!NOTE]
> 无需添加许可证电话系统许可证。 许可证包含在公共区域电话许可证中。

有关许可证详细信息，请参阅Microsoft Teams[附加许可。](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md)

公共区域电话支持： 


|   |  公共区域电话  |
|---------|---------|
|Skype for Business |   &#x2714; |
|Microsoft Teams |   &#x2714; |
|电话系统 |    &#x2714; |
|音频会议 |       &#x2718; &sup1;  |
|Microsoft Intune |    &#x2718; |
|全球可用性 |       &#x2718; &sup2;  |
|频道可用性 |    EA、EAS、CSP、GCC、EES、Web Direct  |
|      |         |

&sup1;公用区域电话可以通过会议组织者提供的拨入号码加入音频会议

&sup2;在主权云中不可用  



## <a name="step-2---create-a-new-user-account-for-the-phone-and-assign-the-licenses"></a>第 2 步 - 为手机创建一个新的用户帐户并分配许可证

1. 在Microsoft 365管理中心，转到 **"活动**  >  **用户""**  >  **添加用户"。**

2. 输入用户名，例如"Main"作为名字，输入"接收"作为第二个名称。

3. 如果没有自动生成显示名称如"主前台"，请输入一个密码。

4. 输入用户名，例如"MainReception"或"Mainlobby"。

5. 对于公用区域电话，你可能希望手动设置密码，或者拥有所有公用区域电话的相同密码。 此外，还可以考虑清除" **使此用户首次登录时更改** 其密码"复选框。

6. 将许可证分配给用户。 在同一页面上，点击展开 **产品许可证**。 打开"公用区域"电话，选择"国内呼叫计划"**或"****国内和国际呼叫计划"。** 

    ![显示许可证分配的屏幕截图](media/set-up-common-area-phone-image2.png)

> [!NOTE]
> 如果使用 Microsoft 电话直接路由，则无需分配呼叫计划许可证。

有关详细信息，请参阅 [向用户分配许可证](/microsoft-365/admin/manage/assign-licenses-to-users)。

## <a name="step-3---assign-a-phone-number-to-the-common-area-phone-user-account"></a>第 3 步 - 将电话号码分配给公共区域电话用户帐户

使用Teams管理中心向用户分配号码。

1. 在"Teams管理中心"中，选择 **"语音**  >  **电话号码"。**

3.    从电话号码列表中选择一个号码，然后点击 **分配**。

4. 在 **"分配** "页面上的"语音用户"框中，键入将使用该电话的用户名，然后在"选择语音用户" **下拉列表中选择该用户** 。

5. 接下来，需要添加紧急地址。 从 **下拉列表中选择**"按城市搜索、按说明搜索"或"按位置搜索"，然后在文本框中输入城市、说明或位置。 搜索后，在" **选择紧急地址"** 下查找以选择正确的地址。

6. 点击 **保存**，你的用户将显示如下：

   ![显示许可证分配的屏幕截图](media/set-up-common-area-phone-image3.png)

> [!NOTE]
> 用户只有在应用了许可证后电话系统显示。 如果你刚执行了该操作，用户可能需要经过一段时间才能在列表中显示。

有关详细信息，请参阅 [获取用户的电话号码](getting-phone-numbers-for-your-users.md)。

您也可以将您拥有的电话号码与另一家运营商联系并"转Microsoft 365或Office 365。 请参阅[将电话号码转移到 Teams。](phone-number-calling-plans/transfer-phone-numbers-to-teams.md)
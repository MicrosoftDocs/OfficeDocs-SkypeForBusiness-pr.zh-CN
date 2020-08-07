---
title: 设置通用区域电话许可证
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
description: '了解如何为大厅、接待区和会议室设置公共区域电话 '
ms.openlocfilehash: 4e9e96c3384fa365004d4b4b5281c10decdc5dd1
ms.sourcegitcommit: 43d66693f6f08d4dcade0095bf613240031fec56
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/06/2020
ms.locfileid: "46581093"
---
# <a name="set-up-the-common-area-phone-license-for-microsoft-teams"></a>为 Microsoft Teams 设置公共区域电话许可证
> [!NOTE]
> 常见的区域电话不支持语音邮件。

常用的区域电话通常放置在一个区域中，该区域类似于供许多用户进行呼叫的前厅浏览区域或其他区域。例如，接收区域、会议厅或会议电话。 常见的区域电话已使用与通用区号许可证相关联的帐户登录。 还必须为手机设置适当的 TeamsIPPhone 策略，使其具有共同的区域用户体验。

在下面的步骤中，我们将帮助你设置电话系统的帐户，以便为你的组织部署公共的区域电话。 要获得更完整的会议室体验（包括音频会议），请考虑使用会议室设备购买专用的会议室许可证。 

首先，您需要购买一个通用的区域电话 (CAP) 许可证，并确保您有经过认证的电话。 若要搜索并了解有关已认证手机的详细信息，请转到 " [Microsoft 团队设备](https://products.office.com/microsoft-teams/across-devices?ms.url=officecomteamsdevices&rtc=1)"。 

## <a name="step-1---buy-the-licenses"></a>第 1 步 - 购买许可证

1. 在 Microsoft 365 管理中心，转到 "**帐单**  >  **购买服务**"，然后展开 "**其他计划**"。

    ![显示公共区域电话磁贴的屏幕截图](media/set-up-common-area-phone-image1.png)

2. 选择 "**通用区域电话**  >  **立即购买**"。

3. 在 "签出" 页面上，单击 "**立即购买**"。

4. 展开 **"加载项订阅**"，然后单击 "购买呼叫计划"。 选择 "**国内呼叫计划**" 或 "**国内和国际通话计划**"。

> [!NOTE]
> 如果您使用的是 Microsoft Phone 系统直接路由，则不需要呼叫计划许可证。

> [!NOTE]
> 无需添加电话系统许可证。 许可证包含在公共区域电话许可证中。

有关许可证的详细信息，请参阅[Microsoft 团队加载项许可](teams-add-on-licensing/microsoft-teams-add-on-licensing.md)。

通用区域电话许可证支持： 


|   |  公共区域电话  |
|---------|---------|
|Skype for Business |   &#x2714; |
|Microsoft Teams |   &#x2714; |
|电话系统 |    &#x2714; |
|音频会议 |       &#x2718; &sup1;  |
|Microsoft Intune |        &#x2718; &sup2; |
|全球可用性 |    &#x2714; |
|频道可用性 |    EA、EAS、CSP、GCC、EES、Web Direct  |
|      |         |

&sup1;常见的区域电话可以通过会议组织者提供的拨入号码加入音频会议

&sup2;在主权云中不可用  



## <a name="step-2---create-a-new-user-account-for-the-phone-and-assign-the-licenses"></a>第 2 步 - 为手机创建一个新的用户帐户并分配许可证

1. 在 Microsoft 365 管理中心中，转到 "**用户**  >  **活动用户**"  >  **添加用户**。

2. 输入用户名（如 "Main"）作为第一个名称，输入 "接收" 作为第二个名称。

3. 如果不自动生成类似 "主接收" 之类的显示名称，请输入一个显示名称。

4. 输入用户名，如 "MainReception" 或 "Mainlobby"。

5. 对于常见的区域电话，您可能需要手动设置密码或对所有公共区域电话设置密码。 此外，您可能会考虑清除 "**当用户首次登录时，使此用户更改其密码**" 复选框。

6. 将许可证分配给用户。 在同一页面上，点击展开**产品许可证**。 打开公共区域电话，然后选择**国内呼叫计划**或**国内和国际通话计划**。 

    ![显示许可证分配的屏幕截图](media/set-up-common-area-phone-image2.png)

> [!NOTE]
> 如果您使用的是 Microsoft Phone 系统直接路由，则无需分配呼叫计划许可证。

有关详细信息，请参阅[为用户分配许可证](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users)。

## <a name="step-3---assign-a-phone-number-to-the-common-area-phone-user-account"></a>第 3 步 - 将电话号码分配给公共区域电话用户帐户

使用 "团队管理中心" 为用户分配一个号码。

1. 在 "团队" 管理中心中，选择 "**语音**  >  **电话号码**"。

3.    从电话号码列表中选择一个号码，然后点击**分配**。

4. 在 "**分配**" 页面上的 "语音用户" 框中，键入将使用该电话的用户的名称，然后在 "**选择语音用户**" 下拉列表中选择用户。

5. 接下来，你需要添加紧急地址。 选择 "**按城市搜索**"、"**按说明搜索**" 或从下拉列表中选择 "**按位置搜索**"，然后在文本框中输入 "城市"、"说明" 或 "位置"。 搜索后，请在 "**选择紧急地址**" 下查看，选择合适的 "紧急地址"。

6. 点击**保存**，你的用户将显示如下：

   ![显示许可证分配的屏幕截图](media/set-up-common-area-phone-image3.png)

> [!NOTE]
> 仅当用户已应用电话系统许可证时，用户才会显示。 如果你刚执行了该操作，用户可能需要经过一段时间才能在列表中显示。

有关详细信息，请参阅[为用户获取电话号码](getting-phone-numbers-for-your-users.md)。

您还可以通过其他运营商和 "端口" 获取您的电话号码，或者将其转移到 Microsoft 365 或 Office 365。 请参阅[将电话号码转移给团队](phone-number-calling-plans/transfer-phone-numbers-to-teams.md)。

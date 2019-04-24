---
title: 为 Microsoft Teams 设置公共区域电话许可证
ms.author: lolaj
author: LolaJacobsen
manager: serdars
ms.date: 12/13/2018
ms.reviewer: kponnus
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
- M365-voice
ms.audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Phone System
description: '了解如何为会议厅、 接待区和会议室设置公用区域电话 '
ms.openlocfilehash: 74806d3dfc66c27c144d6c3a4e1ddd5c6c7e7c60
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32204851"
---
# <a name="set-up-the-common-area-phone-license-for-microsoft-teams"></a>为 Microsoft Teams 设置公共区域电话许可证

公用区域电话通常放置在会议厅类似的区域或可供很多人发起呼叫; 另一个区域例如，接收区域、 会议厅或会议电话。 公用区域电话设置为设备，而不是用户，并可以自动登录到网络。

下面的步骤中，我们将帮助您设置电话系统，以部署您的组织的公用区域电话帐户。 更完整的会议室的体验，包括音频会议，请考虑购买与会议的专用的会议室许可证会议室设备。 

执行所需的首要任务是公共区域电话 （帽） 许可证的购买并确保您已认证的电话。 要搜索并了解有关认证的电话的详细信息，请转到[Microsoft 团队设备](https://products.office.com/microsoft-teams/across-devices?ms.url=officecomteamsdevices&rtc=1)。 

## <a name="step-1---buy-the-licenses"></a>第 1 步 - 购买许可证

1. 在 Office 365 管理中心，转到**帐单** > **购买服务**，然后展开**其他计划**。

    ![显示 Common Area Phone 图块的屏幕截图](media/set-up-common-area-phone-image1.png)

2. 选择**公用区域电话** > **立即购买**。

3. 在**签出**页上单击**立即购买**。

4. 展开**加载项订阅**，然后单击要购买调用规划。 选择**国内调用计划**或**规划国内和国际呼叫**。

> [!NOTE]
> 不需要电话系统许可证。 许可证包含在公共区域电话许可证中。

有关许可证的详细信息，请参阅[Microsoft 团队加载项授权](teams-add-on-licensing/microsoft-teams-add-on-licensing.md)。

## <a name="step-2---create-a-new-user-account-for-the-phone-and-assign-the-licenses"></a>第 2 步 - 为手机创建一个新的用户帐户并分配许可证

1. 在 Office 365 管理中心，转到**用户** > **活动用户** > **添加用户**。

2. 输入的用户名称类似"Main"的第一个名称和"接收"第二个名称。

3. 输入显示名称，如果不是，则自动生成类似"Main 接收。"

4. 输入用户名"MainReception"或"Mainlobby。"

5. 为公用区域电话，您可能需要手动设置密码或已为所有公用区域电话的同一密码。 此外，您可能会认为有关清除**使此用户更改其首次登录时其密码**复选框。

6. 向用户分配许可证。 在同一页面上，点击展开**产品许可证**。 打开公用区域电话和选取**国内调用规划**或**国内和国际呼叫计划**。 

    ![屏幕截图显示许可证分配](media/set-up-common-area-phone-image2.png)

有关详细信息，请参阅[添加用户](https://docs.microsoft.com/office365/admin/add-users/add-users?redirectSourcePath=%252farticle%252f1970f7d6-03b5-442f-b385-5880b9c256ec&view=o365-worldwide)。

## <a name="step-3---assign-a-phone-number-to-the-common-area-phone-user-account"></a>第 3 步 - 将电话号码分配给公共区域电话用户帐户

业务管理中心的 Skype 用于向用户分配一个号码。

1. 在 Microsoft 365 管理中心中，选择**管理中心** > **团队 & Skype** > **旧门户**。

2. 在业务管理中心的 Skype，选择**语音** > **电话号码**。

3.  从电话号码列表中选择一个号码，然后点击**分配**。

4. 在**分配**页上，在语音用户框中，键入将在下拉列表中**选择一个语音用户**的电话，然后选择用户使用的用户的名称。

5. 此时你还需要添加一个紧急联系地址。 从下拉列表中，选择**搜索条件市/县**、**按说明搜索**或**按位置的搜索**，然后在文本框中输入市/县、 说明或位置。 一旦您搜索，查找下**选择紧急地址**选取适合您。

6. 点击**保存**，你的用户将显示如下：

   ![屏幕截图显示许可证分配](media/set-up-common-area-phone-image3.png)

> [!NOTE]
> 用户将仅显示它们是否能应用的电话系统许可证。 如果你刚执行了该操作，用户可能需要经过一段时间才能在列表中显示。

有关详细信息，请参阅[为用户获取电话号码](https://docs.microsoft.com/skypeforbusiness/what-are-calling-plans-in-office-365/getting-phone-numbers-for-your-users)。

您还可使您的电话号码与另一个运营商和"端口"或转移到 Office 365。 请参阅[传输到 Office 365 的电话号码](transfer-phone-numbers-to-office-365.md)。



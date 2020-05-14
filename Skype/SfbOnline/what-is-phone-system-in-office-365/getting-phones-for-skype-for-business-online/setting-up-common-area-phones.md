---
title: 设置公共区域电话
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: wasseemh
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Phone System
description: 了解部署步骤以获取正确的固件、根据需要更新它、分配许可证以及配置通用区域电话的设置。
ms.openlocfilehash: 02cab34b4a1f220e8f28ceeee794470191582704
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/13/2020
ms.locfileid: "44220402"
---
# <a name="set-up-common-area-phones"></a>设置公共区域电话
A common area phone (CAP) is typically placed in an area like a lobby or another area that is available to a lot of people. For example, a reception area phone, door phone or meeting room phone, CAPs are set up as devices rather than users and automatically sign into a network. In the steps below, we’ll help you set up an account for Phone System with Calling Plans so you can deploy these types of phones for your organization.

## <a name="prerequisites-for-common-area-phones"></a>公共区域电话的先决条件

你需要做的第一件事是确认你拥有以下组件：

- 购买公共区域电话许可证和通话套餐。
- 搜索并购买批准的手机（[在此处](deploying-skype-for-business-online-phones.md)查看列表）。
- Update the firmware on your phones (See supported firmware [in this topic](getting-phones-for-skype-for-business-online.md)).  You can check the firmware on you phone by doing this:
  - **Polycom VVX 电话**：转到 "**设置**  >  **状态**  >  **平台**  >  **应用程序**  >  **主**"。
  - **Yealink 电话**：转到主电话屏幕上的 "**状态**"。
  - **AudioCodes 电话**： **Menu**  >  从 "开始" 屏幕转到菜单**设备状态**  >  **固件版本**。
  - **Lync Phone Edition （LPE）手机**：转到**Menu**  >  "开始" 屏幕中的菜单 "**系统信息**"。

    Firmware updates are managed by the Skype for Business Service. Every Skype for Business certified phone's firmware is uploaded to the Skype for Business Update server, and device update is enabled on all phones by default.

    Depending on the inactivity time on the phone and polling intervals, phones will automatically download and install the latest certified builds. You can disable the device update settings by using the  [Set-CsIPPhonePolicy](https://docs.microsoft.com/powershell/module/skype/set-csipphonepolicy) cmdlet and setting the *EnableDeviceUpdate* parameter to `false`.

## <a name="setting-up-a-common-area-phone"></a>设置公共区域电话
你需要按照以下步骤操作：

### <a name="step-1---buy-the-licenses"></a>第 1 步 - 购买许可证
1. 在管理中心，转到 "**帐单**  >  **购买服务**"，然后添加**其他计划**。

    ![CAP-license.png](../../images/cap-license.png)
2. 在** 结账**页面上点击 >  **  公共区域电话**** ** 立即购买，点击** 立即购买** 。
3. Click on to expand **Add-on subscriptions** and then click on to buy a Calling Plan. Choose either the **Domestic Calling Plan** or **Domestic and International Calling Plan**.

> [!Note]
> You don't need a Phone System license. It's included with the **Common Area Phone** license.

有关许可证的更多信息，请参阅 [Skype for Business 和 Microsoft Teams 外接程序许可](../../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)。

### <a name="step-2---create-a-new-user-account-for-the-phone-and-assign-the-licenses"></a>第 2 步 - 为手机创建一个新的用户帐户并分配许可证
1. 在管理中心，转到 "**用户**  >  **活动用户**"  >  **添加用户**。
2. 输入**用户名**，如“Main”为第一个词，“Reception”为第二个词。
3. 如果没有自动生成“Main Reception”用户名，则输入**显示名称**。
4. 输入一个**用户名**，如“MainReception”或“Mainlobby”。
5. For common area phones, you might want to set a password manually or have the same password for all of you common area phones. Also, you might think about unselecting **Make this user change their password when they first sign in**.
6. 如果你仍在该页面，将许可证分配给该用户。 在同一页面上，点击展开**产品许可证**。 打开以下内容：
   - 公共区域电话
   - 然后需选择一个**国内通话套餐**或国内和**国际通话套餐**。

     许可证的分配将如下所示：

     ![TurnOnCapLicense.png](../../images/cap-license-turn-on.png)

     > [!Note]
     > 如你所知，Skype for Business 套餐 2 包含在**公共区域电话**许可证中。

有关详细信息，请参阅[添加用户](https://support.office.com/article/1970f7d6-03b5-442f-b385-5880b9c256ec)。

### <a name="step-3---assign-a-phone-number-to-the-common-area-phone-user-account"></a>第 3 步 - 将电话号码分配给公共区域电话用户帐户

![显示 Skype for Business 徽标的图标 ](../../images/sfb-logo-30x30.png) 使用**skype for business 管理中心**向用户分配电话号码

1. 在管理中心 >**管理中心**  >  **Skype**for business。
2. 在 **Skype for Business 管理中心** >  **语音** > **电话号码**。
3. 从电话号码列表中选择一个号码，然后点击**分配**。
4. 在**分配**页面的**语音用户**框中，输入用于电话的用户名称，然后在**选择语音用户**下拉列表中选择一个用户。
5. 此时你还需要添加一个紧急联系地址。 开始搜索时，在**选择紧急联系地址**下选择一个合适的地址。
6. 点击**保存**，你的用户将显示如下：

    ![cap-user-number.png](../../images/cap-user-number.png)

   > [!Note]
   > 用户只有应用了一个**电话系统**许可证，才会显示。 如果你刚执行了该操作，用户可能需要经过一段时间才能在列表中显示。

有关更多内容，请参阅[为用户获取电话号码](/microsoftteams/getting-phone-numbers-for-your-users)。

如果您想知道，您还可以将您的电话号码与其他运营商和 "*端口*" 一起使用，或者将它们转移到 Microsoft 365 或 Office 365。 请参阅[将电话号码转移给团队](/microsoftteams/phone-number-calling-plans/transfer-phone-numbers-to-teams)。

### <a name="step-4---setting-up-your-phone"></a>第 4 步 - 设置电话

**设置电话模式**

你的电话必须打开**公共区域电话模式**。 建议手动检查以确认。

**以下是如何设置宝利通 VVX 电话的示例**

- 通过以下步骤为宝利通 VVX 启用公共区域电话模式：
    1. 在浏览器中，连接到 Web 界面以便启用 CAP 模式。
    2. 然后进入**设置**并在 **Skype for Business 设置**选项中选择**公共区域电话**。
    3. 点击**是**保存设置。

- CAP 模式已启用，请使用电话的显示器设置电话。 显示屏应显示 **CAP 已启用**。 然后执行以下操作：

    1. 点击**设置**。
    2. 选择 "**高级**"。
    3. 输入密码。
    4. 在**管理设置**，选择**公共区域电话设置**。
    5. 启用 **CAP** 和 **CAP 管理模式**。
    6. 点击**保存配置**。

- 现在，电话已准备就绪，你可以在主屏幕上登录。

    1. 通过选择**设置** > **功能** > **Skype for Business** 登录。
    2. 选择**用户凭证**，然后选择 **Web 登录 (CAP)** 生成一个代码。
    3. 转至[设置门户](https://aka.ms/skypecap)，并登录为**管理员**。
    4. 输入显示名称（例如，Main Reception）。

       > [!Note]
       > 如果**仅搜索公共区域电话**被选中，清除该复选框并重新搜索。

    5. 在配对代码窗口中，输入电话上显示的代码并单击**设置**。

        执行最后一步之后，电话应自动登录。


> [!NOTE]
> CAP 设置站点声明它将 CAP 帐户的密码重置为随机密码。 请注意，CAP 所指的帐户是 Azure Active Directory (AAD) 帐户。 如果仅在 AAD 中创建了帐户，则该过程非常简单。 如果已将本地 Active Directory 同步到 AAD，并且你使用的是第三方 IDP 或 ADFS，CAP 设置将失败。 在这种情况下，你需要仅使用 Microsoft 365 或 Office 365/Azure Active Directory 帐户（例如，具有**onmicrosoft.com**域的帐户）才能使用 CAP 预配。


### <a name="related-topics"></a>相关主题

- 阅读[部署 Skype for Business Online 电话](deploying-skype-for-business-online-phones.md)，详细了解可用电话。
- [获取适用于 Skype for Business Online 的手机](getting-phones-for-skype-for-business-online.md)



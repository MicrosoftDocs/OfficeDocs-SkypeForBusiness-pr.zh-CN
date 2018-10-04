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
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- Phone System
description: 了解获取正确的固件，如果需要对其进行更新、 分配许可证和为公用区域电话配置设置的部署步骤。
ms.openlocfilehash: 3faa66235f3c3364a0da6560a6dc52daa252915b
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25370672"
---
# <a name="set-up-common-area-phones"></a>设置公共区域电话
A common area phone (CAP) is typically placed in an area like a lobby or another area that is available to a lot of people. For example, a reception area phone, door phone or meeting room phone, CAPs are set up as devices rather than users and automatically sign into a network. In the steps below, we’ll help you set up an account for Phone System with Calling Plans so you can deploy these types of phones for your organization.

## <a name="prerequisites-for-common-area-phones"></a>公共区域电话的先决条件

你需要做的第一件事是确认你拥有以下组件：

- 购买公共区域电话许可证和通话套餐。
- 搜索并购买批准的手机（[在此处](deploying-skype-for-business-online-phones.md)查看列表）。
- Update the firmware on your phones (See supported firmware [in this topic](getting-phones-for-skype-for-business-online.md)).  You can check the firmware on you phone by doing this:
  - **Polycom VVX 电话**： 转到**设置** > **状态** > **平台** > **应用程序** > **主**。
  - **Yealink 电话**： 主要电话屏幕上转到**状态**。
  - **AudioCodes 电话**： 转到**菜单** > **设备状态** > 从开始屏幕的**固件版本**。
  - **Lync Phone Edition (LPE) 电话**： 转到**菜单** > **系统信息**开始屏幕。

    Firmware updates are managed by the Skype for Business Service. Every Skype for Business certified phone's firmware is uploaded to the Skype for Business Update server, and device update is enabled on all phones by default.

    Depending on the inactivity time on the phone and polling intervals, phones will automatically download and install the latest certified builds. You can disable the device update settings by using the  [Set-CsIPPhonePolicy](https://docs.microsoft.com/powershell/module/skype/set-csipphonepolicy) cmdlet and setting the *EnableDeviceUpdate* parameter to `false`.

## <a name="setting-up-a-common-area-phone"></a>设置公共区域电话
你需要按照以下步骤操作：

### <a name="step-1---buy-the-licenses"></a>第 1 步 - 购买许可证
1. 在 Office 365 管理中心，转至**账单** > **购买服务**，然后添加**其他计划**。

    ![CAP-license.png](../../images/cap-license.png)
2. 在** 结账**页面上点击 >  **  公共区域电话**** ** 立即购买，点击** 立即购买** 。
3. Click on to expand **Add-on subscriptions** and then click on to buy a Calling Plan. Choose either the **Domestic Calling Plan** or **Domestic and International Calling Plan**.

> [!Note]
> You don't need a Phone System license. It's included with the **Common Area Phone** license.

有关许可证的更多信息，请参阅 [Skype for Business 和 Microsoft Teams 外接程序许可](../../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)。

### <a name="step-2---create-a-new-user-account-for-the-phone-and-assign-the-licenses"></a>第 2 步 - 为手机创建一个新的用户帐户并分配许可证
1. 在 Office 365 管理中心，转至**用户** > **活动用户** > **添加用户**。
2. 输入**用户名**，如“Main”为第一个词，“Reception”为第二个词。
3. 如果没有自动生成“Main Reception”用户名，则输入**显示名称**。
4. 输入一个**用户名**，如“MainReception”或“Mainlobby”。
5. For common area phones, you might want to set a password manually or have the same password for all of you common area phones. Also, you might think about unselecting **Make this user change their password when they first sign in**.

    > [!Tip]
    > WAIT!! Don't click **Add**!! Ugh, if you did click **Add** the do this: Office 365 admin center > **Users** > **Active users** and then find the user. Then on the user's properties page, click **Product licenses** and then click **Edit**. On the **Product licenses** page, turn on **Common Area Phone** and pick either a **Domestic Calling Plan** or a Domestic and **International Calling Plan**.

6. If you are still there, assign the licenses to this user. On the same page, click to expand **Product licenses**. Turn on the following:
   - 公共区域电话
   - 然后需选择一个**国内通话套餐**或国内和**国际通话套餐**。

     许可证的分配将如下所示：

     ![TurnOnCapLicense.png](../../images/cap-license-turn-on.png)

     > [!Note]
     > 如你所知，Skype for Business 套餐 2 包含在**公共区域电话**许可证中。

有关详细信息，请参阅[添加用户](https://support.office.com/article/1970f7d6-03b5-442f-b385-5880b9c256ec)。

### <a name="step-3---assign-a-phone-number-to-the-common-area-phone-user-account"></a>第 3 步 - 将电话号码分配给公共区域电话用户帐户

![sfb-logo-30x30.png](../../images/sfb-logo-30x30.png) 使用 **Skype for Business 管理中心**将电话号码分配给用户

1. 在 Office 365 管理中心 >**管理中心** > **for Business 的 Skype**。
2. 在 **Skype for Business 管理中心** >  **语音** > **电话号码**。
3. 从电话号码列表中选择一个号码，然后点击**分配**。
4. 在**分配**页面的**语音用户**框中，输入用于电话的用户名称，然后在**选择语音用户**下拉列表中选择一个用户。
5. While you're there you will need to add an emergency address. Once you search, look under the **Select emergency address** to pick the right one for you.
6. 点击**保存**，你的用户将显示如下：

    ![cap-user-number.png](../../images/cap-user-number.png)

   > [!Note]
   > Users will only show up if they have a **Phone System** licence applied. If you just did this, then sometimes it takes a bit for the user to show up in the list.

有关更多内容，请参阅[为用户获取电话号码](../../what-are-calling-plans-in-office-365/getting-phone-numbers-for-your-users.md)。

If you're wondering, you can also take your phone number that you have with another carrier and "*port*" or transfer them over to Office 365. See, [Transfer phone numbers to Office 365](/microsoftteams/transfer-phone-numbers-to-office-365).

### <a name="step-4---setting-up-your-phone"></a>第 4 步 - 设置电话

**设置电话模式**

The phone or phones you have must have the **Common Area Phone mode** turned on. You might want to check on that to make sure they do.

**以下是如何设置宝利通 VVX 电话的示例**

- 通过以下步骤为宝利通 VVX 启用公共区域电话模式：
    1. 在浏览器中，连接到 Web 界面以便启用 CAP 模式。
    2. 然后进入**设置**并在 **Skype for Business 设置**选项中选择**公共区域电话**。
    3. 点击**是**保存设置。

- Now that CAP mode is enabled, set up the phone using the phone's display. The display should show **CaAP is enabled**. Then do the following:

    1. 点击**设置**。
    2. 选择**高级**。
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
> The CAP provisioning site states it will reset the CAP account's password to a random password. Take note that the account the CAP is referring is the Azure Active Directory (AAD) account. If you created the account in AAD only then the process is straightforward. If you have synced an on premises Active Directory to AAD make sure to take note of the credentials you are using that will be changed by CAP provisioning.


### <a name="related-topics"></a>相关主题

- 阅读[部署 Skype for Business Online 电话](deploying-skype-for-business-online-phones.md)，详细了解可用电话。
- [获取适用于 Skype for Business Online 的电话](getting-phones-for-skype-for-business-online.md)



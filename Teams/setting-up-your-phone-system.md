---
title: 设置组织内的电话系统
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: makolomi
ms.topic: article
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
f1keywords: None
ms.custom:
- Phone System
description: '了解如何为你的组织设置电话系统（云 PBX）。 '
ms.openlocfilehash: 429cedb3d8bad25982e4eacdaa82f82cacfc75ae
ms.sourcegitcommit: 9fd23cf0e03dd8fcf7ed04ef09dcdac048ebb44a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2019
ms.locfileid: "37571531"
---
# <a name="setting-up-phone-system-in-your-organization"></a>设置组织内的电话系统

The following is a step-by-step guide for setting up Phone System in Office 365. Links to additional, detailed information are available at the end of each step.

## <a name="step-1-make-sure-that-phone-system-is-available-in-your-country-or-region"></a>步骤 1： 请确保您的国家或地区可用使用电话系统

1.  首先转到 [国家和地区的音频会议和呼叫计划的可用性](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md) ，并从页面顶部列表中选择您的国家或地区。 
2.  在 **电话系统** ，下查看的功能和详细信息的列表。 
3.  如果可用电话系统，转到步骤 2。 

**若要了解有关电话系统和音频会议的区域可用性的详细信息，请参阅 [国家和地区音频会议和调用计划的可用性](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md) 。**

## <a name="step-2-buy-and-assign-phone-system-and-calling-plan-licenses"></a>步骤 2： 购买和分配电话系统和通话套餐许可证

将电话系统和呼叫计划许可证分配给单个用户的步骤与分配 Office 365 许可证相同。请参阅[分配 Microsoft 团队许可证](assign-teams-licenses.md)。如果要批量分配多个用户，请参阅[分配 Microsoft 团队许可证](assign-teams-licenses.md)。

## <a name="step-3-get-phone-numbers-for-your-users"></a>步骤3：为用户获取电话号码

在您可以将组织中的用户设置为拨打和接收电话呼叫之前，您必须为他们获取电话号码。

有三种方法可为用户获取号码：
- 使用 Skype for Business 管理中心获得新号码。
- 获取在Skype for Business管理中心不可用的新号码。
- 将您的现有服务提供商或电话运营商中的现有号码移植或转移到 Office 365。

You must use the **Add new user numbers** page to see, search, acquire, and reserve those numbers. You can search by Country/Region, State, and City, and then enter the number of phone numbers you will need for your users.

### <a name="get-new-user-phone-numbers"></a>获取新的用户电话号码 
 
![](media/sfb-logo-30x30.png) **使用 skype for business 管理中心**显示 skype for business 徽标的图标

1. 使用你的工作或学校帐户登录 Microsoft 365。

2. 转到**Microsoft 365 管理中心** > **Skype for business**。
    
3. 在左侧导航中，转到 "**语音** > **电话号码**"，单击 "**添加新号码" 添加新号码** !["](media/c224fbd0-f0f5-46ce-a1a7-73adf4540ef7.png)添加" 按钮，显示为加号，然后单击 "**新用户号码**"。
    
### <a name="get-new-numbers-that-arent-available-in-the-skype-for-business-admin-center"></a>获取在Skype for Business管理中心不可用的新号码
  
Sometimes (depending on your country/region) you won't be able to get your new numbers using the Skype for Business admin center. In this case, you will need to download a form and send it back to us. See [Manage phone numbers for your organization](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) to learn how to request new user numbers.   
  
### <a name="port-or-transfer-phone-numbers-from-your-service-provider-or-phone-carrier"></a>将你的服务提供商或电话运营商提供的电话号码转网或转移
  
- If you need 999 or fewer phone numbers for your users, you can use the **New Local Number Port Order** wizard in the Skype for Business admin center. Follow the steps found in [Transfer phone numbers to Office 365](transfer-phone-numbers-to-office-365.md) to transfer your phone numbers over to Skype for Business Online.
    
- 如果您需要移植超过999的电话号码，请参阅[管理您的组织的电话号码](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)以提交 "订单订单服务请求" 或 "订单" 以获取所有这些电话号码均已移植到 Office 365。 

**有关获取新电话号码或转接现有号码的详细信息，请参阅 [管理您的组织的电话号码](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) 。**

## <a name="step-4-get-service-phone-numbers-audio-conferencing-call-queues-auto-attendants"></a>步骤 4： 获取服务电话号码 （音频会议呼叫的队列，自动助理）

In addition to getting phone numbers for your users from Office 365, you can search and acquire toll or toll-free phone numbers for services such as audio conferencing (for conference bridges), auto attendants, and call queues (also called service numbers). Service phone numbers have a higher concurrent calling capacity than user or subscriber phone numbers. For example, a service number can handle 100s of calls simultaneously, whereas a user's phone number can only handle a few calls simultaneously.

### <a name="get-new-service-numbers"></a>获取新服务号码

![](media/sfb-logo-30x30.png) **使用 skype for business 管理中心**显示 skype for business 徽标的图标


1. 使用你的工作或学校帐户登录 Office 365。

2. 转到**Microsoft 365 管理中心** > **Skype for business**。

3. 在左侧导航中，转到 "**语音** > **电话号码** > " 以**添加新号码**，然后单击 "**新的服务号码**"。

    > [!IMPORTANT]
    > 要在 Skype for Business 管理中心的左侧导航中看到 "**语音**" 选项，您必须首先购买至少一个**企业版 E5 许可证**、一个**电话系统**附加许可证或一个**音频会议**附加设备许可证。

### <a name="get-new-numbers-that-arent-available-in-the-skype-for-business-admin-center"></a>获取在Skype for Business管理中心不可用的新号码
  
Sometimes (depending on your country/region) you won't be able to get your new numbers using the Skype for Business admin center. In this case, you will need to download a form and send it back to us. See [Manage phone numbers for your organization](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) to learn how to request new numbers. 

### <a name="port-or-transfer-existing-service-numbers"></a>转网或转移现有服务号码

If you want to transfer service numbers from your current service provider or carrier, you need to manually submit a port order to Microsoft. You have to submit separate port orders for each type of service number (toll vs. toll-free) that you will be transferring using a Letter of Authorization (LOA). In the Letter of Authorization (LOA), you must select the correct type of service number. When contacting Microsoft support, please make sure you specify that you are transferring a service number (*and not a user or subscriber number*), or the concurrent calling capacity may not be enough to handle call volumes. If you want to transfer phone numbers or do other things with your phone numbers, see [Manage phone numbers for your organization](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md).

## <a name="step-5-if-you-want-to-set-up-calling-plans"></a>步骤 5： 如果您想要设置调用计划

If you have been following the steps above, you have already bought and assigned Phone System and licenses and a Calling Plan (step 2) and acquired phone numbers for your users (step 3), so your calling plan is partially set up. Follow the three procedures below to complete the setup of your Calling Plan.

### <a name="add-emergency-addresses-and-locations-for-your-organization"></a>为您的组织添加紧急地址和位置

1. 在 "**语音**" 页面上，选择 "**紧急位置** > **添加新地址**"。

2. 在 "**新建地址**" 窗格中，为您的地址输入一个名称，然后填写其余的框。
    
     ![新地址窗格的屏幕截图](media/dc1c5ef3-0554-4fb7-9ab1-5ea3ac9e5eb5.png)
  
    > [!TIP]
    > [!提示] 对于英语客户，如果街道名称是数字，请务必在结尾加上"st"或"th"，如上图所示。

3. 选择" **验证**"。

    如果需要，系统将提示你对地址进行更改。

    > [!CAUTION]
    > Validating a street or civic address involves making sure that it is legitimate and correctly formatted. It is possible that a partially correct emergency address, such as if you mistyped the name of the city, may still pass validation. Even though it's misspelled and passed validation, the combination of the misspelled name of city along with the other correct parts of the address are enough information to route the call to the appropriate emergency dispatch center.

    > [!TIP]
    > [!提示] 如果地址需要更正才能处理紧急响应，系统将显示一个绿色横幅，通知你地址已更新。

4. 验证地址之后，请选择" **保存**"。

### <a name="assign-phone-numbers-and-emergency-addresses-to-users"></a>为用户分配电话号码和紧急地址

> [!TIP]
> [!提示] 如果在执行此步骤前刚刚向企业添加了更多人员，这些人员可能需要 **几小时** 才会显示在" **语音用户**"页面。 系统存在延迟。

1. 在 "**语音用户**" 页面上，选择要为其分配电话号码和紧急地址的人员。

2. 在"操作"窗格中，单击" **分配号码**"。

3. 在 "**分配号码**" 页面上的 "**选择要分配的号码**" 列表中，选择用户的电话号码。

4. 若要选择紧急地址，请在框中输入城市的名称，然后选择 "**搜索**"。

    > [!IMPORTANT]
    > If you are outside the United States, your numbers already have an emergency address, but you can change it now. See [Assign or change an emergency address for a user](/skypeforbusiness/what-are-calling-plans-in-office-365/assign-or-change-an-emergency-address-for-a-user). 
  
5. 在分配电话号码和紧急地址之后，选择" **保存**"。

### <a name="tell-your-users-about-their-new-phone-numbers"></a>告诉你的用户有关其新电话号码的信息


我们建议通过发送邮件或使用企业的首选通信方式，将新电话号码告知用户。

下面介绍了他们在**Skype For business**应用中可以看到的电话号码：

1. 登录到桌面上的 Skype for Business。
    
2. 选择 **设置** > **工具选项** > **选项**。 
    
     !["工具" 菜单上选项的屏幕截图](media/20637117-91d7-4a7e-9f06-7abc634a9211.png)
  
3. 然后，选择" **电话**"。 
    
    ![Skype for Business 电话选项的屏幕截图](media/0128d667-2bf8-4165-b703-e9b78a15b63c.png)
 
In **Microsoft Teams**, users can see their phone number by clicking **Calls** in the left navigation. The phone number is shown above the dial pad.

![单击 "呼叫" 后可用选项的屏幕截图](media/teams-phone-number.png)

**有关设置通话套餐所涉及的所有步骤的更详细信息，请参阅 [设置通话套餐](set-up-calling-plans.md) 。**


## <a name="step-6-if-you-want-to-set-up-audio-conferencing"></a>步骤 6： 如果您想要设置音频会议

Sometimes people in your organization will need to use a phone to call in to a meeting. Skype for Business and Microsoft Teams include the audio conferencing feature for just this situation! People can call in to Skype for Business or Microsoft Teams meetings using a phone, instead of using the Skype for Business or Microsoft Teams app on a mobile device or PC.

You only need to set up Audio Conferencing for people who plan to schedule or lead meetings. Meeting attendees who dial in don't need any licenses assigned to them or other setup.
  
有关音频会议的常见问题，请参阅 [音频会议的常见问题](audio-conferencing-common-questions.md) 。
    
1. 如果您购买了 "**音频会议**附加设备许可证" 和 "通讯信用点数" 许可证，也可以分配这些许可证。有关说明，请参阅[分配 Microsoft 团队许可证](assign-teams-licenses.md)。

    Decide on your audio conferencing provider. An audio conferencing provider supplies an audio conferencing bridge. The conferencing bridge sets your dial-in phone numbers, PINs, and conference IDs for meetings. Decide whether to use Microsoft or a third-party audio conferencing provider:

    > [!NOTE]
    > Microsoft Teams 用户不能用户第三方音频会议提供商。

    - **Microsoft 作为您的音频会议提供商**： 如果您希望音频会议的最简单的解决方案，选择 Microsoft 作为您的音频会议提供商。
    
    - **Third party as your audio conferencing provider**: If you are in a country where Audio Conferencing in Office 365 isn't available, the service quality isn't great because of its location, or you have an existing contract, choose a third-party audio conferencing provider. To find a provider, go to [Microsoft PinPoint](http://go.microsoft.com/fwlink/?LinkId=797530).
 
2. Assign the audio conferencing provider to people who lead or schedule meetings. See [Assign Microsoft as the audio conferencing provider](/skypeforbusiness/audio-conferencing-in-office-365/assign-microsoft-as-the-audio-conferencing-provider).

3. Set up meeting invitations. The following steps are optional, but a lot of admins like to do them: 
  
   1. [在 Skype For business 中自定义会议邀请](/skypeforbusiness/set-up-skype-for-business-online/customize-meeting-invitations)。为用户设置的拨入号码将自动添加到发送给与会者的会议邀请。但是，你可以添加自己的帮助和法律链接、短信和小型公司图形。
    
   2. 为在[Skype for](/skypeforbusiness/audio-conferencing-in-office-365/set-the-phone-numbers-included-on-invites) Business 或[Microsoft 团队中](set-the-phone-numbers-included-on-invites-in-teams.md)的邀请中包含的会议组织者设置音频会议电话号码。这是将在由用户安排的会议中显示的电话号码。
    
   3. [在 Skype for](/skypeforbusiness/audio-conferencing-in-office-365/set-auto-attendant-languages-for-audio-conferencing) Business 或[Microsoft 团队](set-auto-attendant-languages-for-audio-conferencing-in-teams.md)中为音频会议设置自动助理语言，音频会议自动助理在拨入音频会议电话号码时使用该功能问候呼叫者。仅当你使用 Microsoft 作为音频提供商时，此步骤才适用。
    
   4. 为[Microsoft 团队中](set-the-pin-length-for-audio-conferencing-meetings-in-teams.md)的音频会议会议设置 PIN 长度。
    
      > [!NOTE]
      > This feature is not yet available to customers using Office 365 operated by 21Vianet in China. To learn more, see [Learn about Office 365 operated by 21Vianet](https://support.office.com/article/A8AB5061-3346-4DA0-BB7C-5260822B53AE).

**有关音频会议的详细信息，请参阅[设置 Microsoft 团队的音频会议](set-up-audio-conferencing-in-teams.md)。**

## <a name="step-7-if-you-want-to-set-up-a-cloud-call-queue"></a>步骤7：要设置云呼叫队列

云呼叫队列包括当某人拨打您的组织的电话号码时使用的问候语、自动保持通话的功能，以及搜索下一个可用的呼叫代理以处理呼叫，而通话的人员在保持状态时收听音乐。您可以为您的组织创建单个或多个通话队列。

Before you can create and set up your call queues, you will need to get or transfer your existing toll or toll-free service numbers. After you get the toll or toll-free service phone numbers, they will show up in **Skype for Business admin center** > **Voice** > **Phone numbers**, and the **Number type** listed will be listed as **Service - Toll-Free**. To get your service numbers, see [Getting service phone numbers for Skype for Business and Microsoft Teams](/microsoftteams/getting-service-phone-numbers) or if you want to transfer and existing service number, see [Transfer phone numbers to Office 365](transfer-phone-numbers-to-office-365.md).
  
> [!NOTE]
> If you are outside the United States, you can't use the Skype for Business admin center to get service numbers. Go to [Manage phone numbers for your organization](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) instead to see how to do it from the outside of the United States.

若要创建新的呼叫队列，请在**Skype for business 管理中心**中，单击 "**呼叫路由** > **呼叫队列**"，单击 "**新增**"，然后按照 "[创建云呼叫队列](/SkypeForBusiness/what-is-phone-system-in-office-365/create-a-phone-system-call-queue#step-3---create-a-new-call-queue)" 的**步骤 3**中的说明进行操作。

**有关通话队列的详细信息，请参阅[创建云呼叫队列](/SkypeForBusiness/what-is-phone-system-in-office-365/create-a-phone-system-call-queue)。**

## <a name="step-8-if-you-want-to-set-up-a-cloud-auto-attendant"></a>步骤8：如果要设置云自动助理

Auto attendants let people that call in to your organization and navigate a menu system to get them to the right department, call queue, person, or the operator. You can create an auto attendant for your organization by using the Skype for Business admin center.

若要创建新的自动助理，请在 Skype for business 管理中心中，单击 "**呼叫路由** > **自动助理**"，单击 "**添加新**"，然后按照创建云自动助理的**步骤 2**中的每个页面上的说明进行操作。 [](https://docs.microsoft.com/microsoftteams/create-a-phone-system-auto-attendant#step-2---create-a-new-auto-attendant).


**有关云自动助理的更多详细信息，请参阅[设置云自动助理](https://docs.microsoft.com/microsoftteams/create-a-phone-system-auto-attendant)。**

## <a name="step-9-assign-service-phone-numbers-audio-conferencing-call-queues-auto-attendants"></a>步骤 9：获取服务电话号码 （音频会议呼叫的队列，自动助理）

Once you have your service numbers from **Step 4 above**, you need to assign them to each type of service that you want. For example, if you want a dedicated service phone number (toll or toll-free), you will need to assign the number to the conferencing bridge.

- 对于音频会议，您可以通过转到**Microsoft 365 管理中心** > **管理中心** > **Skype for business** > **音频会议**，将专用号码分配给会议网桥，然后单击您也能[在您的音频会议网桥上更改收费电话号码或免费电话号码](change-the-phone-numbers-on-your-audio-conferencing-bridge.md)。

- 对于自动助理，你可以通过转到**Microsoft 365 管理中心** > **管理中心** > 的**Skype for** > business**呼叫路由** > **自动助理，将专用号码分配给自动助理**并单击自动助理。在 "**常规**" 页面上，您已拥有的服务号码将在 "**电话号码**" 下拉列表中列出。有关详细信息，请参阅[设置云自动助理](https://docs.microsoft.com/microsoftteams/create-a-phone-system-auto-attendant)。
- 对于呼叫队列，您可以通过转到**Microsoft 365 管理中心** > **管理中心** > **Skype for** > business**呼叫路由** > **呼叫队列**，将专用号码分配给呼叫队列，然后单击通话队列。在 "**常规**" 页面上，您已拥有的服务号码将在 "**电话号码**" 下拉列表中列出。有关详细信息，请参阅[创建云呼叫队列](https://docs.microsoft.com/microsoftteams/create-a-phone-system-call-queue)。

**有关获取新服务号码和移植现有服务号码的详细信息，请参阅 [获取服务电话号码](/microsoftteams/getting-service-phone-numbers) 。**

## <a name="step-10-set-up-communications-credits-for-your-organization"></a>步骤10：为你的组织设置通讯信用点数

You will need to set up Communications Credits if you would like to use toll-free numbers with Skype for Business and Microsoft Teams. Also, we recommend that you set up Communications Credits for your Calling Plans (Domestic or International) and Audio Conferencing users who need the ability to dial out to **any destination**. Many countries/regions are included, but some destinations may not be included in your Calling Plan or Audio Conferencing subscriptions. If you don't set up Communications Credits billing and assign a **Communications Credits** license to your users and you run out minutes for your organization (depending on your Calling Plan or Audio Conferencing plan in your country/region), those users won't be able to make calls or dial out from Audio Conferencing meetings. You can get more information, including recommended funding amounts, by reading [What are Communications Credits?](what-are-communications-credits.md)
  
> [!NOTE]
> 若要找出它的费用， [请参阅下面的价格](https://go.microsoft.com/fwlink/p/?LinkId=799523 )  。

### <a name="to-set-up-communications-credits"></a>设置通信点数

1. 使用你的工作或学校帐户登录 Microsoft 365。

2. 在管理中心的左侧导航中，转到 "**计费** > **订阅** > **加载项** > **购买加载项**"，然后选择 "**立即购买**的**通讯点数** > "。

3. 在**通信点数**订阅页中，填写您的信息，然后单击**下一步**。

4. 输入您的付款信息并单击 **下订单** 。
    >[!IMPORTANT]
    >If you are a volume licensing customer, you may choose your enterprise agreement number for payment. If you have multiple enterprise agreement numbers, you will be able to select which enterprise agreement you would like to use for payment. You will also be given an opportunity to specify a purchase order number to associate with the enterprise agreement number (if applicable).
    
**有关通信点数设置的详细信息，请参阅 [为您的组织设置通信点数](set-up-communications-credits-for-your-organization.md) 。**
  
### <a name="assign-a-communications-credits-license-to-users"></a>将通信点数许可证分配给用户

1. 使用你的工作或学校帐户登录 Office 365。

2. 在 Microsoft 365 管理中心的左侧导航中，转到 "**用户** > **活动用户**"，然后从列表中选择一个或一个用户。

3. 在"操作"窗格中的" **产品许可证**"下，单击" **编辑**"。

4. 在 "**产品许可证**" 页面上，将 "**通信信用点数**" 切换到 **"开"** 以分配此许可证，然后单击 "**保存**"。

    > [!NOTE]
    > 即使你有分配了**企业版 E5**许可证的用户，仍建议你执行此操作。

**若要了解有关分配通信点数许可证的详细信息，请参阅 [为您的组织设置通信点数](set-up-communications-credits-for-your-organization.md) 。**

## <a name="related-topics"></a>相关主题
[以下是 Office 365 中的电话系统功能](here-s-what-you-get-with-phone-system.md)

[获取 Skype for Business 和 Microsoft Teams 的服务电话号码](/microsoftteams/getting-service-phone-numbers)

[音频会议和通话套餐的国家/地区可用性](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)
    
  
 

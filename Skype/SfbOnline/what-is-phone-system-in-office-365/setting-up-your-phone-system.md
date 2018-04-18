---
title: Setting up Phone System in your organization
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: makolomi
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Phone System
- Strat_SB_PSTN
description: 'Learn how to set up Phone System (Cloud PBX) for your organization. '
ms.openlocfilehash: 95fed9f26cefddce80de5c8f12a0e18d7368d1f4
ms.sourcegitcommit: a0d3e7a177fcd0667ab0d7d0e904f4053b09a92d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2018
---
# <a name="setting-up-phone-system-in-your-organization"></a>Setting up Phone System in your organization

The following is a step-by-step guide for setting up Phone System in Office 365. Links to additional, detailed information are available at the end of each step.  

## <a name="step-1-make-sure-that-phone-system-is-available-in-your-country-or-region"></a>Step 1: Make sure that Phone System is available in your country or region

1.  First go to [Country and region availability for Audio Conferencing and Calling Plans](../country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md), and select your country or region from the list at the top of the page. 
2.  Under **Phone System**, review the list of features and details. 
3.  If Phone System is available, go to step 2. 

**To learn more about regional availability of Phone System and Audio Conferencing, see [Country and region availability for Audio Conferencing and Calling Plans](../country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md).**

## <a name="step-2-buy-and-assign-phone-system-and-calling-plan-licenses"></a>Step 2: Buy and assign Phone System and Calling Plan licenses

To assign a Phone System and Calling Plan license to a single user the steps are the same as assigning an Office 365 license. See [Assign Skype for Business and Microsoft Teams licenses](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md). If you want to assign multiple users in bulk, see (../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).

## <a name="step-3-get-phone-numbers-for-your-users"></a>Step 3: Get phone numbers for your users

Before you can set up users in your organization to make and receive phone calls, you must get phone numbers for them. 

You have three ways of getting numbers for your users: 
- 使用 Skype for Business 管理中心获得新号码。
- Get new numbers that aren't available in the Skype for Business admin center.
- Port or transfer your existing numbers from your current service provider or phone carrier to Office 365.

You must use the **Add new user numbers** page to see, search, acquire, and reserve those numbers. You can search by Country/Region, State, and City, and then enter the number of phone numbers you will need for your users. 

### <a name="get-new-user-phone-numbers"></a>Get new user phone numbers 
  
1. 使用你的工作或学校帐户登录 Office 365。
    
2. Go to the **Office 365 admin center** > **Skype for Business**.
    
3. In the left navigation go to **Voice** > **Phone numbers**, click **Add new number** ![Add button](../images/c224fbd0-f0f5-46ce-a1a7-73adf4540ef7.png), and then click **New user numbers**.
    
### <a name="get-new-numbers-that-arent-available-in-the-skype-for-business-admin-center"></a>Get new numbers that aren't available in the Skype for Business admin center
  
Sometimes (depending on your country/region) you won't be able to get your new numbers using the Skype for Business admin center. In this case, you will need to download a form and send it back to us. See [Manage phone numbers for your organization](../what-are-calling-plans-in-office-365/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) to learn how to request new user numbers.   
  
### <a name="port-or-transfer-phone-numbers-from-your-service-provider-or-phone-carrier"></a>将你的服务提供商或电话运营商提供的电话号码转网或转移
  
- If you need 999 or fewer phone numbers for your users, you can use the **New Local Number Port Order** wizard in the Skype for Business admin center. Follow the steps found in [Transfer phone numbers to Office 365](..//what-are-calling-plans-in-office-365/transfer-phone-numbers-to-office-365.md) to transfer your phone numbers over to Skype for Business Online.
    
- If you need to port more than 999 phone numbers, see [Manage phone numbers for your organization](../what-are-calling-plans-in-office-365/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) to submit a port order service request or order to get all of these phone numbers ported over to Office 365. 

**For detailed information about getting new phone numbers or transferring existing numbers, see [Manage phone numbers for your organization](../what-are-calling-plans-in-office-365\manage-phone-numbers-for-your-organization\manage-phone-numbers-for-your-organization.md).**

## <a name="step-4-get-service-phone-numbers-audio-conferencing-call-queues-auto-attendants"></a>Step 4: Get service phone numbers (audio conferencing, call queues, auto attendants)

In addition to getting phone numbers for your users from Office 365, you can search and acquire toll or toll-free phone numbers for services such as audio conferencing (for conference bridges), auto attendants, and call queues (also called service numbers). 服务电话号码具有比用户或订阅者电话号码更高的并发呼叫容量。 For example, a service number can handle 100s of calls simultaneously, whereas a user's phone number can only handle a few calls simultaneously.

### <a name="get-new-service-numbers"></a>获取新服务号码

1. 使用你的工作或学校帐户登录 Office 365。
    
2. Go to the **Office 365 admin center** > **Skype for Business**.
    
3. In the left navigation go to **Voice** > **Phone numbers** > **Add new number**, and then click **New service numbers**.
    
    > [!IMPORTANT] 
    > For you to see the **Voice** option in the left navigation in the Skype for Business admin center, you must first buy at least one **Enterprise E5 license**, one **Phone System** add-on license, or one **Audio Conferencing** add-on license.
    
### <a name="get-new-numbers-that-arent-available-in-the-skype-for-business-admin-center"></a>Get new numbers that aren't available in the Skype for Business admin center
  
Sometimes (depending on your country/region) you won't be able to get your new numbers using the Skype for Business admin center. In this case, you will need to download a form and send it back to us. See [Manage phone numbers for your organization](../what-are-calling-plans-in-office-365/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) to learn how to request new numbers. 

### <a name="port-or-transfer-existing-service-numbers"></a>转网或转移现有服务号码

如果要转移来自当前服务提供商或运营商的服务号码，需要向 Microsoft 手动提交转网订单。 You have to submit separate port orders for each type of service number (toll vs. toll-free) that you will be transferring using a Letter of Authorization (LOA). In the Letter of Authorization (LOA), you must select the correct type of service number. When contacting Microsoft support, please make sure you specify that you are transferring a service number (*and not a user or subscriber number*), or the concurrent calling capacity may not be enough to handle call volumes. If you want to transfer phone numbers or do other things with your phone numbers, see [Manage phone numbers for your organization](../what-are-calling-plans-in-office-365/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md).

## <a name="step-5-if-you-want-to-set-up-calling-plans"></a>Step 5: If you want to set up Calling Plans

If you have been following the steps above, you have already bought and assigned Phone System and licenses and a Calling Plan (step 2) and acquired phone numbers for your users (step 3), so your calling plan is partially set up. Follow the three procedures below to complete the setup of your Calling Plan.

### <a name="add-emergency-addresses-and-locations-for-your-organization"></a>Add emergency addresses and locations for your organization

1. On the **Voice** page, choose **Emergency locations** > **Add new address**.
    
2. 在" **新址**"窗格中，输入你的地址名称，然后填写剩余框。
    
     ![When you enter a new emergency address, the formatting of the street name might cause an error.](../images/dc1c5ef3-0554-4fb7-9ab1-5ea3ac9e5eb5.png)
  
    > [!TIP]
    > [!提示] 对于英语客户，如果街道名称是数字，请务必在结尾加上"st"或"th"，如上图所示。 
  
3. 选择" **验证**"。
    
    如果需要，系统将提示你对地址进行更改。 
    
    > [!CAUTION]
    > [!警告] 验证街道或市镇地址涉及确保该地址是合法的并且格式设置正确。 It is possible that a partially correct emergency address, such as if you mistyped the name of the city, may still pass validation. 即使拼写错误并通过验证，拼错的城市名称和地址的其他正确部分相结合也足以将呼叫路由到合适的紧急派遣中心。 
  
    > [!TIP]
    > [!提示] 如果地址需要更正才能处理紧急响应，系统将显示一个绿色横幅，通知你地址已更新。 
  
4. 验证地址之后，请选择" **保存**"。
    
### <a name="assign-phone-numbers-and-emergency-addresses-to-users"></a>为用户分配电话号码和紧急地址

> [!TIP]
> [!提示] 如果在执行此步骤前刚刚向企业添加了更多人员，这些人员可能需要 **几小时** 才会显示在" **语音用户**"页面。 系统存在延迟。
  
1. On the **Voice users** page, select the people who you want to assign a phone number and emergency address to.
    
2. 在"操作"窗格中，单击" **分配号码**"。
    
3. On the **Assign number** page, in the **Select number to assign** list, select the phone number for the user.
    
4. To select an emergency address, enter name of the city in the box and choose **Search**.
    
    > [!IMPORTANT]
    > If you are outside the United States, your numbers already have an emergency address, but you can change it now. 请参阅[为用户分配或更改紧急地址](../what-are-calling-plans-in-office-365/assign-or-change-an-emergency-address-for-a-user.md)。 
  
5. 在分配电话号码和紧急地址之后，选择" **保存**"。
    
### <a name="tell-your-users-about-their-new-phone-numbers"></a>Tell your users about their new phone numbers


我们建议通过发送邮件或使用企业的首选通信方式，将新电话号码告知用户。 

Here's how they can see that phone number in their **Skype for Business** app:
  
1. 登录到桌面上的 Skype for Business。
    
2. Choose **Settings** > **Tools** > **Options**. 
    
     ![To view your phone number, go to Settings > Tools > Options.](../images/20637117-91d7-4a7e-9f06-7abc634a9211.png)
  
3. 然后，选择" **电话**"。 
    
    ![A user can see their assign number in the Skype for Business app by choosing Settings > Tools > Options > Phone.](../images/0128d667-2bf8-4165-b703-e9b78a15b63c.png)
 
In **Microsoft Teams**, users can see their phone number by clicking **Calls** in the left navigation. The phone number is shown above the dial pad.

![A user can see their number in Microsoft Teams by clicking Calls in the left navigation.](../images/teams-phone-number.png)

**For more detailed information about all of the steps involved in setting up a Calling Plan, see [Set up Calling Plans](../what-are-calling-plans-in-office-365/set-up-calling-plans.md).**


## <a name="step-6-if-you-want-to-set-up-audio-conferencing"></a>Step 6: If you want to set up Audio Conferencing

有时，组织中的用户需要使用电话拨入会议。 Skype for Business and Microsoft Teams include the audio conferencing feature for just this situation! People can call in to Skype for Business or Microsoft Teams meetings using a phone, instead of using the Skype for Business or Microsoft Teams app on a mobile device or PC. 
  
You only need to set up Audio Conferencing for people who plan to schedule or lead meetings. Meeting attendees who dial in don't need any licenses assigned to them or other setup.
  
For frequently asked questions about Audio Conferencing, see [Audio Conferencing common questions](../audio-conferencing-in-office-365/audio-conferencing-common-questions.md).
    
1. If you purchased **Audio Conferencing** add-on licenses and Communications Credits licenses, assign them too. For instructions, see [Assign Skype for Business and Microsoft Teams licenses](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).

    Decide on your audio conferencing provider. An audio conferencing provider supplies an audio conferencing bridge. The conferencing bridge sets your dial-in phone numbers, PINs, and conference IDs for meetings. Decide whether to use Microsoft or a third-party audio conferencing provider: 

    > [!NOTE]
    > Microsoft Teams users can't user a third-party audio conferencing provider. 
  
    - **Microsoft as your audio conferencing provider**: If you want the easiest solution for audio conferencing, choose Microsoft as your audio conferencing provider.
    
    - **Third party as your audio conferencing provider**: If you are in a country where Audio Conferencing in Office 365 isn't available, the service quality isn't great because of its location, or you have an existing contract, choose a third-party audio conferencing provider. To find a provider, go to [Microsoft PinPoint](http://go.microsoft.com/fwlink/?LinkId=797530).
 
2.  Assign the audio conferencing provider to people who lead or schedule meetings. See [Assign Microsoft as the audio conferencing provider](../audio-conferencing-in-office-365/assign-microsoft-as-the-audio-conferencing-provider.md).

3. Set up meeting invitations. The following steps are optional, but a lot of admins like to do them: 
  
    1. [Customize meeting invitations](../set-up-skype-for-business-online/customize-meeting-invitations.md). 为用户设置的拨入号码将自动添加到要发送给与会者的会议邀请中。 However, you can add your own help and legal links, a text message, and small company graphic.
    
    2. [Set the Audio Conferencing phone numbers for meeting organizers that are included on invites](../audio-conferencing-in-office-365/set-the-phone-numbers-included-on-invites.md). This is the phone number that will show up in the meeting that is scheduled by the user.
    
    3. [Set auto attendant languages for Audio Conferencing](../audio-conferencing-in-office-365/set-auto-attendant-languages-for-audio-conferencing.md) that the audio conferencing auto attendant uses to greet a caller when they dial in to an Audio Conferencing phone number. This step only applies if you're using Microsoft as your audio provider.
    
    4. [Set the length of the PIN for Audio Conferencing meetings](../audio-conferencing-in-office-365/set-the-pin-length-for-audio-conferencing-meetings.md).
    
    > [!NOTE]
    > This feature is not yet available to customers using Office 365 operated by 21Vianet in China. To learn more, see [Learn about Office 365 operated by 21Vianet](https://support.office.com/article/A8AB5061-3346-4DA0-BB7C-5260822B53AE). 

**For more information about Audio Conferencing, see [Set up Audio Conferencing](../audio-conferencing-in-office-365/set-up-audio-conferencing.md).**

## <a name="step-7-if-you-want-to-set-up-a-phone-system-call-queue"></a>Step 7: If you want to set up a Phone System call queue

Phone System call queues include greetings that are used when someone calls in to a phone number for your organization, the ability to automatically put the calls on hold, and the ability to search for the next available call agent to handle the call while the people who call are listening to music on hold. You can create single or multiple call queues for your organization.

Before you can create and set up your call queues, you will need to get or transfer your existing toll or toll-free service numbers. After you get the toll or toll-free service phone numbers, they will show up in **Skype for Business admin center** > **Voice** > **Phone numbers**, and the **Number type** listed will be listed as **Service - Toll-Free**. To get your service numbers, see [Getting service phone numbers for Skype for Business and Microsoft Teams](getting-service-phone-numbers.md) or if you want to transfer and existing service number, see [Transfer phone numbers to Office 365](../what-are-calling-plans-in-office-365/transfer-phone-numbers-to-office-365.md).
  
> [!NOTE]
> If you are outside the United States, you can't use the Skype for Business admin center to get service numbers. Go to [Manage phone numbers for your organization](../what-are-calling-plans-in-office-365/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) instead to see how to do it from the outside of the United States.

To create a new call queue, in the **Skype for Business admin center**, click **Call routing** > **Call queues**, click **Add new**, and then follow the instructions in **Step 3** of  [Create a Phone System call queue]( create-a-phone-system-call-queue.md#step-3---create-a-new-call-queue).

**For more details about call queues, see [Create a Phone System call queue](create-a-phone-system-call-queue.md).**

## <a name="step-8-if-you-want-to-set-up-a-phone-system-auto-attendant"></a>Step 8: If you want to set up a Phone System auto attendant

Auto attendants let people that call in to your organization and navigate a menu system to get them to the right department, call queue, person, or the operator. You can create an auto attendant for your organization by using the Skype for Business admin center. 

To create a new auto attendant, in the Skype for Business admin center, click **Call routing** > **Auto attendants**, click **Add new**, and then follow the instructions for each page in **Step 2** of [Set up a Phone System auto attendant](set-up-a-phone-system-auto-attendant.md#step-2---create-a-new-auto-attendant).

**For more details about Phone System auto attendants, see [Set up a Phone System auto attendant](set-up-a-phone-system-auto-attendant.md).**

## <a name="step-9-assign-service-phone-numbers-audio-conferencing-call-queues-auto-attendants"></a>Step 9: Assign service phone numbers (audio conferencing, call queues, auto attendants)

Once you have your service numbers from **Step 4 above**, you need to assign them to each type of service that you want. For example, if you want a dedicated service phone number (toll or toll-free), you will need to assign the number to the conferencing bridge.

- For Audio Conferencing, you can assign a dedicated number to a conferencing bridge by going to **Office 365 admin center** > **Admin centers** > **Skype for Business** > **Audio conferencing** and click on the conference bridge or by seeing  [Change the toll or toll-free numbers on your Audio Conferencing bridge](../audio-conferencing-in-office-365/change-the-phone-numbers-on-your-audio-conferencing-bridge.md).

- For Auto Attendants, you can assign a dedicated number to an auto attendant by going to **Office 365 admin center** > **Admin centers** > **Skype for Business** > **Call routing** > **Auto attendants** and click on the auto attendant. On the **General** page the service number you already have will be listed in the **Phone number** drop down. For details, see [Set up a Phone System Auto Attendant](set-up-a-phone-system-auto-attendant.md).

- For Call Queues, you can assign a dedicated number to a call queue by going to **Office 365 admin center** > **Admin centers** > **Skype for Business** > **Call routing** > **Call queues** and click on the call queue. On the **General** page the service number you already have will be listed in the **Phone number** drop down. For details, see [Create a Phone System call queue](create-a-phone-system-call-queue.md).

**For detailed information about getting new service numbers and porting existing service numbers, see [Getting service phone numbers](getting-service-phone-numbers.md).**

## <a name="step-10-set-up-communications-credits-for-your-organization"></a>Step 10: Set up Communications Credits for your organization

You will need to set up Communications Credits if you would like to use toll-free numbers with Skype for Business and Microsoft Teams. Also, we recommend that you set up Communications Credits for your Calling Plans (Domestic or International) and Audio Conferencing users who need the ability to dial out to **any destination**. Many countries/regions are included, but some destinations may not be included in your Calling Plan or Audio Conferencing subscriptions. If you don't set up Communications Credits billing and assign a **Communications Credits** license to your users and you run out minutes for your organization (depending on your Calling Plan or Audio Conferencing plan in your country/region), those users won't be able to make calls or dial out from Audio Conferencing meetings. You can get more information, including recommended funding amounts, by reading [What are Communications Credits?](../skype-for-business-and-microsoft-teams-add-on-licensing/what-are-communications-credits.md)
  
> [!NOTE]
> To find out how much it costs, [see the rates here](https://go.microsoft.com/fwlink/p/?LinkId=799523 ). 

### <a name="to-set-up-communications-credits"></a>To set up Communications Credits 

1. 使用你的工作或学校帐户登录 Office 365。
    
2. In the left navigation of the Office 365 admin center, go to **Billing** > **Subscriptions** > **Add-ons** > **Buy add-ons**, and then choose **Communications Credits** > **Buy now**.
    
3. On the **Communications Credits** subscription page, fill in your information, and then click **Next**.
        
4. Enter your payment information and click **Place order**.
    >[!IMPORTANT]
    >If you are a volume licensing customer, you may choose your enterprise agreement number for payment. If you have multiple enterprise agreement numbers, you will be able to select which enterprise agreement you would like to use for payment. You will also be given an opportunity to specify a purchase order number to associate with the enterprise agreement number (if applicable).
    
**For more detailed information about setting up Communications Credits, see [Set up Communications Credits for your organization](../skype-for-business-and-microsoft-teams-add-on-licensing/set-up-communications-credits-for-your-organization.md).**
  
### <a name="assign-a-communications-credits-license-to-users"></a>Assign a Communications Credits license to users

1. 使用你的工作或学校帐户登录 Office 365。
    
2. In the left navigation of the Office 365 admin center, go to **Users** > **Active users**, and then select a user or users from the list.
    
3. 在"操作"窗格中的" **产品许可证**"下，单击" **编辑**"。
    
4. On the **Product licenses** page, toggle ** Communications Credits** to **On** to assign this license, and then click **Save**.
    
    > [!NOTE]
    > Even if you have users who are assigned an **Enterprise E5** license, it's still recommended that you do this.

**To learn more about assigning Communications Credits licenses, see [Set up Communications Credits for your organization](../skype-for-business-and-microsoft-teams-add-on-licensing/set-up-communications-credits-for-your-organization.md).**

## <a name="related-topics"></a>相关主题
[下面是 Office 365 中的电话系统的功能](here-s-what-you-get-with-phone-system.md)

[获取 Skype for Business 和 Microsoft Teams 的服务电话号码](getting-service-phone-numbers.md)

[音频会议和通话套餐的国家/地区可用性](../country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)
    
  
 
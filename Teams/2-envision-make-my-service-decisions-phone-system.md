---
title: Make Phone System with Calling Plans service decisions - Microsoft Teams
author: rmw2890
ms.author: MyAdvisor
manager: lehewe
ms.date: 03/13/2018
ms.topic: article
ms.service: msteams
ms.reviewer: rowille
description: Choose from calling plans and licensing, configure emergency locations and features like voicemail and caller ID, acquire or transfer phone numbers.
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 38e382992f3170f16718eac8d2c6f0902dbaff3b
ms.sourcegitcommit: b985035b91ebd7ceff8d50e9e0fa9aa6ff971f3a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/15/2018
---
# <a name="make-my-service-decisions"></a>Make my service decisions

## <a name="calling-in-teams"></a>在 Teams 中进行通话

With Microsoft Teams, your users can place and receive phone calls to or from the public switched telephone network (PSTN). Your users can use their own dedicated phone numbers for placing and receiving domestic and international phone calls from Teams client applications, with advanced features that include voicemail and emergency calling (enhanced 911).

> [!NOTE]
> The latest Teams roadmap for identifying Teams Audio Conferencing features in scope for your deployment can be found at <https://aka.ms/skype2teamsroadmap>.

## <a name="phone-system-in-teams"></a>Phone System in Teams

For Teams users to be able to place and receive PSTN calls, they need to be enabled for Phone System, a feature in Office 365.

To enable connectivity to the PSTN, your organization can use Microsoft as its telecommunications service provider. Eventually, you’ll also have the option to “bring your own” telecommunications service provider to enable connectivity to PSTN for Phone System.

> [!IMPORTANT]
> The ability to choose your own telecommunications service provider for Phone System will be available in the future. To learn more about the projected timeline, please review the [Skype for Business to Microsoft Teams Capabilities Roadmap](https://aka.ms/skype2teamsroadmap).

## <a name="phone-system-with-calling-plans"></a>具有通话套餐的电话系统

To use Microsoft as your telecommunications service provider, you need to obtain Calling Plan licenses and assign them to your Phone System users.

There are two major types of calling plans:

-   Domestic calling plan

-   Domestic and international calling plan

Each type of calling plan allocates a certain number of call minutes per month to each user who has been assigned the license. When the call minutes allocation is exhausted, the user won’t be able to place outbound calls—except for emergency calls—until the next month’s billing cycle. If you want users to be able to continue to place outbound call even after they’ve exhausted their allocation of call minutes, or to let users who have a domestic calling plan place international calls, you can set up Communications Credits for your organization.

<!--ENDOFSECTION-->

## <a name="availability-of-calling-plans"></a>通话套餐的可用情况

Before you plan for the implementation of Calling Plans in Teams, verify that the Calling Plans service is available in your area by reviewing [Country and region availability for Audio Conferencing and Calling Plans](https://docs.microsoft.com/SkypeForBusiness/country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans).

> [!IMPORTANT]
> Due to legal constraints, for Calling Plans to be available to multinational organizations, the contract for Office 365 subscriptions must be based in a country or region where the Calling Plans service is available, or where the Calling Plans service can be purchased.

After confirming that your organization can obtain the Calling Plans service, compile the list of user locations or offices where you’ll be implementing the Calling Plans service, based on the list of available countries and regions.

<br>
|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|Decision points|<ul><li>Decide which user locations or offices you’ll implement the Calling Plans service in.</li></ul>|
|<img src="media/audio_conferencing_image9.png" />|后续步骤|<ul><li>Document the user locations or offices to be enabled for the Calling Plans service.</li></ul>|

> [!TIP]
> Below is an example of a Phone System with Calling Plans site enablement list.
>|办公地点   |位置 |Phone System service  |
>|---------|---------|---------|
>|Epping 路一号|澳大利亚|旧的 PSTN 服务|
>|数码港道 100 号|香港 SAR|旧的 PSTN 服务|
>|滨海林荫道一号|新加坡|旧的 PSTN 服务|
>|伦敦桥大街 32 号|英国|具有通话套餐的电话系统|
>|39 quai du Président Roosevelt|法国|具有通话套餐的电话系统|

<!--ENDOFSECTION-->

## <a name="phone-numbers-and-emergency-locations"></a>电话号码和紧急位置

With Calling Plans in Office 365, every user in your organization needs to have a unique direct inward dialing (DID) phone number and a corresponding validated emergency address. Review [Manage cloud voice telephone numbers](https://docs.microsoft.com/MicrosoftTeams/2-envision-make-my-service-decisions-phone-system#manage-cloud-voice-telephone-numbers) to plan the phone number acquisition for your Calling Plans implementation.

When you’re configuring phone numbers for Calling Plans, you must assign an emergency address to each telephone number before you assign the number to a user. 为了支持紧急呼叫，必须这样做。 The emergency address must be validated to ensure that it’s in the correct format to be used by emergency response services.

> [!IMPORTANT]
> Emergency Services calling operates differently in the Calling Plans service than in traditional telephone services. It’s important that you understand these differences and communicate them to all users. See [Emergency Calling Terms and Conditions](https://docs.microsoft.com/en-us/skypeforbusiness/what-are-calling-plans-in-office-365/emergency-calling-terms-and-conditions) for more details.

In addition to supplying a validated emergency address, you can define emergency locations and associate them with the validated emergency address to give a more exact location within an address. 紧急位置通常是用户所在的建筑物编号、楼层、建筑物侧楼或办公室号码。

To learn more about emergency locations in relation to Calling Plans, review the following articles:

-   [什么是紧急位置、地址和呼叫路由？](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/what-are-emergency-locations-addresses-and-call-routing)

-   [紧急呼叫条款和条件](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/emergency-calling-terms-and-conditions)

<br>
|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|Decision points|<ul><li>Decide the granularity of emergency location information to be collected for user locations or offices in scope for the Calling Plans implementation.</li></ul>|
|<img src="media/audio_conferencing_image9.png" />|后续步骤|<ul><li>Document the detailed emergency address and emergency locations for each user location or office in scope for the Calling Plans implementation.</li></ul>|

> [!TIP]
> You can use the following template to document the details of phone numbers and emergency location details.
>|用户 |Emergency location and address |Phone number |
>|-----|-------------------------------|-------------|
>|Emily Braun |1034/32 London Bridge Street, London, SE1, United Kingdom |+44 23 4567 8901 |
>|Lidia Holloway |1065/32 London Bridge Street, London, SE1, United Kingdom |+44 23 4567 89112 |
>|Louis Lahr |1023/32 London Bridge Street, London, SE1, United Kingdom |+44 23 4567 8921 |
>|Marcel Beauchamp |07E15D/39 quai du Président Roosevelt, 92130 Issy-les-Moulineaux, France | TBA |
>|Rachelle Cormier |07N15D/39 quai du Président Roosevelt, 92130 Issy-les-Moulineaux, France | TBA |
>|Isabell Potvin |07F05E/39 quai du Président Roosevelt, 92130 Issy-les-Moulineaux, France | TBA |

<!--ENDOFSECTION-->

## <a name="voicemail"></a>语音邮件

Phone System voicemail, powered by Azure Voicemail services, supports voicemail deposits to Exchange mailboxes only and doesn’t support third-party email systems.

By default, Phone System voicemail works with Exchange Online; however it has a minimum supported Exchange on-premises version and deployment model to allow delivery of voicemail messages to user mailboxes in the on-premises Exchange deployment.

电话系统语音邮件包括语音邮件转录，默认情况下，为组织中的所有用户启用该功能。 Your business needs might require that you disable voicemail transcription for specific users or everyone throughout the organization. If your organization decided to keep voicemail transcription enabled, you need to also consider whether voicemail transcription profanity masking need to be enabled. See [Setting voicemail policies in your organization](https://docs.microsoft.com/en-us/SkypeForBusiness/what-is-phone-system-in-office-365/phone-system-voicemail/set-up-phone-system-voicemail) for more details.

>[!NOTE]
> 实施了回退机制，以便电话系统语音邮件可以通过使用 SMTP 重新发送邮件，这意味着，在第三方电子邮件系统中有邮箱的用户将会收到其语音邮件。 This mechanism doesn’t include guaranteed service uptime or other voicemail features, such as changing voicemail greeting.

For more information about voicemail in a Phone System implementation, see [Azure PBX voicemail support for Exchange Server](https://docs.microsoft.com/MicrosoftTeams/phone-system-with-calling-plans#licensing-for-calling-plans).

<br>
|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|Decision points|<ul><li>Decide whether you’ll enable Phone System voicemail in your Calling Plans implementation.</li><li>If using Exchange on-premises and your existing deployment doesn’t meet your requirements to support Phone System voicemail, choose from the available options (upgrade and setup for Phone System voicemail support, migrate to Exchange Online, or leverage the fallback mechanism described earlier).</li><li>Decide whether you’ll enable or disable voicemail transcription and voicemail transcription profanity masking throughout the organization or for specific users.</li></ul>|
|<img src="media/audio_conferencing_image9.png" />|后续步骤|<ul><li>If applicable, document the Exchange decision points to support Phone System voicemail.</li><li>If you’ll enable/disable voicemail, voicemail transcription, and voicemail transcription profanity masking only for specific users, document that list of users.</li></ul>|

> [!TIP]
> Phone System voicemail details for the Phone System with Calling Plans implementation can be documented as the following.
>|用户 |Exchange mailbox |Enable voicemail? |Voicemail transcription |Voicemail transcription profanity masking |
>|------------------|------------------|-------------------|----------|----------|
>|Emily Braun      |Online      |是 |启用 |启用 |
>|Lidia Holloway   |Online      |是 |启用 |已禁用 |
>|Louis Lahr       |本地 |是 |启用 |启用 |
>|Marcel Beauchamp |本地 |是 |禁用 |不适用 |
>|Rachelle Cormier |Online      |是 |禁用 |不适用 |
>|Isabell Potvin   |本地 |是 |禁用 |不适用 |

<!--ENDOFSECTION-->

## <a name="calling-identity"></a>呼叫标识

默认情况下，所有出站呼叫均使用分配的电话号码作为呼叫标识（呼叫方 ID）。 呼叫接收人可以快速识别呼叫方，并决定是接收还是拒绝呼叫。 在某些情况下，有合法的业务需求来屏蔽呼叫方 ID 使用以防止调用方的标识的办公室主行号 — — 这通常是由自动助理配置一个服务号码 — — 作为呼叫方 ID 或阻止的呼叫方 ID演示文稿完全。

<br>
|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|Decision points|<ul><li>Decide whether Caller ID manipulation is required for your Calling Plans implementation.</li><li>If applicable, decide the types of Caller ID manipulation (mask with service number or anonymize) to be implemented.</li><li>If applicable, decide which users require Caller ID manipulation and the type of Caller ID manipulation to be assigned to each user.</li></ul>|
|<img src="media/audio_conferencing_image9.png" />|后续步骤|<ul><li>Document the users to be assigned Caller ID manipulation and the type of Caller ID manipulation to assign.</li></ul>|

> [!TIP]
> The following is an example of Caller ID masking details documentation.
>|用户  |启用出站呼叫方 ID 屏蔽  |呼叫方 ID 屏蔽类型  |允许用户覆盖  | 启用入站呼叫方 ID 屏蔽  |
>|---------|---------|---------|---------|---------|
>|Emily Braun|否|不适用|是|否|
>|Lidia Holloway|是|服务号码（OrgAA，+44 20 7946 0000）|否|是|
>|Louis Lahr|否|不适用|是|否|
>|Marcel Beauchamp|是|服务号码（OrgAA，待定）|否|是|
>|Rachelle Cormier|是|匿名|是|否|
>|Isabell Potvin|是|服务号码（OrgAA，待定）|否|是|

<!--ENDOFSECTION-->

## <a name="licensing-for-cloud-voice-capabilities"></a>授权的云语音功能

音频会议和电话系统是在 Office 365 的功能。 可以作为附加服务的 Office 365 E3 或 E1 订阅计划; 现有客户单独许可他们它们已经将 Office 365 E5 订阅计划的一部分。

调用计划不到 Office 365 提供，因此您必须授权电话系统的电话系统功能的加载项可以使用调用计划。

要支持其他音频会议并调用计划使用案例 （国际会议拨出、 外部调用之后调用计划分钟分配已用尽，等等），可以设置您的组织通信贷。

## <a name="licensing-for-calling-plans"></a>通话套餐许可

如果您的组织打算使用 Microsoft，如电信服务提供商，您需要获取加载项调用计划适用于用户的业务需求。 通常情况下，人在组织中都不需要进行国际呼叫，以便可以设置调用规划许可证，国内大多数用户。

有两种类型的调用规划许可证：

-   国内通话套餐

-   国际和国内通话套餐

> [!NOTE]
> 对特定用户而言，“国内”由用户的已分配 Office 365 使用位置确定。

每种通话套餐类型均分配用户每月可以用于拨打国内电话或国际电话的通话分钟数。 国际和国内调用计划少相比国内调用计划成本。

订阅和分配最适当的调用计划类型为单个用户的业务需求的灵活性可帮助组织控制其调用计划实施的成本。

对于每个 Office 365 租户，按国家或地区以及按每种通话套餐类型共用组合的通话分钟数。 达到租户的每月通话分钟数上限时，将会在当月其余时间内暂停通话套餐服务（紧急呼叫除外）。 调用计划服务将自动继续执行下一个月的第一天。

您可以设置为组织的通信贷方以使用户后分配调用分钟耗尽而无需等待，直到下个月计费周期进行出站呼叫。 此外，通信贷方授予用户分配给国内调用计划来打国际电话，然后收取通过"支付每分钟"模型的能力。

若要了解有关电话系统和调用计划的详细信息，请参阅以下文章：

-   [电话系统](https://products.office.com/skype-for-business/phone-system)

-   [通话方案](https://products.office.com/skype-for-business/calling-plans)

<br>
|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|决策点|<ul><li>If your organization doesn’t have the required Phone System license, decide whether you’ll acquire the Phone System license by stepping up your existing Office 365 subscriptions or by acquiring the Phone System add-on service.</li><li>决定哪些用户需要国内调用规划许可证，这需要国内和国际调用规划许可证。</li><li>决定是否需要通信信用为您调用计划的实施。</li></ul>|
|<img src="media/audio_conferencing_image9.png" />|后续步骤|<ul><li>文档分部、 部门、 办公室或电话系统许可证与国内调用计划或国内和国际调用计划会将指派的用户组。</li></ul>|

> [!TIP]
> 下面的示例可用于文档调用计划用户与电话系统的许可分配。
>|用户 |办公地点 |Office 365 许可证 |调用计划 |
>|----|----|----|----|
>|Emily Braun |伦敦桥大街 32 号 |Office 365 E5 |国际和国内通话套餐 |
>|Lidia Holloway |伦敦桥大街 32 号 |Office 365 E5 |国内通话套餐 |
>|Louis Lahr |伦敦桥大街 32 号 |Office 365 E5 |国内通话套餐 |
>|Marcel Beauchamp |39 quai du Président Roosevelt |Office 365 E3, Phone System add-on |国内通话套餐 |
>|Rachelle Cormier |39 quai du Président Roosevelt |Office 365 E5 |国际和国内通话套餐 |
>|Isabell Potvin |39 quai du Président Roosevelt |Office 365 E3，电话系统加载项 |国内通话套餐 |

<!--ENDOFSECTION-->

## <a name="communications-credits"></a>通信点数

使用通信信用，您的用户可以拨出音频会议会议 （在外部会议组织者的原始国家/地区） 世界上任意位置添加从其他人中。 您可以设置为您的组织的通信贷方以使用户之后他们已经耗尽其分配调用分钟的时间，而无需等待，直到下个月的计费周期进行出站呼叫。 此外，通信贷给用户分配与国内调用计划来打国际电话，然后收取通过"支付每分钟"模型的能力。

实施通信点数时首先要考虑的是确定要购买的初始资金数额。 如果您的组织选择使用自动充电，你需要通过测量实际使用情况来确定最佳的量。 随着时间的推移监视通信富余的使用量和调整根据需要您重新充电量。

对于调用计划实现时，您可以控制将通信贷方在每用户的基础，它可以帮助您确保您已与您的业务需求分配这些信用部门的协调。

若要了解有关通信片尾，查看[通讯片尾是什么？](https://docs.microsoft.com/SkypeForBusiness/skype-for-business-and-microsoft-teams-add-on-licensing/what-are-communications-credits)。

<br>
|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|决策点|<ul><li>确定是否需要通信片尾音频会议或调用计划实施。</li></ul>|
|<img src="media/audio_conferencing_image9.png" />|后续步骤|<ul><li>文档将启用通信贷方的部、 部门、 办公室电话或用户组。</li><li>记录音频会议或调用计划实施通信贷计划。</li></ul>|

> [!TIP]
> 下面的示例用于调用计划用户通信信用分配列表中的文档。
>|用户 |办公地点 |Calling Plan |通信点数 |
>|----|----|----|----|
>|Emily Braun |伦敦桥大街 32 号 |国际和国内通话套餐 |启用 |
>|Lidia Holloway |伦敦桥大街 32 号 |国内通话套餐 |已禁用 |
>|Louis Lahr |伦敦桥大街 32 号 |国内通话套餐 |启用 |
>|Marcel Beauchamp |39 quai du Président Roosevelt |国内通话套餐 |禁用 |
>|Rachelle Cormier |39 quai du Président Roosevelt |国际和国内通话套餐 |启用 |
>|Isabell Potvin |39 quai du Président Roosevelt |国内通话套餐 |已禁用 |

<br>
> [!TIP]
> Your Communications Credits planning numbers can be documented as in the following example.
>|         |         |
>|---------|---------|
>|初始数额|$ 1,000|
>|触发数额|$400|
>|自动充值数额|TBA|

<!--ENDOFSECTION-->

## <a name="manage-cloud-voice-telephone-numbers"></a>管理云语音电话号码

如果通过将您自己的电信服务提供商，从而实现电话系统，电话号码管理仍为-是。

对于音频会议和调用计划的实现，可以选择将获得新的电话号码或传输 （端口） 现有的电话号码。

若要让用户拨号电话号码他们习惯的方式 — — 如忽略本地电话的区号、 省略拨打国内电话的国家/地区代码或甚至使用短数字拨号执行会议拨出时或调用其他用户组织中 — —您可以配置自定义的拨号计划并将其分配给用户。

## <a name="acquire-new-telephone-numbers"></a>获取新的电话号码

两种类型的 Microsoft 云语音解决方案中的电话号码是：

-   订户 （用户） 号，可以分配给组织中的用户。

-   服务编号，可用作收费和免费电话服务号码，它具有更高的并发呼叫容量比订户号并可以分配给服务，如音频会议、 自动助理或调用队列。

有关类型的电话号码的详细信息，请参阅[用于调用计划的电话号码的不同种类](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/different-kinds-of-phone-numbers-used-for-calling-plans)。

电话号码可获得的总数取决于类型的电话号码，并且已经购买和分配给您的用户许可证的数量。

总计数的电话号码，您可以获得有关的详细信息，请参阅[您可以得到多少的电话号码？](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/how-many-phone-numbers-can-you-get)

<br>
|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|Decision points|<ul><li>Decide the user locations or offices where new telephone numbers will be acquired from Microsoft.</li><li>Decide the type of telephone numbers to be acquired from Microsoft.</li></ul>|
|<img src="media/audio_conferencing_image9.png" />|后续步骤|<ul><li>Document the user locations or offices where new telephone numbers will be acquired from Microsoft.</li><li>Document the type of telephone numbers to be acquired from Microsoft.</li></ul>|

## <a name="transfer-existing-telephone-numbers"></a>Transfer existing telephone numbers

If your organization wants to transfer (or port) existing telephone numbers to Microsoft, you can do so by submitting a port order request to Microsoft.

您可以传输所有您现有电话号码一次 （全端口），和 — — 在某些市场中 — — 可以转移现有的电话号码 （部分端口） 的子集。 部分端口可在情况下，只是需要逐渐将用户移动到调用计划与电话系统。

单个端口订单只可以将电话号码转移到一个电话号码类型。 如果您需要转移一些订户号作为您的电话号码和服务号码，我们建议您首先完成将传送到 Microsoft，然后执行转换，只要微软控件中数字的。

或者 （如果支持部分的端口），可以将多个端口的请求，一个端口请求提交一次。 但是，此种方法将延续现有的电信服务提供商与您签订合同。

电话号码移植是一个复杂的话题，需要全面规划、 协调和充分管理利益干系人的期望。 若要了解详细信息，请参阅下列文章：

-   [将电话号码转到 Office 365](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/transfer-phone-numbers-to-office-365)

-   [关于转移电话号码的常见问题](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/transferring-phone-numbers-common-questions)

<br>
|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|Decision points|<ul><li>Decide the user locations or offices where existing telephone numbers will be transferred to Microsoft.</li><li>确定类型的电话号码，以转移到 Microsoft。</li></ul>|
|<img src="media/audio_conferencing_image9.png" />|后续步骤|<ul><li>Document the user locations or offices where existing telephone numbers will be transferred to Microsoft.</li><li>Document the type of telephone numbers to be transferred to Microsoft.</li></ul>|

<!--ENDOFSECTION-->

## <a name="dial-plans"></a>拨号计划

A Dial Plan in the Phone System feature of Office 365 is a set of normalization rules that translate dialed phone numbers into an alternate format (typically E.164 format) for call authorization and call routing. The Audio Conferencing service leverages the same capabilities used by Phone System to translate dialed phone numbers in conference dial-out scenarios (for example, invite participants via PSTN and dial back, “call me” feature).

在 Office 365 的电话系统功能，有两种类型的拨号计划：

-   **服务的拨号计划：**这是默认设置适用于用户的拨号计划按 Office 365 的使用地点，并不能对其进行修改。

-   **租户拨号计划：**这是可自定义的拨号计划内的租户，进一步划分为两类：

    -   **组织全局拨号计划：**适用于组织中的所有用户的拨号计划。

    -   **租户用户拨号计划：**应用只为特定用户的拨号计划。

分配给用户的有效拨号计划是服务拨号计划 （根据用户的 Office 365 使用位置） 的组合，租户拨号计划 （它可以是全局租户拨号计划或租户用户拨号计划）。

![表显示了三个组合服务和租户的拨号计划。](media/audio_conferencing_image8.png "表显示了三个组合服务和租户的拨号计划。")

> [!IMPORTANT]
> 在每个租户拨号计划; 可以有最多的 25 个规范化规则因此，十分重要，以避免重复已有的规范化规则作为服务的一部分，拨号计划。

有关拨号计划的详细信息，请参阅[拨号计划是什么？](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/what-are-dial-plans)

<br>
|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|Decision points|<ul><li>Decide whether your organization requires customized dial plans (business requirements, adoption requirements, and so on).</li><li>If applicable, decide the scope of the tenant dial plan (tenant-global or tenant-user) to support your requirements for customized dial plans.</li><li>If applicable, decide the tenant dial plans that you’ll create to support user locations or offices in scope for the cloud voice implementation.</li><li>If applicable, decide which users require a customized dial plan and the tenant dial plan to be assigned for each user.</li></ul>|
|<img src="media/audio_conferencing_image9.png" />|后续步骤|<ul><li>Document the customized dial plans and the associated normalization rules to be configured as part of cloud voice implementation.</li><li>Document the users to be assigned a customized dial plan and the tenant dial plan to be assigned for each user.</li></ul>|

> [!TIP]
> If it’s applicable to your project, you can use the following template to document the tenant dial plan configurations.
>|租户拨号计划名称<br>_说明_  |规范化规则名称<br>_说明_  |模式<br>转换<br>IsInternalExtension  |
>|---------|---------|---------|
>|**AU-NSW-NorthRyde-OER**<br>_新南威尔士北莱德 Epping 路一号，AU 拨号计划_|**AU-NSW-NorthRyde-OER-Internal**<br>_澳大利亚新南威尔士北莱德 Epping 路一号办公地点的内部号码 (x7000 - x7999)_|^(7\d{3})$<br>+6125550$1<br>True|
>||**AU-NSW-Local**<br>_澳大利亚新南威尔士的本地号码规范化_|^([2-9]\d{7})$<br>+612$1<br>False|
>||**AU-TollFree**<br>_澳大利亚的免费电话号码规范化_|^(1[38]\d{4,8})\d*$<br>+61$1<br>False|
>||**AU-Service**<br>_澳大利亚的服务号码规范化_|^(000\|1[0125]\d{1,8})$<br>$1<br>False|
>|**SG-Singapore-OMB**<br>_新加坡 OMB，SG 拨号计划_|**SG-OMB-Internal**<br>_Internal number (x8000 â€“ x8999) for OMB office, Singapore_|^(8\d{3})$<br>+656888$1<br>True|
>||**SG-TollFree**<br>_新加坡的免费电话号码规范化_|^(1?800\d{7})\d*$<br>+65$1<br>False|
>||**SG-Service**<br>_新加坡的服务号码规范化_|^(1\d{3,4}\|9\d{2})$<br>$1<br>False|
>|**FR-Paris-Issy-39qdPR**<br>_39 quai du Président Roosevelt Issy-les-Moulineaux，法国拨号计划_|**FR-39qdPR-Internal**<br>_Internal number (x7000 â€“ x7999) for 39 quai du Président Roosevelt office, Issy-les-Moulineaux, France_|^(7\d{3})$<br>+3319999$1<br>True|
>||**FR-TollFree**<br>_法国的免费电话号码规范化_|^0?(80\d{7})\d*$<br>+33$1<br>False|
>||**FR-Service**<br>_法国的服务号码规范化_|^(1\d{1,2}\|11[68]\d{3}\|10\d{2}\|3\d{3})$<br>$1<br>False|

<br>
> [!TIP]
> 可以利用下面的示例模板来记录拨号计划分配以支持你的项目：
>|用户  |办公地点  |拨号计划类型  |拨号计划名称  |
>|---------|---------|---------|---------|
>|Adele Vance|Epping 路一号|租户拨号计划|AU-NSW-NorthRyde-OER|
>|Alex Wilber|Epping 路一号|租户拨号计划|AU-NSW-NorthRyde-OER|
>|Ben Walters|Epping 路一号|租户拨号计划|AU-NSW-NorthRyde-OER|
>|Christie Cline|滨海林荫道一号|租户拨号计划|SG-Singapore-OMB|
>|Debra Berger|滨海林荫道一号|租户拨号计划|SG-Singapore-OMB|
>|Lee Gu|滨海林荫道一号|租户拨号计划|SG-Singapore-OMB|
>|Emily Braun|伦敦桥大街 32 号|服务拨号计划|不适用|
>|Lidia Holloway|伦敦桥大街 32 号|服务拨号计划|不适用|
>|Louis Lahr|伦敦桥大街 32 号|服务拨号计划|不适用|
>|Marcel Beauchamp|39 quai du Président Roosevelt|租户拨号计划|FR-Paris-Issy-30qdPR|
>|Rachelle Cormier|39 quai du Président Roosevelt|租户拨号计划|FR-Paris-Issy-30qdPR|
>|Isabell Potvin|39 quai du Président Roosevelt|租户拨号计划|FR-Paris-Issy-30qdPR|

<!--ENDOFSECTION-->

## <a name="document-service-decisions"></a>Document service decisions 

Use the information from the previous sections of this article to document your service decisions. In general, this documentation will contain the following main sections:

-   具有通话套餐的电话系统地点启用列表

-   具有通话套餐的电话系统用户的许可证分配

-   通信点数计划数量

-   电话号码获取、电话号码和紧急位置详细信息

-   语音邮件配置详细信息

-   会议桥接设置分配

-   呼叫方 ID 屏蔽配置详细信息

-   租户拨号计划

-   拨号计划分配

<!--ENDOFSECTION-->
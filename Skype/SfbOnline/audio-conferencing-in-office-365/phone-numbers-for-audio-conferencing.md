---
title: Skype for Business Online 中的音频会议电话号码
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 95a08f84-04e5-4f72-88a8-d6472a7c89d7
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
f1keywords: None
ms.custom:
- Audio Conferencing
- LIL_Placement
description: 了解哪些国家和地区有拨入式会议号码，以及号码是如何自动分配的。
ms.openlocfilehash: daa2312350be038153db168517a1d0f5bd7023cf
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34299113"
---
# <a name="phone-numbers-for-audio-conferencing-in-skype-for-business-online"></a>Skype for Business Online 中的音频会议电话号码

> [!NOTE]
> 有关在 Microsoft Teams中电话号码的信息，请参阅 [Microsoft Teams 中的音频会议电话号码](/MicrosoftTeams/phone-numbers-for-audio-conferencing-in-teams)。

When you are setting up **Audio Conferencing** for Skype for Business, dial-in phone numbers are automatically assigned to your organization. You can see the phone numbers that are assigned to your audio conferencing bridge by going to the **Skype for Business admin center** > **Audio conferencing** > **Microsoft bridge**. See [See a list of Audio Conferencing numbers](see-a-list-of-audio-conferencing-numbers.md).
  
> [!NOTE]
> There isn't a resource that contains a listing of all of the dial-in numbers for Audio Conferencing. If you want to see if there are dial-in phone numbers available in your area or country/region, use the **Skype for Business admin center** > **Voice** > **Phone Numbers**, click **Add**, and then click **New Service Numbers**. Use the lists for **Country/Region**, **State/Region**, and **City** to filter your search. Also, if you are looking for toll-free service numbers, select **Toll-Free** from the **State/Region** list.
  
## <a name="audio-conferencing-coverage-and-pricing"></a>音频会议的范围和定价

For a complete list of all the countries/regions and cities where Audio Conferencing is available, see [Countries and region availability for Audio Conferencing and Calling Plans](/microsoftteams/country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans). For pricing information, see [Pricing for Audio Conferencing](https://products.office.com/en-us/skype-for-business/audio-conferencing#Requirements).
  
## <a name="dial-in-phone-numbers-in-a-meeting-invite"></a>会议邀请中的拨入电话号码

When a Skype for Business Online user schedules a meeting in Outlook or Outlook Web App, the default audio conferencing number that is set for the user is included in the meeting invite. If you want to select a different default number for one or more users, you can change that by going to the **Skype for Business admin center** > **Audio conferencing** > **Users**. See [Set the phone numbers included on invites](set-the-phone-numbers-included-on-invites.md).
  
可以通过单击会议邀请上的" **查找本地号码**"链接来查看其他拨入号码。
  
## <a name="dial-in-phone-numbers-set-on-an-audio-conferencing-bridge"></a>在音频会议网桥上设置的拨入电话号码

There are two types of audio conferencing phone numbers that can be assigned to your conferencing bridge: **Shared** and **Dedicated**. Both types of these numbers can be used by any caller to join audio meetings that are being held in your organization.
  
 **专用电话号码** 是只有你组织内的用户才可以使用的电话号码。你可以更改当有人呼入其中的某个号码时使用的语言。
  
 **共享电话号码** 是可以与其他 Office 365 组织共享的电话号码。你无法更改当有人呼入其中的某个号码时使用的语言。
  
While the default audio conferencing number that is assigned to an organizer is only included in the meeting invite, a caller can use any of the phone numbers that are assigned to your conferencing bridge to join a meeting. The list of phone numbers that can be used to join a meeting is available using the **Find a local number** link that is included on every meeting invite.
  
## <a name="automatically-assigned-audio-conferencing-phone-numbers"></a>自动分配的音频会议电话号码

Shared audio conferencing phone numbers are automatically assigned to organizations when they're enabled for audio conferencing. When the phone numbers are assigned, a phone number is assigned as the default phone number of the conferencing bridge. The phone number assigned as the default number of the bridge will be one from the country/region of the organization.
  
> [!NOTE]
> 通过登录到**Office 365 管理中心**并在 "**组织配置文件**" 下查看, 可以找到您的组织的国家或地区位置。 
  
> [!CAUTION]
> Due to limited availability of toll phone numbers in Venezuela, Indonesia, and United Arab Emirates (UAE), organizations from these countries/regions won't have an Audio Conferencing toll number automatically assigned to them. Toll-free numbers from these locations are available depending on available inventory. 
  
Dedicated audio conferencing phone numbers are service numbers that you can get and then assign to your organization. Service numbers can be found by using the **Skype for Business admin center**. For details, see [Getting service phone numbers](/SkypeForBusiness/what-is-phone-system-in-office-365/getting-service-phone-numbers).
  
若要查看支持给组织自动分配电话号码的国家/地区列表，请参阅 [音频会议和通话套餐所支持的国家/地区](/microsoftteams/country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans)。
  
## <a name="what-else-should-you-know"></a>你还需了解哪些信息？

- 若要查看音频会议的受支持语言的列表, 请参阅[音频会议支持的语言](/MicrosoftTeams/audio-conferencing-supported-languages)。
    
- 你可以使用[set-csonlinedialinconferencingservicenumber](https://go.microsoft.com/fwlink/?LinkId=617691) cmdlet 查看你的组织的音频会议的专用电话号码。
    
- 你可以使用 [Get-CsOnlineDialInConferencingLanguagesSupported](https://go.microsoft.com/fwlink/?LinkId=617684) cmdlet 查看可以对专用拨入电话号码设置的语言。
    
- You can set up to four languages for each audio conferencing phone number - one primary and three secondary. And you can also set languages on a dedicated audio conferencing phone number.
    
- 若要为用户设置拨入电话号码, 请参阅[设置邀请附带的电话号码](set-the-phone-numbers-included-on-invites.md)。
    
[!INCLUDE [LinkedIn Learning Info](../../common/office/linkedin-learning-info.md)]
   
## <a name="related-topics"></a>相关主题

[试用或购买 Office 365 中的音频会议](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)

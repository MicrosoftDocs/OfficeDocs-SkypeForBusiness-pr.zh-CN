---
title: "为音频会议的电话号码"
ms.author: tonysmit
author: tonysmit
manager: scotv
ms.date: 11/21/2017
ms.audience: Admin
ms.topic: reference
ms.service: o365-administration
localization_priority: Normal
ms.collection: Adm_Skype4B_Online
ms.custom:
- Adm_O365_FullSet
- LIL_Placement
- Strat_SB_PSTN
ms.assetid: 95a08f84-04e5-4f72-88a8-d6472a7c89d7

description: "Learn what countries and regions have dial-in conferencing numbers, and how they are automatically assigned."
---

# 为音频会议的电话号码

> [!重要信息]
> 本文是由机器翻译的，请参阅[免责声明](95a08f84-04e5-4f72-88a8-d6472a7c89d7.md#MT_Footer)。请在 [此处](https://support.office.com/en-us/article/95a08f84-04e5-4f72-88a8-d6472a7c89d7) 中查找本文的英文版本以便参考。
  
当您设置 **音频会议**for Skype Business 和 Microsoft 团队时，拨入电话号码会自动分配到您的组织。您可以查看分配给您的音频会议网桥通过转到 **Skype for Business 管理中心**的电话号码 > **音频会议**> **Microsoft 网桥**。请参阅[请参阅音频会议号码列表](see-a-list-of-audio-conferencing-numbers.md)。
  
> [!注释]
> 没有音频会议包含所有拨入号码的列表的资源。如果您希望了解是否存在拨入电话号码可在您的区域或国家/地区中，可以使用 **Skype for Business 管理中心**> **语音**> **电话号码**， **添加** **新服务号码**，然后单击。用于 **国家/地区**， **国家/地区列表**和 **城市**以筛选搜索结果。 > 此外，如果您正在寻找收费免费服务号码，请选择 **免费**从 **国家/地区**列表。 
  
## 音频会议报道和定价

所有国家/地区和音频会议位置是可用的城市的完整列表，请参阅[使用电话号码的 PSTN 会议在我的国家或地区是否可用？](https://support.office.com/article/1096d81e-7e14-488c-95d8-b8322e39c059)。
  
[定价的音频会议](https://products.office.com/en-us/skype-for-business/audio-conferencing#Requirements)
  
## 会议邀请中的拨入电话号码

当 Skype for Business Online 或 Microsoft 小组的用户安排会议在 Outlook 或 Outlook Web App 中的时，为用户设置默认音频会议号码将包含在会议邀请。如果您想要选择其他默认号码的一个或多个用户，您可以更改，通过转到 **Skype for Business 管理中心**> **音频会议**> **用户**。请参阅[为会议组织者包含在邀请中设置音频会议电话号码](set-the-audio-conferencing-phone-numbers-for-meeting-organizers-that-are-include.md)。
  
可以通过单击会议邀请上的" **查找本地号码**"链接来查看其他拨入号码。
  
## 在音频会议网桥设置拨入电话号码

有两种类型的可分配给会议网桥的音频会议电话号码： **共享** 和 **专用** 。两种类型的这些数字可以通过任何呼叫者，用于加入保存您的组织中的音频会议。
  
 **专用电话号码** 是这些仅可供您的组织内的用户的电话号码。您可以更改有人呼叫到一个这些数字时使用的语言。
  
 **共享的电话号码** 是可与其他 Office 365 组织共享这些电话号码。有人呼叫到一个这些数字时使用的语言，无法更改。
  
会议邀请中仅包含分配给组织者的默认音频会议号码，而呼叫者可以使用任何分配给会议网桥要加入的会议的电话号码。可用于加入会议的电话号码列表可在每个会议邀请中使用包含 **查找本地号码**链接。
  
## 自动分配音频会议电话号码

共享音频会议电话号码自动分配给组织，当他们正在启用音频会议。分配电话号码，作为默认电话号码的会议网桥分配电话号码。作为默认数网桥分配的电话号码将从组织的国家/地区。
  
> [!注释]
> 通过登录到 **Office 365 管理中心中**，在 **组织配置文件**下查找找不到您的组织的国家或地区位置。 
  
> [!警告]
> 由于收费电话号码委内瑞拉、 印度尼西亚和阿拉伯联合酋长国 （阿拉伯联合酋长国） 中的可用性有限，从这些国家/地区组织都不会有自动分配给他们的音频会议收费电话号码。从这些位置的免费电话号码可根据可用库存。 
  
专用的音频会议电话号码是服务编号，您可以获取，然后将分配给您的组织。通过使用 **Skype for Business 管理中心**，可以找到服务编号。有关详细信息，请参阅[获取 Skype for Business 服务电话号码](../what-is-phone-system-in-office-365/getting-service-phone-numbers-for-skype-for-business-and-microsoft-teams.md)。
  
要查看有自动分配给组织的电话号码这些国家/地区的列表，请参阅[国家和地区和的可用性音频会议呼叫计划](../countries-and-region-availability-for-audio-conferencing-and-calling-plans/countries-and-region-availability-for-audio-conferencing-and-calling-plans.md)。
  
## 你还需了解哪些信息？

- 要查看的音频会议的受支持语言的列表，请参阅[音频会议支持的语言](audio-conferencing-supported-languages.md)。
    
- [获取 CsOnlineDialInConferencingServiceNumber](https://go.microsoft.com/fwlink/?LinkId=617691) cmdlet 可用于查看为您的组织的音频会议的专用的电话号码。
    
- 您可以使用[Get-csonlinedialinconferencinglanguagessupported](https://go.microsoft.com/fwlink/?LinkId=617684) cmdlet，请参阅可以的专用的拨入电话号码设置语言。
    
- 您可以多达 4 语言设置为每个音频会议电话号码的一种主要和三次。然后，您可以在专用的音频会议电话号码设置语言。
    
- 若要为用户设置拨入电话号码，请参阅[为会议组织者包含在邀请中设置音频会议电话号码](set-the-audio-conferencing-phone-numbers-for-meeting-organizers-that-are-include.md)。
    
||
|:-----|
|![领英学习快捷图标。](../images/7e5cb7c8-dc66-4c9a-a16d-a30f10a970bd.png) **刚开始使用 Office 365？**         探索由 LinkedIn Learning 提供的适用于 **Office 365 管理员和 IT 专业人士**的免费视频课程。 |
   
## 
<a name="MT_Footer"> </a>

> [!注释]
> **机器翻译免责声明**：本文是由无人工介入的计算机系统翻译的。Microsoft 提供机器翻译是为了帮助非英语国家/地区用户方便阅读有关 Microsoft 产品、服务和技术的内容。由于机器翻译的原因，本文可能包含词汇、语法或文法方面的错误。 
  
## 另请参阅
<a name="MT_Footer"> </a>

#### 其他资源

[Office 365 中的电话拨入式会议](../misctopics/dial-in-conferencing-in-office-365.md)


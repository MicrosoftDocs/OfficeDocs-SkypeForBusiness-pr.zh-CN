---
title: 会议 Cmdlet
TOCTitle: 会议 Cmdlet
ms:assetid: 7ff94637-6319-4c45-9230-be34e8d81ede
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398641(v=OCS.15)
ms:contentKeyID: 49313406
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 会议 Cmdlet

 

_**上一次修改主题：** 2016-12-08_

通过 Microsoft Lync Server 2013，用户可以采用以下两种不同方式加入会议：通过使用会议应用程序（如 Lync 2013）或通过使用电话拨号加入。使用电话拨入的用户无法执行查看幻灯片、交换即时消息等操作，但他们可以完全参与会议的音频部分。

## 会议 Cmdlet

**CsDialInConferencing** cmdlet 用于配置电话拨入式会议属性，从指定用户通过呼叫以加入会议的电话号码，到用户加入会议后可以使用的小键盘命令（例如，按 6 可将电话静音或取消静音），所有属性都包括在内。会议的大多数其他功能（例如，用户可以记录会议、在会议过程中共享应用程序等）都是使用 **CsConferencingPolicy** cmdlet 进行管理的。

**[电话拨入式会议 Cmdlet](lync-server-2013-dial-in-conferencing-cmdlets.md)**

  -   
    [Get-CsConferenceDirectory](get-csconferencedirectory.md)

  -   
    [Move-CsConferenceDirectory](move-csconferencedirectory.md)

  -   
    [New-CsConferenceDirectory](new-csconferencedirectory.md)

  -   
    [Remove-CsConferenceDirectory](remove-csconferencedirectory.md)

  -   
    [Test-CsDialInConferencing](test-csdialinconferencing.md)

  -   
    [Get-CsDialInConferencingAccessNumber](get-csdialinconferencingaccessnumber.md)

  -   
    [New-CsDialInConferencingAccessNumber](new-csdialinconferencingaccessnumber.md)

  -   
    [Remove-CsDialInConferencingAccessNumber](remove-csdialinconferencingaccessnumber.md)

  -   
    [Set-CsDialInConferencingAccessNumber](set-csdialinconferencingaccessnumber.md)

  -   
    [Get-CsDialInConferencingConfiguration](get-csdialinconferencingconfiguration.md)

  -   
    [New-CsDialInConferencingConfiguration](new-csdialinconferencingconfiguration.md)

  -   
    [Remove-CsDialInConferencingConfiguration](remove-csdialinconferencingconfiguration.md)

  -   
    [Set-CsDialInConferencingConfiguration](set-csdialinconferencingconfiguration.md)

  -   
    [Get-CsDialInConferencingDtmfConfiguration](get-csdialinconferencingdtmfconfiguration.md)

  -   
    [New-CsDialInConferencingDtmfConfiguration](new-csdialinconferencingdtmfconfiguration.md)

  -   
    [Remove-CsDialInConferencingDtmfConfiguration](remove-csdialinconferencingdtmfconfiguration.md)

  -   
    [Set-CsDialInConferencingDtmfConfiguration](set-csdialinconferencingdtmfconfiguration.md)

  -   
    [Get-CsDialInConferencingLanguageList](get-csdialinconferencinglanguagelist.md)

**[Web 会议 Cmdlet](lync-server-2013-web-conferencing-cmdlets.md)**

  -   
    [Get-CsConferenceDisclaimer](get-csconferencedisclaimer.md)

  -   
    [Remove-CsConferenceDisclaimer](remove-csconferencedisclaimer.md)

  -   
    [Set-CsConferenceDisclaimer](set-csconferencedisclaimer.md)

  -   
    [Set-CsConferenceServer](set-csconferenceserver.md)

  -   
    [Get-CsConferencingConfiguration](get-csconferencingconfiguration.md)

  -   
    [New-CsConferencingConfiguration](new-csconferencingconfiguration.md)

  -   
    [Remove-CsConferencingConfiguration](remove-csconferencingconfiguration.md)

  -   
    [Set-CsConferencingConfiguration](set-csconferencingconfiguration.md)

  -   
    [Get-CsConferencingPolicy](get-csconferencingpolicy.md)

  -   
    [Grant-CsConferencingPolicy](grant-csconferencingpolicy.md)

  -   
    [New-CsConferencingPolicy](new-csconferencingpolicy.md)

  -   
    [Remove-CsConferencingPolicy](remove-csconferencingpolicy.md)

  -   
    [Set-CsConferencingPolicy](set-csconferencingpolicy.md)

  -   
    [Get-CsMeetingConfiguration](get-csmeetingconfiguration.md)

  -   
    [New-CsMeetingConfiguration](new-csmeetingconfiguration.md)

  -   
    [Remove-CsMeetingConfiguration](remove-csmeetingconfiguration.md)

  -   
    [Set-CsMeetingConfiguration](set-csmeetingconfiguration.md)

  - [Disable-CsMeetingRoom](disable-csmeetingroom.md)

  - [Enable-CsMeetingRoom](enable-csmeetingroom.md)

  - [Get-CsMeetingRoom](get-csmeetingroom.md)

  - [Move-CsMeetingRoom](Move-CsMeetingRoom.md)

  - [Set-CsMeetingRoom](set-csmeetingroom.md)

  -   
    [Test-CsASConference](test-csasconference.md)

  -   
    [Test-CsAVConference](test-csavconference.md)

  -   
    [Test-CsDataConference](test-csdataconference.md)

  -   
    [Test-CsWebApp](test-cswebapp.md)

  -   
    [Test-CsWebAppAnonymous](test-cswebappanonymous.md)

  -   
    [Test-CsWebScheduler](test-cswebscheduler.md)

## 另请参阅

#### 其他资源

[Lync Server PowerShell 博客](http://go.microsoft.com/fwlink/?linkid=203150%26clcid=0x804)


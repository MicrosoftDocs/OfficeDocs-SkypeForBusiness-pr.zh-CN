---
title: Lync Server 2013： cmdlet 索引
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Lync Server 2013 cmdlets index
ms:assetid: cd37aba7-3d27-4db9-b69f-3a6da1fb4b4a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398867(v=OCS.15)
ms:contentKeyID: 48185661
ms.date: 04/12/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fb713c1f328258bcb80173e0ff7e61ddd8304075
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42138513"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="lync-server-2013-cmdlets-index"></a>Lync Server 2013 cmdlet 索引

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2016-04-12_

Microsoft Lync Server 2013 随附有700个以上的 cmdlet，使管理员能够从命令行管理 Lync Server 2013。 Lync Server cmdlet 通常与 Lync Server 命令行管理程序一起使用。 使用 Lync Server 命令行管理程序的一种方法是，登录到运行 Lync Server 服务或服务器角色的计算机上，依次单击 "**开始**"、"**所有程序**"、" **Microsoft Lync server 2013**"，然后单击 " **Lync server Management Shell**"。 命令行管理程序打开之后，可通过键入类似如下的命令直接从命令行检索有关某个 cmdlet 的帮助：

    Get-Help New-CsVoicePolicy -Full

上述命令检索提供的有关 **New-CsVoicePolicy** cmdlet 的完整帮助。 要查看其他 cmdlet 的帮助，请将 **New-CsVoicePolicy** 替换为要检索其帮助信息的 cmdlet 的名称。

若要检索可用于管理 Lync Server 的 cmdlet 的完整列表，请在 Lync Server 命令行管理程序命令提示符处键入以下内容：

    Get-Command * -Module Lync -CommandType cmdlet

有关使用 Lync Server 命令行管理程序的详细信息，请参阅 Lync Server Windows PowerShell [https://go.microsoft.com/fwlink/p/?linkId=203150](https://go.microsoft.com/fwlink/p/?linkid=203150)博客 at。

<div>

## <a name="lync-server-2013-cmdlets"></a>Lync Server 2013 Cmdlet

以下是 Lync Server 2013 附带的 cmdlet 的列表：

  - [外接 CsSlaDelegates](https://technet.microsoft.com/library/Mt703199(v=OCS.15))

  - [批准-CsDeviceUpdateRule](https://technet.microsoft.com/library/Gg398949(v=OCS.15))

  - [Backup-Start-cspool](https://technet.microsoft.com/library/JJ204955(v=OCS.15))

  - [Clear-CsDeviceUpdateFile](https://technet.microsoft.com/library/Gg425835(v=OCS.15))

  - [Clear-CsDeviceUpdateLog](https://technet.microsoft.com/library/Gg412738(v=OCS.15))

  - [Clear-Set-cspersistentchatroom](https://technet.microsoft.com/library/JJ204976(v=OCS.15))

  - [转换-Export-csuserdata](https://technet.microsoft.com/library/JJ205337(v=OCS.15))

  - [调试-CsAddressBookReplication](https://technet.microsoft.com/library/JJ205232(v=OCS.15))

  - [调试-CsIntraPoolReplication](https://technet.microsoft.com/library/JJ205103(v=OCS.15))

  - [调试-CsLisConfiguration](https://technet.microsoft.com/library/Gg398710(v=OCS.15))

  - [Disable-CsAdDomain](https://technet.microsoft.com/library/Gg398785(v=OCS.15))

  - [Disable-CsAdForest](https://technet.microsoft.com/library/Gg398122(v=OCS.15))

  - [Disable-CsComputer](https://technet.microsoft.com/library/Gg399023(v=OCS.15))

  - [Disable-CsHostingProvider](https://technet.microsoft.com/library/Gg398481(v=OCS.15))

  - [Disable-Disable-csmeetingroom](https://technet.microsoft.com/library/JJ204723(v=OCS.15))

  - [Disable-CsPublicProvider](https://technet.microsoft.com/library/Gg398984(v=OCS.15))

  - [Disable-Get-csuser](https://technet.microsoft.com/library/Gg398747(v=OCS.15))

  - [Enable-CsAdDomain](https://technet.microsoft.com/library/Gg412764(v=OCS.15))

  - [Enable-CsAdForest](https://technet.microsoft.com/library/Gg425713(v=OCS.15))

  - [Enable-CsComputer](https://technet.microsoft.com/library/Gg412815(v=OCS.15))

  - [Enable-CsHostingProvider](https://technet.microsoft.com/library/Gg398166(v=OCS.15))

  - [Enable-Disable-csmeetingroom](https://technet.microsoft.com/library/JJ205062(v=OCS.15))

  - [Enable-CsPublicProvider](https://technet.microsoft.com/library/Gg398780(v=OCS.15))

  - [Enable-CsReplica](https://technet.microsoft.com/library/Gg425965(v=OCS.15))

  - [Enable-Enable-cstopology](https://technet.microsoft.com/library/Gg398398(v=OCS.15))

  - [Enable-Get-csuser](https://technet.microsoft.com/library/Gg398711(v=OCS.15))

  - [Export-Export-csarchivingdata](https://technet.microsoft.com/library/Gg398452(v=OCS.15))

  - [Export-CsConfiguration](https://technet.microsoft.com/library/Gg398627(v=OCS.15))

  - [Export-CsLisConfiguration](https://technet.microsoft.com/library/Gg398539(v=OCS.15))

  - [Export-Export-cspersistentchatdata](https://technet.microsoft.com/library/JJ205378(v=OCS.15))

  - [Export-CsRgsConfiguration](https://technet.microsoft.com/library/JJ205011(v=OCS.15))

  - [Export-Export-csuserdata](https://technet.microsoft.com/library/JJ204897(v=OCS.15))

  - [Set-csaccessedgeconfiguration](https://technet.microsoft.com/library/Gg398574(v=OCS.15))

  - [CsAdContact](https://technet.microsoft.com/library/Gg412776(v=OCS.15))

  - [CsAdDomain](https://technet.microsoft.com/library/Gg398453(v=OCS.15))

  - [CsAddressBookConfiguration](https://technet.microsoft.com/library/Gg398132(v=OCS.15))

  - [CsAdForest](https://technet.microsoft.com/library/Gg412995(v=OCS.15))

  - [CsAdminRole](https://technet.microsoft.com/library/Gg399050(v=OCS.15))

  - [CsAdminRoleAssignment](https://technet.microsoft.com/library/Gg398434(v=OCS.15))

  - [CsAdPrincipal](https://technet.microsoft.com/library/JJ205326(v=OCS.15))

  - [CsAdServerSchema](https://technet.microsoft.com/library/Gg413070(v=OCS.15))

  - [CsAdUser](https://technet.microsoft.com/library/Gg398592(v=OCS.15))

  - [CsAllowedDomain](https://technet.microsoft.com/library/Gg398164(v=OCS.15))

  - [CsAnalogDevice](https://technet.microsoft.com/library/Gg398748(v=OCS.15))

  - [CsAnnouncement](https://technet.microsoft.com/library/Gg398937(v=OCS.15))

  - [CsApplicationEndpoint](https://technet.microsoft.com/library/Gg398655(v=OCS.15))

  - [Set-csarchivingconfiguration](https://technet.microsoft.com/library/Gg399012(v=OCS.15))

  - [New-csarchivingpolicy](https://technet.microsoft.com/library/Gg425731(v=OCS.15))

  - [CsAudioTestServiceApplication](https://technet.microsoft.com/library/Gg412984(v=OCS.15))

  - [CsAutodiscoverConfiguration](https://technet.microsoft.com/library/Hh690014(v=OCS.15))

  - [CsAVEdgeConfiguration](https://technet.microsoft.com/library/Gg413008(v=OCS.15))

  - [CsBackupServiceConfiguration](https://technet.microsoft.com/library/JJ205087(v=OCS.15))

  - [CsBackupServiceStatus](https://technet.microsoft.com/library/JJ205032(v=OCS.15))

  - [CsBandwidthPolicyServiceConfiguration](https://technet.microsoft.com/library/Gg412727(v=OCS.15))

  - [CsBlockedDomain](https://technet.microsoft.com/library/Gg398424(v=OCS.15))

  - [CsCallParkOrbit](https://technet.microsoft.com/library/Gg398554(v=OCS.15))

  - [Set-cscdrconfiguration](https://technet.microsoft.com/library/Gg398298(v=OCS.15))

  - [Set-cscertificate](https://technet.microsoft.com/library/Gg398227(v=OCS.15))

  - [CsClientAccessLicense](https://technet.microsoft.com/library/JJ204853(v=OCS.15))

  - [CsClientCertificate](https://technet.microsoft.com/library/Gg398143(v=OCS.15))

  - [CsClientPinInfo](https://technet.microsoft.com/library/Gg425947(v=OCS.15))

  - [Set-csclientpolicy](https://technet.microsoft.com/library/Gg398830(v=OCS.15))

  - [CsClientVersionConfiguration](https://technet.microsoft.com/library/Gg399072(v=OCS.15))

  - [CsClientVersionPolicy](https://technet.microsoft.com/library/Gg398957(v=OCS.15))

  - [CsClientVersionPolicyRule](https://technet.microsoft.com/library/Gg413048(v=OCS.15))

  - [CsClsRegion](https://technet.microsoft.com/library/JJ204879(v=OCS.15))

  - [CsClsSearchTerm](https://technet.microsoft.com/library/JJ205061(v=OCS.15))

  - [New-csclsscenario](https://technet.microsoft.com/library/JJ205091(v=OCS.15))

  - [CsClsSecurityGroup](https://technet.microsoft.com/library/JJ205285(v=OCS.15))

  - [CsCommonAreaPhone](https://technet.microsoft.com/library/Gg412934(v=OCS.15))

  - [CsComputer](https://technet.microsoft.com/library/Gg425959(v=OCS.15))

  - [New-csconferencedirectory](https://technet.microsoft.com/library/Gg425771(v=OCS.15))

  - [CsConferenceDisclaimer](https://technet.microsoft.com/library/Gg425714(v=OCS.15))

  - [CsConferencingConfiguration](https://technet.microsoft.com/library/Gg398965(v=OCS.15))

  - [Set-csconferencingpolicy](https://technet.microsoft.com/library/Gg398293(v=OCS.15))

  - [CsConfigurationStoreLocation](https://technet.microsoft.com/library/Gg412814(v=OCS.15))

  - [CsCpsConfiguration](https://technet.microsoft.com/library/Gg398948(v=OCS.15))

  - [CsDatabaseMirrorState](https://technet.microsoft.com/library/JJ204845(v=OCS.15))

  - [CsDeviceUpdateConfiguration](https://technet.microsoft.com/library/Gg399030(v=OCS.15))

  - [CsDeviceUpdateRule](https://technet.microsoft.com/library/Gg398215(v=OCS.15))

  - [CsDiagnosticConfiguration](https://technet.microsoft.com/library/Gg413034(v=OCS.15))

  - [CsDiagnosticHeaderConfiguration](https://technet.microsoft.com/library/Gg412774(v=OCS.15))

  - [Set-csdialinconferencingaccessnumber](https://technet.microsoft.com/library/Gg413015(v=OCS.15))

  - [Set-csdialinconferencingconfiguration](https://technet.microsoft.com/library/Gg398575(v=OCS.15))

  - [New-csdialinconferencingdtmfconfiguration](https://technet.microsoft.com/library/Gg398578(v=OCS.15))

  - [CsDialInConferencingLanguageList](https://technet.microsoft.com/library/Gg425869(v=OCS.15))

  - [Grant-csdialplan](https://technet.microsoft.com/library/Gg413043(v=OCS.15))

  - [CsEffectivePolicy](https://technet.microsoft.com/library/JJ204636(v=OCS.15))

  - [CsEnhancedEmergencyServiceDisclaimer](https://technet.microsoft.com/library/Gg412877(v=OCS.15))

  - [Set-csexternalaccesspolicy](https://technet.microsoft.com/library/Gg425805(v=OCS.15))

  - [CsExUmContact](https://technet.microsoft.com/library/Gg412725(v=OCS.15))

  - [CsFileTransferFilterConfiguration](https://technet.microsoft.com/library/Gg398527(v=OCS.15))

  - [CsFIPSConfiguration](https://technet.microsoft.com/library/JJ204904(v=OCS.15))

  - [CsHealthMonitoringConfiguration](https://technet.microsoft.com/library/Gg398667(v=OCS.15))

  - [CsHostedVoicemailPolicy](https://technet.microsoft.com/library/Gg398348(v=OCS.15))

  - [CsHostingProvider](https://technet.microsoft.com/library/Gg413078(v=OCS.15))

  - [CsImFilterConfiguration](https://technet.microsoft.com/library/Gg398980(v=OCS.15))

  - [CsKerberosAccountAssignment](https://technet.microsoft.com/library/Gg398526(v=OCS.15))

  - [CsLisCivicAddress](https://technet.microsoft.com/library/Gg398459(v=OCS.15))

  - [CsLisLocation](https://technet.microsoft.com/library/Gg412834(v=OCS.15))

  - [CsLisPort](https://technet.microsoft.com/library/Gg398820(v=OCS.15))

  - [CsLisServiceProvider](https://technet.microsoft.com/library/Gg398116(v=OCS.15))

  - [CsLisSubnet](https://technet.microsoft.com/library/Gg398473(v=OCS.15))

  - [CsLisSwitch](https://technet.microsoft.com/library/Gg425769(v=OCS.15))

  - [CsLisWirelessAccessPoint](https://technet.microsoft.com/library/Gg398117(v=OCS.15))

  - [New-cslocationpolicy](https://technet.microsoft.com/library/Gg398911(v=OCS.15))

  - [CsManagementConnection](https://technet.microsoft.com/library/Gg412849(v=OCS.15))

  - [Get-csmanagementstorereplicationstatus](https://technet.microsoft.com/library/Gg399052(v=OCS.15))

  - [CsMcxConfiguration](https://technet.microsoft.com/library/Hh690031(v=OCS.15))

  - [Set-csmediaconfiguration](https://technet.microsoft.com/library/Gg398128(v=OCS.15))

  - [Get-csmeetingconfiguration](https://technet.microsoft.com/library/Gg425875(v=OCS.15))

  - [Disable-csmeetingroom](https://technet.microsoft.com/library/JJ205277(v=OCS.15))

  - [Set-csmobilitypolicy](https://technet.microsoft.com/library/Hh690017(v=OCS.15))

  - [CsNetworkBandwidthPolicyProfile](https://technet.microsoft.com/library/Gg425815(v=OCS.15))

  - [CsNetworkConfiguration](https://technet.microsoft.com/library/Gg398140(v=OCS.15))

  - [CsNetworkInterface](https://technet.microsoft.com/library/Gg398121(v=OCS.15))

  - [CsNetworkInterRegionRoute](https://technet.microsoft.com/library/Gg425817(v=OCS.15))

  - [New-csnetworkintersitepolicy](https://technet.microsoft.com/library/Gg412769(v=OCS.15))

  - [CsNetworkRegion](https://technet.microsoft.com/library/Gg398406(v=OCS.15))

  - [CsNetworkRegionLink](https://technet.microsoft.com/library/Gg398972(v=OCS.15))

  - [CsNetworkSite](https://technet.microsoft.com/library/Gg398766(v=OCS.15))

  - [CsNetworkSubnet](https://technet.microsoft.com/library/Gg412825(v=OCS.15))

  - [Set-csoauthconfiguration](https://technet.microsoft.com/library/JJ205155(v=OCS.15))

  - [CsOAuthServer](https://technet.microsoft.com/library/JJ205238(v=OCS.15))

  - [CsOutboundCallingNumberTranslationRule](https://technet.microsoft.com/library/JJ204962(v=OCS.15))

  - [CsOutboundTranslationRule](https://technet.microsoft.com/library/Gg398104(v=OCS.15))

  - [CsPartnerApplication](https://technet.microsoft.com/library/JJ205128(v=OCS.15))

  - [CsPersistentChatAddin](https://technet.microsoft.com/library/JJ204670(v=OCS.15))

  - [CsPersistentChatCategory](https://technet.microsoft.com/library/JJ204771(v=OCS.15))

  - [CsPersistentChatComplianceConfiguration](https://technet.microsoft.com/library/JJ204625(v=OCS.15))

  - [CsPersistentChatConfiguration](https://technet.microsoft.com/library/JJ205140(v=OCS.15))

  - [CsPersistentChatEligiblePrincipal](https://technet.microsoft.com/library/JJ204891(v=OCS.15))

  - [CsPersistentChatEndpoint](https://technet.microsoft.com/library/JJ204764(v=OCS.15))

  - [CsPersistentChatPolicy](https://technet.microsoft.com/library/JJ204673(v=OCS.15))

  - [Set-cspersistentchatroom](https://technet.microsoft.com/library/JJ205123(v=OCS.15))

  - [CsPersistentChatState](https://technet.microsoft.com/library/JJ204915(v=OCS.15))

  - [Get-cspinpolicy](https://technet.microsoft.com/library/Gg398262(v=OCS.15))

  - [Start-cspool](https://technet.microsoft.com/library/Gg398992(v=OCS.15))

  - [CsPoolBackupRelationship](https://technet.microsoft.com/library/JJ204745(v=OCS.15))

  - [CsPoolUpgradeReadinessState](https://technet.microsoft.com/library/JJ204689(v=OCS.15))

  - [CsPresencePolicy](https://technet.microsoft.com/library/Gg398463(v=OCS.15))

  - [CsPresenceProvider](https://technet.microsoft.com/library/JJ204705(v=OCS.15))

  - [CsPrivacyConfiguration](https://technet.microsoft.com/library/Gg413002(v=OCS.15))

  - [CsProxyConfiguration](https://technet.microsoft.com/library/Gg399011(v=OCS.15))

  - [CsPstnUsage](https://technet.microsoft.com/library/Gg412734(v=OCS.15))

  - [CsPublicProvider](https://technet.microsoft.com/library/Gg412945(v=OCS.15))

  - [CsPushNotificationConfiguration](https://technet.microsoft.com/library/Hh690049(v=OCS.15))

  - [New-csqoeconfiguration](https://technet.microsoft.com/library/Gg399004(v=OCS.15))

  - [CsRegistrarConfiguration](https://technet.microsoft.com/library/Gg398483(v=OCS.15))

  - [CsReportingConfiguration](https://technet.microsoft.com/library/JJ205356(v=OCS.15))

  - [CsRgsAgentGroup](https://technet.microsoft.com/library/Gg425793(v=OCS.15))

  - [CsRgsConfiguration](https://technet.microsoft.com/library/Gg412762(v=OCS.15))

  - [CsRgsHolidaySet](https://technet.microsoft.com/library/Gg412983(v=OCS.15))

  - [CsRgsHoursOfBusiness](https://technet.microsoft.com/library/Gg398284(v=OCS.15))

  - [CsRgsQueue](https://technet.microsoft.com/library/Gg412759(v=OCS.15))

  - [CsRgsWorkflow](https://technet.microsoft.com/library/Gg425766(v=OCS.15))

  - [CsRoutingConfiguration](https://technet.microsoft.com/library/Gg425851(v=OCS.15))

  - [CsServerApplication](https://technet.microsoft.com/library/Gg425948(v=OCS.15))

  - [CsServerVersion](https://technet.microsoft.com/library/Gg398470(v=OCS.15))

  - [Get-csservice](https://technet.microsoft.com/library/Gg413038(v=OCS.15))

  - [CsSimpleUrlConfiguration](https://technet.microsoft.com/library/Gg398392(v=OCS.15))

  - [CsSipDomain](https://technet.microsoft.com/library/Gg398701(v=OCS.15))

  - [CsSipResponseCodeTranslationRule](https://technet.microsoft.com/library/Gg398130(v=OCS.15))

  - [Set-csslaconfiguration](https://technet.microsoft.com/library/Mt703200(v=OCS.15))

  - [Get-cssite](https://technet.microsoft.com/library/Gg398185(v=OCS.15))

  - [CsStaticRoutingConfiguration](https://technet.microsoft.com/library/Gg398754(v=OCS.15))

  - [CsTestDevice](https://technet.microsoft.com/library/Gg398304(v=OCS.15))

  - [CsTestUserCredential](https://technet.microsoft.com/library/JJ204759(v=OCS.15))

  - [Enable-cstopology](https://technet.microsoft.com/library/Gg412824(v=OCS.15))

  - [CsTrunk](https://technet.microsoft.com/library/JJ205244(v=OCS.15))

  - [Remove-cstrunkconfiguration](https://technet.microsoft.com/library/Gg398224(v=OCS.15))

  - [CsTrustedApplication](https://technet.microsoft.com/library/Gg399025(v=OCS.15))

  - [CsTrustedApplicationComputer](https://technet.microsoft.com/library/Gg425843(v=OCS.15))

  - [CsTrustedApplicationEndpoint](https://technet.microsoft.com/library/Gg413035(v=OCS.15))

  - [CsTrustedApplicationPool](https://technet.microsoft.com/library/Gg413055(v=OCS.15))

  - [CsUCPhoneConfiguration](https://technet.microsoft.com/library/Gg398070(v=OCS.15))

  - [CsUICulture](https://technet.microsoft.com/library/Gg412900(v=OCS.15))

  - [CsUnassignedNumber](https://technet.microsoft.com/library/Gg412792(v=OCS.15))

  - [Get-csuser](https://technet.microsoft.com/library/Gg398125(v=OCS.15))

  - [CsUserAcp](https://technet.microsoft.com/library/Gg398978(v=OCS.15))

  - [CsUserDatabaseState](https://technet.microsoft.com/library/Gg398831(v=OCS.15))

  - [CsUserPoolInfo](https://technet.microsoft.com/library/Gg398615(v=OCS.15))

  - [CsUserReplicatorConfiguration](https://technet.microsoft.com/library/Gg398548(v=OCS.15))

  - [CsUserServicesConfiguration](https://technet.microsoft.com/library/Gg398133(v=OCS.15))

  - [CsUserServicesPolicy](https://technet.microsoft.com/library/JJ204838(v=OCS.15))

  - [CsVoiceConfiguration](https://technet.microsoft.com/library/Gg398815(v=OCS.15))

  - [CsVoicemailReroutingConfiguration](https://technet.microsoft.com/library/Gg425732(v=OCS.15))

  - [CsVoiceNormalizationRule](https://technet.microsoft.com/library/Gg398393(v=OCS.15))

  - [Set-csvoicepolicy](https://technet.microsoft.com/library/Gg398101(v=OCS.15))

  - [CsVoiceRoute](https://technet.microsoft.com/library/Gg425926(v=OCS.15))

  - [Grant-csvoiceroutingpolicy](https://technet.microsoft.com/library/JJ204940(v=OCS.15))

  - [CsVoiceTestConfiguration](https://technet.microsoft.com/library/Gg412957(v=OCS.15))

  - [New-cswatchernodeconfiguration](https://technet.microsoft.com/library/JJ204739(v=OCS.15))

  - [CsWebServiceConfiguration](https://technet.microsoft.com/library/Gg425751(v=OCS.15))

  - [Start-cswindowsservice](https://technet.microsoft.com/library/Gg398803(v=OCS.15))

  - [CsXmppAllowedPartner](https://technet.microsoft.com/library/JJ204981(v=OCS.15))

  - [CsXmppGatewayConfiguration](https://technet.microsoft.com/library/JJ204869(v=OCS.15))

  - [Grant-New-csarchivingpolicy](https://technet.microsoft.com/library/Gg398475(v=OCS.15))

  - [Grant-Set-csclientpolicy](https://technet.microsoft.com/library/Gg412942(v=OCS.15))

  - [Grant-CsClientVersionPolicy](https://technet.microsoft.com/library/Gg412903(v=OCS.15))

  - [Grant-Set-csconferencingpolicy](https://technet.microsoft.com/library/Gg425937(v=OCS.15))

  - [Grant-Grant-csdialplan](https://technet.microsoft.com/library/Gg398547(v=OCS.15))

  - [Grant-Set-csexternalaccesspolicy](https://technet.microsoft.com/library/Gg425942(v=OCS.15))

  - [Grant-CsHostedVoicemailPolicy](https://technet.microsoft.com/library/Gg412829(v=OCS.15))

  - [Grant-New-cslocationpolicy](https://technet.microsoft.com/library/Gg413049(v=OCS.15))

  - [Grant-Set-csmobilitypolicy](https://technet.microsoft.com/library/Hh690038(v=OCS.15))

  - [Grant-CsOUPermission](https://technet.microsoft.com/library/Gg425739(v=OCS.15))

  - [Grant-CsPersistentChatPolicy](https://technet.microsoft.com/library/JJ204907(v=OCS.15))

  - [Grant-Get-cspinpolicy](https://technet.microsoft.com/library/Gg398871(v=OCS.15))

  - [Grant-CsPresencePolicy](https://technet.microsoft.com/library/Gg398571(v=OCS.15))

  - [Grant-CsSetupPermission](https://technet.microsoft.com/library/Gg398569(v=OCS.15))

  - [Grant-CsUserServicesPolicy](https://technet.microsoft.com/library/JJ205388(v=OCS.15))

  - [Grant-Set-csvoicepolicy](https://technet.microsoft.com/library/Gg398828(v=OCS.15))

  - [Grant-Grant-csvoiceroutingpolicy](https://technet.microsoft.com/library/JJ205141(v=OCS.15))

  - [Import-CsAnnouncementFile](https://technet.microsoft.com/library/Gg398472(v=OCS.15))

  - [Import-Set-cscertificate](https://technet.microsoft.com/library/Gg398688(v=OCS.15))

  - [Import-CsConfiguration](https://technet.microsoft.com/library/Gg398800(v=OCS.15))

  - [Import-CsDeviceUpdate](https://technet.microsoft.com/library/Gg398861(v=OCS.15))

  - [Import-CsLegacyConferenceDirectory](https://technet.microsoft.com/library/Gg398418(v=OCS.15))

  - [Import-CsLegacyConfiguration](https://technet.microsoft.com/library/Gg412923(v=OCS.15))

  - [Import-CsLisConfiguration](https://technet.microsoft.com/library/Gg398380(v=OCS.15))

  - [Import-Export-cspersistentchatdata](https://technet.microsoft.com/library/JJ204709(v=OCS.15))

  - [Import-CsRgsAudioFile](https://technet.microsoft.com/library/Gg412830(v=OCS.15))

  - [Import-CsRgsConfiguration](https://technet.microsoft.com/library/JJ205245(v=OCS.15))

  - [Import-Export-csuserdata](https://technet.microsoft.com/library/JJ205373(v=OCS.15))

  - [Install-CsAdServerSchema](https://technet.microsoft.com/library/Gg398681(v=OCS.15))

  - [Install-CsDatabase](https://technet.microsoft.com/library/Gg399044(v=OCS.15))

  - [Install-CsMirrorDatabase](https://technet.microsoft.com/library/JJ204986(v=OCS.15))

  - [调用 Invoke-csarchivingdatabasepurge](https://technet.microsoft.com/library/JJ204627(v=OCS.15))

  - [调用 CsBackupServiceSync](https://technet.microsoft.com/library/JJ205374(v=OCS.15))

  - [调用 Invoke-cscdrdatabasepurge](https://technet.microsoft.com/library/JJ205113(v=OCS.15))

  - [调用 CsDatabaseFailover](https://technet.microsoft.com/library/JJ204744(v=OCS.15))

  - [调用 CsManagementServerFailover](https://technet.microsoft.com/library/JJ204647(v=OCS.15))

  - [调用 CsManagementStoreReplication](https://technet.microsoft.com/library/Gg413060(v=OCS.15))

  - [调用 CsPoolFailBack](https://technet.microsoft.com/library/JJ204873(v=OCS.15))

  - [调用 CsPoolFailOver](https://technet.microsoft.com/library/JJ205189(v=OCS.15))

  - [调用 CsQoEDatabasePurge](https://technet.microsoft.com/library/JJ205247(v=OCS.15))

  - [调用 Invoke-csucsrollback](https://technet.microsoft.com/library/JJ204661(v=OCS.15))

  - [Lock-Unlock-csclientpin](https://technet.microsoft.com/library/Gg398650(v=OCS.15))

  - [Merge-CsLegacyTopology](https://technet.microsoft.com/library/Gg425870(v=OCS.15))

  - [移动-CsAnalogDevice](https://technet.microsoft.com/library/Gg398816(v=OCS.15))

  - [移动-CsApplicationEndpoint](https://technet.microsoft.com/library/Gg398188(v=OCS.15))

  - [移动-CsCommonAreaPhone](https://technet.microsoft.com/library/Gg412837(v=OCS.15))

  - [移动-New-csconferencedirectory](https://technet.microsoft.com/library/Gg412968(v=OCS.15))

  - [移动-CsExUmContact](https://technet.microsoft.com/library/Gg425842(v=OCS.15))

  - [移动-CsLegacyUser](https://technet.microsoft.com/library/Gg413025(v=OCS.15))

  - [移动-Move-csmanagementserver](https://technet.microsoft.com/library/Gg412921(v=OCS.15))

  - [移动-Disable-csmeetingroom](https://technet.microsoft.com/library/JJ204889(v=OCS.15))

  - [移动-CsRgsConfiguration](https://technet.microsoft.com/library/Gg398782(v=OCS.15))

  - [移动-Get-csuser](https://technet.microsoft.com/library/Gg398528(v=OCS.15))

  - [新 CsAddressBookConfiguration](https://technet.microsoft.com/library/Gg398395(v=OCS.15))

  - [新 CsAdminRole](https://technet.microsoft.com/library/Gg398271(v=OCS.15))

  - [新 CsAllowedDomain](https://technet.microsoft.com/library/Gg398628(v=OCS.15))

  - [新 CsAnalogDevice](https://technet.microsoft.com/library/Gg412937(v=OCS.15))

  - [新 CsAnnouncement](https://technet.microsoft.com/library/Gg398522(v=OCS.15))

  - [新 Set-csarchivingconfiguration](https://technet.microsoft.com/library/Gg398471(v=OCS.15))

  - [新 New-csarchivingpolicy](https://technet.microsoft.com/library/Gg399032(v=OCS.15))

  - [新 CsAutodiscoverConfiguration](https://technet.microsoft.com/library/Hh690022(v=OCS.15))

  - [新 CsAVEdgeConfiguration](https://technet.microsoft.com/library/Gg412884(v=OCS.15))

  - [新 CsBandwidthPolicyServiceConfiguration](https://technet.microsoft.com/library/Gg398175(v=OCS.15))

  - [新 CsBlockedDomain](https://technet.microsoft.com/library/Gg398822(v=OCS.15))

  - [新 CsCallParkOrbit](https://technet.microsoft.com/library/Gg398936(v=OCS.15))

  - [新 Set-cscdrconfiguration](https://technet.microsoft.com/library/Gg399018(v=OCS.15))

  - [新 Set-csclientpolicy](https://technet.microsoft.com/library/Gg425949(v=OCS.15))

  - [新 CsClientPolicyEntry](https://technet.microsoft.com/library/Gg399046(v=OCS.15))

  - [新 CsClientVersionConfiguration](https://technet.microsoft.com/library/Gg399029(v=OCS.15))

  - [新 CsClientVersionPolicy](https://technet.microsoft.com/library/Gg398709(v=OCS.15))

  - [新 CsClientVersionPolicyRule](https://technet.microsoft.com/library/Gg398905(v=OCS.15))

  - [新 CsClsRegion](https://technet.microsoft.com/library/JJ204658(v=OCS.15))

  - [新 New-csclsscenario](https://technet.microsoft.com/library/JJ205022(v=OCS.15))

  - [新 CsClsSecurityGroup](https://technet.microsoft.com/library/JJ205359(v=OCS.15))

  - [新 CsCommonAreaPhone](https://technet.microsoft.com/library/Gg398430(v=OCS.15))

  - [新 New-csconferencedirectory](https://technet.microsoft.com/library/Gg413080(v=OCS.15))

  - [新 CsConferencingConfiguration](https://technet.microsoft.com/library/Gg412967(v=OCS.15))

  - [新 Set-csconferencingpolicy](https://technet.microsoft.com/library/Gg413019(v=OCS.15))

  - [新 CsCpsConfiguration](https://technet.microsoft.com/library/Gg412919(v=OCS.15))

  - [新 CsDeviceUpdateConfiguration](https://technet.microsoft.com/library/Gg425761(v=OCS.15))

  - [新 CsDiagnosticConfiguration](https://technet.microsoft.com/library/Gg398733(v=OCS.15))

  - [新 CsDiagnosticHeaderConfiguration](https://technet.microsoft.com/library/Gg398350(v=OCS.15))

  - [新 CsDiagnosticsFilter](https://technet.microsoft.com/library/Gg413009(v=OCS.15))

  - [新 Set-csdialinconferencingaccessnumber](https://technet.microsoft.com/library/Gg398818(v=OCS.15))

  - [新 Set-csdialinconferencingconfiguration](https://technet.microsoft.com/library/Gg412816(v=OCS.15))

  - [新 New-csdialinconferencingdtmfconfiguration](https://technet.microsoft.com/library/Gg425792(v=OCS.15))

  - [新 Grant-csdialplan](https://technet.microsoft.com/library/Gg425860(v=OCS.15))

  - [新 CsExtendedTest](https://technet.microsoft.com/library/JJ205275(v=OCS.15))

  - [新 Set-csexternalaccesspolicy](https://technet.microsoft.com/library/Gg398441(v=OCS.15))

  - [新 CsExUmContact](https://technet.microsoft.com/library/Gg398139(v=OCS.15))

  - [新 CsFileTransferFilterConfiguration](https://technet.microsoft.com/library/Gg425897(v=OCS.15))

  - [新 CsFIPSConfiguration](https://technet.microsoft.com/library/JJ205114(v=OCS.15))

  - [新 CsHealthMonitoringConfiguration](https://technet.microsoft.com/library/Gg398718(v=OCS.15))

  - [新 CsHostedVoicemailPolicy](https://technet.microsoft.com/library/Gg398653(v=OCS.15))

  - [新 CsHostingProvider](https://technet.microsoft.com/library/Gg398490(v=OCS.15))

  - [新 CsImFilterConfiguration](https://technet.microsoft.com/library/Gg398244(v=OCS.15))

  - [新 CsIssuedCertId](https://technet.microsoft.com/library/Gg425814(v=OCS.15))

  - [新 CsKerberosAccount](https://technet.microsoft.com/library/Gg398485(v=OCS.15))

  - [新 CsKerberosAccountAssignment](https://technet.microsoft.com/library/Gg398074(v=OCS.15))

  - [新 New-cslocationpolicy](https://technet.microsoft.com/library/Gg398231(v=OCS.15))

  - [新 CsMcxConfiguration](https://technet.microsoft.com/library/Hh690035(v=OCS.15))

  - [新 Set-csmediaconfiguration](https://technet.microsoft.com/library/Gg425881(v=OCS.15))

  - [新 Get-csmeetingconfiguration](https://technet.microsoft.com/library/Gg398065(v=OCS.15))

  - [新 Set-csmobilitypolicy](https://technet.microsoft.com/library/Hh689987(v=OCS.15))

  - [新 CsNetworkBandwidthPolicyProfile](https://technet.microsoft.com/library/Gg398675(v=OCS.15))

  - [新 CsNetworkBWAlternatePath](https://technet.microsoft.com/library/Gg398732(v=OCS.15))

  - [新 CsNetworkBWPolicy](https://technet.microsoft.com/library/Gg412916(v=OCS.15))

  - [新 CsNetworkInterRegionRoute](https://technet.microsoft.com/library/Gg398779(v=OCS.15))

  - [新 New-csnetworkintersitepolicy](https://technet.microsoft.com/library/Gg398994(v=OCS.15))

  - [新 CsNetworkMediaBypassConfiguration](https://technet.microsoft.com/library/Gg425718(v=OCS.15))

  - [新 CsNetworkRegion](https://technet.microsoft.com/library/Gg425829(v=OCS.15))

  - [新 CsNetworkRegionLink](https://technet.microsoft.com/library/Gg398437(v=OCS.15))

  - [新 CsNetworkSite](https://technet.microsoft.com/library/Gg398365(v=OCS.15))

  - [新 CsNetworkSubnet](https://technet.microsoft.com/library/Gg398226(v=OCS.15))

  - [新 CsOAuthServer](https://technet.microsoft.com/library/JJ205206(v=OCS.15))

  - [新 CsOutboundCallingNumberTranslationRule](https://technet.microsoft.com/library/JJ205097(v=OCS.15))

  - [新 CsOutboundTranslationRule](https://technet.microsoft.com/library/Gg412803(v=OCS.15))

  - [新 CsPartnerApplication](https://technet.microsoft.com/library/JJ204628(v=OCS.15))

  - [新 CsPersistentChatAddin](https://technet.microsoft.com/library/JJ204641(v=OCS.15))

  - [新 CsPersistentChatCategory](https://technet.microsoft.com/library/JJ204803(v=OCS.15))

  - [新 CsPersistentChatComplianceConfiguration](https://technet.microsoft.com/library/JJ205163(v=OCS.15))

  - [新 CsPersistentChatConfiguration](https://technet.microsoft.com/library/JJ205330(v=OCS.15))

  - [新 CsPersistentChatEndpoint](https://technet.microsoft.com/library/JJ204811(v=OCS.15))

  - [新 CsPersistentChatPolicy](https://technet.microsoft.com/library/JJ205396(v=OCS.15))

  - [新 Set-cspersistentchatroom](https://technet.microsoft.com/library/JJ205166(v=OCS.15))

  - [新 Get-cspinpolicy](https://technet.microsoft.com/library/Gg398935(v=OCS.15))

  - [新 CsPresencePolicy](https://technet.microsoft.com/library/Gg412747(v=OCS.15))

  - [新 CsPresenceProvider](https://technet.microsoft.com/library/JJ204895(v=OCS.15))

  - [新 CsPrivacyConfiguration](https://technet.microsoft.com/library/Gg398807(v=OCS.15))

  - [新 CsProxyConfiguration](https://technet.microsoft.com/library/Gg398335(v=OCS.15))

  - [新 CsPublicProvider](https://technet.microsoft.com/library/Gg398161(v=OCS.15))

  - [新 CsPushNotificationConfiguration](https://technet.microsoft.com/library/Hh690027(v=OCS.15))

  - [新 New-csqoeconfiguration](https://technet.microsoft.com/library/Gg398325(v=OCS.15))

  - [新 CsRegistrarConfiguration](https://technet.microsoft.com/library/Gg425893(v=OCS.15))

  - [新 CsReportingConfiguration](https://technet.microsoft.com/library/JJ204787(v=OCS.15))

  - [新 CsRgsAgentGroup](https://technet.microsoft.com/library/Gg413065(v=OCS.15))

  - [新 CsRgsAnswer](https://technet.microsoft.com/library/Gg412812(v=OCS.15))

  - [新 New-csrgscallaction](https://technet.microsoft.com/library/Gg398136(v=OCS.15))

  - [新 CsRgsHoliday](https://technet.microsoft.com/library/Gg398075(v=OCS.15))

  - [新 CsRgsHolidaySet](https://technet.microsoft.com/library/Gg398403(v=OCS.15))

  - [新 CsRgsHoursOfBusiness](https://technet.microsoft.com/library/Gg398291(v=OCS.15))

  - [新 CsRgsPrompt](https://technet.microsoft.com/library/Gg398486(v=OCS.15))

  - [新 CsRgsQuestion](https://technet.microsoft.com/library/Gg398186(v=OCS.15))

  - [新 CsRgsQueue](https://technet.microsoft.com/library/Gg398989(v=OCS.15))

  - [新 CsRgsTimeRange](https://technet.microsoft.com/library/Gg399040(v=OCS.15))

  - [新 CsRgsWorkflow](https://technet.microsoft.com/library/Gg398246(v=OCS.15))

  - [新 CsRoutingConfiguration](https://technet.microsoft.com/library/Gg399056(v=OCS.15))

  - [新 CsServerApplication](https://technet.microsoft.com/library/Gg398096(v=OCS.15))

  - [新 CsSimpleUrl](https://technet.microsoft.com/library/Gg398180(v=OCS.15))

  - [新 CsSimpleUrlConfiguration](https://technet.microsoft.com/library/Gg425813(v=OCS.15))

  - [新 CsSimpleUrlEntry](https://technet.microsoft.com/library/Gg425902(v=OCS.15))

  - [新 CsSipDomain](https://technet.microsoft.com/library/Gg425857(v=OCS.15))

  - [新 CsSipProxyCustom](https://technet.microsoft.com/library/Gg425904(v=OCS.15))

  - [新 CsSipProxyRealm](https://technet.microsoft.com/library/Gg413084(v=OCS.15))

  - [新 CsSipProxyTCP](https://technet.microsoft.com/library/Gg425745(v=OCS.15))

  - [新 CsSipProxyTLS](https://technet.microsoft.com/library/Gg398629(v=OCS.15))

  - [新 CsSipProxyTransport](https://technet.microsoft.com/library/Gg398489(v=OCS.15))

  - [新 CsSipProxyUseDefault](https://technet.microsoft.com/library/Gg398274(v=OCS.15))

  - [新 CsSipProxyUseDefaultCert](https://technet.microsoft.com/library/Gg425858(v=OCS.15))

  - [新 CsSipResponseCodeTranslationRule](https://technet.microsoft.com/library/Gg413041(v=OCS.15))

  - [新 CsStaticRoute](https://technet.microsoft.com/library/Gg398265(v=OCS.15))

  - [新 CsStaticRoutingConfiguration](https://technet.microsoft.com/library/Gg425811(v=OCS.15))

  - [新 CsTestDevice](https://technet.microsoft.com/library/Gg425899(v=OCS.15))

  - [新 Remove-cstrunkconfiguration](https://technet.microsoft.com/library/Gg413021(v=OCS.15))

  - [新 CsTrustedApplication](https://technet.microsoft.com/library/Gg398259(v=OCS.15))

  - [新 CsTrustedApplicationComputer](https://technet.microsoft.com/library/Gg398405(v=OCS.15))

  - [新 CsTrustedApplicationEndpoint](https://technet.microsoft.com/library/Gg398594(v=OCS.15))

  - [新 CsTrustedApplicationPool](https://technet.microsoft.com/library/Gg425804(v=OCS.15))

  - [新 CsUCPhoneConfiguration](https://technet.microsoft.com/library/Gg398445(v=OCS.15))

  - [新 CsUnassignedNumber](https://technet.microsoft.com/library/Gg398651(v=OCS.15))

  - [新 CsUserReplicatorConfiguration](https://technet.microsoft.com/library/Gg399059(v=OCS.15))

  - [新 CsUserServicesConfiguration](https://technet.microsoft.com/library/Gg412926(v=OCS.15))

  - [新 CsUserServicesPolicy](https://technet.microsoft.com/library/JJ205072(v=OCS.15))

  - [新 CsVoicemailReroutingConfiguration](https://technet.microsoft.com/library/Gg425849(v=OCS.15))

  - [新 CsVoiceNormalizationRule](https://technet.microsoft.com/library/Gg398240(v=OCS.15))

  - [新 Set-csvoicepolicy](https://technet.microsoft.com/library/Gg425856(v=OCS.15))

  - [新 CsVoiceRegex](https://technet.microsoft.com/library/Gg412751(v=OCS.15))

  - [新 CsVoiceRoute](https://technet.microsoft.com/library/Gg398197(v=OCS.15))

  - [新 Grant-csvoiceroutingpolicy](https://technet.microsoft.com/library/JJ205135(v=OCS.15))

  - [新 CsVoiceTestConfiguration](https://technet.microsoft.com/library/Gg398961(v=OCS.15))

  - [新 New-cswatchernodeconfiguration](https://technet.microsoft.com/library/JJ205254(v=OCS.15))

  - [新 CsWebLink](https://technet.microsoft.com/library/Hh690053(v=OCS.15))

  - [新 CsWebServiceConfiguration](https://technet.microsoft.com/library/Gg398440(v=OCS.15))

  - [新 CsWebTrustedCACertificate](https://technet.microsoft.com/library/Gg412746(v=OCS.15))

  - [新 CsXmppAllowedPartner](https://technet.microsoft.com/library/JJ204631(v=OCS.15))

  - [发布-CsLisConfiguration](https://technet.microsoft.com/library/Gg398364(v=OCS.15))

  - [发布-Enable-cstopology](https://technet.microsoft.com/library/Gg398953(v=OCS.15))

  - [CsAddressBookConfiguration](https://technet.microsoft.com/library/Gg398934(v=OCS.15))

  - [CsAdminRole](https://technet.microsoft.com/library/Gg413036(v=OCS.15))

  - [CsAllowedDomain](https://technet.microsoft.com/library/Gg398913(v=OCS.15))

  - [CsAnalogDevice](rehttps://technet.microsoft.com/library/Gg398816(v=OCS.15))

  - [CsAnnouncement](https://technet.microsoft.com/library/Gg412766(v=OCS.15))

  - [Set-csarchivingconfiguration](https://technet.microsoft.com/library/Gg398951(v=OCS.15))

  - [New-csarchivingpolicy](https://technet.microsoft.com/library/Gg425924(v=OCS.15))

  - [CsAutodiscoverConfiguration](https://technet.microsoft.com/library/Hh690054(v=OCS.15))

  - [CsAVEdgeConfiguration](https://technet.microsoft.com/library/Gg398786(v=OCS.15))

  - [CsBackupServiceConfiguration](https://technet.microsoft.com/library/JJ204903(v=OCS.15))

  - [CsBandwidthPolicyServiceConfiguration](https://technet.microsoft.com/library/Gg398877(v=OCS.15))

  - [CsBlockedDomain](https://technet.microsoft.com/library/Gg425832(v=OCS.15))

  - [CsCallParkOrbit](https://technet.microsoft.com/library/Gg412901(v=OCS.15))

  - [Set-cscdrconfiguration](https://technet.microsoft.com/library/Gg398451(v=OCS.15))

  - [Set-cscertificate](https://technet.microsoft.com/library/Gg412895(v=OCS.15))

  - [Set-csclientpolicy](https://technet.microsoft.com/library/Gg425772(v=OCS.15))

  - [CsClientVersionConfiguration](https://technet.microsoft.com/library/Gg425925(v=OCS.15))

  - [CsClientVersionPolicy](https://technet.microsoft.com/library/Gg425801(v=OCS.15))

  - [CsClientVersionPolicyRule](https://technet.microsoft.com/library/Gg398541(v=OCS.15))

  - [CsClsRegion](https://technet.microsoft.com/library/JJ204971(v=OCS.15))

  - [New-csclsscenario](https://technet.microsoft.com/library/JJ205010(v=OCS.15))

  - [CsClsSecurityGroup](https://technet.microsoft.com/library/JJ204958(v=OCS.15))

  - [CsCommonAreaPhone](rehttps://technet.microsoft.com/library/Gg412837(v=OCS.15))

  - [New-csconferencedirectory](rehttps://technet.microsoft.com/library/Gg412968(v=OCS.15))

  - [CsConferenceDisclaimer](https://technet.microsoft.com/library/Gg398243(v=OCS.15))

  - [CsConferencingConfiguration](https://technet.microsoft.com/library/Gg412767(v=OCS.15))

  - [Set-csconferencingpolicy](https://technet.microsoft.com/library/Gg398728(v=OCS.15))

  - [CsConfigurationStoreLocation](https://technet.microsoft.com/library/Gg398214(v=OCS.15))

  - [CsCpsConfiguration](https://technet.microsoft.com/library/Gg398358(v=OCS.15))

  - [CsDeviceUpdateConfiguration](https://technet.microsoft.com/library/Gg425933(v=OCS.15))

  - [CsDeviceUpdateRule](https://technet.microsoft.com/library/Gg425930(v=OCS.15))

  - [CsDiagnosticConfiguration](https://technet.microsoft.com/library/Gg412853(v=OCS.15))

  - [CsDiagnosticHeaderConfiguration](https://technet.microsoft.com/library/Gg398941(v=OCS.15))

  - [Set-csdialinconferencingaccessnumber](https://technet.microsoft.com/library/Gg412782(v=OCS.15))

  - [Set-csdialinconferencingconfiguration](https://technet.microsoft.com/library/Gg398174(v=OCS.15))

  - [New-csdialinconferencingdtmfconfiguration](https://technet.microsoft.com/library/Gg425894(v=OCS.15))

  - [Grant-csdialplan](https://technet.microsoft.com/library/Gg398791(v=OCS.15))

  - [CsEnhancedEmergencyServiceDisclaimer](https://technet.microsoft.com/library/Gg425810(v=OCS.15))

  - [Set-csexternalaccesspolicy](https://technet.microsoft.com/library/Gg399057(v=OCS.15))

  - [CsExUmContact](rehttps://technet.microsoft.com/library/Gg425842(v=OCS.15))

  - [CsFileTransferFilterConfiguration](https://technet.microsoft.com/library/Gg413064(v=OCS.15))

  - [CsFIPSConfiguration](https://technet.microsoft.com/library/JJ205201(v=OCS.15))

  - [CsHealthMonitoringConfiguration](https://technet.microsoft.com/library/Gg425794(v=OCS.15))

  - [CsHostedVoicemailPolicy](https://technet.microsoft.com/library/Gg398211(v=OCS.15))

  - [CsHostingProvider](https://technet.microsoft.com/library/Gg425809(v=OCS.15))

  - [CsImFilterConfiguration](https://technet.microsoft.com/library/Gg398171(v=OCS.15))

  - [CsKerberosAccountAssignment](https://technet.microsoft.com/library/Gg413052(v=OCS.15))

  - [CsLisLocation](https://technet.microsoft.com/library/Gg425722(v=OCS.15))

  - [CsLisPort](https://technet.microsoft.com/library/Gg412899(v=OCS.15))

  - [CsLisServiceProvider](https://technet.microsoft.com/library/Gg398904(v=OCS.15))

  - [CsLisSubnet](https://technet.microsoft.com/library/Gg413053(v=OCS.15))

  - [CsLisSwitch](https://technet.microsoft.com/library/Gg398352(v=OCS.15))

  - [CsLisWirelessAccessPoint](https://technet.microsoft.com/library/Gg398461(v=OCS.15))

  - [New-cslocationpolicy](https://technet.microsoft.com/library/Gg398727(v=OCS.15))

  - [CsManagementConnection](https://technet.microsoft.com/library/Gg425803(v=OCS.15))

  - [CsMcxConfiguration](https://technet.microsoft.com/library/Hh690026(v=OCS.15))

  - [Set-csmediaconfiguration](https://technet.microsoft.com/library/Gg398705(v=OCS.15))

  - [Get-csmeetingconfiguration](https://technet.microsoft.com/library/Gg412775(v=OCS.15))

  - [Set-csmobilitypolicy](https://technet.microsoft.com/library/Hh690048(v=OCS.15))

  - [CsNetworkBandwidthPolicyProfile](https://technet.microsoft.com/library/Gg398609(v=OCS.15))

  - [CsNetworkConfiguration](https://technet.microsoft.com/library/Gg398938(v=OCS.15))

  - [CsNetworkInterRegionRoute](https://technet.microsoft.com/library/Gg398743(v=OCS.15))

  - [New-csnetworkintersitepolicy](https://technet.microsoft.com/library/Gg398963(v=OCS.15))

  - [CsNetworkRegion](https://technet.microsoft.com/library/Gg398466(v=OCS.15))

  - [CsNetworkRegionLink](https://technet.microsoft.com/library/Gg413012(v=OCS.15))

  - [CsNetworkSite](https://technet.microsoft.com/library/Gg398135(v=OCS.15))

  - [CsNetworkSubnet](https://technet.microsoft.com/library/Gg425726(v=OCS.15))

  - [CsOAuthServer](https://technet.microsoft.com/library/JJ205408(v=OCS.15))

  - [CsOutboundCallingNumberTranslationRule](https://technet.microsoft.com/library/JJ204836(v=OCS.15))

  - [CsOutboundTranslationRule](https://technet.microsoft.com/library/Gg398556(v=OCS.15))

  - [CsPartnerApplication](https://technet.microsoft.com/library/JJ204820(v=OCS.15))

  - [CsPersistentChatAddin](https://technet.microsoft.com/library/JJ205350(v=OCS.15))

  - [CsPersistentChatCategory](https://technet.microsoft.com/library/JJ204660(v=OCS.15))

  - [CsPersistentChatComplianceConfiguration](https://technet.microsoft.com/library/JJ204767(v=OCS.15))

  - [CsPersistentChatConfiguration](https://technet.microsoft.com/library/JJ204927(v=OCS.15))

  - [CsPersistentChatEndpoint](https://technet.microsoft.com/library/JJ204626(v=OCS.15))

  - [CsPersistentChatMessage](https://technet.microsoft.com/library/JJ204668(v=OCS.15))

  - [CsPersistentChatPolicy](https://technet.microsoft.com/library/JJ205301(v=OCS.15))

  - [Set-cspersistentchatroom](https://technet.microsoft.com/library/JJ204639(v=OCS.15))

  - [Get-cspinpolicy](https://technet.microsoft.com/library/Gg398431(v=OCS.15))

  - [CsPresencePolicy](https://technet.microsoft.com/library/Gg399070(v=OCS.15))

  - [CsPresenceProvider](https://technet.microsoft.com/library/JJ205036(v=OCS.15))

  - [CsPrivacyConfiguration](https://technet.microsoft.com/library/Gg425821(v=OCS.15))

  - [CsProxyConfiguration](https://technet.microsoft.com/library/Gg398553(v=OCS.15))

  - [CsPublicProvider](https://technet.microsoft.com/library/Gg412906(v=OCS.15))

  - [CsPushNotificationConfiguration](https://technet.microsoft.com/library/Hh690028(v=OCS.15))

  - [New-csqoeconfiguration](https://technet.microsoft.com/library/Gg425879(v=OCS.15))

  - [CsRegistrarConfiguration](https://technet.microsoft.com/library/Gg398482(v=OCS.15))

  - [CsReportingConfiguration](https://technet.microsoft.com/library/JJ204711(v=OCS.15))

  - [CsRgsAgentGroup](https://technet.microsoft.com/library/Gg398969(v=OCS.15))

  - [CsRgsHolidaySet](https://technet.microsoft.com/library/Gg398521(v=OCS.15))

  - [CsRgsHoursOfBusiness](https://technet.microsoft.com/library/Gg398568(v=OCS.15))

  - [CsRgsQueue](https://technet.microsoft.com/library/Gg398576(v=OCS.15))

  - [CsRgsWorkflow](https://technet.microsoft.com/library/Gg398765(v=OCS.15))

  - [CsRoutingConfiguration](https://technet.microsoft.com/library/Gg398643(v=OCS.15))

  - [CsServerApplication](https://technet.microsoft.com/library/Gg398366(v=OCS.15))

  - [CsSimpleUrlConfiguration](https://technet.microsoft.com/library/Gg398515(v=OCS.15))

  - [CsSipDomain](https://technet.microsoft.com/library/Gg398865(v=OCS.15))

  - [CsSipResponseCodeTranslationRule](https://technet.microsoft.com/library/Gg412932(v=OCS.15))

  - [Set-csslaconfiguration](https://technet.microsoft.com/library/Mt703201(v=OCS.15))

  - [CsSlaDelegates](https://technet.microsoft.com/library/Mt703203(v=OCS.15))

  - [CsStaticRoutingConfiguration](https://technet.microsoft.com/library/Gg398668(v=OCS.15))

  - [CsTestDevice](https://technet.microsoft.com/library/Gg398790(v=OCS.15))

  - [CsTestUserCredential](https://technet.microsoft.com/library/JJ204870(v=OCS.15))

  - [Remove-cstrunkconfiguration](https://technet.microsoft.com/library/Gg425943(v=OCS.15))

  - [CsTrustedApplication](https://technet.microsoft.com/library/Gg398176(v=OCS.15))

  - [CsTrustedApplicationComputer](https://technet.microsoft.com/library/Gg398838(v=OCS.15))

  - [CsTrustedApplicationEndpoint](https://technet.microsoft.com/library/Gg398837(v=OCS.15))

  - [CsTrustedApplicationPool](https://technet.microsoft.com/library/Gg398750(v=OCS.15))

  - [CsUCPhoneConfiguration](https://technet.microsoft.com/library/Gg398249(v=OCS.15))

  - [CsUnassignedNumber](https://technet.microsoft.com/library/Gg398209(v=OCS.15))

  - [CsUserAcp](https://technet.microsoft.com/library/Gg398982(v=OCS.15))

  - [CsUserReplicatorConfiguration](https://technet.microsoft.com/library/Gg425738(v=OCS.15))

  - [CsUserServicesConfiguration](https://technet.microsoft.com/library/Gg398722(v=OCS.15))

  - [CsUserServicesPolicy](https://technet.microsoft.com/library/JJ204629(v=OCS.15))

  - [CsUserStoreBackupData](https://technet.microsoft.com/library/JJ205003(v=OCS.15))

  - [CsVoiceConfiguration](https://technet.microsoft.com/library/Gg398804(v=OCS.15))

  - [CsVoicemailReroutingConfiguration](https://technet.microsoft.com/library/Gg398573(v=OCS.15))

  - [CsVoiceNormalizationRule](https://technet.microsoft.com/library/Gg398501(v=OCS.15))

  - [Set-csvoicepolicy](https://technet.microsoft.com/library/Gg398309(v=OCS.15))

  - [CsVoiceRoute](https://technet.microsoft.com/library/Gg398468(v=OCS.15))

  - [Grant-csvoiceroutingpolicy](https://technet.microsoft.com/library/JJ204799(v=OCS.15))

  - [CsVoiceTestConfiguration](https://technet.microsoft.com/library/Gg412813(v=OCS.15))

  - [New-cswatchernodeconfiguration](https://technet.microsoft.com/library/JJ204926(v=OCS.15))

  - [CsWebServiceConfiguration](https://technet.microsoft.com/library/Gg398266(v=OCS.15))

  - [CsXmppAllowedPartner](https://technet.microsoft.com/library/JJ205055(v=OCS.15))

  - [请求-Set-cscertificate](https://technet.microsoft.com/library/Gg425723(v=OCS.15))

  - [Reset-CsDeviceUpdateRule](https://technet.microsoft.com/library/Gg398181(v=OCS.15))

  - [Restore-CsDeviceUpdateRule](https://technet.microsoft.com/library/Gg398305(v=OCS.15))

  - [CsClientCertificate](https://technet.microsoft.com/library/Gg425748(v=OCS.15))

  - [CsOUPermission](https://technet.microsoft.com/library/Gg398977(v=OCS.15))

  - [CsSetupPermission](https://technet.microsoft.com/library/Gg425834(v=OCS.15))

  - [Set-csaccessedgeconfiguration](https://technet.microsoft.com/library/Gg413017(v=OCS.15))

  - [CsAddressBookConfiguration](https://technet.microsoft.com/library/Gg412784(v=OCS.15))

  - [CsAdminRole](https://technet.microsoft.com/library/Gg399066(v=OCS.15))

  - [CsAllowedDomain](https://technet.microsoft.com/library/Gg398931(v=OCS.15))

  - [CsAnalogDevice](https://technet.microsoft.com/library/Gg412843(v=OCS.15))

  - [CsAnnouncement](https://technet.microsoft.com/library/Gg425752(v=OCS.15))

  - [CsApplicationServer](https://technet.microsoft.com/library/Gg398562(v=OCS.15))

  - [Set-csarchivingconfiguration](https://technet.microsoft.com/library/Gg413030(v=OCS.15))

  - [New-csarchivingpolicy](https://technet.microsoft.com/library/Gg398294(v=OCS.15))

  - [CsArchivingServer](https://technet.microsoft.com/library/Gg398923(v=OCS.15))

  - [CsAudioTestServiceApplication](https://technet.microsoft.com/library/Gg398907(v=OCS.15))

  - [CsAutodiscoverConfiguration](https://technet.microsoft.com/library/Hh689980(v=OCS.15))

  - [CsAVEdgeConfiguration](https://technet.microsoft.com/library/Gg412869(v=OCS.15))

  - [CsBackupServiceConfiguration](https://technet.microsoft.com/library/JJ205006(v=OCS.15))

  - [CsBandwidthPolicyServiceConfiguration](https://technet.microsoft.com/library/Gg412863(v=OCS.15))

  - [CsBlockedDomain](https://technet.microsoft.com/library/Gg398090(v=OCS.15))

  - [CsCallParkOrbit](https://technet.microsoft.com/library/Gg398796(v=OCS.15))

  - [CsCallParkServiceMusicOnHoldFile](https://technet.microsoft.com/library/Gg412836(v=OCS.15))

  - [Set-cscdrconfiguration](https://technet.microsoft.com/library/Gg398774(v=OCS.15))

  - [Set-cscertificate](https://technet.microsoft.com/library/Gg398518(v=OCS.15))

  - [Unlock-csclientpin](https://technet.microsoft.com/library/Gg398929(v=OCS.15))

  - [Set-csclientpolicy](https://technet.microsoft.com/library/Gg398300(v=OCS.15))

  - [CsClientVersionConfiguration](https://technet.microsoft.com/library/Gg398623(v=OCS.15))

  - [CsClientVersionPolicy](https://technet.microsoft.com/library/Gg398876(v=OCS.15))

  - [CsClientVersionPolicyRule](https://technet.microsoft.com/library/Gg425790(v=OCS.15))

  - [CsClsRegion](https://technet.microsoft.com/library/JJ204746(v=OCS.15))

  - [New-csclsscenario](https://technet.microsoft.com/library/JJ204622(v=OCS.15))

  - [CsClsSearchTerm](https://technet.microsoft.com/library/JJ204911(v=OCS.15))

  - [CsClsSecurityGroup](https://technet.microsoft.com/library/JJ204700(v=OCS.15))

  - [CsCommonAreaPhone](https://technet.microsoft.com/library/Gg398579(v=OCS.15))

  - [CsConferenceDisclaimer](https://technet.microsoft.com/library/Gg398776(v=OCS.15))

  - [CsConferenceServer](https://technet.microsoft.com/library/Gg398738(v=OCS.15))

  - [CsConferencingConfiguration](https://technet.microsoft.com/library/Gg412969(v=OCS.15))

  - [Set-csconferencingpolicy](https://technet.microsoft.com/library/Gg425788(v=OCS.15))

  - [CsConfigurationStoreLocation](https://technet.microsoft.com/library/Gg398258(v=OCS.15))

  - [CsCpsConfiguration](https://technet.microsoft.com/library/Gg412721(v=OCS.15))

  - [CsDeviceUpdateConfiguration](https://technet.microsoft.com/library/Gg398320(v=OCS.15))

  - [CsDiagnosticConfiguration](https://technet.microsoft.com/library/Gg425734(v=OCS.15))

  - [CsDiagnosticHeaderConfiguration](https://technet.microsoft.com/library/Gg399045(v=OCS.15))

  - [Set-csdialinconferencingaccessnumber](https://technet.microsoft.com/library/Gg425770(v=OCS.15))

  - [Set-csdialinconferencingconfiguration](https://technet.microsoft.com/library/Gg425825(v=OCS.15))

  - [New-csdialinconferencingdtmfconfiguration](https://technet.microsoft.com/library/Gg398860(v=OCS.15))

  - [Grant-csdialplan](https://technet.microsoft.com/library/Gg398644(v=OCS.15))Grant-csdialplan

  - [CsDirector](https://technet.microsoft.com/library/Gg398565(v=OCS.15))

  - [CsEdgeServer](https://technet.microsoft.com/library/Gg398859(v=OCS.15))

  - [CsEnhancedEmergencyServiceDisclaimer](https://technet.microsoft.com/library/Gg398620(v=OCS.15))

  - [Set-csexternalaccesspolicy](https://technet.microsoft.com/library/Gg398916(v=OCS.15))

  - [CsExUmContact](https://technet.microsoft.com/library/Gg412944(v=OCS.15))

  - [CsFileTransferFilterConfiguration](https://technet.microsoft.com/library/Gg425736(v=OCS.15))

  - [CsFIPSConfiguration](https://technet.microsoft.com/library/JJ205084(v=OCS.15))

  - [CsHealthMonitoringConfiguration](https://technet.microsoft.com/library/Gg425847(v=OCS.15))

  - [CsHostedVoicemailPolicy](https://technet.microsoft.com/library/Gg412722(v=OCS.15))

  - [CsHostingProvider](https://technet.microsoft.com/library/Gg398532(v=OCS.15))

  - [CsImFilterConfiguration](https://technet.microsoft.com/library/Gg412960(v=OCS.15))

  - [CsKerberosAccountAssignment](https://technet.microsoft.com/library/Gg398232(v=OCS.15))

  - [CsKerberosAccountPassword](https://technet.microsoft.com/library/Gg398659(v=OCS.15))

  - [CsLisLocation](https://technet.microsoft.com/library/Gg398757(v=OCS.15))

  - [CsLisPort](https://technet.microsoft.com/library/Gg398700(v=OCS.15))

  - [CsLisServiceProvider](https://technet.microsoft.com/library/Gg425911(v=OCS.15))

  - [CsLisSubnet](https://technet.microsoft.com/library/Gg399016(v=OCS.15))

  - [CsLisSwitch](https://technet.microsoft.com/library/Gg412823(v=OCS.15))

  - [CsLisWirelessAccessPoint](https://technet.microsoft.com/library/Gg412723(v=OCS.15))

  - [New-cslocationpolicy](https://technet.microsoft.com/library/Gg412987(v=OCS.15))

  - [CsManagementConnection](https://technet.microsoft.com/library/Gg413045(v=OCS.15))

  - [CsMcxConfiguration](https://technet.microsoft.com/library/Hh690050(v=OCS.15))

  - [Move-csmanagementserver](https://technet.microsoft.com/library/Gg398465(v=OCS.15))

  - [Set-csmediaconfiguration](https://technet.microsoft.com/library/Gg398580(v=OCS.15))

  - [Set-csmediationserver](https://technet.microsoft.com/library/Gg398213(v=OCS.15))

  - [Get-csmeetingconfiguration](https://technet.microsoft.com/library/Gg398648(v=OCS.15))

  - [Disable-csmeetingroom](https://technet.microsoft.com/library/JJ204831(v=OCS.15))

  - [Set-csmobilitypolicy](https://technet.microsoft.com/library/Hh690021(v=OCS.15))

  - [CsMonitoringServer](https://technet.microsoft.com/library/Gg425776(v=OCS.15))

  - [CsNetworkBandwidthPolicyProfile](https://technet.microsoft.com/library/Gg398338(v=OCS.15))

  - [CsNetworkConfiguration](https://technet.microsoft.com/library/Gg398927(v=OCS.15))

  - [CsNetworkInterRegionRoute](https://technet.microsoft.com/library/Gg398410(v=OCS.15))

  - [New-csnetworkintersitepolicy](https://technet.microsoft.com/library/Gg398772(v=OCS.15))

  - [CsNetworkRegion](https://technet.microsoft.com/library/Gg413089(v=OCS.15))

  - [CsNetworkRegionLink](https://technet.microsoft.com/library/Gg412867(v=OCS.15))

  - [CsNetworkSite](https://technet.microsoft.com/library/Gg398295(v=OCS.15))

  - [CsNetworkSubnet](https://technet.microsoft.com/library/Gg412739(v=OCS.15))

  - [Set-csoauthconfiguration](https://technet.microsoft.com/library/JJ204841(v=OCS.15))

  - [CsOAuthServer](https://technet.microsoft.com/library/JJ204896(v=OCS.15))

  - [CsOutboundCallingNumberTranslationRule](https://technet.microsoft.com/library/JJ205400(v=OCS.15))

  - [CsOutboundTranslationRule](https://technet.microsoft.com/library/Gg413073(v=OCS.15))

  - [CsPartnerApplication](https://technet.microsoft.com/library/JJ204755(v=OCS.15))

  - [Set-cspersistentchatactiveserver](https://technet.microsoft.com/library/JJ205065(v=OCS.15))

  - [CsPersistentChatAddin](https://technet.microsoft.com/library/JJ204721(v=OCS.15))

  - [CsPersistentChatCategory](https://technet.microsoft.com/library/JJ204952(v=OCS.15))

  - [CsPersistentChatComplianceConfiguration](https://technet.microsoft.com/library/JJ204949(v=OCS.15))

  - [CsPersistentChatConfiguration](https://technet.microsoft.com/library/JJ205122(v=OCS.15))

  - [CsPersistentChatPolicy](https://technet.microsoft.com/library/JJ205192(v=OCS.15))

  - [Set-cspersistentchatroom](https://technet.microsoft.com/library/JJ204801(v=OCS.15))

  - [CsPersistentChatState](https://technet.microsoft.com/library/JJ205109(v=OCS.15))

  - [Get-cspinpolicy](https://technet.microsoft.com/library/Gg412997(v=OCS.15))

  - [CsPresencePolicy](https://technet.microsoft.com/library/Gg425782(v=OCS.15))

  - [CsPresenceProvider](https://technet.microsoft.com/library/JJ204833(v=OCS.15))

  - [CsPrivacyConfiguration](https://technet.microsoft.com/library/Gg398484(v=OCS.15))

  - [CsProxyConfiguration](https://technet.microsoft.com/library/Gg425796(v=OCS.15))

  - [CsPstnGateway](https://technet.microsoft.com/library/Gg398408(v=OCS.15))

  - [CsPstnUsage](https://technet.microsoft.com/library/Gg399069(v=OCS.15))

  - [CsPublicProvider](https://technet.microsoft.com/library/Gg413087(v=OCS.15))

  - [CsPushNotificationConfiguration](https://technet.microsoft.com/library/Hh690013(v=OCS.15))

  - [New-csqoeconfiguration](https://technet.microsoft.com/library/Gg398245(v=OCS.15))

  - [CsRegistrar](https://technet.microsoft.com/library/Gg398993(v=OCS.15))

  - [CsRegistrarConfiguration](https://technet.microsoft.com/library/Gg398764(v=OCS.15))

  - [CsReportingConfiguration](https://technet.microsoft.com/library/JJ205075(v=OCS.15))

  - [CsRgsAgentGroup](https://technet.microsoft.com/library/Gg425955(v=OCS.15))

  - [CsRgsConfiguration](https://technet.microsoft.com/library/Gg425728(v=OCS.15))

  - [CsRgsHolidaySet](https://technet.microsoft.com/library/Gg398736(v=OCS.15))

  - [CsRgsHoursOfBusiness](https://technet.microsoft.com/library/Gg412929(v=OCS.15))

  - [CsRgsQueue](https://technet.microsoft.com/library/Gg412947(v=OCS.15))

  - [CsRgsWorkflow](https://technet.microsoft.com/library/Gg425845(v=OCS.15))

  - [CsRoutingConfiguration](https://technet.microsoft.com/library/Gg412811(v=OCS.15))

  - [CsServerApplication](https://technet.microsoft.com/library/Gg412850(v=OCS.15))

  - [CsSimpleUrlConfiguration](https://technet.microsoft.com/library/Gg412991(v=OCS.15))

  - [CsSipDomain](https://technet.microsoft.com/library/Gg412949(v=OCS.15))

  - [CsSipResponseCodeTranslationRule](https://technet.microsoft.com/library/Gg425895(v=OCS.15))

  - [Get-cssite](https://technet.microsoft.com/library/Gg413023(v=OCS.15))

  - [Set-csslaconfiguration](https://technet.microsoft.com/library/Mt703202(v=OCS.15))

  - [CsStaticRoutingConfiguration](https://technet.microsoft.com/library/Gg398724(v=OCS.15))

  - [CsTestDevice](https://technet.microsoft.com/library/Gg398156(v=OCS.15))

  - [Remove-cstrunkconfiguration](https://technet.microsoft.com/library/Gg398238(v=OCS.15))

  - [CsTrustedApplication](https://technet.microsoft.com/library/Gg425840(v=OCS.15))

  - [CsTrustedApplicationEndpoint](https://technet.microsoft.com/library/Gg398509(v=OCS.15))

  - [CsTrustedApplicationPool](https://technet.microsoft.com/library/Gg398187(v=OCS.15))

  - [CsUCPhoneConfiguration](https://technet.microsoft.com/library/Gg413042(v=OCS.15))

  - [CsUICulture](https://technet.microsoft.com/library/Gg398354(v=OCS.15))

  - [CsUnassignedNumber](https://technet.microsoft.com/library/Gg399033(v=OCS.15))

  - [Get-csuser](https://technet.microsoft.com/library/Gg398510(v=OCS.15))

  - [CsUserAcp](https://technet.microsoft.com/library/Gg413018(v=OCS.15))

  - [CsUserDatabaseState](https://technet.microsoft.com/library/Gg412973(v=OCS.15))

  - [CsUserReplicatorConfiguration](https://technet.microsoft.com/library/Gg398540(v=OCS.15))

  - [CsUserServer](https://technet.microsoft.com/library/Gg413026(v=OCS.15))

  - [CsUserServicesConfiguration](https://technet.microsoft.com/library/Gg398340(v=OCS.15))

  - [CsUserServicesPolicy](https://technet.microsoft.com/library/JJ205414(v=OCS.15))

  - [CsVoiceConfiguration](https://technet.microsoft.com/library/Gg398967(v=OCS.15))

  - [CsVoicemailReroutingConfiguration](https://technet.microsoft.com/library/Gg412948(v=OCS.15))

  - [CsVoiceNormalizationRule](https://technet.microsoft.com/library/Gg398491(v=OCS.15))

  - [Set-csvoicepolicy](https://technet.microsoft.com/library/Gg399021(v=OCS.15))

  - [CsVoiceRoute](https://technet.microsoft.com/library/Gg412893(v=OCS.15))

  - [Grant-csvoiceroutingpolicy](https://technet.microsoft.com/library/JJ205313(v=OCS.15))

  - [CsVoiceTestConfiguration](https://technet.microsoft.com/library/Gg398614(v=OCS.15))

  - [New-cswatchernodeconfiguration](https://technet.microsoft.com/library/JJ204620(v=OCS.15))

  - [CsWebServer](https://technet.microsoft.com/library/Gg398759(v=OCS.15))

  - [CsWebServiceConfiguration](https://technet.microsoft.com/library/Gg398396(v=OCS.15))

  - [CsXmppAllowedPartner](https://technet.microsoft.com/library/JJ204686(v=OCS.15))

  - [CsXmppGatewayConfiguration](https://technet.microsoft.com/library/JJ204769(v=OCS.15))

  - [启动-Start-cswindowsservice](https://technet.microsoft.com/library/Gg398561(v=OCS.15))

  - [Start-cswindowsservice](https://technet.microsoft.com/library/Gg398426(v=OCS.15))

  - [Sync-Export-csuserdata](https://technet.microsoft.com/library/JJ205242(v=OCS.15))

  - [Test-CsAddressBookService](https://technet.microsoft.com/library/Gg398661(v=OCS.15))

  - [Test-CsAddressBookWebQuery](https://technet.microsoft.com/library/Gg398773(v=OCS.15))

  - [Test-CsASConference](https://technet.microsoft.com/library/JJ205227(v=OCS.15))

  - [Test-CsAudioConferencingProvider](https://technet.microsoft.com/library/JJ205117(v=OCS.15))

  - [Test-CsAVConference](https://technet.microsoft.com/library/Gg412749(v=OCS.15))

  - [Test-CsAVEdgeConnectivity](https://technet.microsoft.com/library/JJ205138(v=OCS.15))

  - [Test-CsCertificateConfiguration](https://technet.microsoft.com/library/Gg398647(v=OCS.15))

  - [Test-CsComputer](https://technet.microsoft.com/library/Gg398162(v=OCS.15))

  - [Test-CsDatabase](https://technet.microsoft.com/library/JJ204839(v=OCS.15))

  - [Test-CsDataConference](https://technet.microsoft.com/library/JJ205219(v=OCS.15))

  - [Test-Test-csdialinconferencing](https://technet.microsoft.com/library/Gg399013(v=OCS.15))

  - [Test-Grant-csdialplan](https://technet.microsoft.com/library/Gg399024(v=OCS.15))

  - [Test-CsExStorageConnectivity](https://technet.microsoft.com/library/JJ204740(v=OCS.15))

  - [Test-CsExStorageNotification](https://technet.microsoft.com/library/JJ205331(v=OCS.15))

  - [Test-Test-csexumconnectivity](https://technet.microsoft.com/library/JJ204784(v=OCS.15))

  - [Test-CsExUMVoiceMail](https://technet.microsoft.com/library/JJ205058(v=OCS.15))

  - [Test-CsFederatedPartner](https://technet.microsoft.com/library/Gg398281(v=OCS.15))

  - [Test-CsGroupExpansion](https://technet.microsoft.com/library/Gg399009(v=OCS.15))

  - [Test-CsGroupIM](https://technet.microsoft.com/library/Gg398273(v=OCS.15))

  - [Test-CsIM](https://technet.microsoft.com/library/Gg425802(v=OCS.15))

  - [Test-Test-csintertrunkrouting](https://technet.microsoft.com/library/JJ204741(v=OCS.15))

  - [Test-CsKerberosAccountAssignment](https://technet.microsoft.com/library/Gg425938(v=OCS.15))

  - [Test-CsLisCivicAddress](https://technet.microsoft.com/library/Gg425914(v=OCS.15))

  - [Test-CsLisConfiguration](https://technet.microsoft.com/library/Gg398497(v=OCS.15))

  - [Test-New-cslocationpolicy](https://technet.microsoft.com/library/Gg425962(v=OCS.15))

  - [Test-CsMcxConference](https://technet.microsoft.com/library/Hh690045(v=OCS.15))

  - [Test-Test-csmcxp2pim](https://technet.microsoft.com/library/Hh690020(v=OCS.15))

  - [Test-CsMcxPushNotification](https://technet.microsoft.com/library/Hh690043(v=OCS.15))

  - [Test-CsOUPermission](https://technet.microsoft.com/library/Gg398787(v=OCS.15))

  - [Test-CsP2PAV](https://technet.microsoft.com/library/Gg412821(v=OCS.15))

  - [Test-CsPersistentChatMessage](https://technet.microsoft.com/library/JJ204656(v=OCS.15))

  - [Test-CsPhoneBootstrap](https://technet.microsoft.com/library/Gg412852(v=OCS.15))

  - [Test-CsPresence](https://technet.microsoft.com/library/Gg398148(v=OCS.15))

  - [Test-CsPstnOutboundCall](https://technet.microsoft.com/library/Gg398207(v=OCS.15))

  - [Test-CsPstnPeerToPeerCall](https://technet.microsoft.com/library/Gg398662(v=OCS.15))

  - [Test-CsRegistration](https://technet.microsoft.com/library/Gg412737(v=OCS.15))

  - [Test-CsReplica](https://technet.microsoft.com/library/JJ205289(v=OCS.15))

  - [Test-CsSetupPermission](https://technet.microsoft.com/library/Gg398428(v=OCS.15))

  - [Test-Enable-cstopology](https://technet.microsoft.com/library/Gg398127(v=OCS.15))

  - [Test-Remove-cstrunkconfiguration](https://technet.microsoft.com/library/Gg398137(v=OCS.15))

  - [Test-Test-csunifiedcontactstore](https://technet.microsoft.com/library/JJ204662(v=OCS.15))

  - [Test-CsVoiceNormalizationRule](https://technet.microsoft.com/library/Gg399003(v=OCS.15))

  - [Test-Set-csvoicepolicy](https://technet.microsoft.com/library/Gg398310(v=OCS.15))

  - [Test-CsVoiceRoute](https://technet.microsoft.com/library/Gg425873(v=OCS.15))

  - [Test-CsVoiceTestConfiguration](https://technet.microsoft.com/library/Gg398260(v=OCS.15))

  - [Test-CsVoiceUser](https://technet.microsoft.com/library/Gg413013(v=OCS.15))

  - [Test-New-cswatchernodeconfiguration](https://technet.microsoft.com/library/JJ204652(v=OCS.15))

  - [Test-CsWebApp](https://technet.microsoft.com/library/Hh689989(v=OCS.15))

  - [Test-CsWebAppAnonymous](https://technet.microsoft.com/library/Hh690041(v=OCS.15))

  - [Test-CsWebScheduler](https://technet.microsoft.com/library/JJ204829(v=OCS.15))

  - [Test-CsXmppIM](https://technet.microsoft.com/library/JJ205423(v=OCS.15))

  - [卸载-CsDatabase](unhttps://technet.microsoft.com/library/Gg399044(v=OCS.15))

  - [卸载-CsMirrorDatabase](unhttps://technet.microsoft.com/library/JJ204986(v=OCS.15))

  - [解锁-Unlock-csclientpin](unhttps://technet.microsoft.com/library/Gg398650(v=OCS.15))

  - [取消发布-CsLisConfiguration](unhttps://technet.microsoft.com/library/Gg398364(v=OCS.15))

  - [更新-CsAddressBook](https://technet.microsoft.com/library/Gg398194(v=OCS.15))

  - [更新-CsAdminRole](https://technet.microsoft.com/library/JJ204851(v=OCS.15))

  - [更新-CsTenantMeetingUrl](https://technet.microsoft.com/library/Dn424754(v=OCS.15))

  - [更新-Export-csuserdata](https://technet.microsoft.com/library/JJ205358(v=OCS.15))

  - [更新-CsUserDatabase](https://technet.microsoft.com/library/Gg398682(v=OCS.15))

</div>

</div>

<span> </span>

</div>

</div>

</div>


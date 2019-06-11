---
title: Lync Server 2013：CDR 表详细信息
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: CDR table details
ms:assetid: 896198f5-672b-48ea-852f-0211c0c90857
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398693(v=OCS.15)
ms:contentKeyID: 48184730
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f87e681cc25f9ed64509ff3bdb31abc5fd77101d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34837675"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="cdr-table-details-in-lync-server-2013"></a>Lync Server 2013 中的 CDR 表详细信息

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2012-10-18_

以下主题详细介绍每个 "呼叫详细记录" (CDR) 数据库架构表中的列。

<div>

## <a name="in-this-section"></a>本节内容

  - [Lync Server 2013 中的 Application 表](lync-server-2013-application-table.md)

  - [Lync Server 2013 中的 CallPriorities 表](lync-server-2013-callpriorities-table.md)

  - [Lync Server 2013 中的 CallType 表](lync-server-2013-calltype-table.md)

  - [Lync Server 2013 中的 ClientVersions 表](lync-server-2013-clientversions-table.md)

  - [Lync Server 2013 中的 ConferenceJoinTimeThresholds 表](lync-server-2013-conferencejointimethresholds-table.md)

  - [Lync Server 2013 中的 ConferenceMessageCount 表](lync-server-2013-conferencemessagecount-table.md)

  - [Lync Server 2013 中的 Conferences 表](lync-server-2013-conferences-table.md)

  - [Lync Server 2013 中的 ConferenceSessionDetails 表](lync-server-2013-conferencesessiondetails-table.md)

  - [Lync Server 2013 中的 ConferenceUris 表](lync-server-2013-conferenceuris-table.md)

  - [Lync Server 2013 中的 ContentTypes 表](lync-server-2013-contenttypes-table.md)

  - [Lync Server 2013 中的 DeRegisterType 表](lync-server-2013-deregistertype-table.md)

  - [Lync Server 2013 中的 Devices 表](lync-server-2013-devices-table.md)

  - [Lync Server 2013 中的 Dialogs 表](lync-server-2013-dialogs-table.md)

  - [Lync Server 2013 中的 EdgeServers 表](lync-server-2013-edgeservers-table.md)

  - [Lync Server 2013 中的 ErrorCategory 表](lync-server-2013-errorcategory-table.md)

  - [Lync Server 2013 中的 ErrorDef 表](lync-server-2013-errordef-table.md)

  - [Lync Server 2013 中的 ErrorReport 表](lync-server-2013-errorreport-table.md)

  - [Lync Server 2013 中的 FileTransfers 表](lync-server-2013-filetransfers-table.md)

  - [Lync Server 2013 中的 FocusJoinsAndLeaves 表](lync-server-2013-focusjoinsandleaves-table.md)

  - [Lync Server 2013 中的前端表](lync-server-2013-frontend-table.md)

  - [Lync Server 2013 中的 Gateways 表](lync-server-2013-gateways-table.md)

  - [Lync Server 2013 中的 HardwareVersions 表](lync-server-2013-hardwareversions-table.md)

  - [Lync Server 2013 中的 IMReportSummary 表](lync-server-2013-imreportsummary-table.md)

  - [Lync Server 2013 中的 Locations 表](lync-server-2013-locations-table.md)

  - [Lync Server 2013 中的 Manufacturers 表](lync-server-2013-manufacturers-table.md)

  - [Lync Server 2013 中的 McuJoinsAndLeaves 表](lync-server-2013-mcujoinsandleaves-table.md)

  - [Lync Server 2013 中的 Mcus 表](lync-server-2013-mcus-table.md)

  - [Lync Server 2013 中的 Media 表](lync-server-2013-media-table.md)

  - [Lync Server 2013 中的 MediaList 表](lync-server-2013-medialist-table.md)

  - [Lync Server 2013 中的 MediationServers 表](lync-server-2013-mediationservers-table.md)

  - [Lync Server 2013 中的 MSMQProcessing 表](lync-server-2013-msmqprocessing-table.md)

  - [Lync Server 2013 中的 Phones 表](lync-server-2013-phones-table.md)

  - [Lync Server 2013 中的 Pools 表](lync-server-2013-pools-table.md)

  - [Lync Server 2013 中的 ProgressReport 表](lync-server-2013-progressreport-table.md)

  - [Lync Server 2013 中的 PurgeSettings 表](lync-server-2013-purgesettings-table.md)

  - [Lync Server 2013 中的 Registration 表](lync-server-2013-registration-table.md)

  - [Lync Server 2013 中的 Roles 表](lync-server-2013-roles-table.md)

  - [Lync Server 2013 中的 Servers 表](lync-server-2013-servers-table.md)

  - [Lync Server 2013 中的 SessionDetails 表](lync-server-2013-sessiondetails-table.md)

  - [Lync Server 2013 中的 SIPResponseMetaData 表](lync-server-2013-sipresponsemetadata-table.md)

  - [Lync Server 2013 中的 Syndicators 表](lync-server-2013-syndicators-table.md)

  - [Lync Server 2013 中的 SyndicatorsTenantMap 表](lync-server-2013-syndicatorstenantmap-table.md)

  - [Lync Server 2013 中的任务表](lync-server-2013-task-table.md)

  - [Lync Server 2013 中的 Tenants 表](lync-server-2013-tenants-table.md)

  - [Lync Server 2013 中的 UriTypes 表](lync-server-2013-uritypes-table.md)

  - [Lync Server 2013 中的 Users 表](lync-server-2013-users-table.md)

  - [Lync Server 2013 中的 UserAgentDef 表](lync-server-2013-useragentdef-table.md)

  - [Lync Server 2013 中的 UserStatistics 表](lync-server-2013-userstatistics-table.md)

  - [Lync Server 2013 中的 VoipDetails 表](lync-server-2013-voipdetails-table.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>


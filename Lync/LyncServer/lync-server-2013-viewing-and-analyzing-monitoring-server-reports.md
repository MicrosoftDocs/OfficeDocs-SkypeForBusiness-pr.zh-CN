---
title: Lync Server 2013：查看和分析监视服务器报告
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Viewing and analyzing monitoring server reports
ms:assetid: 4dd448f1-01d2-49b2-b109-0728f36566b7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720332(v=OCS.15)
ms:contentKeyID: 63969599
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3fc5f963ab9b0181463e3bf065baa61730c9fd0d
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42211298"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="viewing-and-analyzing-monitoring-server-reports-in-lync-server-2013"></a>在 Lync Server 2013 中查看和分析监视服务器报告

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2014-05-19_

监视服务器报告提供了几种不同的语音质量指标，以监视正在传递给最终用户的 QoE。 此外，监视服务器还包括几个内置报告，您的组织可以使用这些报告来监视组织网络上的使用率和媒体质量趋势，并解决出现的媒体质量问题。

使监视服务器报告对日常和每周操作感兴趣的主要部分是查看和分析媒体质量报告，具体具体如下：

  - QoE 摘要/趋势报告

  - QoE 性能报告

<div>

## <a name="view-reports-from-the-monitoring-server"></a>查看来自监控服务器的报告

1.  在 web 浏览器中，找到托管 SQL 报告服务的服务器。

2.  从浏览器屏幕查看所需的报告。

3.  Optional通过选择 "导出" 选项和所需的输出格式导出报告。

</div>

<div>

## <a name="configure-call-detail-recording-cdr"></a>配置呼叫详细信息记录（CDR）

1.  从属于 RTCUniversalServerAdmins 组成员（或具有同等权限）的用户帐户，或分配给 CsServerAdministrator 或 CsAdministrator 角色的用户登录到您在其中部署了 Lync Server 2013 的网络中的任何计算机。

2.  打开浏览器窗口，然后输入管理员 URL 以打开 "Lync Server 控制面板"。

3.  在左侧导航栏中，单击“监控和存档”****，然后单击“呼叫详细信息记录”****。

4.  在“呼叫详细信息记录”**** 页上，单击表中的相应站点，再单击“编辑”****，然后单击“显示详细信息”****。

5.  若要打开清除，请选择 "**启用对监视服务器的清除**"。

6.  在 "**保留呼叫详细信息记录的最长持续时间（天）：** " 中选择呼叫详细信息录制应保留的最大天数。

7.  在“错误报告数据最长保留期限(天):”**** 中选择错误报告的最长保留天数。

8.  单击“提交”****。

</div>

<div>

## <a name="configure-qoe"></a>配置 QoE

1.  以 RTCUniversalServerAdmins 组成员的身份或者以 CsVoiceAdministrator、CsServerAdministrator 或 CsAdministrator 角色成员的身份登录计算机。 有关详细信息，请参阅Delegate Setup Permissions。

2.  打开浏览器窗口，然后输入管理员 URL 以打开 "Lync Server 控制面板"。

3.  在左侧导航栏中，单击“监控和存档”****，然后单击“用户体验质量数据”****。

4.  在“用户体验质量数据”**** 页上，单击表中的相应站点，再单击“编辑”****，然后单击“显示详细信息”****。

5.  若要打开清除，请选择 "**启用对监视服务器的清除**"。

6.  在 "**保留呼叫详细信息记录的最长持续时间（天）：** " 中，选择 QoE 数据应保留的最大天数。

7.  单击“提交”。

</div>

<div>

## <a name="change-the-archiving-policy"></a>更改存档策略

1.  使用分配给 CsArchivingAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。

2.  打开浏览器窗口，然后输入管理员 URL 以打开 "Lync Server 控制面板"。

3.  在左侧导航栏中，单击 **“监控和存档”**，然后单击 **“存档策略”**。

4.  单击策略列表中的 **“全局”**，再单击 **“编辑”**，然后单击 **“显示详细信息”**。

5.  在 **“编辑存档策略 - 全局”** 中，执行下列操作：

6.  若要启用或禁用部署的内部存档，请选中或清除 "**存档内部通信**" 复选框。

7.  若要启用或禁用部署的外部存档，请选中或清除 "**存档外部通信**" 复选框。

8.  单击“提交”****。

</div>

<div>

## <a name="apply-an-archiving-policy-to-a-user"></a>将存档策略应用于用户

1.  使用分配给 CsArchivingAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。

2.  打开浏览器窗口，然后输入管理员 URL 以打开 "Lync Server 控制面板"。

3.  在左侧导航栏中，单击“用户”****，然后搜索要配置的用户帐户。

4.  在列出搜索结果的表中，单击相应的用户帐户，再单击“编辑”****，然后单击“显示详细信息”****。

5.  在 "**编辑 Lync Server 用户**" 中的 "**存档策略**" 下，选择要应用的存档用户策略。

6.  单击“提交”****。

</div>

<div>

## <a name="see-also"></a>另请参阅


[在 Lync Server 2013 中使用监控报告](lync-server-2013-using-monitoring-reports.md)  
[Lync Server 2013 中的服务器性能报告](lync-server-2013-server-performance-report.md)  
[Lync Server 2013 中的媒体质量比较报告](lync-server-2013-media-quality-comparison-report.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


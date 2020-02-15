---
title: 配置 Lync Server 2013 以与 Office Web Apps Server 配合使用
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Lync Server 2013 to work with Office Web Apps Server
ms:assetid: 6231e519-9010-4ff9-b5a6-b5859c2b3e11
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204944(v=OCS.15)
ms:contentKeyID: 48184288
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 69a5cd13b139cb2544e1d89971a8480d1e1fb296
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42030546"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-lync-server-2013-to-work-with-office-web-apps-server"></a>配置 Lync Server 2013 以与 Office Web Apps Server 配合使用

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2013-04-22_

必须先部署和配置 Office Web Apps Server，然后才能将 Lync Server 2013 配置为使用 Office Web Apps Server。 有关如何安装和配置 Office Web Apps 服务器的详细信息以及为了高可用性如何安装和配置 Office Web Apps 服务器场的信息，请参阅文档“Office Web Apps 服务器和 Office Web Apps 部署指南”****。

成功安装 Office Web Apps Server 并正确配置 Web 服务器场后，必须将 Lync Server 配置为与新服务器通信;这是通过将 Office Web Apps Server 发现 URL 添加到你的 Lync Server 拓扑来实现的。 若要向拓扑中添加 Office Web Apps 服务器，请完成下列步骤：

1.  依次单击 "**开始**"、"**所有程序**"、" **Microsoft Lync server 2013**"，然后单击 " **Lync server 拓扑生成器**"。

2.  在“拓扑生成器”**** 对话框中，选择“从现有部署下载拓扑”****，然后单击“确定”****。

3.  在“将拓扑另存为”**** 对话框的“文件名”**** 框中为拓扑文档键入一个名称（例如，**PreWebAppsServerTopology**），然后单击“保存”****。如果之后您的新拓扑遇到问题，则可检索和重新发布此拓扑。

4.  在拓扑生成器中，展开 " **Lync Server 2013**"，展开您的网站的名称，展开 " **Enterprise Edition 前端池**"，右键单击其中一个池的名称，然后单击 "**编辑属性**"。

5.  在“编辑属性”**** 对话框的“常规”**** 选项卡上，查找标题“关联 Office Web Apps 服务器”****，然后单击“新建”****（或从下拉列表中选择现有 Office Web Apps 服务器）。

6.  在“定义新的 Office Web Apps 服务器”**** 对话框的“Office Web Apps 服务器 FQDN”**** 框中，键入您的 Office Web Apps 服务器计算机的完全限定域名 (FQDN)；执行此操作时，您的 Office Web Apps 服务器搜索 URL 应自动输入到“Office Web Apps 服务器搜索 URL”**** 框中。
    
    如果 Office Web Apps Server 安装在本地和与 Lync Server 2013 位于同一网络区域中，则不应选择在**外部网络（即，外围/Internet）中部署 "Office Web Apps 服务器**" 选项。
    
    如果 Office Web Apps 服务器部署在内部防火墙之外，则请选择选项“在外部网络(即，外围/Internet)中部署 Office Web Apps 服务器”****。

7.  在“定义新的 Office Web Apps 服务器”**** 对话框中，单击“确定”****，然后在“编辑属性”**** 对话框中单击“确定”****。Office Web Apps 搜索 URL 将作为池的关联之一列出。

您必须对需要与您的 Office Web Apps 服务器关联的每个池重复此过程。

向拓扑添加搜索 URL 后，您必须发布此更新的拓扑。请在拓扑生成器中执行此操作：

1.  单击“操作”****，然后单击“发布拓扑”****。

2.  在发布拓扑向导的“发布拓扑”**** 页上，单击“下一步”****。

3.  在“发布向导已完成”**** 页上，单击“完成”****。

4.  关闭拓扑生成器。

</div>

<span> </span>

</div>

</div>

</div>


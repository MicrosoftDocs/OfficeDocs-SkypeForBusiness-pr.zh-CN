---
title: 'Lync Server 2013: 配置网站的存档选项'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring Archiving options for a site
ms:assetid: 59b48fd9-d5fc-40b4-abae-e9cf89ee5573
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204930(v=OCS.15)
ms:contentKeyID: 48184247
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 14b0e29a2796c23c13a16bfb3e8a202a0a535aaa
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34837282"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-archiving-options-for-a-site-in-lync-server-2013"></a>在 Lync Server 2013 中配置网站的存档选项

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2012-10-09_

你可以通过在每个网站的存档配置中创建和配置选项来指定要应用到特定网站的存档选项。 站点配置可覆盖全局配置，但它仅适用于站点配置中指定的站点。 池配置替代网站配置

有关存档配置的工作原理的详细信息 (包括全局、网站和池配置的层次结构), 请参阅规划文档、部署文档或操作文档中的[存档在 Lync Server 2013 中的工作原理](lync-server-2013-how-archiving-works.md).

<div>


> [!NOTE]  
> 在启用存档之前, 应在存档配置中指定所有适当的选项。



</div>

<div>


> [!IMPORTANT]  
> 若要启用存档，您必须指定存档策略以控制全局级别（适当情况下还包括站点和用户级别）的内部和外部通信的存档。 如果配置用户级别策略，还必须向特定用户分配用户策略。 有关创建和配置存档策略的详细信息, 请参阅在操作文档中<A href="lync-server-2013-managing-the-archiving-of-internal-and-external-communications.md">管理 Lync Server 2013 中的内部和外部通信的存档</A>。



</div>

<div>

## <a name="to-configure-archiving-options-at-the-site-level"></a>在网站级别配置存档选项

1.  使用分配给 CsArchivingAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。

2.  打开一个浏览器窗口, 然后输入管理员 URL 以打开 Lync Server 2013 控制面板。 有关可用于启动 Lync Server 2013 控制面板的不同方法的详细信息, 请参阅[打开 Lync server 2013 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左侧导航栏中，单击“监控和存档”****，然后单击“存档配置”****。

4.  在“**存档配置**”页上，单击“**新建**”，然后单击“**站点配置**”。

5.  在“**选择站点**”中，选择要为存档配置的站点。

6.  在“**新建存档设置**”的“**存档设置**”下拉列表框中，执行下列操作之一：
    
      - 若要只为即时消息 (IM) 会话启用存档，请单击“**存档 IM 会话**”。
    
      - 若要为 IM 会话和会议启用存档，请单击“**存档 IM 和 Web 会议会话**”。
    
      - 若要为策略禁用存档，请单击“**禁用存档**”。

7.  另请在“**新建存档设置**”中，执行下列操作：
    
      - 要在存档不可用时阻止活动，请选中“**存档失败时阻止即时消息 (IM) 或 Web 会议会话**”复选框。
    
      - 若要使用 Microsoft Exchange Server 存储存档数据, 请单击 " **Microsoft exchange 集成**" 复选框。
    
      - 若要启用数据清除，请选中“**启用存档数据清除**”复选框，然后执行下列操作之一：
        
          - 要指定在特定的天数之后清除，请单击“**在最长期限（天）后清除导出的存档数据和存储的存档数据**”，然后指定天数。
        
          - 要限制仅清除已导出的存档数据，请单击“**仅清除导出的存档数据**”。

8.  单击“**提交**”。

</div>

</div>

<span> </span>

</div>

</div>

</div>


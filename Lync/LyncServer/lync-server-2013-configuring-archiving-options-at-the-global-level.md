---
title: Lync Server 2013：在全局级别配置存档选项
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Archiving options at the global level
ms:assetid: bfe415f7-2abf-41ee-a1cb-cf48b2d59c0c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205233(v=OCS.15)
ms:contentKeyID: 48185303
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 965d82f63b776ed9bc1790715b14524dd39ba054
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42150801"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-archiving-options-at-the-global-level-in-lync-server-2013"></a>在 Lync Server 2013 中配置全局级别的存档选项

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-10-10_

当您向拓扑中添加存档并发布拓扑时，Lync Server 将为存档创建全局配置。 默认情况下，不会在全局配置中启用任何存档选项。 除非您自己设置站点或池配置（这将重写全局配置），否则全局配置将控制要为整个部署启用的选项。

有关存档配置的工作原理（包括全局、站点和池配置的层次结构）的详细信息，请参阅规划文档、部署文档或操作文档中的[存档在 Lync Server 2013 中的工作原理](lync-server-2013-how-archiving-works.md)。

<div>


> [!NOTE]  
> 在启用存档之前，应在存档配置中指定所有适当选项。



</div>

<div>

## <a name="to-configure-archiving-options-at-the-global-level"></a>在全局级别配置存档选项

1.  使用分配给 CsArchivingAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。

2.  打开浏览器窗口，然后输入管理员 URL 以打开 Lync Server 2013 控制面板。 有关可用于启动 Lync Server 2013 控制面板的不同方法的详细信息，请参阅[Open Lync server 2013 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左侧导航栏中，单击 **“监控和存档”**，然后单击 **“存档配置”**。

4.  在“存档配置”**** 页上，单击“全局”****，再单击“编辑”****，然后单击“显示详细信息”****。

5.  在“编辑存档设置 - 全局”**** 的“存档设置”**** 下拉列表中，选择下列存档选项之一：
    
      - **禁用存档**
    
      - **存档 IM 会话**
    
      - **存档 IM 和 Web 会议会话**

6.  另请在“编辑存档设置 - 全局”**** 页中，执行下列操作：
    
      - 要在存档不可用时阻止活动，请选中“存档失败时阻止即时消息(IM)或 Web 会议会话”**** 复选框。
    
      - 若要使用 Microsoft Exchange Server 存储存档数据，请单击 " **Microsoft exchange 集成**" 复选框。
    
      - 若要启用数据清除，请选中“启用存档数据清除”**** 复选框，然后执行下列操作之一：
        
          - 要指定在特定的天数之后清除，请单击“在最长期限(天)后清除导出的存档数据和存储的存档数据”****，然后指定天数。
        
          - 要限制仅清除已导出的存档数据，请单击“仅清除导出的存档数据”****。

7.  单击“提交”****。

</div>

</div>

<span> </span>

</div>

</div>

</div>


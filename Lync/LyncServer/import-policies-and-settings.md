---
title: 导入策略和设置
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Import policies and settings
ms:assetid: b25decee-2ee5-4836-b370-454411d39252
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205178(v=OCS.15)
ms:contentKeyID: 48185147
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8c6a56f1a622aca4d3f50565bc86528cf474c845
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/16/2020
ms.locfileid: "44756531"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="import-policies-and-settings"></a>导入策略和设置

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-09-28_

将 Office 通信服务器 2007 R2 拓扑信息与 Lync Server 2013 试验池合并后，您需要运行 Lync Server 2013 命令行管理程序 cmdlet，将 Office 通信服务器 2007 R2 策略和配置设置迁移到 Lync Server 2013 引导池。

**CsLegacyConfiguration** cmdlet 可将策略、语音路由、拨号计划、Communicator Web 访问 url 和电话拨入访问号码导入到 Lync Server 2013。

<div>

## <a name="to-migrate-policies-and-settings"></a>迁移策略和设置

1.  在 Lync Server 2013 前端服务器上，启动 Lync Server 命令行管理程序。

2.  在命令行中键入：
    
        Import-CsLegacyConfiguration
    
    导入策略后，请按照下面的过程操作，在 Lync Server 控制面板中查看导入的策略。

</div>

<div>

## <a name="to-view-imported-policies"></a>查看导入的策略

1.  打开 "Lync Server 2013 控制面板"。

2.  单击“语音路由”**** 并查看导入的策略。

3.  单击“会议”**** 并查看导入的策略。

4.  单击“联盟和外部访问”**** 并查看导入的策略。

5.  单击“监控和存档”**** 并查看导入的策略。

</div>

</div>

<span> </span>

</div>

</div>

</div>


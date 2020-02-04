---
title: 导入策略和设置
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Import policies and settings
ms:assetid: b25decee-2ee5-4836-b370-454411d39252
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205178(v=OCS.15)
ms:contentKeyID: 48185147
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6f8023f917e3da6757ce27ede44a63cf0ab1a08d
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41734082"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="import-policies-and-settings"></a>导入策略和设置

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2012-09-28_

将 Office 通信服务器 2007 R2 拓扑信息与 Lync Server 2013 试验池合并后，您需要运行 Lync Server 2013 Management Shell cmdlet 来迁移 Office 通信服务器 2007 R2 策略和配置设置您的 Lync Server 2013 试验池。

**CsLegacyConfiguration** cmdlet 将策略、语音路由、拨号计划、Communicator Web Access url 和电话拨入访问号码导入 Lync Server 2013。

<div>

## <a name="to-migrate-policies-and-settings"></a>迁移策略和设置

1.  在 Lync Server 2013 前端服务器上，启动 Lync Server 命令行管理程序。

2.  在命令行中键入：
    
        Import-CsLegacyConfiguration
    
    导入策略后，请使用下面的过程在 Lync Server 控制面板中查看导入的策略。

</div>

<div>

## <a name="to-view-imported-policies"></a>查看导入的策略

1.  打开 "Lync Server 2013 控制面板"。

2.  单击 "**语音路由**"，然后查看导入的策略。

3.  单击 "**会议**" 并查看导入的策略。

4.  单击 "**联盟和外部访问**" 并查看导入的策略。

5.  单击 "**监视和存档**"，然后查看导入的策略。

</div>

</div>

<span> </span>

</div>

</div>

</div>


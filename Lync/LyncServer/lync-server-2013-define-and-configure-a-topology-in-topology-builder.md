---
title: Lync Server 2013：在拓扑生成器中定义和配置拓扑
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Define and configure a topology in Topology Builder
ms:assetid: 99231ff5-1c21-432b-ad65-8675fcd484f9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398788(v=OCS.15)
ms:contentKeyID: 48184953
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4ee952eef30fc50f30448c98956899c3a1a06dc2
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34830708"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="define-and-configure-a-topology-in-topology-builder-for-lync-server-2013"></a>在 Lync Server 2013 拓扑生成器中定义和配置拓扑

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2013-02-21_

运行拓扑生成器以定义新拓扑或修改现有拓扑不需要本地管理员或特权域组的成员身份。 拓扑生成器将指导你完成根据你的配置要求定义企业版前端池或标准版的拓扑所需的步骤。

必须使用拓扑生成器完成并发布拓扑, 然后才能在服务器上安装 Lync Server 2013。 以下过程包括定义新拓扑所需的步骤。

<div>

## <a name="to-define-a-topology"></a>定义拓扑

1.  启动拓扑生成器: 单击 "**开始**", 单击 "**所有程序**", 单击 " **Microsoft Lync server 2013**", 然后单击 " **Lync server 拓扑生成器**"。

2.  在拓扑生成器中, 选择 "**新建拓扑**"。 系统将提示你输入用于保存拓扑的位置和文件名。 为拓扑文件指定一个有意义的名称, 并接受 tbxml 的默认扩展名。 单击“**确定**”。

3.  导航到要保存新拓扑 XML 文件的位置, 输入文件的名称, 然后单击 "**保存**"。

4.  在 "**定义主域**" 页面上, 输入您的组织的主要 SIP 域的名称, 然后单击 "**下一步**"。

5.  在 "**指定其他支持的域**" 页面上, 输入其他域的名称 (如果有), 然后单击 "**下一步**"。

6.  在 "**定义第一个网站**" 页面上, 输入第一个网站的名称和说明, 然后单击 "**下一步**"。

7.  在 "**指定网站详细信息**" 页面上, 输入网站的位置信息, 然后单击 "**下一步**"。

8.  在 "已**成功定义新拓扑**" 页面上, 确保选中 "**此向导关闭时打开新的前端向导**" 复选框, 然后单击 "**完成**"。

定义并保存拓扑后, 使用新的前端向导为网站定义前端池或标准版服务器。 有关详细信息, 请参阅[在 Lync server 2013 中定义和配置前端池或标准版服务器](lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md)。

</div>

</div>

<span> </span>

</div>

</div>

</div>


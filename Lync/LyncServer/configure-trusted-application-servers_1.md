---
title: 配置受信任应用程序服务器
ms.reviewer: ''
ms.author: kenwith
author: kenwith
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Configure trusted application servers
ms:assetid: 47a9e72e-566c-4c23-bec2-760a3098a974
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204865(v=OCS.15)
ms:contentKeyID: 48184056
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 92e7f2c808e9ea5a3e8dfbf3010715c86e02596e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41728942"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-trusted-application-servers"></a>配置受信任应用程序服务器

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2012-10-04_

在混合环境中，如果在将旧式 Office 通信服务器拓扑与 Lync Server 2013 合并后创建新的受信任的应用程序服务器，并且使用拓扑生成器定义新的受信任的应用程序服务器，则必须将下一个跃点池设置为Lync Server 2013 池。 在合并环境中，旧版 Office 通信服务器池和 Lync Server 2013 池均会显示在下拉列表中。 *不*支持选择旧版池。

<div>

## <a name="to-select-lync-server-2013-as-next-hop-when-creating-a-trusted-application-server"></a>创建受信任的应用服务器时，将 Lync Server 2013 选作下一个跃点

1.  在拓扑生成器中打开现有拓扑。

2.  在左窗格中，右键单击 "**受信任的应用程序服务器**"，然后单击 "**新建受信任应用程序池**"

3.  输入受信任的应用程序池的**池 FQDN** ，并选择它是单服务器部署还是多服务器部署。

4.  单击" **下一步**"。

5.  在 "**选择下一个跃点**" 页面上，从列表中选择 "Lync Server 2013 前端池"。
    
    !["定义新的受信任的应用程序池" 对话框](images/JJ204865.ecfe2bb8-758b-4b36-8146-573005c4ab09(OCS.15).jpg ""定义新的受信任的应用程序池" 对话框")  

6.  单击“**完成**”。

7.  选择顶部节点**Lync 服务器**，然后从 "**操作**" 窗格中选择 "**发布**"。

8.  验证**受信任的应用程序池**已成功创建且与正确的前端池相关联。

</div>

</div>

<span> </span>

</div>

</div>

</div>


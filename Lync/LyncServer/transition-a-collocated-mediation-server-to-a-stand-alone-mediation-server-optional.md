---
title: 将 collocated 中介服务器转换为独立的中介服务器（可选）
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Transition a collocated Mediation Server to a stand-alone Mediation Server (optional)
ms:assetid: 7c3c2fb4-4ff2-47b1-aab3-0aa91472eadb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205026(v=OCS.15)
ms:contentKeyID: 48184602
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2c6a76bceb935900521859911ce5398ae2213e22
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41738662"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="transition-a-collocated-mediation-server-to-a-stand-alone-mediation-server-optional"></a>将 collocated 中介服务器转换为独立的中介服务器（可选）

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2012-10-19_

使用以下过程将你的中介服务器（collocated）从你的标准版服务器或前端池切换到独立的中介服务器以进行单站点部署。

<div>

## <a name="to-transition-a-collocated-mediation-server-to-a-stand-alone-mediation-server"></a>将 collocated 中介服务器转换为独立的中介服务器

1.  从拓扑生成器打开现有拓扑。

2.  在左窗格中，导航到 "**中介池**"。

3.  右键单击 "**中介池**"，然后选择 "**新建中介服务器**"。

4.  在 "**定义新的中介池**" 页面上，提供新中介服务器池的 FQDN。 此外，选择此池是单服务器池还是多服务器池，然后单击 "**下一步**"。

5.  选择新中介服务器将向其路由入站呼叫的下一个跃点前端服务器池，然后单击 "**下一步**"。

6.  选择要由中介服务器使用的边缘池，然后单击 "**下一步**"。

7.  在 "**指定 PSTN 网关**" 页面上，将以前的 PSTN 网关与中介服务器相关联。 选择网关，然后单击 "**添加**"。

8.  单击 "**完成**" 以关闭 "**定义新的中介池**" 向导。

9.  从**拓扑生成器**中，选择顶级节点**Lync Server 2013**。

10. 从 "**操作**" 窗格中，选择 "**发布拓扑**" 并完成向导。

11. 按照在 "部署" 文档中的[Lync server 2013 中安装中介服务器文件](lync-server-2013-install-the-files-for-mediation-server.md)中的步骤进行操作，以在新的中介服务器上安装文件。

12. 在中介服务器上安装文件后，返回到拓扑生成器，然后在左窗格中导航到该池。

13. 右键单击该池，然后选择 "**编辑属性**"。

14. 在 "**中介服务器**" 下，清除 "**启用中介服务器 Collocated** " 复选框，然后单击 **"确定"**。

15. 从**拓扑生成器**中，选择顶级节点**Lync Server 2013**。

16. 从 "**操作**" 菜单中，选择 "**发布拓扑**" 并完成向导。

</div>

</div>

<span> </span>

</div>

</div>

</div>


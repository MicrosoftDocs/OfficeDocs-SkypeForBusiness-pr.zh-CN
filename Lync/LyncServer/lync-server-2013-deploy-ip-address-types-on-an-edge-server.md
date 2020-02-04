---
title: Lync Server 2013：在边缘服务器上部署 IP 地址类型
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploy IP address types on an Edge Server
ms:assetid: 6e2fe7e8-6e90-4d1a-8fc5-e3be92c46571
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204984(v=OCS.15)
ms:contentKeyID: 48184435
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ece4b55f42958916876539f05b951e862e0d493f
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41729662"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploy-ip-address-types-on-an-edge-server-for-lync-server-2013"></a>在 Lync Server 2013 边缘服务器上部署 IP 地址类型

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2012-06-14_

使用拓扑生成器，执行以下过程中的步骤以在 Edge 服务器上部署 IP 地址类型。

<div>

## <a name="to-deploy-ip-address-types-on-an-edge-server"></a>在边缘服务器上部署 IP 地址类型

1.  在拓扑生成器中，在 "**边缘池**" 下，右键单击池中的服务器，然后选择 "**编辑属性**"。 （或者，选择服务器，然后从 "**操作**" 菜单中单击 "**编辑属性**"。）

2.  在“**编辑属性**”窗口中，选择要支持的 IP 地址配置。下图显示用于内部接口和外部接口的双协议栈配置。
    
    **双协议栈边缘服务器内部接口**
    
    ![Lync Server 常规属性页面](images/JJ204984.5b0883ee-b9f2-4a21-91a9-3286d0beb63b(OCS.15).png "Lync Server 常规属性页面")
    
    **双协议栈边缘服务器外部接口**
    
    ![Lync Server 下一跃点/外部配置页面](images/JJ204984.2aa00ce2-ba50-40aa-bbf1-78636016daf9(OCS.15).png "Lync Server 下一跃点/外部配置页面")

3.  对于您选择的每个地址类型，必须提供适当的内部和外部地址。

</div>

</div>

<span> </span>

</div>

</div>

</div>


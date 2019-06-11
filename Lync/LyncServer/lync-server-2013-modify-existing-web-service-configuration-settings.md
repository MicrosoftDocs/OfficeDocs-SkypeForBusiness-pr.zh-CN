---
title: 'Lync Server 2013: 修改现有 Web 服务配置设置'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Modify existing Web Service configuration settings
ms:assetid: bd9c7aa5-d31c-4fab-b31d-8baae26b1296
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182580(v=OCS.15)
ms:contentKeyID: 48185272
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f53d0eb34412c746332a0f74d140b6c41c9c257f
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34827149"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="modify-existing-web-service-configuration-settings-in-lync-server-2013"></a>在 Lync Server 2013 中修改现有的 Web 服务配置设置

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2012-11-01_

你可以使用**Web 服务**页面配置用于访问 Lync Server 2013 相关 web 服务器和 web 服务的身份验证方法。

按照以下步骤修改现有的 Web 服务策略。

<div>

## <a name="to-modify-existing-web-service-configuration-settings"></a>修改现有的 Web 服务配置设置

1.  从 RTCUniversalServerAdmins 组的成员 (或具有等效用户权限) 或分配给 CsServerAdministrator 或 CsAdministrator 角色的用户帐户, 登录到你在其中部署 Lync Server 2013 的网络中的任何计算机。

2.  打开一个浏览器窗口, 然后输入 "管理员" URL 以打开 Lync Server "控制面板"。 有关可用于启动 Lync Server "控制面板" 的不同方法的详细信息, 请参阅[打开 Lync server 2013 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左侧导航栏中，单击“安全性”****，然后单击“Web 服务”****。

4.  在“Web 服务”**** 页上，单击某个配置，再单击“编辑”****，然后单击“显示详细信息”****。

5.  在“编辑 Web 服务设置”**** 的“集成 Windows 身份验证”**** 中，选择“协商”****、“集成 Windows 身份验证”**** 或“无”****。

6.  根据环境中的客户端功能和支持情况，选择下列一项或多项：
    
      - **启用 PIN 身份验证**，允许使用 PIN 号对客户端进行身份验证。
    
      - **启用证书身份验证**，可使池中的服务器向客户端颁发证书。
    
      - **启用证书链下载**，让具有身份验证证书的服务器下载该证书的证书链。

7.  单击“**提交**”。

</div>

<div>

## <a name="see-also"></a>另请参阅


[在 Lync Server 2013 "控制面板" 中配置身份验证](lync-server-2013-configuring-authentication-in-the-lync-server-control-panel.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


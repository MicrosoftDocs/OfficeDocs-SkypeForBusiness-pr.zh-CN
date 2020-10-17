---
title: Lync Server 2013：配置 AD FS 2.0 以支持客户端身份验证
description: Lync Server 2013：配置 AD FS 2.0 以支持客户端身份验证。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring AD FS 2.0 to support client authentication
ms:assetid: 4d93d400-ccaa-4da8-a71b-d05d7ba79d93
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn308565(v=OCS.15)
ms:contentKeyID: 54973687
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 156eb6d7e8af85dec04601ab8f88c55181db20d5
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48553248"
---
# <a name="configuring-ad-fs-20-to-support-client-authentication-in-lync-server-2013"></a>在 Lync Server 2013 中配置 AD FS 2.0 以支持客户端身份验证

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2013-07-03_

有两种可能的身份验证类型可配置为允许 AD FS 2.0 支持使用智能卡的身份验证：

  - 基于表单的身份验证 (FBA) 

  - 传输层安全性客户端身份验证

使用基于表单的身份验证，您可以开发允许用户通过使用其用户名/密码或使用智能卡和 PIN 进行身份验证的网页。 本主题重点介绍如何使用 AD FS 2.0 实施传输层安全性客户端身份验证。 有关 AD FS 2.0 身份验证类型的详细信息，请参阅 AD FS 2.0：如何更改本地身份验证类型 [https://go.microsoft.com/fwlink/p/?LinkId=313384](https://go.microsoft.com/fwlink/p/?linkid=313384) 。

<div>


**配置 AD FS 2.0 以支持客户端身份验证**

1.  使用域管理员帐户登录到 AD FS 2.0 计算机。

2.  启动 Windows 资源管理器。

3.  浏览到 C： \\ inetpub \\ adfs \\ ls

4.  创建现有 web.config 文件的备份副本。

5.  使用记事本打开现有 web.config 文件。

6.  从菜单栏中，选择 " **编辑** "，然后选择 " **查找**"。

7.  搜索 **\<localAuthenticationTypes\>** 。
    
    请注意，每行列出了四种身份验证类型。

8.  将包含 TLSClient 身份验证类型的行移到 "" 部分的列表顶部。

9.  保存并关闭 web.config 文件。

10. 使用提升的权限启动命令提示符。

11. 通过运行以下命令来重新启动 IIS：
    
        IISReset /Restart /NoForce

</div>

</div>

<span> </span>

</div>

</div>

</div>


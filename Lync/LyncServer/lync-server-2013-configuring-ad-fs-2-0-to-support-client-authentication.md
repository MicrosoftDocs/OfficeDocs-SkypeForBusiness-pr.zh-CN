---
title: 'Lync Server 2013: 配置 AD FS 2.0 以支持客户端身份验证'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring AD FS 2.0 to support client authentication
ms:assetid: 4d93d400-ccaa-4da8-a71b-d05d7ba79d93
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn308565(v=OCS.15)
ms:contentKeyID: 54973687
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 12f7cad4b36eb96f7b36925aa91e6363b8cdd264
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34837294"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-ad-fs-20-to-support-client-authentication-in-lync-server-2013"></a>配置 AD FS 2.0 以支持 Lync Server 2013 中的客户端身份验证

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2013-07-03_

有两种可能的身份验证类型可配置为允许 AD FS 2.0 支持使用智能卡进行身份验证：

  - 基于表单的身份验证 (FBA)

  - 传输层安全性客户端身份验证

使用基于表单的身份验证，您可以开发一个网页以允许用户使用其用户名/密码或使用其智能卡和 PIN 进行身份验证。 本主题着重介绍如何实施传输层安全性客户端身份验证与 AD FS 2.0。 有关 AD FS 2.0 身份验证类型的详细信息, 请参阅广告 FS 2.0: 如何更改本地身份验证类型[http://go.microsoft.com/fwlink/p/?LinkId=313384](http://go.microsoft.com/fwlink/p/?linkid=313384)。

<div>


**配置 AD FS 2.0 以支持客户端身份验证**

1.  使用域管理员帐户登录到 AD FS 2.0 计算机。

2.  启动 Windows 资源管理器。

3.  浏览到 C:\\inetpub\\adfs\\ls

4.  创建现有 web.config 文件的备份副本。

5.  使用记事本打开现有 web.config 文件。

6.  从菜单栏中，选择“编辑”****，然后选择“查找”****。

7.  搜索** \<localAuthenticationTypes\>**。
    
    请注意，列出了四种身份验证类型，每行一个。

8.  将包含 TLSClient 身份验证类型的行移动到列表顶部。

9.  保存并关闭 web.config 文件。

10. 使用提升的特权启动命令提示符。

11. 通过运行以下命令来重新启动 IIS：
    
        IISReset /Restart /NoForce

</div>

</div>

<span> </span>

</div>

</div>

</div>


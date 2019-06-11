---
title: Lync Server 2013：安装本地配置存储
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Install the Local Configuration store
ms:assetid: b563030d-d338-411f-9611-28d5eb4b3238
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412874(v=OCS.15)
ms:contentKeyID: 48185180
ms.date: 06/28/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 135dedc38bbc24dd69dfd44b74c70db8e3397252
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34829991"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="install-the-local-configuration-store-in-lync-server-2013"></a>在 Lync Server 2013 中安装本地配置存储

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2014-06-27_

在执行以下步骤之前, 请确保你使用既是本地管理员又是 RTCUniversalReadOnlyAdmin 组成员的域用户帐户登录到服务器。

为了能够使用 Lync Server 部署向导执行任何操作, 需要在服务器上存在本地配置存储。 本地配置存储是中央管理存储的只读副本, 它是在 SQL Server Express 的本地安装之后创建的。 将中央管理存储本身添加到安装在标准版服务器或基于 SQL Server Express 的数据库上的现有 SQL Server 数据库。

<div>


> [!IMPORTANT]  
> 如果以前未在此服务器上运行 Lync Server 2013 设置, 系统将提示你提供安装 Lync Server 2013 的驱动器和路径。 这将允许你安装到除系统驱动器之外的驱动器, 如果你的组织需要, 或者你有空间问题。 您只需将 "设置" 对话框中的 Lync 服务器文件的安装位置路径更改为新的可用驱动器。 如果将安装文件安装到此路径 (包括 OCSCore), 则 Lync Server 2013 文件的其余部分也将部署到其中。



</div>

<div>

## <a name="to-install-the-local-configuration-store"></a>安装本地配置存储

1.  从安装媒体中, 浏览到\\"\\安装\\Amd64 Setup.exe", 然后单击 **"确定"**。

2.  如果系统提示您安装 Microsoft Visual c + + 2012 可再发行组件, 请单击 **"是"**。

3.  在 " **Lync Server 2013 安装位置**" 页面上, 单击 **"确定"**。

4.  在 "**最终用户许可协议**" 页面上, 查看许可条款, 您需要选择 "**我接受许可协议中的条款**", 然后单击 **"确定"** 以继续。

5.  在 "部署向导" 页面上, 单击 "**安装或更新 Lync Server 系统**"。

6.  在 " **Lync Server 2013** " 页面上, 在 " **Step1: 安装本地配置存储**" 旁边, 单击 "**运行**"。

7.  在“**安装本地配置存储**”页面上，确保选择“**直接从中央管理存储中检索**”选项，然后单击“**下一步**”。

8.  本地服务器配置安装完成后, 应单击 "**完成**"。

</div>

</div>

<span> </span>

</div>

</div>

</div>


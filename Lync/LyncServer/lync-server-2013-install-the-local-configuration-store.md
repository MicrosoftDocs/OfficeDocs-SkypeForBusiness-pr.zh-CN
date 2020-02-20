---
title: Lync Server 2013：安装本地配置存储
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Install the Local Configuration store
ms:assetid: b563030d-d338-411f-9611-28d5eb4b3238
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412874(v=OCS.15)
ms:contentKeyID: 48185180
ms.date: 06/28/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 478f45ff682b399f911b41d11a16c802181d14ef
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42146765"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="install-the-local-configuration-store-in-lync-server-2013"></a>在 Lync Server 2013 中安装本地配置存储

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2014-06-27_

在执行以下步骤之前，请确保您使用具有本地管理员和 RTCUniversalReadOnlyAdmin 组成员的域用户帐户登录到服务器。

若要能够在 Lync Server 部署向导中执行任何操作，我们需要在服务器上存在本地配置存储。 本地配置存储是中央管理存储的只读副本，它是在本地安装 SQL Server Express 之后创建的。 中央管理存储本身将添加到安装在 Standard Edition Server 或基于 SQL Server Express 的数据库上的现有 SQL Server 数据库中。

<div>


> [!IMPORTANT]  
> 如果之前未在此服务器上运行 Lync Server 2013 安装程序，系统会提示你提供用于安装 Lync Server 2013 的驱动器和路径。 这将允许你安装到除系统驱动器之外的驱动器，如果你的组织需要，或者你有空间问题。 只需将 "安装程序" 对话框中的 Lync Server 文件的安装位置路径更改为新的可用驱动器即可。 如果将安装文件安装到此路径（包括 OCSCore），则其余的 Lync Server 2013 文件也将部署到该路径中。



</div>

<div>

## <a name="to-install-the-local-configuration-store"></a>安装本地配置存储

1.  在安装媒体中，浏览到\\"\\安装\\Amd64" Setup.exe，然后单击 **"确定"**。

2.  如果系统提示您安装 Microsoft Visual c + + 2012 可再发行组件，请单击 **"是"**。

3.  在“Lync Server 2013 安装位置”**** 页上，单击“确定”****。

4.  在 "**最终用户许可协议**" 页上，查看许可条款，您需要选择 "**我接受许可协议中的条款**"，然后单击 **"确定"** 才能继续。

5.  在“部署向导”页上，单击 **“安装或更新 Lync Server 系统”**。

6.  在“Lync Server 2013”**** 页上，在“步骤 1: 安装本地配置存储”**** 旁边，单击“运行”****。

7.  在 "**安装本地配置存储**" 页上，确保选择了 "**直接从中央管理存储区检索**" 选项，然后单击 "**下一步**"。

8.  本地服务器配置安装完成后，应单击 "**完成**"。

</div>

</div>

<span> </span>

</div>

</div>

</div>


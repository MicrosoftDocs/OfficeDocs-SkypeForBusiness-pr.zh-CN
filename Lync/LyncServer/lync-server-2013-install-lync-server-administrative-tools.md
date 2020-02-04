---
title: Lync Server 2013：安装 Lync Server 管理工具
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Install Lync Server administrative tools
ms:assetid: 842b85e4-2eeb-464f-b1c1-ceb8cc04f8d5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398665(v=OCS.15)
ms:contentKeyID: 48184695
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5ebdcf355618c4257ceaeced5f5e4032ede40cec
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763736"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="install-lync-server-2013-administrative-tools"></a>安装 Lync Server 2013 管理工具

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2013-02-21_

本主题介绍了如何安装您需要用于部署和管理 Lync Server 2013 的管理工具。 默认情况下，在运行 Lync Server 2013 的每台服务器上安装 "管理工具"。 此外，还可以在其他计算机上安装管理工具，如专用管理控制台。 我们强烈建议你在正在创建的 Lync Server 2013 部署所在的计算机上安装管理工具，因为这样做会确保已启用 Active Directory 域服务准备步骤完整，使你可以在以后使用该计算机上的管理工具发布拓扑。

在安装或使用 Lync Server 2013 管理工具之前，请确保查看基础结构、操作系统、软件和管理员权限要求。 有关基础结构要求的详细信息，请参阅[Lync Server 2013 中的管理工具基础结构要求](lync-server-2013-administrative-tools-infrastructure-requirements.md)。 有关操作系统和软件要求的详细信息安装 Lync Server 2013 管理工具，请参阅 lync [server 2013 中的 "服务器和工具" 操作系统支持](lync-server-2013-server-and-tools-operating-system-support.md)、lync [server 2013 的其他软件要求](lync-server-2013-additional-software-requirements.md)以及[Lync server 2013 中的其他服务器支持和要求](lync-server-2013-additional-server-support-and-requirements.md)。 有关安装和使用工具所需的用户权利和权限的详细信息，请参阅[安装和管理 Lync Server 2013 所需的管理员权利和权限](lync-server-2013-administrator-rights-and-permissions-required-for-setup-and-administration.md)。

<div>


> [!IMPORTANT]  
> 如果你的组织要求你在系统驱动器之外的驱动器上找到 Internet 信息服务（IIS）和所有 Web 服务，则可以在 "设置" 对话框中更改 Lync Server 文件的安装位置路径。 如果将安装文件安装到此路径（包括 OCSCore），则其他 Lync Server 2013 文件也将同时部署到此驱动器。



</div>

<div>

## <a name="to-install-the-lync-server-2013-administrative-tools"></a>安装 Lync Server 2013 管理工具

1.  以本地管理员身份（最低要求）登录到要安装管理工具的计算机。 如果在 Windows Vista 或 Windows 7 操作系统上以标准用户身份登录，并且启用了用户帐户控制（UAC），系统将提示您输入本地管理员或域等效的用户名和密码。

2.  在计算机上找到安装媒体，然后双击 " \\设置\\amd64\\setup.exe"。

3.  如果系统提示您安装 Microsoft Visual c + + 2008 可分发，请单击 **"是"**。

4.  在 " **Microsoft Lync Server 2013 安装位置**" 页面上，单击 **"确定"**。 如果需要将文件安装到其他位置，请将此路径更改为其他位置或驱动器。
    
    <div>
    

    > [!IMPORTANT]  
    > 如果你的组织要求你在系统驱动器之外的驱动器上找到 Internet 信息服务（IIS）和所有 Web 服务，则可以在 "设置" 对话框中更改 Lync Server 2013 文件的安装位置路径。 如果将安装文件安装到此路径（包括 OCSCore），则 Lync Server 2013 文件的其余部分也将同时部署到此驱动器。

    
    </div>

5.  在 "**最终用户许可协议**" 页面上，查看许可条款，单击 "**我接受**"，然后单击 **"确定"**。 必须先执行此步骤，然后才能继续。

6.  在 " **Microsoft Lync Server 2013-部署向导**" 页面上，单击 "**安装管理员工具**"。

7.  安装成功完成后，单击 "**退出**"。

</div>

<div>

## <a name="see-also"></a>另请参阅


[打开 Lync Server 2013 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)  


[Lync Server 2013 管理工具](lync-server-2013-lync-server-administrative-tools.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


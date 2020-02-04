---
title: Lync Server 2013：运行架构准备
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Running schema preparation
ms:assetid: 9d02bdb1-ff29-417a-bcce-b068b31207d8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412729(v=OCS.15)
ms:contentKeyID: 48184911
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 06b02981e9baa589801839c8fd8c871ae35b0dde
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41765040"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="running-active-directory-schema-preparation-in-lync-server-2013"></a>在 Lync Server 2013 中运行 Active Directory 架构准备

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2012-10-29_

你可以使用安装程序或 Lync Server Management Shell cmdlet 来准备 Active Directory 架构。 扩展 Active Directory 架构的 cmdlet 为**Install-CsAdServerSchema**。

<div>


> [!NOTE]  
> 架构准备 cmdlet （<STRONG>Install-CsAdServerSchema</STRONG>）必须访问架构主机，这要求远程注册表服务正在运行且远程注册表项已启用。 如果无法在架构主机上启用远程注册表服务，则可以在架构主机上本地运行 cmdlet。 有关注册表远程访问的详细信息，请参阅 Microsoft 知识库文章 314837 "如何管理对注册表的远程访问" <A href="http://go.microsoft.com/fwlink/p/?linkid=125769">http://go.microsoft.com/fwlink/p/?linkId=125769</A>。



</div>

完成架构准备后，手动验证架构分区是否已复制，然后再继续执行林准备。 有关详细信息，请参阅[在 Lync Server 2013 中验证 Active Directory 架构复制](lync-server-2013-verifying-schema-replication.md)。

<div>

## <a name="to-use-setup-to-prepare-the-schema-of-the-current-forest"></a>使用安装程序准备当前林的架构

1.  以架构管理员组的成员身份登录到林中的服务器，并使用架构主机上的管理员权限登录。

2.  从 Lync Server 2013 安装文件夹或媒体中，运行 Setup.exe 以启动部署向导。

3.  如果系统提示您安装 Microsoft Visual c + + 可再发行组件，请单击 **"是"**。

4.  "Lync Server 2013 设置" 对话框提示你输入安装 Lync Server 文件的位置。 选择默认位置或**浏览**到您选择的位置，然后单击 "**安装**"。

5.  在 "许可协议" 页面上，选中 "**我接受许可协议中的条款**"，然后单击 **"确定"**。

6.  安装程序安装 Lync Server 核心组件。

7.  当部署向导准备就绪时，单击 "**准备 Active Directory**"，然后等待确定部署状态。

8.  在**步骤1：准备架构**中，单击 "**运行**"。

9.  在 "**准备架构**" 页面上，单击 "**下一步**"。

10. 在“**正在执行命令**”页上，查找“**任务状态：已完成**”，然后单击“**查看日志**”。

11. 在 "**操作**" 列下，展开 "**架构准备**"，查找每个任务末尾的** \<\>成功**执行结果，验证架构准备是否已成功完成，关闭日志，然后单击 "**完成**"。

12. 等待 Active Directory 复制完成或强制执行复制。

13. 手动验证架构更改是否已复制到所有其他域控制器。 有关详细信息，请参阅[在 Lync Server 2013 中验证 Active Directory 架构复制](lync-server-2013-verifying-schema-replication.md)。

</div>

<div>

## <a name="to-use-cmdlets-to-prepare-the-schema-of-the-current-forest"></a>使用 cmdlet 准备当前林的架构

1.  以架构管理员组的成员身份登录到林中的计算机，并使用架构主机上的管理员权限登录。

2.  安装 Lync Server Core 组件，如下所示：
    
    1.  从 Lync Server 2013 安装文件夹或媒体中，运行 Setup.exe 以启动 Lync Server 部署向导。
    
    2.  如果系统提示您安装 Microsoft Visual c + + 可再发行组件，请单击 **"是"**。
    
    3.  "Lync Server 2013 设置" 对话框提示你输入安装 Lync Server 文件的位置。 选择默认位置或**浏览**到您选择的位置，然后单击 "**安装**"。
    
    4.  在 "许可协议" 页面上，选中 "**我接受许可协议中的条款**"，然后单击 **"确定"**。 安装程序安装 Lync Server 2013 核心组件。

3.  启动 Lync Server 命令行管理程序：依次单击 "**开始**"、"**所有程序**"、" **Microsoft Lync server 2013**"，然后单击 " **Lync server Management shell**"。

4.  运行：
    
        Install-CsAdServerSchema [-Ldf <directory where the .ldf file is located>] 
    
    如果不指定 Ldf 参数，则默认值为从注册表中读取的 Lync Server 2013 安装路径。
    
    例如：
    
        Install-CsAdServerSchema -Ldf "C:\Program Files\Microsoft Lync Server 2013\Deployment\Setup"

5.  使用以下 cmdlet 验证架构准备是否已完成运行。
    
        Get-CsAdServerSchema 
    
    如果架构准备成功，此 cmdlet 将返回**架构\_\_版本状态\_的当前**值。

6.  等待 Active Directory 复制完成或强制执行复制。

7.  手动验证架构更改是否已复制到所有其他域控制器。 有关详细信息，请参阅[在 Lync Server 2013 中验证 Active Directory 架构复制](lync-server-2013-verifying-schema-replication.md)。

</div>

<div>

## <a name="see-also"></a>另请参阅


[在 Lync Server 2013 中验证 Active Directory 架构复制](lync-server-2013-verifying-schema-replication.md)  


[在 Lync Server 2013 中准备 Active Directory 架构](lync-server-2013-preparing-the-active-directory-schema.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


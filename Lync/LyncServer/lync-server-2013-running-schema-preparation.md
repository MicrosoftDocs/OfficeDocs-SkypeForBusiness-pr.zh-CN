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
ms.openlocfilehash: c58f50cb5c4668525450c4aa95b4a00513d5fc17
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42050964"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="running-active-directory-schema-preparation-in-lync-server-2013"></a>在 Lync Server 2013 中运行 Active Directory 架构准备

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-10-29_

您可以使用安装程序或 Lync Server 命令行管理程序 cmdlet 来准备 Active Directory 架构。 展开 Active Directory 架构的 cmdlet 为 **Install-CsAdServerSchema**。

<div>


> [!NOTE]  
> 架构准备 cmdlet (<STRONG>Install-CsAdServerSchema</STRONG>) 必须访问架构主机，这就要求运行远程注册表服务并启用远程注册表项。 如果无法在架构主机上启用远程注册表服务，可以在架构主机上本地运行该 cmdlet。 有关注册表远程访问的详细信息，请参阅 Microsoft 知识库文章 314837 "如何管理对注册表的远程访问？" <A href="http://go.microsoft.com/fwlink/p/?linkid=125769">http://go.microsoft.com/fwlink/p/?linkId=125769</A>。



</div>

完成架构准备之后，在继续林准备之前手动验证是否复制了架构分区。 有关详细信息，请参阅[在 Lync Server 2013 中验证 Active Directory 架构复制](lync-server-2013-verifying-schema-replication.md)。

<div>

## <a name="to-use-setup-to-prepare-the-schema-of-the-current-forest"></a>使用安装程序准备当前林的架构

1.  以 Schema Admins 组成员和在架构主机上具有 Administrator 权限的身份登录到林中的服务器。

2.  从 Lync Server 2013 安装文件夹或媒体中，运行 Setup.exe 以启动部署向导。

3.  如果提示您安装 Microsoft Visual C++ 可再发行软件产品，单击“是”****。

4.  "Lync Server 2013 安装程序" 对话框将提示您输入安装 Lync Server 文件的位置。 选择默认位置或“浏览”**** 至要选择的位置，然后单击“安装”****。

5.  在“许可协议”页上，选中“我接受许可协议中的条款”****，然后单击“确定”****。

6.  安装程序安装 Lync Server Core 组件。

7.  部署向导准备就绪后，单击“准备 Active Directory”****，然后等待确定部署状态。

8.  在“步骤 1: 准备架构”**** 中，单击“运行”****。

9.  在“准备架构”**** 页上，单击“下一步”****。

10. 在“正在执行命令”**** 页上，查找“任务状态: 已完成”****，然后单击“查看日志”****。

11. 在 "**操作**" 列下，展开 "**架构准备**"，在每个任务的末尾查找** \<\>成功**执行结果，以验证架构准备是否成功完成，关闭日志，然后单击 "**完成**"。

12. 等待 Active Directory 复制完成，或强制执行复制。

13. 手动验证是否已将架构更改复制到其他所有域控制器。 有关详细信息，请参阅[在 Lync Server 2013 中验证 Active Directory 架构复制](lync-server-2013-verifying-schema-replication.md)。

</div>

<div>

## <a name="to-use-cmdlets-to-prepare-the-schema-of-the-current-forest"></a>使用 cmdlet 准备当前林的架构

1.  以 Schema Admins 组成员的身份和架构主机上的管理员权限登录到林中的计算机。

2.  安装 Lync Server Core 组件，如下所示：
    
    1.  从 Lync Server 2013 安装文件夹或媒体中，运行 Setup.exe 以启动 Lync Server 部署向导。
    
    2.  如果提示您安装 Microsoft Visual C++ 可再发行软件产品，单击“是”****。
    
    3.  "Lync Server 2013 安装程序" 对话框将提示您输入安装 Lync Server 文件的位置。 选择默认位置或“浏览”**** 至要选择的位置，然后单击“安装”****。
    
    4.  在“许可协议”页上，选中“我接受许可协议中的条款”****，然后单击“确定”****。 安装程序安装 Lync Server 2013 核心组件。

3.  启动 Lync Server 命令行管理程序：依次单击“开始”****、“所有程序”****、“Microsoft Lync Server 2013”**** 和“Lync Server 命令行管理程序”****。

4.  以
    
        Install-CsAdServerSchema [-Ldf <directory where the .ldf file is located>] 
    
    如果不指定 Ldf 参数，则默认值是从注册表中读取的 Lync Server 2013 安装路径。
    
    例如：
    
        Install-CsAdServerSchema -Ldf "C:\Program Files\Microsoft Lync Server 2013\Deployment\Setup"

5.  使用以下 cmdlet 确认架构准备运行结束。
    
        Get-CsAdServerSchema 
    
    如果架构准备成功，则此 cmdlet 返回**架构\_\_版本状态\_的当前**值。

6.  等待 Active Directory 复制完成，或强制执行复制。

7.  手动验证是否已将架构更改复制到其他所有域控制器。 有关详细信息，请参阅[在 Lync Server 2013 中验证 Active Directory 架构复制](lync-server-2013-verifying-schema-replication.md)。

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


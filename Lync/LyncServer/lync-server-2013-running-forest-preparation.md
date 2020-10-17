---
title: Lync Server 2013：运行林准备
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Running forest preparation
ms:assetid: 9d62f7be-bcfe-421d-8d8a-225567102a35
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412732(v=OCS.15)
ms:contentKeyID: 48184991
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3e4ed33466e9b31fbabb3432927baea8f087ea1d
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48511119"
---
# <a name="running-forest-preparation-for-lync-server-2013"></a>为 Lync Server 2013 运行林准备

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-10-29_

您可以使用安装程序或 Lync Server 命令行管理程序 cmdlet 来准备林。 准备林的 cmdlet 为 **Enable-CsAdForest**。

在准备林之后，您必须验证在运行域准备之前是否复制了全局设置。

<div>

## <a name="to-use-setup-to-prepare-the-forest"></a>使用安装程序准备林

1.  以目录林级根域的 Enterprise Admins 组成员的身份登录到加入域的计算机。

2.  在 Lync Server 2013 安装文件夹或媒体中，运行 Setup.exe 以启动部署向导。

3.  单击“准备 Active Directory”****，然后等待确定部署状态。

4.  在“步骤 3: 准备当前林”**** 中，单击“运行”****。

5.  在“准备林”**** 页上，单击“下一步”****。
    
    <div>
    

    > [!NOTE]  
    > 林准备允许你选择将 Lync Server 2013 的通用组放置在什么位置。 选择与组织要求一致的位置。

    
    </div>

6.  在“正在执行命令”**** 页上，查找“任务状态: 已完成”****，然后单击“查看日志”****。

7.  在 " **操作** " 列下，展开 " **林准备**"，查找 **\<Success\>** 每个任务末尾的 "执行结果"，以验证是否已成功完成 "林准备"，然后关闭日志，然后单击 " **完成**"。

8.  等待 Active Directory 复制完成，或者强制向目录林根级域控制器的“Active Directory 站点和服务”**** 管理单元中列出的所有域控制器进行复制，然后再运行域准备。在所有 Active Directory 站点中的域控制器之间强制进行复制，以使几分钟内就在站点中进行复制操作。

</div>

<div>

## <a name="to-use-cmdlets-to-prepare-the-forest"></a>使用 cmdlet 准备林

1.  以目录林根级域中的 Domain Admins 组成员身份登录到加入域的计算机。

2.  安装 Lync Server Core 组件，如下所示：
    
    1.  在 Lync Server 2013 安装文件夹或媒体中，运行 Setup.exe 以启动 Lync Server 部署向导。
    
    2.  如果提示您安装 Microsoft Visual C++ 可再发行软件产品，单击“是”****。
    
    3.  "Lync Server 2013 安装程序" 对话框将提示您输入安装 Lync Server 文件的位置。 选择默认位置或“浏览”**** 至要选择的位置，然后单击“安装”****。
    
    4.  在“许可协议”页上，选中“我接受许可协议中的条款”****，然后单击“确定”****。 安装程序安装 Lync Server 2013 核心组件。

3.  启动 Lync Server 命令行管理程序：依次单击“开始”****、“所有程序”****、“Microsoft Lync Server 2013”**** 和“Lync Server 命令行管理程序”****。

4.  以
    
        Enable-CsAdForest [-GroupDomain <FQDN of the domain in which to create the universal groups>]
    
    例如：
    
        Enable-CsAdForest -GroupDomain domain1.contoso.com 
    
    如果不指定 GroupDomain 参数，则默认值为本地域。如果先前在默认域以外的域中创建了通用组，则必须显式指定 GroupDomain 参数。

5.  等待 Active Directory 复制完成，或者强制向目录林根级域控制器的“Active Directory 站点和服务”**** 管理单元中列出的所有域控制器进行复制，然后再运行域准备。

6.  验证林准备是否成功。运行：
    
        Get-CsAdForest 
    
    如果林准备成功，则此 cmdlet 将返回 **LC \_ FORESTSETTINGS \_ 状态 \_ ** 为 "就绪" 的值。

</div>

<div>

## <a name="see-also"></a>另请参阅


[使用 cmdlet 对 Lync Server 2013 反向林准备](lync-server-2013-using-cmdlets-to-reverse-forest-preparation.md)  


[准备 Lync Server 2013 的林](lync-server-2013-preparing-the-forest.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


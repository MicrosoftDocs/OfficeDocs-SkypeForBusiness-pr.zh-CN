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
ms.openlocfilehash: 129926afe17f946a2ea32d7c67fdea89fab32a54
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41732813"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="running-forest-preparation-for-lync-server-2013"></a>为 Lync Server 2013 运行林准备

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2012-10-29_

你可以使用安装程序或 Lync Server Management Shell cmdlet 准备林。 准备林的 cmdlet 为**Enable-CsAdForest**。

准备好林后，必须先验证全局设置是否已复制，然后再运行域准备。

<div>

## <a name="to-use-setup-to-prepare-the-forest"></a>使用安装程序准备林

1.  以林根域的企业管理员组的成员身份登录加入域的计算机。

2.  从 Lync Server 2013 安装文件夹或媒体中，运行 Setup.exe 以启动部署向导。

3.  单击“**准备 Active Directory**”，然后等待确定部署状态。

4.  在**步骤3：准备当前林**，单击 "**运行**"。

5.  在 "**准备林**" 页面上，单击 "**下一步**"。
    
    <div>
    

    > [!NOTE]  
    > 林准备允许你选择在何处放置 Lync Server 2013 的通用组。 选择与组织要求一致的位置。

    
    </div>

6.  在“**正在执行命令**”页上，查找“**任务状态：已完成**”，然后单击“**查看日志**”。

7.  在 "**操作**" 列下，展开 "**林准备**"，查找每个任务末尾的** \<\>成功**执行结果以验证林准备是否已成功完成，关闭日志，然后单击 "**完成**"。

8.  等待 Active Directory 复制完成，或强制复制到林根域控制器的**Active Directory 站点和服务**管理单元中列出的所有域控制器，然后再运行域准备。 在所有 Active Directory 网站中的域控制器之间强制进行复制，以使网站内的复制在分钟内发生。

</div>

<div>

## <a name="to-use-cmdlets-to-prepare-the-forest"></a>使用 cmdlet 准备林

1.  以林根域中的 "域管理员" 组的成员身份登录加入域的计算机。

2.  安装 Lync Server Core 组件，如下所示：
    
    1.  从 Lync Server 2013 安装文件夹或媒体中，运行 Setup.exe 以启动 Lync Server 部署向导。
    
    2.  如果系统提示您安装 Microsoft Visual c + + 可再发行组件，请单击 **"是"**。
    
    3.  "Lync Server 2013 设置" 对话框提示你输入安装 Lync Server 文件的位置。 选择默认位置或**浏览**到您选择的位置，然后单击 "**安装**"。
    
    4.  在 "许可协议" 页面上，选中 "**我接受许可协议中的条款**"，然后单击 **"确定"**。 安装程序安装 Lync Server 2013 核心组件。

3.  启动 Lync Server 命令行管理程序：依次单击 "**开始**"、"**所有程序**"、" **Microsoft Lync server 2013**"，然后单击 " **Lync server Management shell**"。

4.  运行：
    
        Enable-CsAdForest [-GroupDomain <FQDN of the domain in which to create the universal groups>]
    
    例如：
    
        Enable-CsAdForest -GroupDomain domain1.contoso.com 
    
    如果不指定 GroupDomain 参数，则默认值为本地域。 如果以前在非默认域的域中创建了通用组，则必须显式指定 GroupDomain 参数。

5.  等待 Active Directory 复制完成，或强制复制到林根域控制器的**Active Directory 站点和服务**管理单元中列出的所有域控制器，然后再运行域准备。

6.  验证林准备是否成功。 运行：
    
        Get-CsAdForest 
    
    如果林准备成功，此 cmdlet 将返回**\_LC FORESTSETTINGS\_状态\_** 的值为 "已准备就绪"。

</div>

<div>

## <a name="see-also"></a>另请参阅


[针对 Lync Server 2013 使用 Cmdlet 反向执行林准备](lync-server-2013-using-cmdlets-to-reverse-forest-preparation.md)  


[为 Lync Server 2013 准备林](lync-server-2013-preparing-the-forest.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


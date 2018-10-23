---
title: Lync Server 2013：运行林准备
TOCTitle: 运行林准备
ms:assetid: 9d62f7be-bcfe-421d-8d8a-225567102a35
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg412732(v=OCS.15)
ms:contentKeyID: 49313741
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 为 Lync Server 2013 运行林准备

 

_**上一次修改主题：** 2012-10-29_

您可使用安装程序或 Lync Server 命令行管理程序 cmdlet 准备林。准备林的 cmdlet 为 **Enable-CsAdForest**。

在准备林之后，您必须验证在运行域准备之前是否复制了全局设置。

## 使用安装程序准备林

1.  以目录林级根域的 Enterprise Admins 组成员的身份登录到加入域的计算机。

2.  从 Lync Server 2013 安装文件夹或媒体中，运行 Setup.exe 来启动部署向导。

3.  单击“准备 Active Directory”，然后等待确定部署状态。

4.  在“步骤 3: 准备当前林”中，单击“运行”。

5.  在“准备林”页上，单击“下一步”。
    
    > [!NOTE]  
	> 林准备允许您为 Lync Server 2013 选择放置通用组的位置。选择与组织要求一致的位置。
    


6.  在“正在执行命令”页上，查找“任务状态: 已完成”，然后单击“查看日志”。

7.  在“操作”列下，展开“林准备”，在每项任务结束时查找“\<成功\>”执行结果，以确认林准备成功完成，关闭日志，然后单击“完成”。

8.  等待 Active Directory 复制完成，或者强制向目录林根级域控制器的“Active Directory 站点和服务”管理单元中列出的所有域控制器进行复制，然后再运行域准备。在所有 Active Directory 站点中的域控制器之间强制进行复制，以使几分钟内就在站点中进行复制操作。

## 使用 cmdlet 准备林

1.  以目录林根级域中的 Domain Admins 组成员身份登录到加入域的计算机。

2.  安装 Lync Server 核心组件，如下所示：
    
    1.  从 Lync Server 2013 安装文件夹或媒体中，运行 Setup.exe 来启动 Lync Server 部署向导。
    
    2.  如果提示您安装 Microsoft Visual C++ 可再发行软件产品，单击“是”。
    
    3.  Lync Server 2013 的“安装”对话框将提示您选择安装 Lync Server 文件的位置。选择默认位置或“浏览”至要选择的位置，然后单击“安装”。
    
    4.  在“许可协议”页上，选中“我接受许可协议中的条款”，然后单击“确定”。此时安装程序将安装 Lync Server 2013 核心组件。

3.  启动 Lync Server 命令行管理程序：依次单击“开始”、“所有程序”和“Microsoft Lync Server 2013”，然后单击“Lync Server 命令行管理程序”。

4.  运行：
    
        Enable-CsAdForest [-GroupDomain <FQDN of the domain in which to create the universal groups>]
    
    例如：
    
        Enable-CsAdForest -GroupDomain domain1.contoso.com 
    
    如果不指定 GroupDomain 参数，则默认值为本地域。如果先前在默认域以外的域中创建了通用组，则必须显式指定 GroupDomain 参数。

5.  等待 Active Directory 复制完成，或者强制向目录林根级域控制器的“Active Directory 站点和服务”管理单元中列出的所有域控制器进行复制，然后再运行域准备。

6.  验证林准备是否成功。运行：
    
        Get-CsAdForest 
    
    如果林准备已成功，则此 cmdlet 将返回 **LC\_FORESTSETTINGS\_STATE\_READY** 的值。

## 另请参阅

#### 任务

[针对 Lync Server 2013 使用 Cmdlet 反向执行林准备](lync-server-2013-using-cmdlets-to-reverse-forest-preparation.md)  

#### 其他资源

[为 Lync Server 2013 准备林](lync-server-2013-preparing-the-forest.md)


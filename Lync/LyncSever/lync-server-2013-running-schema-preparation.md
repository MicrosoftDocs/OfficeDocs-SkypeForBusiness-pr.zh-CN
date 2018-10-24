---
title: Lync Server 2013：运行架构准备
TOCTitle: 运行架构准备
ms:assetid: 9d02bdb1-ff29-417a-bcce-b068b31207d8
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg412729(v=OCS.15)
ms:contentKeyID: 49313745
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 在 Lync Server 2013 中运行 Active Directory 架构准备

 

_**上一次修改主题：** 2016-12-08_

您可使用安装程序或 Lync Server 命令行管理程序 cmdlet 准备 Active Directory 架构。展开 Active Directory 架构的 cmdlet 为 **Install-CsAdServerSchema**。

> [!NOTE]  
> 架构准备 cmdlet ( <strong>Install-CsAdServerSchema</strong>) 必须访问架构主机，这就要求运行远程注册表服务并启用远程注册表项。如果无法在架构主机上启用远程注册表服务，可以在架构主机上本地运行该 cmdlet。有关注册表远程访问的详细信息，请参阅 Microsoft 知识库文章 314837“如何管理对注册表的远程访问”，网址为 <a href="http://go.microsoft.com/fwlink/p/?linkid=125769">http://go.microsoft.com/fwlink/p/?linkId=125769</a>。



完成架构准备之后，在继续林准备之前手动验证是否复制了架构分区。有关详细信息，请参阅 [在 Lync Server 2013 中验证 Active Directory 架构复制](lync-server-2013-verifying-schema-replication.md)。

## 使用安装程序准备当前林的架构

1.  以 Schema Admins 组成员和在架构主机上具有 Administrator 权限的身份登录到林中的服务器。

2.  从 Lync Server 2013 安装文件夹或媒体中，运行 Setup.exe 来启动部署向导。

3.  如果提示您安装 Microsoft Visual C++ 可再发行软件产品，单击“是”。

4.  Lync Server 2013 的“安装”对话框将提示您选择安装 Lync Server 文件的位置。选择默认位置或“浏览”至要选择的位置，然后单击“安装”。

5.  在“许可协议”页上，选中“我接受许可协议中的条款”，然后单击“确定”。

6.  此时安装程序将安装 Lync Server 核心组件。

7.  部署向导准备就绪后，单击“准备 Active Directory”，然后等待确定部署状态。

8.  在“步骤 1: 准备架构”中，单击“运行”。

9.  在“准备架构”页上，单击“下一步”。

10. 在“正在执行命令”页上，查找“任务状态: 已完成”，然后单击“查看日志”。

11. 在“操作”列下展开“架构准备”，在每项任务结束时查找“\<成功\>”执行结果以确认成功完成了架构准备，关闭日志，然后单击“完成”。

12. 等待 Active Directory 复制完成，或强制执行复制。

13. 手动验证是否已将架构更改复制到其他所有域控制器。有关详细信息，请参阅 [在 Lync Server 2013 中验证 Active Directory 架构复制](lync-server-2013-verifying-schema-replication.md)。

## 使用 cmdlet 准备当前林的架构

1.  以 Schema Admins 组成员的身份和架构主机上的管理员权限登录到林中的计算机。

2.  安装 Lync Server 核心组件，如下所示：
    
    1.  从 Lync Server 2013 安装文件夹或媒体中，运行 Setup.exe 来启动 Lync Server 部署向导。
    
    2.  如果提示您安装 Microsoft Visual C++ 可再发行软件产品，单击“是”。
    
    3.  Lync Server 2013 的“安装”对话框将提示您选择安装 Lync Server 文件的位置。选择默认位置或“浏览”至要选择的位置，然后单击“安装”。
    
    4.  在“许可协议”页上，选中“我接受许可协议中的条款”，然后单击“确定”。此时安装程序将安装 Lync Server 2013 核心组件。

3.  启动 Lync Server 命令行管理程序：依次单击“开始”、“所有程序”和“Microsoft Lync Server 2013”，然后单击“Lync Server 命令行管理程序”。

4.  运行：
    
        Install-CsAdServerSchema [-Ldf <directory where the .ldf file is located>] 
    
    如果不指定 Ldf 参数，则默认值为从注册表中读取的 Lync Server 2013 安装路径。
    
    例如：
    
        Install-CsAdServerSchema -Ldf "C:\Program Files\Microsoft Lync Server 2013\Deployment\Setup"

5.  使用以下 cmdlet 确认架构准备运行结束。
    
        Get-CsAdServerSchema 
    
    如果架构准备已成功，则此 cmdlet 将返回 **SCHEMA\_VERSION\_STATE\_CURRENT** 的值。

6.  等待 Active Directory 复制完成，或强制执行复制。

7.  手动验证是否已将架构更改复制到其他所有域控制器。有关详细信息，请参阅 [在 Lync Server 2013 中验证 Active Directory 架构复制](lync-server-2013-verifying-schema-replication.md)。

## 另请参阅

#### 任务

[在 Lync Server 2013 中验证 Active Directory 架构复制](lync-server-2013-verifying-schema-replication.md)  

#### 概念

[在 Lync Server 2013 中准备 Active Directory 架构](lync-server-2013-preparing-the-active-directory-schema.md)


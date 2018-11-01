---
title: Lync Server 2013：安装 Standard Edition 服务器数据库
TOCTitle: 安装 Standard Edition 服务器数据库
ms:assetid: 0bd3a804-aad6-48cb-981b-54725af032db
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398167(v=OCS.15)
ms:contentKeyID: 49311971
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 安装适用于 Lync Server 2013 的 Standard Edition 服务器数据库

 

_**上一次修改主题：** 2012-10-01_

将 Standard Edition Server 设置为基础结构中唯一一个驻留用户的服务器不同于在其他服务器安装过程中通过“部署向导”采用选择的方式来设置初始服务器。

## 安装标准版服务器

1.  以本地管理员身份或域等效帐户登录到要安装 Standard Edition Server 的服务器。

2.  如果尚未准备 Active Directory 域服务，则首先执行这些步骤。有关详细信息，请参阅 [为 Lync Server 2013 准备 Active Directory 域服务](lync-server-2013-preparing-active-directory-domain-services.md)。

3.  在 Lync Server 部署向导中，单击“准备第一个 Standard Edition Server”。

4.  在“准备单个 Standard Edition Server”页上，单击“下一步”。

5.  在“正在执行命令”页上，将 SQL Server 2012 Express 作为 中央管理存储进行安装。创建必需的防火墙规则。完成安装数据库和必备软件后，单击“完成”。
    
    > [!NOTE]  
    > 初始安装可能要花费一些时间，这期间命令输出摘要屏幕上不显示更新。这是由 SQL Server Express 安装所导致的。如果需要监视数据库安装，请使用任务管理器监视安装过程。
    


6.  如果之前尚未安装管理工具，请在“Lync Server 部署向导”页上单击“安装拓扑生成器”。有关详细信息，请参阅[安装 Lync Server 2013 管理工具](lync-server-2013-install-lync-server-administrative-tools.md)。

7.  确认“准备 Active Directory”、“准备第一个 Standard Edition Server”和“安装拓扑生成器”旁边有绿色复选标记。


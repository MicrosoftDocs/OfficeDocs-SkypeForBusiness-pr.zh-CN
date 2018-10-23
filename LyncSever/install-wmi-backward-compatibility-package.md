---
title: 安装 WMI 向后兼容包
TOCTitle: 安装 WMI 向后兼容包
ms:assetid: 38797fbd-06a0-4008-b099-158e7b5d7703
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ204816(v=OCS.15)
ms:contentKeyID: 49312501
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 安装 WMI 向后兼容包

 

_**上一次修改主题：** 2012-10-02_

如果试图在没有安装 WMI 向后兼容包的情况下运行拓扑生成器合并向导，将会出现以下错误：

![WMI 错误消息](images/JJ204816.a007d2f2-fc85-430c-91eb-382b032469af(OCS.15).jpg "WMI 错误消息")

如果试图在没有安装 WMI 向后兼容包的情况下运行 **Merge-CsLegacytopology** cmdlet，将会出现以下错误：

![Windows PowerShell WMI 提供程序错误](images/JJ204816.c510824e-1807-4c7e-bb28-c6cfea2eac1d(OCS.15).jpg "Windows PowerShell WMI 提供程序错误")

安装 WMI 向后兼容包

1.  从您的安装媒体中，导航到 \\SETUP\\AMD64\\SETUP\\OCSWMIBC.MSI。

2.  安装 OCSWMIBC.MSI。
    
    > [!IMPORTANT]  
    > OCSWMIBC.msi 必须安装在运行拓扑生成器合并向导的计算机上。不过，建议将 OCSWMIBC.msi 安装在拓扑中的所有前端服务器上。
    
    > [!IMPORTANT]  
    > OCSWMIBC.msi 可以安装在域中安装了 Lync Server 2013 核心组件和 Lync Server 2013 命令行管理程序且有权访问 Office Communications Server 2007 R2 拓扑（Active Directory 域服务 (AD DS) 和 SQL Server 的 WMI 提供程序）的任何计算机上。


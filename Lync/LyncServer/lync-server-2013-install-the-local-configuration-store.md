---
title: Lync Server 2013：安装本地配置存储
TOCTitle: 安装本地配置存储
ms:assetid: b563030d-d338-411f-9611-28d5eb4b3238
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg412874(v=OCS.15)
ms:contentKeyID: 49314002
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 在 Lync Server 2013 中安装本地配置存储

 

_**上一次修改主题：** 2014-06-27_

在执行这些步骤之前，请确保使用属于本地管理员和 RTCUniversalReadOnlyAdmins 组的成员的域用户帐户登录服务器。

要能够使用 Lync Server 部署向导 执行任何操作，我们需要服务器上存在本地配置存储。本地配置存储是中央管理存储的本地副本，它是在 SQL Server Express 的本地安装之后创建的。中央管理存储本身将添加到基于 Standard Edition Server或 SQL Server Express 的数据库上安装的现有 SQL Server 数据库。

> [!IMPORTANT]
> 如果您的组织要求安装到系统驱动器之外的某个系统驱动器上或者您考虑空间问题，这将允许您安装到非系统驱动器。您可以在“安装”对话框中将 Lync Server 文件的本地安装路径更改为新的可用驱动器。如果您将安装文件（包括 OCSCore.msi）安装到此路径，则其余的 Lync Server 2013 文件也将部署到这里。


## 安装本地配置存储

1.  在安装介质上浏览到 \\setup\\amd64\\Setup.exe，然后单击“确定”。

2.  如果系统提示您安装 Microsoft Visual C++ 2012 可再发行软件包，请单击“是”。

3.  在“Lync Server 2013 安装位置”页上，单击“确定”。

4.  在“最终用户许可协议”页上，阅读许可条款，选择“我接受许可协议中的条款”，然后单击“确定”才能继续。

5.  在“部署向导”页上，单击“安装或更新 Lync Server 系统”。

6.  在“Lync Server 2013”页上，在“步骤 1: 安装本地配置存储”旁边，单击“运行”。

7.  在“安装本地配置存储”页面上，确保选择“直接从中央管理存储中检索”选项，然后单击“下一步”。

8.  完成本地服务器配置安装后，您应该单击“完成”。


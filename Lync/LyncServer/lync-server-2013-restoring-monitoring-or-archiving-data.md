---
title: 还原监控或存档数据
TOCTitle: 还原监控或存档数据
ms:assetid: 60118526-13bb-4b03-803e-6ffae219d436
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Hh202175(v=OCS.15)
ms:contentKeyID: 52061030
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 还原监控或存档数据

 

_**上一次修改主题：** 2013-02-18_

发生故障后使 Lync Server 正常运行不需要还原监控和存档数据。但是，如果监控和存档数据对组织而言非常关键，则将需要在重新创建数据库之后还原这些数据。

以下过程介绍如何使用 SQL Server Management Studio 还原存档或监控数据。

## 从备份文件中还原监控或存档数据

1.  以本地计算机上 Administrators 组成员的身份或具有同等用户权限的组成员身份登录到要还原的服务器。

2.  打开 SQL Server Management Studio：依次单击“开始”、“所有程序”、“Microsoft SQL Server 2012”或“Microsoft SQL Server 2008 R2”，然后单击“SQL Server Management Studio”。

3.  在“连接到服务器”中，至少提供服务器的名称和身份验证信息，以连接到 SQL Server 实例。

4.  在“对象资源管理器”中，右键单击“数据库”，然后单击“还原数据库”。

5.  在“选择页”下，单击“常规”，然后在“目标数据库”中选择数据库名称，如下所示：
    
      - 对于存档数据库，请选择“LcsLog”。
    
      - 对于呼叫详细信息记录 (CDR) 数据库，请选择“LcsCDR”。
    
      - 对于用户体验质量 (QoE) 数据库，请选择“QoEMetrics”。

6.  单击“自设备”。

7.  在“选择用于还原的备份集”下，单击备份文件，然后单击“还原”。

8.  在“选择页”下，单击“选项”，确认数据文件路径和日志路径位于正确的文件夹中，然后单击“确定”。

## 确保访问控制列表 (ACL) 是正确的

1.  依次展开“数据库”、存档数据库或监控数据库、“安全”，然后展开“用户”。

2.  确认域组 RTCComponentUniversalServices 作为用户存在。

3.  如果“用户”下不存在 RTCComponentUniversalServices，请执行以下操作：
    
    1.  右键单击“用户”，然后单击“新建用户”。
    
    2.  在“登录名”中，键入缺少的组名 RTCComponentUniversalServices。
    
    3.  在“数据库角色成员身份”中，选择“ServerRole”权限，然后单击“确定”。
    
    > [!NOTE]  
	> 无需重新启动存档服务或监控服务。
    


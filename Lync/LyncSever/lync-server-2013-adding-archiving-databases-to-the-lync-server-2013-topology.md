---
title: 向 Lync Server 2013 拓扑添加存档数据库
TOCTitle: 向 Lync Server 2013 拓扑添加存档数据库
ms:assetid: 089ab32f-1167-4bb8-a283-fdc6c9613072
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ204654(v=OCS.15)
ms:contentKeyID: 49311922
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 向 Lync Server 2013 拓扑添加存档数据库

 

_**上一次修改主题：** 2012-10-10_

必须先在拓扑中纳入存档，然后才能配置您的部署以支持存档。本主题中的信息说明了如何使用拓扑生成器向现有拓扑中添加存档。

> [!NOTE]  
> 若要使用 Microsoft Exchange 集成将部署中所有用户的存档数据和文件存储在 Exchange 2013 服务器上，不要指定“存档 SQL Server 存储”或“启用 SQL Server 存储镜像”信息。



## 向拓扑中添加存档数据库支持

1.  在运行 Lync Server 2013 或其上安装有 Lync Server 管理工具的计算机上，使用具有本地 Users 组成员身份的帐户（或具有同等用户权限的帐户）登录。
    
    > [!NOTE]  
    > 您可以使用具有本地 Users 组成员身份的帐户定义拓扑，但要发布拓扑（向拓扑中添加服务器时需要），您必须使用具有“Domain Admins”组和“RTCUniversalServerAdmins”组成员身份的帐户，且该帐户对您要用于 Lync Server 2013 文件存储的文件共享具有完全控制权限（即读取、写入和修改）（以便拓扑生成器可以配置必需的自定义访问控制列表 (DACL)），或者使用具有同等权限的帐户。
    


2.  启动拓扑生成器。

3.  在控制台树中，导航到您要在其中部署存档的前端池，然后单击要在其中部署存档的前端池的名称。

4.  在“操作”菜单上，单击“编辑属性”。

5.  在“编辑属性”对话框中，单击“常规”。

6.  向下滚动到“存档”。

7.  选中“存档”复选框。

8.  在“存档 SQL Server 存储”下，执行下列操作之一：
    
      - 若要使用现有 SQL Server 存储，请在下拉列表框中，单击要使用的 SQL Server 存储的名称。如果所有用户均驻留在 Microsoft Exchange Server 2013 或更高版本中，则可以将 Exchange 中所有用户的 Lync 通信进行存档。这种情况下，您不需要配置 SQL Server 存档存储。
    
      - 若要指定新的 SQL Server 存储，请单击“新建”，然后在“定义新的 SQL Server 存储”对话框中，执行下列操作：
        
          - 在“SQL Server FQDN”中，指定要在其上创建新 SQL Server 存储的服务器的 FQDN。
        
          - 单击“默认实例”以使用默认的实例，或者，若要指定其他实例，请单击“命名实例”，然后指定要使用的实例。
        
          - 如果指定的 SQL Server 实例处于镜像关系中，请选中“此 SQL 实例处于镜像关系中”复选框，然后在“镜像端口号”中，指定端口号。

9.  若要使用 SQL Server 存储镜像，请选择“启用 SQL Server 存储镜像”，然后执行以下操作之一：
    
      - 若要将现有 SQL Server 存储用于镜像，请在“存档 SQL Server 存储镜像”下拉列表框中，单击要用于镜像的 SQL Server 存储的名称。
    
      - 若要指定新的 SQL Server 存储用于镜像，请单击“新建”，然后在“定义新的 SQL Server 存储”对话框中，执行下列操作之一：
        
        1.  在“SQL Server FQDN”中，指定要在其中创建新的 SQL Server 存储的 SQL Server 的 FQDN。
        
        2.  单击“默认实例”以使用默认的实例，或者，若要指定其他实例，请单击“命名实例”，然后指定要使用的实例。
        
        3.  如果指定的 SQL Server 实例处于镜像关系中，请选中“此 SQL 实例处于镜像关系中”复选框，然后在“镜像端口号”中，指定端口号。
    
      - 如果启用 SQL Server 镜像并希望包含 SQL Server 镜像见证（第三个单独的 SQL Server 实例，可以检测主 SQL Server 服务器和镜像实例的运行状况），请选中“使用 SQL Server 镜像见证启用自动故障转移”复选框，然后执行以下操作之一：
        
        1.  在“SQL Server FQDN”中，指定要在其上创建新 SQL Server 镜像见证的服务器的 FQDN。
        
        2.  单击“默认实例”以使用默认的实例，或者，若要指定其他实例，请单击“命名实例”，然后指定要用于镜像见证的实例。
        
        3.  如果指定的 SQL Server 实例处于镜像关系中，请选中“此 SQL 实例处于镜像关系中”复选框，然后在“镜像端口号”中，指定端口号。

10. 若要保存配置，请单击“确定”。


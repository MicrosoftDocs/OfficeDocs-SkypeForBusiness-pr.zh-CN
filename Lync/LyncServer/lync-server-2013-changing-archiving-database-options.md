---
title: 在 Lync Server 2013 中更改存档数据库选项
TOCTitle: 在 Lync Server 2013 中更改存档数据库选项
ms:assetid: 3775f09d-65b0-48bc-8a4d-d97bd0c3423c
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ204814(v=OCS.15)
ms:contentKeyID: 49312520
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 在 Lync Server 2013 中更改存档数据库选项

 

_**上一次修改主题：** 2012-11-01_

如果您通过将 SQL Server 存储用于存档存储来为您的任何用户部署存档，可以进行下列数据库存储更改：

  - 将不同的 SQL Server 数据库用于存档存储。这包括主存档数据库和用于 SQL Server 镜像的任何数据库。

  - 切换到 Microsoft Exchange 集成以将存档数据和文件存储在 Exchange 2013 服务器上。如果您的所有用户都驻留在 Exchange 2013 服务器上并且您要对部署中的所有用户使用 Microsoft Exchange 存储，则应从您的拓扑中删除 SQL Server 存储数据库。

要进行其中任一项更改，您必须运行拓扑生成器，进行更改，然后重新发布拓扑。可以使用拓扑生成器执行此操作。请勿指定“存档 SQL Server 存储”或“启用 SQL Server 存储镜像”信息，除非有些 Lync 用户未驻留在 Exchange 2013 服务器上。

## 更改存档数据库选项

1.  在运行 Lync Server 2013 或其上安装有 Lync Server 管理工具的计算机上，使用具有本地 Users 组成员身份的帐户（或具有同等用户权限的帐户）登录。
    
    > [!NOTE]  
    > 您可以使用具有本地 Users 组成员身份的帐户定义拓扑，但要发布拓扑（向拓扑中添加组件时需要），您必须使用具有“Domain Admins”组和“RTCUniversalServerAdmins”组成员身份的帐户，且该帐户对您要用于 Lync Server 2013 文件存储的文件共享具有完全控制权限（即读取、写入和修改）（以便拓扑生成器可以配置必需的自定义访问控制列表 (DACL)），或者使用具有同等权限的帐户。
    


2.  启动拓扑生成器。

3.  在控制台树中，导航到您在其中部署了存档的前端池，然后单击要在其中更改数据库选项的前端池的名称。

4.  在“操作”菜单上，单击“编辑属性”。

5.  在“编辑属性”对话框中，单击“常规”。

6.  向下滚动到“存档”。

7.  在“存档”中，执行下列操作：
    
      - 若要切换到其他现有 SQL Server 存储，请在“存档 SQL Server 存储”下的下拉列表框中，执行下列操作：
        
          - 若要使用现有 SQL Server 存储，请在下拉列表框中，单击要使用的 SQL Server 存储的名称。
        
          - 若要指定新的 SQL Server 存储，请单击“新建”，然后在“定义新的 SQL Server 存储”对话框中，执行下列操作：
            
              - 若要使用现有 SQL Server 存储，请在下拉列表框中，单击要使用的 SQL Server 存储的名称。
            
              - 若要指定新的 SQL Server 存储，请单击“新建”，然后在“定义新的 SQL Server 存储”对话框中，执行下列操作：
                
                  - 在“SQL Server FQDN”中，指定要在其上创建新 SQL Server 存储的服务器的 FQDN。
                
                  - 单击“默认实例”以使用默认的实例，或者，若要指定其他实例，请单击“命名实例”，然后指定要使用的实例。
                
                  - 如果指定的 SQL Server 实例处于镜像关系中，请选中“此 SQL 实例处于镜像关系中”复选框，然后在“镜像端口号”中，指定端口号。
    
      - 若要添加用于镜像的 SQL Server 存储或将其他现有 SQL Server 存储用于 SQL Server 存储镜像，请选择“启用 SQL Server 存储镜像”，然后执行下列操作：
        
          - 若要将现有 SQL Server 存储用于镜像，请在“存档 SQL Server 存储镜像”下拉列表框中，单击要用于镜像的 SQL Server 存储的名称。
        
          - 若要指定将新的 SQL Server 存储用于镜像，请单击“新建”，然后在“定义新的 SQL Server 存储”对话框中，执行下列操作之一：
            
            1.  在“SQL Server FQDN”中，指定要在其上创建新 SQL Server 存储的 SQL Server 的 FQDN。
            
            2.  单击“默认实例”以使用默认的实例，或者，若要指定其他实例，请单击“命名实例”，然后指定要使用的实例。
            
            3.  如果指定的 SQL Server 实例处于镜像关系中，请选中“此 SQL 实例处于镜像关系中”复选框，然后在“镜像端口号”中，指定端口号。
        
          - 如果启用 SQL Server 镜像并希望添加或更改 SQL Server 镜像见证（第三个单独的 SQL Server 实例，可以检测主 SQL Server 服务器和镜像实例的运行状况），请选中“使用 SQL Server 镜像见证启用自动故障转移”复选框，然后执行以下操作之一：
            
            1.  在“SQL Server FQDN”中，指定要在其上创建新的 SQL Server 镜像见证的服务器的 FQDN。
            
            2.  单击“默认实例”以使用默认的实例，或者，若要指定其他实例，请单击“命名实例”，然后指定要用于镜像见证的实例。
            
            3.  如果指定的 SQL Server 实例处于镜像关系中，请选中“此 SQL 实例处于镜像关系中”复选框，然后在“镜像端口号”中，指定端口号。
    
      - 若要切换到 Microsoft Exchange 集成以将存档数据和文件存储到 Exchange 2013 服务器上（如果您的部署中的所有用户都驻留在 Exchange 2013 服务器上），请删除存档数据库的所有信息。
    
    > [!IMPORTANT]  
	> 如果您的任何 Lync 用户未驻留在 Exchange 2013 服务器上，请不要删除 SQL Server 存储信息。


8.  若要保存配置，请单击“确定”。
    
    > [!IMPORTANT]  
	> 仅在发布新拓扑之后，您在拓扑生成器中进行的更改才会生效。有关详细信息，请参阅部署文档中的<a href="lync-server-2013-publishing-the-updated-topology-to-add-archiving-databases.md">发布更新的拓扑以添加存档数据库</a>。


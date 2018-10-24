---
title: Lync Server 2013：配置 Microsoft Exchange Server 统一消息以与 Lync Server 2013 一起工作
TOCTitle: 配置 Microsoft Exchange Server 统一消息以与 Lync Server 2013 一起工作
ms:assetid: 058da9c4-23af-4ddb-9f63-70133a8aafc6
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398106(v=OCS.15)
ms:contentKeyID: 49311875
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 配置 Microsoft Exchange Server 统一消息以与 Lync Server 2013 一起工作

 

_**上一次修改主题：** 2016-12-08_

> [!IMPORTANT]
> 如果您想要使用 Exchange 统一消息 (UM) 为 企业语音用户提供呼叫应答、Outlook Voice Access 或自动助理服务，请阅读规划文档中的 <a href="lync-server-2013-planning-for-exchange-unified-messaging-integration.md">在 Lync Server 2013 中规划 Exchange 统一消息集成</a>，然后按照本节中的说明进行操作。


要配置 Exchange 统一消息 (UM) 与 企业语音一起使用，您需要执行以下任务：

  - 在运行 Exchange 统一消息 (UM) 服务的服务器上配置证书
    
    > [!NOTE]  
    > 向所有 UM SIP URI 拨号计划添加所有客户端访问和邮箱服务器。否则，出站呼叫路由将无法正常工作。
    


  - 创建一个或多个 UM SIP URI 拨号计划，根据需要还可以创建订阅者访问电话号码，然后创建对应的 Lync Server 拨号计划。

  - 使用 **exchucutil.ps1** 脚本执行以下操作：
    
      - 创建 UM IP 网关。
    
      - 创建 UM 智能寻线。
    
      - 授予 Lync Server 2013 读取 UM Active Directory 域服务 对象的权限。

  - 创建 UM 自动助理对象。

  - 创建订阅者访问对象。

  - 为每个用户创建一个 SIP URI，并将用户与 UM SIP URI 拨号计划关联。

## 要求与建议

开始之前，本节中的文档假设您已部署以下 Exchange 2013 角色：客户端访问和邮箱。在 Microsoft Exchange Server 2013 中， Exchange UM 作为这些服务器上的服务运行。

有关部署 Exchange 2013 的详细信息，请参阅 Exchange 2013 TechNet 库，网址为 [http://go.microsoft.com/fwlink/p/?LinkId=266637](http://go.microsoft.com/fwlink/p/?linkid=266637)

另外还需注意以下事项：

  - 如果在多个林中安装 Exchange UM，则必须对每个 UM 林执行 Exchange Server 集成步骤。此外，必须将每个 UM 林配置为信任部署 Lync Server 2013 的林，还必须将部署 Lync Server 2013 的林配置为信任每个 UM 林。

  - 集成步骤同时在运行统一消息服务的 Exchange Server 角色上和运行 Lync Server 2013 的服务器上执行。执行 Lync Server 2013 集成步骤之前应先执行 Exchange Server 统一消息集成步骤。
    
    > [!NOTE]  
    > 要查看在哪些服务器上执行了哪些集成步骤并且由哪些管理员角色执行，请参阅<a href="lync-server-2013-deployment-process-for-integrating-on-premises-unified-messaging.md">集成本地统一消息与 Lync Server 2013 的部署过程</a>。
    


每台运行 Exchange UM 的服务器上都必须具有以下工具：

  - Exchange 命令行管理程序

  - 脚本 **exchucutil.ps1**，它将执行以下任务：
    
      - 为每个 Lync Server 2013 创建 UM IP 网关。
    
      - 为每个网关创建一个智能寻线。每个智能寻线的引导标识符指定与该网关关联的 前端池或 Standard Edition Server 所使用的 UM SIP URI 拨号计划。
    
      - 授予 Lync Server 2013 读取 Active Directory 域服务 中 Exchange UM 对象的权限。

## 本节内容

  - [在运行 Microsoft Exchange Server 统一消息的服务器上配置证书](lync-server-2013-configure-certificates-on-the-server-running-microsoft-exchange-server-unified-messaging.md)

  - [在 Microsoft Exchange 中为 Lync Server 2013 配置统一消息](lync-server-2013-configure-unified-messaging-on-microsoft-exchange.md)


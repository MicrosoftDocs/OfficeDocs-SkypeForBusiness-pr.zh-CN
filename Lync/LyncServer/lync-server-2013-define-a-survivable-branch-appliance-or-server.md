---
title: Lync Server 2013：定义 Survivable Branch Appliance 或 Survivable Branch Server
TOCTitle: 定义 Survivable Branch Appliance 或 Survivable Branch Server
ms:assetid: 1f49cfbe-30b3-4600-af15-47cb2f58d18a
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398280(v=OCS.15)
ms:contentKeyID: 49312208
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 在 Lync Server 2013 中定义 Survivable Branch Appliance 或 Survivable Branch Server

 

_**上一次修改主题：** 2012-10-07_

如果在将 Survivable Branch Appliance 或 Survivable Branch Server 添加到拓扑时尚未对其进行定义，则在中央站点执行以下过程。

## 定义 Survivable Branch Appliance 或Survivable Branch Server

1.  依次单击“开始”、“所有程序”、“Microsoft Lync Server 2013”，然后单击“Lync Server拓扑生成器”。

2.  在控制台树中展开中央站点，展开“分支站点”，然后展开计划在其上部署 Survivable Branch Appliance 或Survivable Branch Server的分支站点的名称。

3.  右键单击“Survivable Branch Appliance”，然后单击“新建 Survivable Branch Appliance”。
    
    > [!IMPORTANT]
    > “Survivable Branch Appliance”是定义Survivable Branch Server和 Survivable Branch Appliance 的位置。


4.  在“定义 Survivable Branch Appliance”对话框中，单击“FQDN”，键入要在该分支站点上部署的 Survivable Branch Appliance 或Survivable Branch Server的完全限定的域名 (FQDN)，然后单击“下一步”。
    
    > [!IMPORTANT]
    > 如果要定义 Survivable Branch Appliance，则在“FQDN”中输入的名称必须与分配给“servicePrincipalName”属性的 Survivable Branch Appliance FQDN 相同。有关详细信息，请参阅<a href="lync-server-2013-add-a-survivable-branch-appliance-to-active-directory.md">在 Lync Server 2013 中向 Active Directory 中添加 Survivable Branch Appliance</a>。


5.  单击“前端池”，再单击该 Survivable Branch Appliance 或Survivable Branch Server将连接到的中央站点上的前端服务器（用户服务池），然后单击“下一步”。

6.  单击“边缘服务器”，再单击该 Survivable Branch Appliance 或Survivable Branch Server将连接到的边缘池，以便向分支站点的远程用户提供 PSTN 连接，然后单击“下一步”。

7.  单击“网关 FQDN 或 IP 地址”，然后键入与 Survivable Branch Appliance 或Survivable Branch Server关联并用于路由入站或出站 PSTN 呼叫的对等网关的 FQDN 或 IP 地址。
    
    > [!IMPORTANT]
    > 如果要定义 Survivable Branch Appliance，这是 Survivable Branch Appliance 内的中介服务器为建立 PSTN 连接而连接的网关。


8.  单击“IP/PSTN 网关的侦听端口”，然后接受默认端口。

9.  在“SIP 传输协议”中，单击 Survivable Branch Appliance 或Survivable Branch Server使用的传输协议，然后单击“完成”。
    
    > [!NOTE]  
    > 出于安全考虑，强烈建议使用传输层安全性 (TLS)。如果要定义 Survivable Branch Appliance，请参考 Survivable Branch Appliance 供应商文档，以验证 Survivable Branch Appliance 是否支持 TLS 协议。
    


10. 在控制台树中，右键单击新的 Survivable Branch Appliance 或 Survivable Branch Server，再单击“拓扑”，然后单击“发布”。

**下一步** ：[使用 Lync Server 2013 部署 Survivable Branch Appliance 或 Survivable Branch Server - 分支站点任务](lync-server-2013-deploy-a-survivable-branch-appliance-or-server-branch-site-task.md)


---
title: 配置中介服务器
TOCTitle: 配置中介服务器
ms:assetid: 583236fd-33cd-4045-81df-baa58ed07779
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ204913(v=OCS.15)
ms:contentKeyID: 49312905
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 配置中介服务器

 

_**上一次修改主题：** 2016-12-08_

该过程详细说明将 Lync Server 2013 池配置为使用 Lync Server 2013 中介服务器而不是旧 Office Communications Server 2007 R2 中介服务器的步骤。

若要在添加或删除服务器角色时成功发布、启用或禁用拓扑，应以 RTCUniversalServerAdmins 和 Domain Admins 组成员的用户身份登录。还可以委派用于添加服务器角色的相应管理员权限。有关详细信息，请参阅 Standard Edition 服务器或 Enterprise Edition 服务器部署文档中的“委派安装权限”。对于其他配置更改，只需要 RTCUniversalServerAdmins 组的成员身份。

> [!NOTE]  
> 有关查找可与 Lync Server 2013 配合使用的合格 PSTN 网关、IP-PBX 和 SIP 中继服务的最新信息，请参阅 <a href="http://go.microsoft.com/fwlink/p/?linkid=206015">http://go.microsoft.com/fwlink/p/?linkId=206015</a> 上的“Microsoft 统一通信开放互操作性计划”。



## 使用拓扑生成器配置中介服务器

1.  从拓扑生成器中打开现有拓扑。

2.  在左窗格中，导航到“PSTN 网关”。

3.  右键单击“PSTN 网关”，然后单击“新建 IP/PSTN 网关”。

4.  参考以下信息，完成“定义新的 IP/PSTN 网关”页：
    
      - 输入网关的 FQDN 或 IP 地址。如果网关使用 TLS 协议，则需要网关的 FQDN。
    
      - 接受“IP/PSTN 网关的侦听端口”的默认值，或者输入新侦听端口（如果已修改）。
    
      - 设置“SIP 传输协议”。

5.  在左窗格中，导航到“Enterprise Edition 前端池”或“Standard Edition Server”。

6.  右键单击该池，然后单击“编辑属性”。

7.  在“中介服务器”下，设置“侦听端口”。

8.  接下来，选择新创建的 PSTN 网关，然后单击“添加”，以关联该网关。

9.  在“拓扑生成器”中，选择最顶层节点“Lync Server”。

10. 从“操作”菜单中，选择“发布拓扑”，然后单击“下一步”。

11. “发布向导”完成时，单击“完成”关闭向导。

> [!NOTE]  
> 必须完成下一主题（ <a href="change-voice-routes-to-use-the-new-lync-server-2013-mediation-server.md">更改语音路由以使用新的 Lync Server 2013 中介服务器</a>），以确保语音路由指向正确的中介服务器。



---
title: 在 Lync Server 2013 中配置新的受信任应用程序服务器
TOCTitle: 在 Lync Server 2013 中配置新的受信任应用程序服务器
ms:assetid: a7233db7-fac3-43ff-972e-3bc29a56adb3
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg617964(v=OCS.15)
ms:contentKeyID: 49313871
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 在 Lync Server 2013 中配置新的受信任应用程序服务器

 

_**上一次修改主题：** 2016-12-08_

受信任应用程序是基于 Microsoft 统一通信托管 API (UCMA) 3.0 核心 SDK 且受 Microsoft Lync Server 2013 信任的应用程序。有关 UCMA 应用程序的详细信息，请参阅“统一通信托管 API 3.0 核心 SDK 文档”，网址为 [http://go.microsoft.com/fwlink/?linkid=210320\&clcid=0x804](http://go.microsoft.com/fwlink/?linkid=210320%26clcid=0x804)。

有关配置 Microsoft Outlook Web Access (OWA) 和 Lync Server 2013 的信息，请参阅 Microsoft Exchange Server 2013 文档中的“配置 Outlook Web App 和 Lync Server 2010 集成”。

若要在添加或删除服务器角色时成功发布、启用或禁用拓扑，应以 RTCUniversalServerAdmins 和 Domain Admins 组成员的用户身份登录。还可以委派用于添加服务器角色的相应管理员权限。有关详细信息，请参阅部署文档中的[Lync Server 2013 中的委派安装权限](lync-server-2013-delegate-setup-permissions.md)。对于其他配置更改，只需要 RTCUniversalServerAdmins 组的成员身份。

## 配置受信任应用程序服务器

1.  以 Domain Admins 组和 RTCUniversalServerAdmins 组成员的身份登录安装了拓扑生成器的计算机。

2.  启动拓扑生成器：依次单击“开始”、“所有程序”和“Microsoft Lync Server 2013”，然后单击“Lync Server 拓扑生成器”。

3.  选择“从现有部署下载拓扑”，然后单击“确定”。

4.  在“将拓扑另存为”对话框中，单击要使用的拓扑生成器文件，然后单击“保存”。

5.  在左侧窗格中，右键单击“受信任应用程序服务器”，然后单击“新建受信任应用程序池”。

6.  输入受信任应用程序池的“池 FQDN”，选择该池是将包含单服务器还是多服务器，然后单击“下一步”。

7.  在“选择下一个跃点”页上，从列表中选择 Lync Server 2013前端池。

8.  单击“完成”。

9.  选择顶级节点“Lync Server 2013”，然后在“操作”菜单中单击“发布拓扑”。
    
    “受信任应用程序池”应已成功创建且与正确的前端池关联。


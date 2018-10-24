---
title: 导入策略和设置
TOCTitle: 导入策略和设置
ms:assetid: b25decee-2ee5-4836-b370-454411d39252
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ205178(v=OCS.15)
ms:contentKeyID: 49313958
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 导入策略和设置

 

_**上一次修改主题：** 2012-09-28_

将 Office Communications Server 2007 R2 拓扑信息与 Lync Server 2013 试点池合并后，需要运行 Lync Server 2013 Management Shell cmdlet 以将 Office Communications Server 2007 R2 策略和配置设置迁移到 Lync Server 2013 试点池。

**Import-CsLegacyConfiguration** cmdlet 会将策略、语音路由、拨号计划、Communicator Web Access URL 和拨入访问号码导入到 Lync Server 2013 中。

## 迁移策略和设置

1.  在 Lync Server 2013 前端服务器上，启动 Lync Server 命令行管理程序。

2.  在命令行中键入：
    
        Import-CsLegacyConfiguration
    
    导入策略后，请使用下面的过程在 Lync Server 控制面板中查看导入的策略。

## 查看导入的策略

1.  打开 Lync Server 2013 控制面板。

2.  单击“语音路由”并查看导入的策略。

3.  单击“会议”并查看导入的策略。

4.  单击“联盟和外部访问”并查看导入的策略。

5.  单击“监控和存档”并查看导入的策略。


---
title: 配置受信任应用程序服务器
TOCTitle: 配置受信任应用程序服务器
ms:assetid: 47a9e72e-566c-4c23-bec2-760a3098a974
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ204865(v=OCS.15)
ms:contentKeyID: 49312722
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 配置受信任应用程序服务器

 

_**上一次修改主题：** 2012-10-04_

在混合环境中，如果在将旧 Office Communications Server 拓扑与 Lync Server 2013 合并后创建新的受信任的应用程序服务器，并使用拓扑生成器对其进行定义，则必须将下一个跃点池设置为 Lync Server 2013 池。在合并环境中，旧 Office Communications Server 池和 Lync Server 2013 池都显示在下拉列表中。此环境 *不* 支持选择旧池。

## 创建受信任的应用程序服务器时选择 Lync Server 2013 作为下一跃点

1.  在拓扑生成器中打开现有拓扑。

2.  在左窗格中，右键单击“受信任的应用程序服务器”，然后单击“新建受信任的应用程序池”。

3.  输入受信任应用程序池的“池 FQDN”，选择该池是包含一台服务器还是多台服务器部署。

4.  单击“下一步”。

5.  在“选择下一个跃点”页上，从列表中选择 Lync Server 2013 前端池。
    
    ![“定义新的受信任应用程序池”对话框](images/JJ204865.ecfe2bb8-758b-4b36-8146-573005c4ab09(OCS.15).jpg "“定义新的受信任应用程序池”对话框")  

6.  单击“完成”。

7.  选择顶层节点“Lync Server”，然后从“操作”窗格中选择“发布”。

8.  验证“受信任应用程序池”是否已成功创建且与正确的前端池关联。


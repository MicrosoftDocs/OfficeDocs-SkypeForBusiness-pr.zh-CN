---
title: 删除 BackCompatSite
TOCTitle: 删除 BackCompatSite
ms:assetid: 039650e3-541b-45c2-a682-c4fa08423118
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ204637(v=OCS.15)
ms:contentKeyID: 49311840
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 删除 BackCompatSite

 

_**上一次修改主题：** 2012-09-28_

停用所有池并卸载所有边缘服务器之后，请运行拓扑生成器合并向导以删除 **BackCompatSite**。

## 从拓扑生成器中删除 BackCompat 站点

1.  从拓扑生成器打开一个现有部署。

2.  在“操作”菜单中，单击“合并 2007 R2 拓扑”。

3.  单击“下一步”继续。

4.  在“指定旧边缘”页上，确保边缘服务器列表为空。如果该列表不为空，请使用“删除”按钮删除所有旧边缘服务器，然后单击“下一步”。
    
    ![合并拓扑向导 -“指定边缘设置”页](images/JJ204637.fb35a59a-711e-4259-b177-7311df1fed3c(OCS.15).jpg "合并拓扑向导 -“指定边缘设置”页")  

5.  在“指定内部 SIP 端口”设置页上，单击“下一步”。

6.  在“摘要”页上，单击“下一步”开始合并拓扑，以删除旧站点。

7.  在“状态”列中，确认值为“成功”，然后单击“完成”以关闭向导。

8.  在拓扑生成器的左窗格中，展开 BackCompatSite，确保未列出任何服务器。

9.  右键单击“BackCompatSite”，然后单击“删除”。

10. 在“拓扑生成器”中，选择最顶层节点“Lync Server”。

11. 从“操作”菜单中，选择“发布拓扑”，然后单击“下一步”。

12. “发布向导”完成时，单击“完成”关闭向导。


---
title: Lync Server 2013：在拓扑生成器中定义和配置拓扑
TOCTitle: 在拓扑生成器中定义和配置拓扑
ms:assetid: 99231ff5-1c21-432b-ad65-8675fcd484f9
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398788(v=OCS.15)
ms:contentKeyID: 49313700
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 在 Lync Server 2013 拓扑生成器中定义和配置拓扑

 

_**上一次修改主题：** 2013-02-21_

运行 拓扑生成器定义新拓扑或修改现有拓扑不需要本地管理员或授权域组的成员身份。根据您的配置要求， 拓扑生成器会指导您完成为 Enterprise Edition 前端池或 Standard Edition 定义拓扑的必要步骤。

必须先使用 拓扑生成器来完成并发布拓扑，才能在服务器上安装 Lync Server 2013。下列过程包含定义新拓扑所需的步骤。

## 定义拓扑

1.  启动拓扑生成器：依次单击“开始”、“所有程序”和“Microsoft Lync Server 2013”，然后单击“Lync Server 拓扑生成器”。

2.  在 拓扑生成器中，选择“新建拓扑”。将提示您输入位置和文件名以保存拓扑。为拓扑文件提供一个有意义的名称，并接受默认扩展名 .tbxml。单击“确定”。

3.  导航至要保存新拓扑 XML 文件的位置，为文件输入一个名称，然后单击“保存”。

4.  在“定义主域”页上，为组织输入主 SIP 域的名称，然后单击“下一步”。

5.  在“指定其他支持域”页上，输入其他域的名称（如果有），然后单击“下一步”。

6.  在“定义首个站点”页上，输入首个站点的名称和说明，然后单击“下一步”。

7.  在“指定站点详细信息”页上，输入站点的位置信息，然后单击“下一步”。

8.  在“已成功定义新拓扑”页上，确保已选中“此向导关闭时打开新建前端向导”复选框，然后单击“完成”。

定义并保存拓扑之后，使用新建前端向导为站点定义前端池或 Standard Edition Server。有关详细信息，请参阅 [在 Lync Server 2013 中定义和配置前端池或 Standard Edition 服务器](lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md)。


---
title: 使用拓扑生成器合并向导进行合并
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Merge using Topology Builder Merge wizard
ms:assetid: c3f3c425-dab6-4dcd-bf0e-d7fde05f2ebf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205243(v=OCS.15)
ms:contentKeyID: 48185343
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8578217d5e3b35351937dbf2838e2994e74fb32e
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42148981"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="merge-using-topology-builder-merge-wizard"></a>使用拓扑生成器合并向导进行合并

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-10-02_

1.  使用拓扑生成器下载现有部署。

2.  在“操作”**** 菜单中，选择“合并 Office Communications Server 2007 R2”****。

3.  单击“下一步”****。

4.  在“指定边缘设置”**** 中，单击“添加”****。
    
    ![合并拓扑向导中，指定 "边缘设置" 页](images/JJ205243.cdca609d-d4d5-47d9-9ff8-8b1daa4106e1(OCS.15).jpg "合并拓扑向导中，指定 "边缘设置" 页")  

5.  在“指定边缘类型”**** 中，输入边缘服务器配置的类型，然后单击“下一步”****。此示例使用“单个边缘服务器”**** 选项。
    
    <div>
    

    > [!IMPORTANT]  
    > “扩展边缘部署”<STRONG></STRONG>不是支持的配置。必须先将“扩展边缘服务器”<STRONG></STRONG>转换为“单个边缘服务器”<STRONG></STRONG>或“负载平衡合并边缘”<STRONG></STRONG>服务器。

    
    </div>

6.  在 "**指定内部边缘设置**" 中，根据需要为边缘池的内部 FQDN 和端口输入相关信息，然后单击 "**下一步**"。
    
    !["指定内部边缘设置" 对话框](images/JJ205243.dd664761-839c-4ac8-bd1a-5525589dfbb0(OCS.15).jpg ""指定内部边缘设置" 对话框")  

7.  在“指定外部边缘”**** 中，输入边缘服务器的 Web 会议 FQDN 信息。
    
    <div>
    

    > [!IMPORTANT]  
    > 在单击“下一步”<STRONG></STRONG>之前，先执行该过程的下一步。请务必不要错过此步骤，这一点非常重要。

    
    </div>

8.  如果计划将旧版 Office 通信服务器 2007 R2 边缘服务器用于联盟，请选中 "**此边缘池用于联盟和公用 IM 连接**" 复选框。 如果已部署多台边缘服务器，则将只为其中一台边缘服务器启用联盟。 如果未选中此复选框，但之后决定要启用联盟，则必须运行拓扑生成器合并向导，并再次发布拓扑。
    
    !["边缘服务器" 对话框中，指定外部边缘页面](images/JJ205243.32e97ce5-92f0-477e-8125-5d2ece237b13(OCS.15).jpg ""边缘服务器" 对话框中，指定外部边缘页面")  

9.  在“指定下一跃点”**** 中，输入所在环境中下一跃点位置的完全限定的域名 (FQDN)。 单击“完成”****。
    
    !["边缘服务器" 对话框，"指定下一跃点" 页](images/JJ205243.e734ee0d-f91c-4f3f-8ae6-248ecabcf678(OCS.15).jpg ""边缘服务器" 对话框，"指定下一跃点" 页")  

10. 在 "**指定边缘设置**" 中，如果已添加所有 Office 通信服务器 2007 R2 边缘服务器，请单击 "**下一步**"。 如果要添加更多的 Office 通信服务器 2007 R2 边缘服务器，请从步骤4开始，重复此过程。

11. 在 "**指定内部 SIP 端口**" 中，选择默认设置（即，如果您未修改默认 SIP 端口）。 如果不使用默认端口 5061，则根据需要进行更改，然后单击“下一步”****。

12. 在“摘要”**** 中，单击“下一步”**** 开始合并拓扑。

13. 向导页用于验证拓扑合并是否成功。

14. 在“状态”**** 列中，确认值为“成功”****，然后单击“完成”****。

15. 在拓扑生成器的左窗格中，您现在应该会看到**BackCompatSite**，这表示您的 Office 通信服务器 2007 R2 环境已与 Lync Server 2013 合并。
    
    ![显示合并拓扑的拓扑生成器](images/JJ205243.62751c76-f018-4c6d-bb48-c61ef8974d31(OCS.15).jpg "显示合并拓扑的拓扑生成器")  

16. 从“操作”**** 菜单中，单击“发布拓扑”****，然后单击“下一步”****。

17. “发布向导”**** 完成时，单击“完成”****。
    
    <div>
    

    > [!NOTE]  
    > 请务必填写下一个主题 "<A href="import-policies-and-settings.md">导入策略和设置</A>"，以确保将旧策略设置导入到 Lync Server 2013。

    
    </div>

</div>

<span> </span>

</div>

</div>

</div>


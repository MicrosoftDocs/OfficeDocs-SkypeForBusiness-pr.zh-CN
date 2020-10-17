---
title: Lync Server 2013：创建初始拓扑设计
description: Lync Server 2013：创建初始拓扑设计。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create the initial design
ms:assetid: f3131153-de14-41be-b1e6-7d4bb0191af1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615047(v=OCS.15)
ms:contentKeyID: 51541530
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c91bfe68a1de4a1f9862948edd708b8efa6a5c6d
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48551088"
---
# <a name="create-the-initial-topology-design-for-lync-server-2013"></a>为 Lync Server 2013 创建初始拓扑设计

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2013-02-21_

安装完 Lync Server 2013 （规划工具）后，即可启动规划工具并开始设计建议的 Lync Server 2013 基础结构。

<div>


> [!NOTE]  
> 规划工具是一个向导驱动的工具，其中包含详细指南，可在设计网站和拓扑时向决策过程发出通知。 本主题不是一种详尽的指南，只是为了帮助您在设计会话中开始使用规划工具。



</div>

<div>

## <a name="to-get-started-using-the-planning-tool-and-create-the-initial-design"></a>开始使用规划工具并创建初始设计

1.  启动 Lync Server 2013，规划工具：依次单击 " **开始**"、" **所有程序**"、" **Microsoft Lync Server 2013**" 和 " **规划工具**"。

2.  在规划工具启动之后，将显示 " **欢迎使用 Microsoft Lync Server 2013 的规划工具** " 页。 选择下列选项之一以开始您的设计：
    
      - **选项1：入门**    单击 "**入门**" 提供了一系列针对相关选择的调查问题，以定义条件。 完成最初的 " **开始** 访谈" 部分之后，您将继续 **设计网站** 以定义网站体系结构。 若要完成此选项，请继续执行步骤3。
    
      - **选项2：设计网站**    单击 "欢迎" 页面上的 "**设计网站**" 可绕过 "**入门**" 部分中介绍的访谈问题。 通过响应 " **入门** " 部分中的 "会见问题" 部分收集的信息将使用此选项设置为 "默认值"。 通过单击 " **设计网站**"，经验丰富的设计人员可以绕过初始访谈，并根据需要在 " **中心网站** 起始页" 上更改默认值。 若要完成此选项，请跳过步骤3-5 并从步骤6开始。
    
      - **选项3：显示已保存的拓扑**    如果已通过以前使用规划工具完成并保存了拓扑，则可以跳过这些步骤，并首先打开并显示拓扑。 您还可以对拓扑进行更改和更新，重新保存它，然后将其导出到 Microsoft Excel 或 Microsoft Visio。 若要完成此选项，请跳过步骤3-12 并从步骤13开始。

3.  单击 " **开始** " 开始设计 Lync Server 2013 拓扑。

4.  通过为设计选择相应的条件回答每部分的问题，然后单击 **“下一步”** 继续进入下一个向导页。 单击 " **上一步** "，在以前的页面上进行更改。
    
    <div>
    

    > [!TIP]  
    > 每个页面中都有对选择条件的说明以及基于首选做法和容量规划给出的建议。 如果需要更多详细信息，请单击 Microsoft TechNet 网站上的 " <STRONG>了解详细</STRONG> 信息"，以阅读 Lync Server 2013 规划文档中的详细信息。 要访问 Microsoft TechNet 网站，必须具有 Internet 连接。

    
    </div>

5.  为设计选择适当的选项。 定义初始条件后，会出现一个页面，确认“功能概述”已完成。

6.  单击 " **设计网站** " 以定义您的中心网站。
    
    <div>
    

    > [!NOTE]  
    > 每个 Lync Server 2013 拓扑都至少有一个中央站点。 您的设计可能有一个中央站点、一个包含多个分支站点的中央站点、多个中央站点，或者具有与每个中心站点相关联的分支站点的多个中央站点。

    
    </div>

7.  在 " **网站名称**" 中，键入将标识此中心网站的名称。

8.  在 " **网站托管用户**" 中，键入将驻留在此中央站点中的本地并发用户的预期数量。

9.  在 " **云托管用户**" 中，键入将托管在此中央站点中的联机并发用户的预期数量。

10. 根据需要修改联机协作、用户、语音、其他部署选项或服务器应用程序的选择。
    
    <div>
    

    > [!IMPORTANT]  
    > 在设计的这一时刻，只能选择或清除部署的选项。 但是，您可以在规划工具的后续阶段中配置更多选项。 还有一些选项不可用且无法清除。 此外，可能必须先清除一个选项后才能清除另一个。 例如，如果清除 "语音" 下的 " <STRONG>企业语音</STRONG> " 选项，则 "服务器应用程序" 下的 " <STRONG>响应组</STRONG>"、" <STRONG>通知</STRONG>" 和 " <STRONG>呼叫寄存</STRONG> " 选项也会被清除 (企业语音) 的功能。

    
    </div>

11. 定义站点名称和用户数量后，单击 **“下一步”**。

12. 以下页面要求提供有关 SIP 域、会议设置、语音设置和基础结构、Exchange UM、外部用户访问、持久聊天设置、客户端设置、并置选项和分支站点的信息。 根据需要回答这些问题。

13. 最后一个问题询问您是否要创建另一个中心站点。 如果选择 **"是**"，则规划工具将返回到 "中央站点" 页面。 如果选择 " **否**"，请单击 " **下一步**"，然后单击 " **绘图** " 显示高级别全局拓扑视图。

14. 若要查看现有拓扑，请单击 " **显示**"。

15. 单击代表之前保存的拓扑的 .xml 文件，然后单击 **“打开”**。

16. 规划工具将显示 "全局拓扑" 页面。 您现在可以使用规划工具中提供的工具开始编辑、更新或更改拓扑。

</div>

<div>

## <a name="see-also"></a>另请参阅


[在 Lync Server 2013 中编辑设计](lync-server-2013-editing-the-design.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


---
title: Lync Server 2013：修改语音路由
description: Lync Server 2013：修改语音路由。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Modify a voice route
ms:assetid: afc562cc-8807-489b-8850-dbbe1c1ab9f5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412838(v=OCS.15)
ms:contentKeyID: 48185143
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0aa507f3d0f459dd200b9c772f3a330d7da36197
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48546408"
---
# <a name="modify-a-voice-route-in-lync-server-2013"></a>在 Lync Server 2013 中修改语音路由

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-11-01_

本主题介绍如何编辑语音路由。 若要创建新的路由，请参阅 [在 Lync Server 2013 中创建语音路由](lync-server-2013-create-a-voice-route.md)。

<div>

## <a name="to-modify-a-voice-route"></a>修改语音路由

1.  以 RTCUniversalServerAdmins 组成员的身份或者以 CsVoiceAdministrator、CsServerAdministrator 或 CsAdministrator 角色成员的身份登录计算机。 有关详细信息，请参阅 [Lync Server 2013 中的委派安装权限](lync-server-2013-delegate-setup-permissions.md)。

2.  打开浏览器窗口，然后输入管理员 URL 以打开 "Lync Server 控制面板"。 有关可用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅 [Open Lync server 2013 "管理工具](lync-server-2013-open-lync-server-administrative-tools.md)"。

3.  在左侧导航栏中，单击“语音路由”****，然后单击“路由”****。

4.  在 **“路由”** 页上，使用以下任意一种方式修改语音路由：
    
      - 单击语音路由名称，再单击 **“编辑”**，然后单击 **“显示详细信息”**。
    
      - 单击语音路由名称，再单击 **“编辑”**、**“复制”**，然后单击 **“粘贴”**。单击刚创建的新语音路由副本，再单击 **“编辑”**，然后单击 **“显示详细信息”**。

5.  在 **“编辑语音路由”** 页上的 **“名称”** 字段中，为语音路由键入一个描述性名称。

6.  （可选）在 **“说明”** 字段中，为语音路由键入其他描述性信息。

7.  要指定希望此路由满足的模式，可以使用 **“建立匹配的模式”** 工具生成正则表达式，或手动写入正则表达式。
    
      - 要使用 **“建立匹配的模式”** 工具生成正则表达式，请按如下所示输入值。可以指定两种匹配的模式类型：
        
          - **要允许的数字的起始数字：** 输入此路由必须满足的前缀值 (包括前导 + （如果需要）) 。 例如，键入 **+425**，然后单击 **“添加”**。 对希望包含在路由中的每个前缀值重复此过程。
        
          - **异常：** 如果要为前缀值指定一个或多个例外，请突出显示前缀并单击 " **例外**"。 为不** 希望此路由满足的匹配模式键入一个或多个值。 例如，若要从路由中排除从 + 425237 开始的号码，请在 "**例外日期**" 字段中输入值 **+ 425237** ，然后单击 **"确定"**。
    
      - 若要手动定义匹配模式，请在“构建要匹配的模式”**** 工具中单击“编辑”****，然后键入 .NET Framework 正则表达式，以便为应用路由的目标电话号码指定匹配模式。 有关如何编写正则表达式的信息，请参阅处的 ".NET Framework 正则表达式" [https://go.microsoft.com/fwlink/p/?linkId=140927](https://go.microsoft.com/fwlink/p/?linkid=140927) 。

8.  如果不希望让出站呼叫显示给呼叫收件人的电话的 ID，请选择 " **禁止呼叫方 id** "。 如果选择此选项，必须指定显示在接收人的呼叫者 ID 显示器上的 **“备用呼叫者 ID”**。

9.  若要将一个或多个公开交换的电话网络 (PSTN) 中继与语音路由相关联，请单击 " **添加**"，然后从列表中选择一个中继。
    
    <div>
    

    > [!NOTE]  
    > 如果您的部署包含任何 Microsoft Office 通信服务器 2007 R2 中介服务器，则这些服务器也将在列表中可用。

    
    </div>

10. 若要将一个或多个 PSTN 用法与语音路由相关联，请单击 " **选择** "，然后从已为您的企业语音部署定义的 PSTN 用法记录列表中选择一个记录。
    
    <div>
    

    > [!NOTE]  
    > 若要查看每个可用 PSTN 用法记录的属性，请参阅 <A href="lync-server-2013-view-pstn-usage-records.md">在 Lync Server 2013 中查看 PSTN 用法记录</A>。<BR>若要创建或编辑 PSTN 用法记录，请参阅 <A href="lync-server-2013-create-a-voice-policy-and-configure-pstn-usage-records.md">在 Lync server 2013 中创建语音策略和配置 pstn 用法记录</A> 或 <A href="lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md">在 lync Server 2013 中修改语音策略和配置 pstn 用法记录</A>。

    
    </div>

11. 排列 PSTN 用法记录以获得最佳性能。要更改记录在列表中的位置，请突出显示相应的记录名称，然后单击向上箭头或向下箭头。
    
    <div>
    

    > [!NOTE]  
    > 与语音策略（其中列出了 PSTN 用法记录的顺序非常重要）相反，语音路由中的 PSTN 用法记录的顺序是无关紧要的。 但是，我们建议您按使用频率组织列表，例如： RedmondLocal、RedmondLongDist、RedmondInternational、RedmondBackup。  (Lync Server 从上到下遍历列表。 ) 

    
    </div>

12. （可选）在 **“输入转换后的号码以进行测试”** 字段中键入一个值，然后单击 **“执行”**。测试结果将显示在该字段下面。
    
    <div>
    

    > [!NOTE]  
    > 您可以保存尚未通过测试的语音路由，并在稍后对其进行重新配置。 有关详细信息，请参阅 <A href="lync-server-2013-test-voice-routing.md">在 Lync Server 2013 中测试语音路由</A>。

    
    </div>

13. 单击 **“确定”**。

14. 在 **“路由”** 页上，单击 **“提交”**，然后单击 **“全部提交”**。
    
    <div>
    

    > [!NOTE]  
    > 无论何时创建或修改语音路由，都必须运行 " <STRONG>全部提交</STRONG> " 命令以发布配置更改。 有关详细信息，请参阅操作文档中的在 <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Lync Server 2013 中发布待处理的语音路由配置的更改</A> 。

    
    </div>

</div>

<div>

## <a name="see-also"></a>另请参阅


[在 Lync Server 2013 中创建语音路由](lync-server-2013-create-a-voice-route.md)  
[在 Lync Server 2013 中查看 PSTN 用法记录](lync-server-2013-view-pstn-usage-records.md)  
[在 Lync Server 2013 中创建语音策略和配置 PSTN 用法记录](lync-server-2013-create-a-voice-policy-and-configure-pstn-usage-records.md)  
[在 Lync Server 2013 中修改语音策略和配置 PSTN 用法记录](lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md)  
[在 Lync Server 2013 中发布对语音路由配置所做的挂起更改](lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md)  


[在 Lync Server 2013 中测试语音路由](lync-server-2013-test-voice-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


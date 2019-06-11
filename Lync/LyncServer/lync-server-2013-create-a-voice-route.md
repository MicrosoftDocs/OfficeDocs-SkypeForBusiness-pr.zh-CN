---
title: 'Lync Server 2013: 创建语音路由'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create a voice route
ms:assetid: d189057d-cc9d-4622-9d10-f5385d703faf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398898(v=OCS.15)
ms:contentKeyID: 48185438
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fe4c6a9492cbbecafff95a1f6e626087e79f62d0
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34837073"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-a-voice-route-in-lync-server-2013"></a>在 Lync Server 2013 中创建语音路由

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2012-11-01_

以下过程介绍了如何使用 Lync Server 2013 控制面板创建新的语音路由。 若要编辑现有路线, 请参阅[在 Lync Server 2013 中为过程修改语音路由](lync-server-2013-modify-a-voice-route.md)。

<div>

## <a name="to-create-a-voice-route-by-using-the-lync-server-control-panel"></a>使用 Lync Server "控制面板" 创建语音路由

1.  以 RTCUniversalServerAdmins 组成员或者 **CsVoiceAdministrator**、**CsServerAdministrator** 或 **CsAdministrator** 管理角色成员的身份登录计算机。

2.  打开一个浏览器窗口, 然后输入 "管理员" URL 以打开 Lync Server "控制面板"。 有关可用于启动 Lync Server "控制面板" 的不同方法的详细信息, 请参阅[打开 Lync server 2013 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左侧导航栏中，单击“语音路由”****。

4.  单击“路由”****。

5.  单击“新建”**** 以显示“新建语音路由”**** 对话框。

6.  在“名称”**** 中，键入语音路由的描述性名称。

7.  （可选）在“说明”**** 中，为语音路由键入其他描述性信息。

8.  要指定希望此路由满足的模式，可以使用“建立匹配的模式”**** 工具生成正则表达式，或手动写入正则表达式。
    
      - 要使用“建立匹配的模式”**** 工具生成正则表达式，请按如下所示输入值。可以指定两种匹配的模式类型：
        
          - **要允许的数字的起始位数:** 输入此路线必须容纳的前缀值 (包括前导 + (如果需要)。 例如，键入 **+425**，然后单击“添加”****。 对希望包含在路由中的每个前缀值重复此过程。
        
          - **例外:** 如果要为前缀值指定一个或多个例外, 请突出显示前缀, 然后单击 "**例外**"。 为 *不*希望此路由满足的匹配模式键入一个或多个值。 例如，要从路由中排除以 +425237 开头的号码，请在“例外”**** 字段中输入值 **+425237**，然后单击“确定”****。
    
      - 若要手动定义匹配模式，请在“构建要匹配的模式”**** 工具中单击“编辑” ****，然后键入 .NET Framework 正则表达式，以便为应用路由的目标电话号码指定匹配模式。 有关如何编写正则表达式的详细信息, 请参阅的[http://go.microsoft.com/fwlink/p/?linkId=140927](http://go.microsoft.com/fwlink/p/?linkid=140927)".Net Framework 正则表达式"。

9.  如果不希望对呼叫接收人显示发起出站呼叫的电话的 ID，请选择“隐藏呼叫者 ID”****。如果选择此选项，必须指定显示在接收人的呼叫者 ID 显示器上的“备用呼叫者 ID”****。

10. 要将一个或多个中继与语音路由相关联，请单击“添加”****，然后从列表中选择中继。
    
    <div>
    

    > [!NOTE]  
    > 如果你的部署包含任何 Microsoft Office 通信服务器 2007 R2 中介服务器, 则这些服务器也将在列表中可用。

    
    </div>

11. 若要将一个或多个公共交换电话网络 (PSTN) 用途与语音路由相关联, 请单击 "**选择**", 然后从已为你的企业语音部署定义的 PSTN 使用记录列表中选择一条记录。
    
    <div>
    

    > [!NOTE]  
    > 若要查看每个可用 PSTN 使用记录的属性, 请参阅<A href="lync-server-2013-view-pstn-usage-records.md">在 Lync Server 2013 中查看 PSTN 使用情况记录</A>。<BR>若要创建或编辑 PSTN 使用记录, 请参阅<A href="lync-server-2013-create-a-voice-policy-and-configure-pstn-usage-records.md">在 Lync server 2013 中创建语音策略和配置 pstn 使用记录</A>或<A href="lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md">在 lync Server 2013 中修改语音策略和配置 pstn 使用记录</A>。

    
    </div>

12. 排列 PSTN 用法记录以获得最佳性能。要更改记录在列表中的位置，请突出显示相应的记录名称，然后单击向上箭头或向下箭头。
    
    <div>
    

    > [!NOTE]  
    > 在语音策略中，PSTN 用法记录的列出顺序非常重要，而在语音路由中，PSTN 用法记录的列出顺序则无关紧要。 但是，建议您按使用频率来组织该列表，例如：RedmondLocal、RedmondLongDist、RedmondInternational 和 RedmondBackup。 （skype16_server_short 按照从上到下的顺序遍历该列表。 (Lync Server 从上到下遍历列表。)

    
    </div>

13. （可选）在“输入转换后的号码以进行测试”**** 字段中键入一个值，然后单击“执行”****。测试结果将显示在该字段下面。
    
    <div>
    

    > [!NOTE]  
    > 你可以保存尚未通过测试的语音路由, 然后稍后重新配置它。 有关详细信息, 请参阅<A href="lync-server-2013-test-voice-routing.md">在 Lync Server 2013 中测试语音路由</A>。

    
    </div>

14. 单击“确定”**** 保存语音路由。

<div>


> [!IMPORTANT]  
> 任何时候创建语音路由，都必须运行“全部提交”<STRONG></STRONG>命令以发布配置更改。 有关详细信息, 请参阅<A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">在 Lync Server 2013 中将挂起的更改发布到语音路由配置</A>。



</div>

</div>

<div>

## <a name="see-also"></a>另请参阅


[在 Lync Server 2013 中修改语音路由](lync-server-2013-modify-a-voice-route.md)  
[在 Lync Server 2013 中查看 PSTN 使用记录](lync-server-2013-view-pstn-usage-records.md)  
[在 Lync Server 2013 中创建语音策略和配置 PSTN 使用记录](lync-server-2013-create-a-voice-policy-and-configure-pstn-usage-records.md)  
[在 Lync Server 2013 中修改语音策略和配置 PSTN 使用记录](lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md)  
[将挂起的更改发布到 Lync Server 2013 中的语音路由配置](lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md)  


[在 Lync Server 2013 中测试语音路由](lync-server-2013-test-voice-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>


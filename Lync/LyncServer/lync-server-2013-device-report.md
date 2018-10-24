---
title: Lync Server 2013：设备报告
TOCTitle: 设备报告
ms:assetid: f42e4d60-699b-4870-8bb5-13b51bb6eb2b
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg615049(v=OCS.15)
ms:contentKeyID: 49314738
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 中的设备报告

 

_**上一次修改主题：** 2015-03-09_

设备报告可能更好地为麦克风和扬声器报告加了标题；这是因为，该设备报告检索按呼叫中使用的麦克风和扬声器分组的呼叫相关的指标（例如，质量欠佳的呼叫百分比、回声和语音切换时间）。如果您对 IP 电话（通常另指“设备”）感兴趣，请改用 [Lync Server 2013 中的 IP 电话清单报告](lync-server-2013-ip-phone-inventory-report.md)。

该设备报告在管理员确定特定类型的设备遇到的质量欠佳的呼叫量是否高于其他呼叫时极其有用。转而，这会对即将购买新设备或替换现有设备时所做的任何决策产生影响。

默认情况下，设备报告中显示的信息也基于该呼叫中使用的麦克风（捕获设备）和扬声器/耳麦（呈现设备）。例如，假定您有多个使用下列捕获设备和下列呈现设备的用户：

  - 捕获设备 - 麦克风（SoundMAX 集成的数字 HD 音频）

  - 呈现设备 - 头戴式耳机 (Microsoft LifeChat LX-3000)

如果这些用户进行了总共 254 次呼叫，则您将在此报告中看到此类似条目：


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>捕获设备</th>
<th>呈现设备</th>
<th>呼叫量</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>麦克风（SoundMAX 集成数字 HD 音频）</p></td>
<td><p>头戴式耳机 (Microsoft LifeChat LX-3000)</p></td>
<td><p>254</p></td>
</tr>
</tbody>
</table>


现在，假定您有一些使用相同捕获设备但不同的呈现设备的用户。在这种情况下，您在报告中将有第二行的条目，一行用于捕获设备和呈现设备的唯一组合：


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>捕获设备</th>
<th>呈现设备</th>
<th>呼叫量</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>麦克风（SoundMAX 集成数字 HD 音频）</p></td>
<td><p>头戴式耳机 (Microsoft LifeChat LX-3000)</p></td>
<td><p>254</p></td>
</tr>
<tr class="even">
<td><p>麦克风（SoundMAX 集成数字 HD 音频）</p></td>
<td><p>扬声器（SoundMAX 集成数字 HD 音频）</p></td>
<td><p>319</p></td>
</tr>
</tbody>
</table>


如果您更想看到给定设备（例如，对于 SoundMAX 捕获设备，与使用的呈现设备无关）的合并总数，从设备类型下拉列表（捕获设备或呈现设备）选择相应的选项。如果在此示例中选择捕获设备，将会为您提供类似以下输出：


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>捕获设备</th>
<th>呼叫量</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>麦克风（SoundMAX 集成数字 HD 音频）</p></td>
<td><p>573</p></td>
</tr>
</tbody>
</table>


## 访问设备报告

通常可从监控报告主页访问该设备报告。但是，如果您在查看 [Lync Server 2013 中的呼叫详情报告](lync-server-2013-call-detail-report.md)，则可以通过单击下列任何指标深入到特定设备的设备报告：

  - 捕获设备

  - 呈现设备

从该设备报告，您可通过单击下列任何指标深入到 [Lync Server 2013 中的呼叫列表报告](lync-server-2013-call-list-report.md)：

  - 呼叫量

  - 质量欠佳的呼叫百分比

## 充分利用设备报告

当涉及到设备名称时，设备报告会进行极其详细的描述；例如，假定您有下列捕获设备：

  - Aastra 3002 麦克风 (2- Aastra 3002)

  - Aastra 3002 麦克风 (3- Aastra 3002)

  - Aastra 3002 麦克风 (Aastra 3002)

  - Aastra 6725ip

  - Aastra 6725ip 麦克风 (10- Aastra 6725ip)

  - Aastra 6725ip 麦克风 (10- Aastra 6725ip)-V0

  - Aastra 6725ip 麦克风 (2- Aastra 6725ip)

  - Aastra 6725ip 麦克风 (3- Aastra 6725ip)

  - Aastra 6725ip 麦克风 (4- Aastra 6725ip)

  - Aastra 6725ip 麦克风 (5- Aastra 6725ip)

  - Aastra 6725ip 麦克风 (6- Aastra 6725ip)

  - Aastra 6725ip 麦克风 (7- Aastra 6725ip)

  - Aastra 6725ip 麦克风 (9- Aastra 6725ip)

  - Aastra 6725ip 麦克风 (9- Aastra 6725ip)-V0

  - Aastra 6725ip 麦克风 (Aastra 6725ip)

  - Aastra 6725ip 麦克风 (Aastra 6725ip)-V0

  - Aastra 6725ip 麦克风（USB 音频设备）

  - Aastra 6725ip 麦克风（USB 音频设备）-V0

> [!NOTE]  
> 请记住，如果您运行的是 Lync Server 2013 的已本地化版本，捕获设备的名称可能不相同。美国英语中名为 Aastra 6725ip 麦克风 (Aastra 6725ip)-V0 的设备在法语和西班牙语中可能会有不同的名称。



很多时候，您想拥有该级别的详细信息；但在其他时候，您可能仅对多少呼叫在使用普通的 Aastra 麦克风感兴趣，而与型号无关。获得类似此信息的一个方法是将设备报告数据导出到 Microsoft Excel，然后将此数据保存到以逗号分隔的值文件（例如，C:\\Data\\Devices\_Report.csv）中。然后使用一组类似这些的命令，将 .CSV 文件导入到 Windows PowerShell 中，并报告回使用 Aastra 捕获设备所做的呼叫总数：

    $devices = Import-Csv "C:\Data\Device_Report.csv
    $sum = $devices | Where-Object {$_."Capture device" -match "Aastra"}
    $sum | foreach-object {[Int]$x = [Int]$x + [Int]$_."call volume"}
    $x

这将返回使代表用 Aastra 捕获设备执行的呼叫总数的单个值。例如：

    384

## 筛选器

利用筛选器，您可以返回一组针对性更强的数据或通过不同的方式查看返回的数据。例如，通过设备报告，您可以对诸如呼叫类型（即，该呼叫是否为客户端呼叫）的内容、电话会议或公用电话交换网 (PSTN) 呼叫进行筛选。您还可以选择数据的分组方式。在此示例中，将按小时、日、周或月对设备进行分组。

下表列出了可用于设备报告的筛选器。

### 设备报告筛选器

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>名称</th>
<th>说明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>开始日期</strong></p></td>
<td><p>时间范围的开始日期/时间。若要按小时查看数据，请输入开始日期和时间，如下所示：</p>
<p>7/7/2012 1:00 PM</p>
<p>如果您未输入开始时间，该报告会自动将某个特定日的上午 12:00 作为开始时间。若要按日查看数据，请只输入日期：</p>
<p>7/7/2012</p>
<p>若要按周或按月查看，请输入您要查看的周或月中的任一日期（您不必输入周或月的第一天）：</p>
<p>7/3/2012</p>
<p>一周始终是从星期日开始至星期六结束。</p></td>
</tr>
<tr class="even">
<td><p><strong>结束日期</strong></p></td>
<td><p>时间范围的结束日期/时间。若要按小时查看数据，请输入结束日期和时间，如下所示：</p>
<p>7/7/2012 1:00 PM</p>
<p>如果您未输入结束时间，该报告会自动将某个特定日的上午 12:00 作为结束时间。若要按日查看数据，请只输入日期：</p>
<p>7/7/2012</p>
<p>若要按周或按月查看，请输入您要查看的周或月中的任一日期（您不必输入周或月的第一天）：</p>
<p>7/3/2012</p>
<p>一周始终是从星期日开始至星期六结束。</p></td>
</tr>
<tr class="odd">
<td><p><strong>语音切换原因</strong></p></td>
<td><p>呼叫必须切换为半双工模式才能防止回声的原因。在半双工模式中，通信一次只能在一个方向进行，与用户在使用对讲机进行通信时的轮流方式相似。选择下列选项之一：</p>
<dl>
<dd><p>[所有]</p>
</dd>
<dd><p>无</p>
</dd>
<dd><p>错误的时间戳</p>
</dd>
<dd><p>回声</p>
</dd>
<dd><p>DNLP（动态非线性处理器）</p>
</dd>
<dd><p>复杂度低</p>
</dd>
<dd><p>设备状态差</p>
</dd>
<dd><p>AEC 后的回声（回声抑制）</p>
</dd>
</dl></td>
</tr>
<tr class="even">
<td><p><strong>回声原因</strong></p></td>
<td><p>在呼叫中检测到超出接受水平的回声的原因。（在长途通讯中，回声是声音的反射，与朝井底大喊时出现的现象一样。）选择下列选项之一：</p>
<dl>
<dd><p>[所有]</p>
</dd>
<dd><p>无</p>
</dd>
<dd><p>错误的时间戳</p>
</dd>
<dd><p>AEC 后的回声（回声抑制）</p>
</dd>
<dd><p>ANLP（自适应非线性处理器）</p>
</dd>
<dd><p>DNLP（动态非线性处理器）</p>
</dd>
<dd><p>麦克风剪辑</p>
</dd>
</dl></td>
</tr>
<tr class="odd">
<td><p><strong>呼叫类型</strong></p></td>
<td><p>指示发起的呼叫类型。选择下列选项之一：</p>
<dl>
<dd><p>[所有]</p>
</dd>
<dd><p>客户端呼叫</p>
</dd>
<dd><p>PSTN 呼叫</p>
</dd>
<dd><p>电话会议</p>
</dd>
</dl></td>
</tr>
<tr class="even">
<td><p><strong>访问类型</strong></p></td>
<td><p>指示客户端在发起呼叫时已登录到内部网络还是外部网络。选择下列选项之一：</p>
<dl>
<dd><p>[所有]</p>
</dd>
<dd><p>内部</p>
</dd>
<dd><p>外部</p>
</dd>
</dl></td>
</tr>
<tr class="odd">
<td><p><strong>网络类型</strong></p></td>
<td><p>指示客户端在发起呼叫时已连接到的网络的类型。选择下列选项之一：</p>
<dl>
<dd><p>[所有]</p>
</dd>
<dd><p>有线</p>
</dd>
<dd><p>无线</p>
</dd>
</dl></td>
</tr>
<tr class="even">
<td><p><strong>VPN</strong></p></td>
<td><p>指示外部客户端在发起呼叫时是否使用了虚拟专用网 (VPN) 连接。选择下列选项之一：</p>
<dl>
<dd><p>[所有]</p>
</dd>
<dd><p>VPN</p>
</dd>
<dd><p>非 VPN</p>
</dd>
</dl></td>
</tr>
<tr class="odd">
<td><p><strong>设备类型</strong></p></td>
<td><p>指示设备的类型。选择下列选项之一：</p>
<dl>
<dd><p>捕获设备</p>
</dd>
<dd><p>呈现设备</p>
</dd>
<dd><p>捕获/呈现设备</p>
</dd>
</dl></td>
</tr>
<tr class="even">
<td><p><strong>设备名称</strong></p></td>
<td><p>捕获或呈现设备的名称。您可以输入完整设备名称，也可以输入设备名称的任何部分。例如，若要查找设备麦克风 (Microsoft LifeCam VX-1000.)，可输入完整设备名称，如下所示：</p>
<p>麦克风 (Microsoft LifeCam VX-1000.)</p>
<p>或者，可只输入该名称的一部分。例如：</p>
<p>LifeCam</p>
<p>注意，上述筛选器返回在其名称中的任何位置包含字符串“LifeCam”的任何设备。</p></td>
</tr>
</tbody>
</table>


## 指标

下表列出了设备报告中提供的信息。

### 设备报告度量

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>名称</th>
<th>是否可按此项排序？</th>
<th>说明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>捕获设备</strong></p></td>
<td><p>是</p></td>
<td><p>用于传输音频的设备（例如麦克风或网络摄像机）。</p></td>
</tr>
<tr class="even">
<td><p><strong>呈现设备</strong></p></td>
<td><p>是</p></td>
<td><p>用于接收音频的设备（例如耳机或扬声器）。</p></td>
</tr>
<tr class="odd">
<td><p><strong>呼叫量</strong></p></td>
<td><p>是</p></td>
<td><p>发起的呼叫总数。</p></td>
</tr>
<tr class="even">
<td><p><strong>质量欠佳的呼叫百分比</strong></p></td>
<td><p>是</p></td>
<td><p>归类为“质量欠佳”的呼叫的百分比。质量欠佳的呼叫是指至少一项测量指标超过允许值的任何呼叫（例如，信号极不稳定的呼叫）。</p></td>
</tr>
<tr class="odd">
<td><p><strong>唯一用户数</strong></p></td>
<td><p>是</p></td>
<td><p>使用过该设备的唯一用户。如果某用户使用该设备 13 次，他（她）也被计为一个唯一用户，与使用该设备一次的用户相同。</p></td>
</tr>
<tr class="even">
<td><p><strong>语音切换时间比率</strong></p></td>
<td><p>是</p></td>
<td><p>必须在半双工模式中执行的用于防止回声的呼叫百分比。在半双工模式中，通信一次只能在一个方向进行，与用户在使用对讲机进行通信时的轮流方式相似。</p></td>
</tr>
<tr class="odd">
<td><p><strong>麦克风无法正常工作的比率</strong></p></td>
<td><p>是</p></td>
<td><p>捕获设备未在可接受水平运行的呼叫的百分比。这些值高表示呼叫的质量问题主要是由于捕获设备未按预期正常运行造成的。</p></td>
</tr>
<tr class="even">
<td><p><strong>扬声器无法正常工作的比率</strong></p></td>
<td><p>是</p></td>
<td><p>呈现设备未在可接受水平运行的呼叫的百分比。这些值高表示呼叫的质量问题主要是由于呈现设备未按预期正常运行造成的。</p></td>
</tr>
<tr class="odd">
<td><p><strong>具有语音切换的呼叫(%)</strong></p></td>
<td><p>是</p></td>
<td><p>必须在半双工模式中拨打的总呼叫数的百分比。在半双工模式中，通信一次只能在一个方向进行，与用户在使用对讲机进行通信时的轮流方式相似。</p></td>
</tr>
<tr class="even">
<td><p><strong>麦克风回声(%)</strong></p></td>
<td><p>是</p></td>
<td><p>在麦克风捕获流量中检测回声时的时间百分比。通常，对于耳机或话筒，值较低，而对于扬声器电话或独立扬声器，值较高。对于支持板载声学回声消除的设备，高值表示回声泄漏。对于其他设备，不应使用此指标评估设备质量。</p></td>
</tr>
<tr class="odd">
<td><p><strong>回声发送(%)</strong></p></td>
<td><p>是</p></td>
<td><p>传输到其他用户的回声的百分比。</p></td>
</tr>
<tr class="even">
<td><p><strong>具有回声的呼叫(%)</strong></p></td>
<td><p>是</p></td>
<td><p>回声超出可接受水平的总呼叫数的百分比。</p>
<p></p></td>
</tr>
</tbody>
</table>


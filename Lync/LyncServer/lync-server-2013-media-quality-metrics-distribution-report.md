---
title: 媒体质量标准分发报告
TOCTitle: 媒体质量标准分发报告
ms:assetid: d07996e6-b0a5-4ff8-9512-ab707762b4e2
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ205262(v=OCS.15)
ms:contentKeyID: 49314313
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 媒体质量标准分发报告

 

_**上一次修改主题：** 2015-03-09_

通过媒体质量指标分布报告可以查看显示用户体验质量指标（如抖动或数据包丢失）分布值的图形。例如，假设您的用户总共进行 10 次电话呼叫；这 10 次呼叫报告以下往返时间：


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>呼叫编号</th>
<th>往返时间（毫秒）</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>1</p></td>
<td><p>50</p></td>
</tr>
<tr class="even">
<td><p>2</p></td>
<td><p>50</p></td>
</tr>
<tr class="odd">
<td><p>3</p></td>
<td><p>50</p></td>
</tr>
<tr class="even">
<td><p>4</p></td>
<td><p>50</p></td>
</tr>
<tr class="odd">
<td><p>5</p></td>
<td><p>50</p></td>
</tr>
<tr class="even">
<td><p>6</p></td>
<td><p>50</p></td>
</tr>
<tr class="odd">
<td><p>7</p></td>
<td><p>50</p></td>
</tr>
<tr class="even">
<td><p>8</p></td>
<td><p>4550</p></td>
</tr>
<tr class="odd">
<td><p>9</p></td>
<td><p>50</p></td>
</tr>
<tr class="even">
<td><p>10</p></td>
<td><p>50</p></td>
</tr>
</tbody>
</table>


这些往返时间的平均值为 500 毫秒（5000 除以 10）。500 毫秒是非常大的往返时间；因此，您可能会相信您遇到了严重的网络拥塞问题。（往返时间长通常是网络过载的结果。）

当然，实际上 90% 的呼叫有良好的往返时间；仅仅有一次呼叫不佳歪曲了整体结果。如果仅看平均往返时间，可能会得出非常错误的结论。

媒体质量指标分布报告可显示指定指标（如往返时间）的图形分布，帮助您避免得出错误结论。这些图形有助于清楚表明有 9 次非常好的呼叫而只有 1 次非常不良的呼叫。无可否认地，您可能仍然想进一步调查那一次呼叫；但是，10 次呼叫中有 9 次非常好，表明没有理由对网络进行任何重大更改，至少此时不应更改。

## 筛选器

利用筛选器，您可以返回一组针对性更强的数据或通过不同的方式查看返回的数据。下表列出了可用于媒体质量指标分布报告的筛选器。

### 媒体质量指标分布报告筛选器

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
<td><p><strong>开始时间</strong></p></td>
<td><p>时间范围的开始时间/日期。若要按小时查看数据，请输入开始日期和时间，如下所示：</p>
<p>7/7/2012 1:00 PM</p>
<p>如果您未输入开始时间，该报告会自动将某个特定日的上午 12:00 作为开始时间。若要按日查看数据，请只输入日期：</p>
<p>7/7/2012</p>
<p>若要按周或按月查看，请输入您要查看的周或月中的任一日期（您不必输入周或月的第一天）：</p>
<p>7/3/2012</p>
<p>一周始终是从星期日开始至星期六结束。</p></td>
</tr>
<tr class="even">
<td><p><strong>结束时间</strong></p></td>
<td><p>时间范围的结束日期/时间. 若要按小时查看数据，请输入结束日期和时间，如下所示：</p>
<p>7/7/2012 1:00 PM</p>
<p>如果您未输入结束时间，该报告会自动将某个特定日的上午 12:00 作为结束时间。 若要按日查看数据，请只输入日期：</p>
<p>7/7/2012</p>
<p>若要按周或按月查看，请输入您要查看的周或月中的任一日期（您不必输入周或月的第一天）：</p>
<p>7/3/2012</p>
<p>一周始终是从星期日开始至星期六结束。</p></td>
</tr>
<tr class="odd">
<td><p><strong>x 轴中的最小值</strong></p></td>
<td><p>要在图形 X 轴上显示的最小值。</p></td>
</tr>
<tr class="even">
<td><p><strong>x 轴中的最大值</strong></p></td>
<td><p>要在图形 X 轴上显示的最大值。</p></td>
</tr>
<tr class="odd">
<td><p><strong>访问类型</strong></p></td>
<td><p>指示客户端在发起呼叫时已登录到内部网络还是外部网络。选择下列选项之一：</p>
<ul>
<li><p>[所有]</p></li>
<li><p>内部</p></li>
<li><p>外部</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>VPN</strong></p></td>
<td><p>指示外部客户端在发起呼叫时是否使用了虚拟专用网 (VPN) 连接。选择下列选项之一：</p>
<ul>
<li><p>[所有]</p></li>
<li><p>VPN</p></li>
<li><p>非 VPN</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><strong>网络类型</strong></p></td>
<td><p>指示客户端在发起呼叫时已连接到的网络的类型。选择下列选项之一：</p>
<ul>
<li><p>[所有]</p></li>
<li><p>有线</p></li>
<li><p>无线</p></li>
</ul></td>
</tr>
</tbody>
</table>


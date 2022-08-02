---
title: 了解见解阅读进度建议
author: DaniEASmith
ms.author: danismith
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: karsmith
description: 了解如何在阅读进度中使用 Insights 数据来帮助提高学生的阅读能力。
search.appverid: MET150
ms.collection:
- M365-collaboration
- m365initiative-edu
appliesto:
- Microsoft Teams
ms.openlocfilehash: 30a98c9ccda13635a6c3fccaae41e8869b8cfce5
ms.sourcegitcommit: 07761c26b53d92fc36b82cab7b3e38a6de4ff945
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/02/2022
ms.locfileid: "67157871"
---
# <a name="understand-insights-for-reading-progress-recommendations"></a>了解见解阅读进度建议

本文适用于想要了解如何将 Insights 数据用于阅读进度建议的教育 IT 管理员。

通过见解，教师可以使用阅读进度跟踪学生的阅读流畅性，阅读进度是一种记录学生大声朗读并自动检测错误的工具。

阅读进度提供以下类型的阅读质询分配：

- **上下文单词**：练习基于学生在以往阅读进度作业中误读的单词推荐的单词。
- **相关单词**：根据具有相同阅读挑战类型的学生常见的错误练习推荐的单词。

有关使用 Insights for Reading Progress 的教师指南，请参阅使用 [Insights 创建阅读进度质询分配](https://support.microsoft.com/topic/c2f8f4c0-69d5-4302-b3a5-ee4dfb7a8ffe)。

## <a name="how-does-microsoft-recommend-correlated-words"></a>Microsoft 如何推荐相关字词？

相关单词是个性化的推荐词，见解教育版认为，对于具有相似阅读模式的其他学生来说，这些单词具有挑战性。

相关字词基于一种称为 **协作筛选** 的机器学习技术。

- 见解可跨共享地理区域和语言的班级分析学生的阅读数据，以识别对学生具有挑战性的单词群集。

- 鉴于一组具有挑战性的单词，Insights 还标识了类似的群集，并使用这些词向学生推荐其他单词以进行有针对性的实践。

## <a name="does-microsoft-keep-students-data-private-and-secure"></a>Microsoft 是否使学生的数据保持私密和安全？

Microsoft 致力于负责任和合乎道德地使用数据。

下面是生成此功能所采取的一些措施：

- 学生数据分析是以一种放眼的方式构建的，这意味着 Microsoft 无法访问学生的阅读数据，只能访问分析结果。

- 租户管理员可以通过关闭 [“高级推理”切换](class-insights.md#turn-on-and-off-advanced-inferences-in-insights)来选择退出数据分析过程。

- 从 **相关单词** 建议列表中筛选出不恰当的单词。 这是通过数据科学技术和阻止已知有问题的单词的组合来实现的。 但是，此过程不是错误证明。 教师应查看建议。

## <a name="what-are-the-limitations-of-insights-word-recommendations"></a>Insights 的单词建议有哪些限制？

- [这些语言](https://support.microsoft.com/topic/getting-started-with-reading-progress-in-teams-7617c11c-d685-4cb7-8b75-3917b297c407#ID0EDD=Supported_Languages)目前支持有关阅读进度的 Word 建议。

- 相关单词仅在至少五个已提交阅读进度作业的学生的课堂上显示。

- 在没有具有类似但不相同的错误模式的学生的情况下，见解可能不会推荐新单词。

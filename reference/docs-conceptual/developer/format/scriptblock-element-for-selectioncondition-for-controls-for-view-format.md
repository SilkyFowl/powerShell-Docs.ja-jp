---
title: ビューのコントロールの SelectionCondition の ScriptBlock 要素 (Format) |Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: e5f4295a989307cb6ffb655c2c39596f3d1ea806
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2020
ms.locfileid: "87785423"
---
# <a name="scriptblock-element-for-selectioncondition-for-controls-for-view-format"></a>View の Controls の SelectionCondition の ScriptBlock 要素 (書式)

条件をトリガーするスクリプトを指定します。 このスクリプトがに評価されると、 `true` 条件が満たされ、定義が使用されます。 この要素は、ビューで使用できるコントロールを定義するときに使用されます。

Configuration 要素 (Format) ViewDefinitions 要素 (書式) ビュー要素 (書式) コントロールのコントロールの要素 (形式) コントロールのコントロール要素 (format) のコントロールの要素 (書式) を制御するためのコントロールの要素 (書式) の CustomControl 要素 (format) のコントロールの CustomControl のカスタム CustomEntries ビュー (format) のためのコントロールの CustomEntries の参照 (書式) の参照 (形式) の SelectionCondition 要素を表示するためのコントロールの場合は、ビュー (形式) のコントロールの SelectionCondition のコントロールに対して、ビュー (format) の SelectionCondition 要素を指定します。

## <a name="syntax"></a>構文

```xml
<ScriptBlock>ScriptToEvaluate</ScriptBlock>
```

## <a name="attributes-and-elements"></a>属性および要素

次のセクションでは、要素の属性、子要素、および親要素について説明し `ScriptBlock` ます。

### <a name="attributes"></a>属性

なし。

### <a name="child-elements"></a>子要素

なし。

### <a name="parent-elements"></a>親要素

|要素|説明|
|-------------|-----------------|
|[View の Controls の EntrySelectedBy の SelectionCondition 要素 (書式)](./selectioncondition-element-for-entryselectedby-for-controls-for-view-format.md)|コントロール定義を使用するために必要な条件を定義します。|

## <a name="text-value"></a>テキスト値

評価されるスクリプトを指定します。

## <a name="remarks"></a>解説

選択条件には、評価するスクリプトまたはプロパティ名を少なくとも1つ指定する必要がありますが、両方を指定することはできません。 選択条件の使用方法の詳細については、「[データを表示するための条件の定義](./defining-conditions-for-displaying-data.md)」を参照してください。

## <a name="see-also"></a>参照

[View の Controls の EntrySelectedBy の SelectionCondition 要素 (書式)](./selectioncondition-element-for-entryselectedby-for-controls-for-view-format.md)

[PowerShell 書式設定ファイルを記述する](./writing-a-powershell-formatting-file.md)

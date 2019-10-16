---
title: TableControl (Format) の EntrySelectedBy の SelectionCondition 要素Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 912f3e63-e4d5-41ce-8710-6dfd8c885dc2
caps.latest.revision: 12
ms.openlocfilehash: 2faca6021dc26878869bdd2d35bc4ffc64d0fe7b
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/15/2019
ms.locfileid: "72368391"
---
# <a name="selectioncondition-element-for-entryselectedby-for-tablecontrol-format"></a>TableControl の EntrySelectedBy の SelectionCondition 要素 (書式)

テーブルビューのこの定義に使用する必要がある条件を定義します。 テーブル定義に指定できる選択条件の数に制限はありません。

Configuration 要素 (Format) ViewDefinitions 要素 (書式) ビュー要素 (Format) TableControl Element (Format) TableRowEntries Element (format) TableRowEntry Element (format) TableRowEntry (Format) の要素TableRowEntry (Format) の EntrySelectedBy の SelectionCondition 要素

## <a name="syntax"></a>構文

```xml
<SelectionCondition>
  <TypeName>Nameof.NetType</TypeName>
  <SelectionSetName>NameofSelectionSet</SelectionSetName>
  <PropertyName>.NetTypeProperty</PropertyName>
  <ScriptBlock>ScriptToEvaluate</ScriptBlock>
</SelectionCondition>
```

## <a name="attributes-and-elements"></a>属性と要素

次のセクションでは、属性、子要素、および SelectionCondition 要素の親要素について説明します。

### <a name="attributes"></a>属性

なし。

### <a name="child-elements"></a>子要素

|要素|[説明]|
|-------------|-----------------|
|[TableRowEntry (Format) の EntrySelectedBy の SelectionCondition の PropertyName 要素](./propertyname-element-for-selectioncondition-for-entryselectedby-for-tablerowentry-format.md)|省略可能な要素。<br /><br /> 条件をトリガーする .NET プロパティを指定します。|
|[TableRowEntry (Format) の EntrySelectedBy の SelectionCondition の ScriptBlock 要素](./scriptblock-element-for-selectioncondition-for-entryselectedby-for-tablecontrol-format.md)|省略可能な要素。<br /><br /> 条件をトリガーするスクリプトを指定します。|
|[EntrySelectedBy for TableRowEntry (Format) の SelectionCondition の SelectionSetName 要素](./selectionsetname-element-for-selectioncondition-for-entryselectedby-for-tablecontrol-format.md)|省略可能な要素。<br /><br /> 条件をトリガーする .NET 型のセットを指定します。|
|[TableRowEntry (Format) の EntrySelectedBy の SelectionCondition の TypeName 要素](./typename-element-for-selectioncondition-for-entryselectedby-for-tablecontrol-format.md)|省略可能な要素。<br /><br /> 条件をトリガーする .NET 型を指定します。|

### <a name="parent-elements"></a>親要素

|要素|[説明]|
|-------------|-----------------|
|[TableRowEntry の EntrySelectedBy 要素 (形式)](./entryselectedby-element-for-tablerowentry-for-tablecontrol-format.md)|このテーブルエントリを使用する .NET 型、またはこのエントリを使用するために必要な条件を定義します。|

## <a name="remarks"></a>コメント

各リストエントリには、少なくとも1つの型名、選択セット、または選択条件が定義されている必要があります。

選択条件を定義する場合は、次の要件が適用されます。

- 選択条件には、少なくとも1つのプロパティ名またはスクリプトブロックを指定する必要がありますが、両方を指定することはできません。

- 選択条件では、任意の数の .NET 型または選択セットを指定できますが、両方を指定することはできません。

選択条件の使用方法の詳細については、「[ビューエントリまたは項目が使用される場合の条件の定義](./defining-conditions-for-displaying-data.md)」を参照してください。

テーブルビューのコンポーネントの詳細については、「[テーブルビューの作成](./creating-a-table-view.md)」を参照してください。

## <a name="see-also"></a>参照

[テーブルビューの作成](./creating-a-table-view.md)

[データを表示するときの条件の定義](./defining-conditions-for-displaying-data.md)

[EntrySelectedBy 要素 (形式)](./entryselectedby-element-for-tablerowentry-for-tablecontrol-format.md)

[TableRowEntry (Format) の EntrySelectedBy の SelectionCondition の PropertyName 要素](./propertyname-element-for-selectioncondition-for-entryselectedby-for-tablerowentry-format.md)

[TableRowEntry (Format) の EntrySelectedBy の SelectionCondition の ScriptBlock 要素](./scriptblock-element-for-selectioncondition-for-entryselectedby-for-tablecontrol-format.md)

[EntrySelectedBy for TableRowEntry (Format) の SelectionCondition の SelectionSetName 要素](./selectionsetname-element-for-selectioncondition-for-entryselectedby-for-tablecontrol-format.md)

[TableRowEntry (Format) の EntrySelectedBy の SelectionCondition の TypeName 要素](./typename-element-for-selectioncondition-for-entryselectedby-for-tablecontrol-format.md)

[Windows PowerShell のフォーマットファイルと型ファイルの作成](./writing-a-powershell-formatting-file.md)
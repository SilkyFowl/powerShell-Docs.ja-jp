---
title: GroupBy (Format) の SelectionCondition の TypeName 要素 |Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: ea1e0cb50c3a749f6c26d13fff4b001240ce6b95
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2020
ms.locfileid: "87772554"
---
# <a name="typename-element-for-selectioncondition-for-groupby-format"></a>GroupBy の SelectionCondition の TypeName 要素 (書式)

条件をトリガーする .NET 型を指定します。 この要素は、新しいオブジェクトのグループをどのように表示するかを定義するときに使用されます。

Configuration 要素 (Format) ViewDefinitions 要素 (書式) ビュー要素 (形式) GroupBy 要素の groupby (format) CustomControl 要素を groupby (format) CustomEntry 要素の CustomControl の CustomEntries 要素 groupby (format) の CustomControl の Entryselectedby for groupby (format) Selectionselectedby 要素の EntrySelectedBy 要素の Selectionselectedby groupby (形式) の selectioncondition に対する groupby (format) TypeName 要素の SelectionCondition 要素

## <a name="syntax"></a>構文

```xml
<TypeName>Nameof.NetType</TypeName>

```

## <a name="attributes-and-elements"></a>属性および要素

次のセクションでは、要素の属性、子要素、および親要素について説明し `TypeName` ます。

### <a name="attributes"></a>属性

なし。

### <a name="child-elements"></a>子要素

なし。

### <a name="parent-elements"></a>親要素

|要素|説明|
|-------------|-----------------|
|[GroupBy の EntrySelectedBy の SelectionCondition 要素 (書式)](./selectioncondition-element-for-entryselectedby-for-groupby-format.md)|コントロール定義を使用するために必要な条件を定義します。|

## <a name="text-value"></a>テキスト値

.NET 型の完全修飾名 (など) を指定し `System.IO.DirectoryInfo` ます。

## <a name="remarks"></a>解説

この要素が指定されている場合、要素を指定することはできません `SelectionSetName` 。 選択条件の定義の詳細については、「[データを表示するための条件の定義](./defining-conditions-for-displaying-data.md)」を参照してください。

## <a name="see-also"></a>参照

[GroupBy の EntrySelectedBy の SelectionCondition 要素 (書式)](./selectioncondition-element-for-entryselectedby-for-groupby-format.md)

[PowerShell 書式設定ファイルを記述する](./writing-a-powershell-formatting-file.md)

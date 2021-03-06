---
title: ビューのコントロールの SelectionCondition の TypeName 要素 (Format) |Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 4795c3af40cf60fb8e71185feced18c192b3a0aa
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2020
ms.locfileid: "87780051"
---
# <a name="typename-element-for-selectioncondition-for-controls-for-view-format"></a>View の Controls の SelectionCondition の TypeName 要素 (書式)

条件をトリガーする .NET 型を指定します。 この要素は、ビューで使用できるコントロールを定義するときに使用されます。

Configuration 要素 (Format) ViewDefinitions 要素 (書式) ビュー要素 (書式) コントロールのコントロールの要素 (形式) コントロールのコントロール要素 (format) のコントロールの要素 (書式) を制御するためのコントロールの要素 (書式) の CustomControl 要素 (format) のコントロールの CustomControl のカスタム CustomEntries view (format) のコントロールの CustomEntries のためのコントロールのために、ビュー (format) のコントロールの SelectionCondition 要素を表示するためのコントロール (format) の SelectionCondition 要素をコントロールに対して使用します。

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
|[View の Controls の EntrySelectedBy の SelectionCondition 要素 (書式)](./selectioncondition-element-for-entryselectedby-for-controls-for-view-format.md)|コントロール定義を使用するために必要な条件を定義します。|

## <a name="text-value"></a>テキスト値

.NET 型の完全修飾名 (など) を指定し `System.IO.DirectoryInfo` ます。

## <a name="remarks"></a>解説

## <a name="see-also"></a>参照

[View の Controls の EntrySelectedBy の SelectionCondition 要素 (書式)](./selectioncondition-element-for-entryselectedby-for-controls-for-view-format.md)

[PowerShell 書式設定ファイルを記述する](./writing-a-powershell-formatting-file.md)

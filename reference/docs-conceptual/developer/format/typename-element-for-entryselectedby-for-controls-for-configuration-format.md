---
title: 構成用のコントロール (Format) の EntrySelectedBy の TypeName 要素Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 994cd368872392abe47b4e9422c661cd8c03e05c
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2020
ms.locfileid: "87783349"
---
# <a name="typename-element-for-entryselectedby-for-controls-for-configuration-format"></a>Configuration の Controls の EntrySelectedBy の TypeName 要素 (書式)

コントロールのこの定義を使用する .NET 型を指定します。 この要素は、書式設定ファイル内のすべてのビューで使用できるコモンコントロールを定義するときに使用されます。

Configuration 要素 (Format) コントロールの configuration (format) CustomControl 要素のコントロール要素を構成するためのコントロールの要素の構成 (形式) CustomControl の構成 (形式) の CustomEntries 要素の構成 (形式) CustoCustomControl 用の Mentry 要素の構成 (形式) のために、CustomEntry for コントロールの構成 (形式) の TypeName 要素を構成するためのコントロール用の EntrySelectedBy 要素

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
|[Configuration の Controls の CustomEntry の EntrySelectedBy 要素 (書式)](./entryselectedby-element-for-customentry-for-controls-for-configuration-format.md)|このコントロール定義を使用する .NET 型、またはこの定義を使用するために必要な条件を定義します。|

## <a name="text-value"></a>テキスト値

.NET 型の完全修飾名 (など) を指定し `System.IO.DirectoryInfo` ます。

## <a name="remarks"></a>解説

## <a name="see-also"></a>参照

[Configuration の Controls の CustomEntry の EntrySelectedBy 要素 (書式)](./entryselectedby-element-for-customentry-for-controls-for-configuration-format.md)

[PowerShell 書式設定ファイルを記述する](./writing-a-powershell-formatting-file.md)

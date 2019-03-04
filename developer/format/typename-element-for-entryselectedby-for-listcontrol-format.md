---
title: EntrySelectedBy ListControl (形式) 用の TypeName 要素 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 33c7345c-b808-4c1e-bd54-cb870b407432
caps.latest.revision: 14
ms.openlocfilehash: 3f0c0ba1fe85d70557e67a30b3a9a59a33043475
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2019
ms.locfileid: "56856108"
---
# <a name="typename-element-for-entryselectedby-for-listcontrol-format"></a><span data-ttu-id="a4b51-102">ListControl の EntrySelectedBy の TypeName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="a4b51-102">TypeName Element for EntrySelectedBy for ListControl (Format)</span></span>

<span data-ttu-id="a4b51-103">このエントリのリスト ビューを使用する .NET 型を指定します。</span><span class="sxs-lookup"><span data-stu-id="a4b51-103">Specifies a .NET type that uses this entry of the list view.</span></span> <span data-ttu-id="a4b51-104">一覧のエントリに指定できる型の数に制限はありません。</span><span class="sxs-lookup"><span data-stu-id="a4b51-104">There is no limit to the number of types that can be specified for a list entry.</span></span>

<span data-ttu-id="a4b51-105">構成要素 (形式) ViewDefinitions 要素 (形式) ビュー要素 (形式) ListControl 要素 (形式) ListEntries 要素 (形式) ListEntry 要素 (形式) EntrySelectedBy 要素の TypeName 要素を ListEntry (形式)EntrySelectedBy ListControl (形式) の</span><span class="sxs-lookup"><span data-stu-id="a4b51-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) ListControl Element (Format) ListEntries Element (Format) ListEntry Element (Format) EntrySelectedBy Element for ListEntry (Format) TypeName Element for EntrySelectedBy for ListControl (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="a4b51-106">構文</span><span class="sxs-lookup"><span data-stu-id="a4b51-106">Syntax</span></span>

```xml
<TypeName>Nameof.NetType</TypeName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="a4b51-107">属性と要素</span><span class="sxs-lookup"><span data-stu-id="a4b51-107">Attributes and Elements</span></span>

<span data-ttu-id="a4b51-108">次のセクションでは、属性、子要素、およびの親要素について説明します、`TypeName`要素。</span><span class="sxs-lookup"><span data-stu-id="a4b51-108">The following sections describe attributes, child elements, and the parent element of the `TypeName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="a4b51-109">属性</span><span class="sxs-lookup"><span data-stu-id="a4b51-109">Attributes</span></span>

<span data-ttu-id="a4b51-110">なし。</span><span class="sxs-lookup"><span data-stu-id="a4b51-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="a4b51-111">子要素</span><span class="sxs-lookup"><span data-stu-id="a4b51-111">Child Elements</span></span>

<span data-ttu-id="a4b51-112">なし。</span><span class="sxs-lookup"><span data-stu-id="a4b51-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="a4b51-113">親要素</span><span class="sxs-lookup"><span data-stu-id="a4b51-113">Parent Elements</span></span>

|<span data-ttu-id="a4b51-114">要素</span><span class="sxs-lookup"><span data-stu-id="a4b51-114">Element</span></span>|<span data-ttu-id="a4b51-115">説明</span><span class="sxs-lookup"><span data-stu-id="a4b51-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="a4b51-116">ListEntry (形式) の EntrySelectedBy 要素</span><span class="sxs-lookup"><span data-stu-id="a4b51-116">EntrySelectedBy Element for ListEntry (Format)</span></span>](./entryselectedby-element-for-listentry-for-listcontrol-format.md)|<span data-ttu-id="a4b51-117">このリストのエントリまたは条件を使用するには、このエントリが存在する必要がありますを使用する .NET 型を定義します。</span><span class="sxs-lookup"><span data-stu-id="a4b51-117">Defines the .NET types that use this list entry or the condition that must exist for this entry to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="a4b51-118">テキスト値</span><span class="sxs-lookup"><span data-stu-id="a4b51-118">Text Value</span></span>

<span data-ttu-id="a4b51-119">.NET 型の完全修飾名を指定します。`System.IO.DirectoryInfo`します。</span><span class="sxs-lookup"><span data-stu-id="a4b51-119">Specify the fully-qualified name of the .NET type, such as `System.IO.DirectoryInfo`.</span></span>

## <a name="remarks"></a><span data-ttu-id="a4b51-120">コメント</span><span class="sxs-lookup"><span data-stu-id="a4b51-120">Remarks</span></span>

<span data-ttu-id="a4b51-121">リストの各エントリに少なくとも 1 つの型名、選択範囲のセット、または選択条件が定義されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="a4b51-121">Each list entry must have at least one type name, selection set, or selection condition defined.</span></span>

<span data-ttu-id="a4b51-122">この要素はリスト ビューで使用する方法の詳細については、次を参照してください。[リスト ビュー](./creating-a-list-view.md)します。</span><span class="sxs-lookup"><span data-stu-id="a4b51-122">For more information about how this element is used in a list view, see [List View](./creating-a-list-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="a4b51-123">例</span><span class="sxs-lookup"><span data-stu-id="a4b51-123">Example</span></span>

<span data-ttu-id="a4b51-124">次の例では、選択リスト ビューのエントリのセットを指定する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="a4b51-124">The following example shows how to specify a selection set for an entry of a list view.</span></span>

```xml
<ListEntry>
  <EntrySelectedBy>
    <TypeName>Nameof.NetType</TypeName>
  </EntrySelectedBy>
  <ListItems>...</ListItems>
</ListEntry>
```

## <a name="see-also"></a><span data-ttu-id="a4b51-125">参照</span><span class="sxs-lookup"><span data-stu-id="a4b51-125">See Also</span></span>

[<span data-ttu-id="a4b51-126">リスト ビューの作成</span><span class="sxs-lookup"><span data-stu-id="a4b51-126">Creating a List View</span></span>](./creating-a-list-view.md)

[<span data-ttu-id="a4b51-127">ListEntry (形式) の EntrySelectedBy 要素</span><span class="sxs-lookup"><span data-stu-id="a4b51-127">EntrySelectedBy Element for ListEntry (Format)</span></span>](./entryselectedby-element-for-listentry-for-listcontrol-format.md)

[<span data-ttu-id="a4b51-128">ListEntry (形式) の EnrtySelectedBy SelectionSetName 要素</span><span class="sxs-lookup"><span data-stu-id="a4b51-128">SelectionSetName Element for EnrtySelectedBy for ListEntry (Format)</span></span>](./selectionsetname-element-for-entryselectedby-for-listcontrol-format.md)

[<span data-ttu-id="a4b51-129">PowerShell のファイルを書式設定の書き込み</span><span class="sxs-lookup"><span data-stu-id="a4b51-129">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
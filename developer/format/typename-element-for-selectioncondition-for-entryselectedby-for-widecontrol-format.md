---
title: SelectionCondition EntrySelectedBy WideControl (形式) のための TypeName 要素 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6d6d43fa-c900-4e2f-952d-deccd584236f
caps.latest.revision: 11
ms.openlocfilehash: 0d7bbfd8be3bf2bd1af75a45ca4db016dfb6bff6
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2019
ms.locfileid: "56857958"
---
# <a name="typename-element-for-selectioncondition-for-entryselectedby-for-widecontrol-format"></a><span data-ttu-id="863cb-102">WideControl の EntrySelectedBy の SelectionCondition の TypeName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="863cb-102">TypeName Element for SelectionCondition for EntrySelectedBy for WideControl (Format)</span></span>

<span data-ttu-id="863cb-103">条件をトリガーする .NET 型を指定します。</span><span class="sxs-lookup"><span data-stu-id="863cb-103">Specifies a .NET type that triggers the condition.</span></span> <span data-ttu-id="863cb-104">この型が存在する場合は、定義を使用します。</span><span class="sxs-lookup"><span data-stu-id="863cb-104">When this type is present, the definition is used.</span></span>

<span data-ttu-id="863cb-105">構成要素 (形式) ViewDefinitions 要素 (形式) ビュー要素 (形式) WideControl 要素 (形式) WideEntries 要素 (形式) WideEntry 要素 (形式) EntrySelectedBy 要素の WideEntry (形式) SelectionCondition 要素EntrySelectedBy SelectionCondition EntrySelectedBy WideEntry (形式) のための TypeName 要素を WideEntry (形式)</span><span class="sxs-lookup"><span data-stu-id="863cb-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) WideControl Element (Format) WideEntries Element (Format) WideEntry Element (Format) EntrySelectedBy Element for WideEntry (Format) SelectionCondition Element for EntrySelectedBy for WideEntry (Format) TypeName Element for SelectionCondition for EntrySelectedBy for WideEntry (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="863cb-106">構文</span><span class="sxs-lookup"><span data-stu-id="863cb-106">Syntax</span></span>

```xml
<TypeName>Nameof.NetType</TypeName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="863cb-107">属性と要素</span><span class="sxs-lookup"><span data-stu-id="863cb-107">Attributes and Elements</span></span>

<span data-ttu-id="863cb-108">次のセクションでは、属性、子要素、およびの親要素について説明します、`TypeName`要素。</span><span class="sxs-lookup"><span data-stu-id="863cb-108">The following sections describe attributes, child elements, and the parent element of the `TypeName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="863cb-109">属性</span><span class="sxs-lookup"><span data-stu-id="863cb-109">Attributes</span></span>

<span data-ttu-id="863cb-110">なし。</span><span class="sxs-lookup"><span data-stu-id="863cb-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="863cb-111">子要素</span><span class="sxs-lookup"><span data-stu-id="863cb-111">Child Elements</span></span>

<span data-ttu-id="863cb-112">なし。</span><span class="sxs-lookup"><span data-stu-id="863cb-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="863cb-113">親要素</span><span class="sxs-lookup"><span data-stu-id="863cb-113">Parent Elements</span></span>

|<span data-ttu-id="863cb-114">要素</span><span class="sxs-lookup"><span data-stu-id="863cb-114">Element</span></span>|<span data-ttu-id="863cb-115">説明</span><span class="sxs-lookup"><span data-stu-id="863cb-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="863cb-116">WideEntry (形式) の EntrySelectedBy SelectionCondition 要素</span><span class="sxs-lookup"><span data-stu-id="863cb-116">SelectionCondition Element for EntrySelectedBy for WideEntry (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-widecontrol-format.md)|<span data-ttu-id="863cb-117">このワイド エントリを使用するのに必要な条件を定義します。</span><span class="sxs-lookup"><span data-stu-id="863cb-117">Defines the condition that must exist for this wide entry to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="863cb-118">テキスト値</span><span class="sxs-lookup"><span data-stu-id="863cb-118">Text Value</span></span>

<span data-ttu-id="863cb-119">.NET 型の完全修飾名を指定します。`System.IO.DirectoryInfo`します。</span><span class="sxs-lookup"><span data-stu-id="863cb-119">Specify the fully qualified name of the .NET type, such as `System.IO.DirectoryInfo`.</span></span>

## <a name="remarks"></a><span data-ttu-id="863cb-120">コメント</span><span class="sxs-lookup"><span data-stu-id="863cb-120">Remarks</span></span>

<span data-ttu-id="863cb-121">選択条件が .NET 型を指定または選択範囲を設定するが、両方を指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="863cb-121">The selection condition can specify a .NET type or a selection set, but cannot specify both.</span></span> <span data-ttu-id="863cb-122">選択条件を使用する方法の詳細については、次を参照してください。[データが表示される場合の条件を定義する](./defining-conditions-for-displaying-data.md)します。</span><span class="sxs-lookup"><span data-stu-id="863cb-122">For more information about how to use selection conditions, see [Defining Conditions for when Data is Displayed](./defining-conditions-for-displaying-data.md).</span></span>

<span data-ttu-id="863cb-123">ワイド ビューの他のコンポーネントに関する詳細については、次を参照してください。[ワイド ビューを作成する](./creating-a-wide-view.md)します。</span><span class="sxs-lookup"><span data-stu-id="863cb-123">For more information about other components of a wide view, see [Creating a Wide View](./creating-a-wide-view.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="863cb-124">参照</span><span class="sxs-lookup"><span data-stu-id="863cb-124">See Also</span></span>

[<span data-ttu-id="863cb-125">ワイド ビューの作成</span><span class="sxs-lookup"><span data-stu-id="863cb-125">Creatng a Wide View</span></span>](./creating-a-wide-view.md)

[<span data-ttu-id="863cb-126">データが表示される場合の条件の定義</span><span class="sxs-lookup"><span data-stu-id="863cb-126">Defining Conditions for When Data Is Displayed</span></span>](./defining-conditions-for-displaying-data.md)

[<span data-ttu-id="863cb-127">WideEntry (形式) の EntrySelectedBy SelectionCondition 要素</span><span class="sxs-lookup"><span data-stu-id="863cb-127">SelectionCondition Element for EntrySelectedBy for WideEntry (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-widecontrol-format.md)

[<span data-ttu-id="863cb-128">EntrySelectedBy WideEntry (形式) 用の SelectionCondition SelectionSetName 要素</span><span class="sxs-lookup"><span data-stu-id="863cb-128">SelectionSetName Element for SelectionCondition for EntrySelectedBy for WideEntry (Format)</span></span>](./selectionsetname-element-for-selectioncondition-for-entryselectedby-for-wideentry-format.md)

[<span data-ttu-id="863cb-129">PowerShell のファイルを書式設定の書き込み</span><span class="sxs-lookup"><span data-stu-id="863cb-129">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
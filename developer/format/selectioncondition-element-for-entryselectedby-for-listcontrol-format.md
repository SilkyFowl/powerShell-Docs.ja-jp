---
title: ListControl (形式) の EntrySelectedBy SelectionCondition 要素 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7649d5d0-2b56-49b5-a670-dde46caca343
caps.latest.revision: 11
ms.openlocfilehash: ec75945c5517c02fa001f0a38573c045ffcdbfd3
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2019
ms.locfileid: "56857488"
---
# <a name="selectioncondition-element-for-entryselectedby-for-listcontrol-format"></a><span data-ttu-id="d9440-102">ListControl の EntrySelectedBy の SelectionCondition 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="d9440-102">SelectionCondition Element for EntrySelectedBy for ListControl (Format)</span></span>

<span data-ttu-id="d9440-103">リスト ビューのこの定義を使用する必要があります条件を定義します。</span><span class="sxs-lookup"><span data-stu-id="d9440-103">Defines the condition that must exist to use this definition of the list view.</span></span> <span data-ttu-id="d9440-104">リスト定義に指定できる選択条件の数に制限はありません。</span><span class="sxs-lookup"><span data-stu-id="d9440-104">There is no limit to the number of selection conditions that can be specified for a list definition.</span></span>

<span data-ttu-id="d9440-105">構成要素 (形式) ViewDefinitions 要素 (形式) ビュー要素 (形式) ListControl 要素 (形式) ListEntries 要素 (形式) ListEntry 要素 (形式) EntrySelectedBy 要素の ListEntry (形式) SelectionCondition 要素EntrySelectedBy ListEntry (形式) の</span><span class="sxs-lookup"><span data-stu-id="d9440-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) ListControl Element (Format) ListEntries Element (Format) ListEntry Element (Format) EntrySelectedBy Element for ListEntry (Format) SelectionCondition Element for EntrySelectedBy for ListEntry (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="d9440-106">構文</span><span class="sxs-lookup"><span data-stu-id="d9440-106">Syntax</span></span>

```xml
<SelectionCondition>
  <TypeName>Nameof.NetType</TypeName>
  <SelectionSetName>NameofSelectionSet</SelectionSetName>
  <PropertyName>.NetTypeProperty</PropertyName>
  <ScriptBlock>ScriptToEvaluate</ScriptBlock>
</SelectionCondition>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="d9440-107">属性と要素</span><span class="sxs-lookup"><span data-stu-id="d9440-107">Attributes and Elements</span></span>

<span data-ttu-id="d9440-108">次のセクションでは、属性、子要素、およびの親要素について説明します、`SelectionCondition`要素。</span><span class="sxs-lookup"><span data-stu-id="d9440-108">The following sections describe attributes, child elements, and the parent element of the `SelectionCondition` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="d9440-109">属性</span><span class="sxs-lookup"><span data-stu-id="d9440-109">Attributes</span></span>

<span data-ttu-id="d9440-110">なし。</span><span class="sxs-lookup"><span data-stu-id="d9440-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="d9440-111">子要素</span><span class="sxs-lookup"><span data-stu-id="d9440-111">Child Elements</span></span>

|<span data-ttu-id="d9440-112">要素</span><span class="sxs-lookup"><span data-stu-id="d9440-112">Element</span></span>|<span data-ttu-id="d9440-113">説明</span><span class="sxs-lookup"><span data-stu-id="d9440-113">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="d9440-114">SelectionCondition EmtrySelectedBy ListEntry (形式) のための PropertyName 要素</span><span class="sxs-lookup"><span data-stu-id="d9440-114">PropertyName Element for SelectionCondition for EmtrySelectedBy for ListEntry (Format)</span></span>](./propertyname-element-for-selectioncondition-for-entryselectedby-for-listcontrol-format.md)|<span data-ttu-id="d9440-115">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="d9440-115">Optional element.</span></span><br /><br /> <span data-ttu-id="d9440-116">条件をトリガーする、.NET プロパティを指定します。</span><span class="sxs-lookup"><span data-stu-id="d9440-116">Specifies the .NET property that triggers the condition.</span></span>|
|[<span data-ttu-id="d9440-117">SelectionCondition EntrySelectedBy ListEntry (形式) のためのスクリプト ブロックの要素</span><span class="sxs-lookup"><span data-stu-id="d9440-117">ScriptBlock Element for SelectionCondition for EntrySelectedBy for ListEntry (Format)</span></span>](./scriptblock-element-for-selectioncondition-for-entryselectedby-for-listcontrol-format.md)|<span data-ttu-id="d9440-118">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="d9440-118">Optional element.</span></span><br /><br /> <span data-ttu-id="d9440-119">条件をトリガーするスクリプトを指定します。</span><span class="sxs-lookup"><span data-stu-id="d9440-119">Specifies the script that triggers the condition.</span></span>|
|[<span data-ttu-id="d9440-120">EntrySelectedBy ListEntry (形式) 用の SelectionCondition SelectionSetName 要素</span><span class="sxs-lookup"><span data-stu-id="d9440-120">SelectionSetName Element for SelectionCondition for EntrySelectedBy for ListEntry (Format)</span></span>](./selectionsetname-element-for-selectioncondition-for-entryselectedby-for-listentry-format.md)|<span data-ttu-id="d9440-121">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="d9440-121">Optional element.</span></span><br /><br /> <span data-ttu-id="d9440-122">条件をトリガーする .NET 型のセットを指定します。</span><span class="sxs-lookup"><span data-stu-id="d9440-122">Specifies the set of .NET types that trigger the condition.</span></span>|
|[<span data-ttu-id="d9440-123">SelectionCondition EntrySelectedBy ListEntry (形式) のための TypeName 要素</span><span class="sxs-lookup"><span data-stu-id="d9440-123">TypeName Element for SelectionCondition for EntrySelectedBy for ListEntry (Format)</span></span>](./typename-element-for-selectioncondition-for-entryselectedby-for-listcontrol-format.md)|<span data-ttu-id="d9440-124">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="d9440-124">Optional element.</span></span><br /><br /> <span data-ttu-id="d9440-125">条件をトリガーする .NET 型を指定します。</span><span class="sxs-lookup"><span data-stu-id="d9440-125">Specifies a .NET type that triggers the condition.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="d9440-126">親要素</span><span class="sxs-lookup"><span data-stu-id="d9440-126">Parent Elements</span></span>

|<span data-ttu-id="d9440-127">要素</span><span class="sxs-lookup"><span data-stu-id="d9440-127">Element</span></span>|<span data-ttu-id="d9440-128">説明</span><span class="sxs-lookup"><span data-stu-id="d9440-128">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="d9440-129">TableRowEntry (形式) の EntrySelectedBy 要素</span><span class="sxs-lookup"><span data-stu-id="d9440-129">EntrySelectedBy Element for TableRowEntry (Format)</span></span>](./entryselectedby-element-for-tablerowentry-for-tablecontrol-format.md)|<span data-ttu-id="d9440-130">このテーブルのエントリまたは条件を使用するには、このエントリが存在する必要がありますを使用する .NET 型を定義します。</span><span class="sxs-lookup"><span data-stu-id="d9440-130">Defines the .NET types that use this table entry or the condition that must exist for this entry to be used.</span></span>|

## <a name="remarks"></a><span data-ttu-id="d9440-131">コメント</span><span class="sxs-lookup"><span data-stu-id="d9440-131">Remarks</span></span>

<span data-ttu-id="d9440-132">lWhen 選択条件を定義する、次の要件が適用されます。</span><span class="sxs-lookup"><span data-stu-id="d9440-132">lWhen you are defining a selection condition, the following requirements apply:</span></span>

- <span data-ttu-id="d9440-133">選択条件では、少なくとも 1 つのプロパティ名またはスクリプト ブロックを指定する必要がありますが、両方を指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="d9440-133">The selection condition must specify a least one property name or a script block, but cannot specify both.</span></span>

- <span data-ttu-id="d9440-134">選択条件が .NET 型の任意の数を指定するか、選択範囲を設定するが、両方を指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="d9440-134">The selection condition can specify any number of .NET types or selection sets, but cannot specify both.</span></span>

<span data-ttu-id="d9440-135">選択条件を使用する方法の詳細については、次を参照してください。[データが表示される場合の条件を定義する](./defining-conditions-for-displaying-data.md)します。</span><span class="sxs-lookup"><span data-stu-id="d9440-135">For more information about how to use selection conditions, see [Defining Conditions for when Data is Displayed](./defining-conditions-for-displaying-data.md).</span></span>

<span data-ttu-id="d9440-136">リスト ビューの他のコンポーネントに関する詳細については、次を参照してください。[リスト ビューを作成する](./creating-a-list-view.md)します。</span><span class="sxs-lookup"><span data-stu-id="d9440-136">For more information about other components of a list view, see [Creating a List View](./creating-a-list-view.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="d9440-137">参照</span><span class="sxs-lookup"><span data-stu-id="d9440-137">See Also</span></span>

[<span data-ttu-id="d9440-138">リスト ビューの作成</span><span class="sxs-lookup"><span data-stu-id="d9440-138">Creating a List View</span></span>](./creating-a-list-view.md)

[<span data-ttu-id="d9440-139">データが表示される場合の条件の定義</span><span class="sxs-lookup"><span data-stu-id="d9440-139">Defining Conditions for When Data Is Displayed</span></span>](./defining-conditions-for-displaying-data.md)

[<span data-ttu-id="d9440-140">ListEntry 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="d9440-140">ListEntry Element (Format)</span></span>](./listentry-element-for-listcontrol-format.md)

[<span data-ttu-id="d9440-141">ListEntry (形式) の EnrtySelectedBy SelectionSetName 要素</span><span class="sxs-lookup"><span data-stu-id="d9440-141">SelectionSetName Element for EnrtySelectedBy for ListEntry (Format)</span></span>](./selectionsetname-element-for-entryselectedby-for-listcontrol-format.md)

[<span data-ttu-id="d9440-142">EntrySelectedBy ListEntry (形式) 用の TypeName 要素</span><span class="sxs-lookup"><span data-stu-id="d9440-142">TypeName Element for EntrySelectedBy for ListEntry (Format)</span></span>](http://msdn.microsoft.com/en-us/fcd4daa6-f3fd-43f7-a468-03c582d34533)

[<span data-ttu-id="d9440-143">PowerShell のファイルを書式設定の書き込み</span><span class="sxs-lookup"><span data-stu-id="d9440-143">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
---
title: ValidateRange Attribute 宣言 |Microsoft Docs
ms.date: 09/13/2016
helpviewer_keywords:
- ValidateRange, described
- ValidateRange attribute
- attributes, ValidateRange
ms.openlocfilehash: 9aeaa6f03c170389ff61a058b505dbcf74df6958
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2020
ms.locfileid: "87787786"
---
# <a name="validaterange-attribute-declaration"></a><span data-ttu-id="13452-102">ValidateRange 属性の宣言</span><span class="sxs-lookup"><span data-stu-id="13452-102">ValidateRange Attribute Declaration</span></span>

<span data-ttu-id="13452-103">ValidateRange 属性は、コマンドレットパラメーター引数の最小値と最大値 (範囲) を指定します。</span><span class="sxs-lookup"><span data-stu-id="13452-103">The ValidateRange attribute specifies the minimum and maximum values (the range) for the cmdlet parameter argument.</span></span> <span data-ttu-id="13452-104">この属性は、Windows PowerShell の関数でも使用できます。</span><span class="sxs-lookup"><span data-stu-id="13452-104">This attribute can also be used by Windows PowerShell functions.</span></span>

## <a name="syntax"></a><span data-ttu-id="13452-105">構文</span><span class="sxs-lookup"><span data-stu-id="13452-105">Syntax</span></span>

```csharp
[ValidateRange(object minRange, object maxRange)]
```

#### <a name="parameters"></a><span data-ttu-id="13452-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="13452-106">Parameters</span></span>

<span data-ttu-id="13452-107">`MinRange`([System.object](/dotnet/api/system.object)) が必要です。</span><span class="sxs-lookup"><span data-stu-id="13452-107">`MinRange` ([System.Object](/dotnet/api/system.object)) Required.</span></span> <span data-ttu-id="13452-108">許容される最小値を指定します。</span><span class="sxs-lookup"><span data-stu-id="13452-108">Specifies the minimum value allowed.</span></span>

<span data-ttu-id="13452-109">`MaxRange`([System.object](/dotnet/api/system.object)) が必要です。</span><span class="sxs-lookup"><span data-stu-id="13452-109">`MaxRange` ([System.Object](/dotnet/api/system.object)) Required.</span></span> <span data-ttu-id="13452-110">許容される最大値を指定します。</span><span class="sxs-lookup"><span data-stu-id="13452-110">Specifies the maximum value allowed.</span></span>

## <a name="remarks"></a><span data-ttu-id="13452-111">解説</span><span class="sxs-lookup"><span data-stu-id="13452-111">Remarks</span></span>

- <span data-ttu-id="13452-112">パラメーターの値 `MinRange` がパラメーターの値よりも大きい場合、Windows PowerShell ランタイムは構築エラーをスローし `MaxRange` ます。</span><span class="sxs-lookup"><span data-stu-id="13452-112">The Windows PowerShell runtime throws a construction error when the value of the `MinRange` parameter is greater than the value of the `MaxRange` parameter.</span></span>

- <span data-ttu-id="13452-113">Windows PowerShell ランタイムは、次の条件下で検証エラーをスローします。</span><span class="sxs-lookup"><span data-stu-id="13452-113">The Windows PowerShell runtime throws a validation error under the following conditions:</span></span>

  - <span data-ttu-id="13452-114">引数の値が制限よりも小さいか、または制限を超えている場合 `MinRange` `MaxRange` 。</span><span class="sxs-lookup"><span data-stu-id="13452-114">When the value of the argument is less than the `MinRange` limit or greater than the `MaxRange` limit.</span></span>

  - <span data-ttu-id="13452-115">引数がおよびパラメーターと同じ型ではない場合 `MinRange` `MaxRange` 。</span><span class="sxs-lookup"><span data-stu-id="13452-115">When the argument is not of the same type as the `MinRange` and the `MaxRange` parameters.</span></span>

- <span data-ttu-id="13452-116">ValidateRange 属性は、system.servicemodel[属性](/dotnet/api/System.Management.Automation.ValidateRangeAttribute)クラスによって定義されます。</span><span class="sxs-lookup"><span data-stu-id="13452-116">The ValidateRange attribute is defined by the [System.Management.Automation.Validaterangeattribute](/dotnet/api/System.Management.Automation.ValidateRangeAttribute) class.</span></span>

## <a name="see-also"></a><span data-ttu-id="13452-117">参照</span><span class="sxs-lookup"><span data-stu-id="13452-117">See Also</span></span>

[<span data-ttu-id="13452-118">System. Automation. Validaterangeattribute</span><span class="sxs-lookup"><span data-stu-id="13452-118">System.Management.Automation.Validaterangeattribute</span></span>](/dotnet/api/System.Management.Automation.ValidateRangeAttribute)

[<span data-ttu-id="13452-119">Writing a Windows PowerShell Cmdlet (Windows PowerShell コマンドレットの記述)</span><span class="sxs-lookup"><span data-stu-id="13452-119">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)

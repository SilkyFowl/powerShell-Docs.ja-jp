---
title: コマンドレットのパラメーター |Microsoft Docs
ms.date: 09/13/2016
helpviewer_keywords:
- optional parameters [PowerShell SDK]
- aliases [PowerShell SDK]
- parameter sets [PowerShell SDK]
- parameters [PowerShell SDK]
- mandatory parameters [PowerShell SDK]
- positional parameters [PowerShell SDK]
- cmdlets [PowerShell SDK], parameters
ms.openlocfilehash: 98b1d5fd0e7ffbf2d4d161f1bed73fb96a737bd4
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2020
ms.locfileid: "87774764"
---
# <a name="cmdlet-parameters"></a>コマンドレットのパラメーター

コマンドレットのパラメーターは、コマンドレットが入力を受け入れることができるメカニズムを提供します。 パラメーターでは、コマンドラインから直接入力を受け取ることも、パイプラインを介してコマンドレットに渡されたオブジェクトから入力を受け入れることもできます。また、これらのパラメーターの引数 (*値*とも呼ばれます) は、コマンドレットが受け入れる入力、コマンドレットがアクションを実行する方法、コマンドレットがパイプラインに返すデータを指定できます。

## <a name="in-this-section"></a>このセクションの内容

[パラメーターとしてのプロパティの宣言](./declaring-properties-as-parameters.md)コマンドレットのパラメーターを宣言する前に理解しておく必要がある基本情報について説明します。

[コマンドレットパラメーターの型](./types-of-cmdlet-parameters.md)コマンドレットで宣言できるさまざまな種類のパラメーターについて説明します。

[コマンドレットのパラメーター名と機能のガイドライン](./standard-cmdlet-parameter-names-and-types.md)標準パラメーターの名前、推奨されるデータ型、および機能について説明します。

[パラメーターの別名](./parameter-aliases.md)パラメーターに対して定義できるエイリアスについて説明します。

[共通パラメーター名](./common-parameter-names.md)このトピックでは、Windows PowerShell によってコマンドレットに追加されるパラメーターについて説明します。

[コマンドレットのパラメーターセット](./cmdlet-parameter-sets.md)パラメーターセットを使用して、さまざまなシナリオでさまざまなアクションを実行できる単一のコマンドレットを作成する方法について説明します。

[コマンドレット動的パラメーター](./cmdlet-dynamic-parameters.md)特別な条件下でユーザーが使用できるパラメーターについて説明します。

[コマンドレットパラメーターでのワイルドカード文字のサポート](./supporting-wildcard-characters-in-cmdlet-parameters.md)リソースグループに対して実行されるコマンドレットを設計するときに、ワイルドカード文字のサポートを提供する方法について説明します。

[パラメーター入力の検証](./validating-parameter-input.md)コマンドレットパラメーターに渡された引数を Windows PowerShell が検証する方法について説明します。

[入力フィルターパラメーター](./input-filter-parameters.md)コマンドレットによって `Filter` `Include` 影響を `Exclude` 与える入力オブジェクトのセットをフィルター処理する、、、およびの各パラメーターについて説明します。

## <a name="related-sections"></a>関連項目

[パラメーター入力を検証する方法](./how-to-validate-parameter-input.md)

## <a name="see-also"></a>参照

[パラメーター属性の宣言](./parameter-attribute-declaration.md)

[Windows PowerShell コマンドレット](./cmdlet-overview.md)

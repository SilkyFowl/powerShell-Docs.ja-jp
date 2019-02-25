---
ms.date: 06/12/2017
keywords: DSC, PowerShell, 構成, セットアップ
title: MSFT_DSCLocalConfigurationManager クラスの ResourceSet メソッド
ms.openlocfilehash: 2712b7ff0a19e643c1f343d436c084f8970c9dd4
ms.sourcegitcommit: e04292a9c10de9a8391d529b7f7aa3753b362dbe
ms.translationtype: MTE95
ms.contentlocale: ja-JP
ms.lasthandoff: 01/04/2019
ms.locfileid: "54047665"
---
# <a name="resourceset-method-of-the-msftdsclocalconfigurationmanager-class"></a>MSFT_DSCLocalConfigurationManager クラスの ResourceSet メソッド

DSC リソースの **Set** メソッドを直接呼び出します。

## <a name="syntax"></a>構文

```mof
uint32 ResourceSet(
  [in]  string  ResourceType,
  [in]  string  ModuleName,
  [in]  uint8   resourceProperty[],
  [out] boolean RebootRequired
);
```

## <a name="parameters"></a>パラメーター

*ResourceType* \[in\] 呼び出すリソースの名前。

*ModuleName* \[in\] 呼び出すリソースを含むモジュールの名前。

*resourceProperty* \[in\] ハッシュ テーブルで、リソースのプロパティ名と値を、それぞれキーと値として指定します。 リソースのプロパティと種類を検出するには、[Get-DscResource](/powershell/module/PSDesiredStateConfiguration/Get-DscResource) コマンドレットを使用します。

*RebootRequired* \[out\] ターゲット ノードの再起動が必要な場合、制御が戻るときに、このプロパティは **true** に設定されます。

## <a name="return-value"></a>戻り値

成功した場合は 0 を返します。それ以外の場合はエラー コードを返します。

## <a name="remarks"></a>コメント

これは静的メソッドです。

## <a name="requirements"></a>要件

MOF**DscCore.mof

**［名前空間］:Root \microsoft\windows\desiredstateconfiguration

## <a name="see-also"></a>関連項目

[**MSFT_DSCLocalConfigurationManager**](msft-dsclocalconfigurationmanager.md)
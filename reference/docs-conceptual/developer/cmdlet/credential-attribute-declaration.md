---
title: Credential 属性の宣言 |Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: a6deca52fa6c9e46138ae92401f58ac5dbd15852
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2020
ms.locfileid: "87784369"
---
# <a name="credential-attribute-declaration"></a>資格情報属性の宣言

Credential 属性は省略可能な属性であり、文字列を引数としてパラメーターに渡すこともできるように、型 system.servicemodel の credential パラメーターと共に使用[できます。](/dotnet/api/System.Management.Automation.PSCredential) この属性がパラメーター宣言に追加されると、Windows PowerShell は文字列入力を system.string[オブジェクトに](/dotnet/api/System.Management.Automation.PSCredential)変換します。 たとえば、 [Get Credential](/powershell/module/Microsoft.PowerShell.Security/Get-Credential)コマンドレットでは、この属性を使用して、Windows PowerShell に対して、コマンドレットによって返される[system.servicemodel オブジェクトが](/dotnet/api/System.Management.Automation.PSCredential)生成されるようにします。

## <a name="syntax"></a>構文

```csharp
[Credential]
```

## <a name="remarks"></a>解説

- 通常、この属性は、文字列を引数としてパラメーターに渡すことが[できるように、型](/dotnet/api/System.Management.Automation.PSCredential)system.servicemodel のパラメーターによって使用されます。 System.string オブジェクト[が](/dotnet/api/System.Management.Automation.PSCredential)パラメーターに渡されると、Windows PowerShell は何も行いません。

- Windows PowerShell で[は、system.servicemodel オブジェクトを](/dotnet/api/System.Management.Automation.PSCredential)作成するときに、現在のホストを使用してユーザーに適切なプロンプトが表示されます。 たとえば、既定のホストでは、この属性を使用するときに、ユーザー名とパスワードの入力を求めるプロンプトが表示されます。 ただし、別のプロンプトを定義するカスタムホストが使用されている場合は、そのプロンプトが表示されます。

- この属性は、Parameter 属性と共に使用されます。 この属性の詳細については、「[パラメーター属性の宣言](./parameter-attribute-declaration.md)」を参照してください。

- Credential 属性は、system.servicemodel[属性](/dotnet/api/System.Management.Automation.CredentialAttribute)クラスによって定義されます。

## <a name="see-also"></a>参照

[パラメーターのエイリアス](./parameter-aliases.md)

[パラメーター属性の宣言](./parameter-attribute-declaration.md)

[Writing a Windows PowerShell Cmdlet (Windows PowerShell コマンドレットの記述)](./writing-a-windows-powershell-cmdlet.md)

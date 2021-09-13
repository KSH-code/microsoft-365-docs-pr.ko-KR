---
title: PowerShell을 사용하여 사용자 지정 중요한 정보 유형 수정
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: PowerShell을 사용하여 사용자 지정 중요한 정보를 수정하는 방법을 학습합니다.
ms.openlocfilehash: 9f8a9ef119e632c695113320ab86a3bdfef8a197
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2021
ms.locfileid: "59218852"
---
# <a name="modify-a-custom-sensitive-information-type-using-powershell"></a>PowerShell을 사용하여 사용자 지정 중요한 정보 유형 수정

규정 준수 센터 PowerShell에서 사용자 지정 중요한 정보 유형을 수정하려면 다음을 수행해야 합니다.

1. XML 파일에 사용자 지정 중요한 정보 유형을 포함하는 기존 규칙 패키지를 내보냅니다. (또는 기존 XML 파일이 있는 경우이를 내보냅니다)

2. 내보낸 XML 파일의 사용자 지정 중요한 정보 유형을 수정합니다.

3. 기존 규칙 패키지에 업데이트된 XML 파일을 다시 가져옵니다.

규정 준수 센터 PowerShell에 연결하려면 [규정 준수 센터 PowerShell에 연결하기](/powershell/exchange/exchange-online-powershell)를 참조하세요.

### <a name="step-1-export-the-existing-rule-package-to-an-xml-file"></a>1단계: XML 파일로 기존 규칙 패키지 내보내기

> [!NOTE]
> XML 파일의 복사본이 있는 경우(예: XML 파일을 만들고 가져온 경우) 다음 단계로 건너 뛰고 XML 파일을 수정할 수 있습니다.

1. 아직 모르는 경우 [Get-DlpSensitiveInformationTypeRulePackage](/powershell/module/exchange/get-dlpsensitiveinformationtype) cmdlet을 실행하여 사용자 지정 규칙 패키지의 이름을 찾습니다.

   ```powershell
   Get-DlpSensitiveInformationTypeRulePackage
   ```

   > [!NOTE]
   > 기본 제공 민감한 정보 유형이 들어있는 기본 제공 규칙 패키지의 이름은 Microsoft Rule Package입니다. 규정 준수 센터 UI에서 만든 사용자 지정 중요한 정보 유형이 포함된 규칙 패키지의 이름은 Microsoft.SCCManaged.CustomRulePack입니다.

2. [DlpSensitiveInformationTypeRulePackage](/powershell/module/exchange/get-dlpsensitiveinformationtyperulepackage) cmdlet을 사용하여 사용자 지정 규칙 패키지를 변수에 저장합니다.

   ```powershell
   $rulepak = Get-DlpSensitiveInformationTypeRulePackage -Identity "RulePackageName"
   ```

   예를 들어, 규칙 패키지의 이름이 "Employee ID Custom Rule Pack"인 경우 다음 cmdlet을 실행합니다.

   ```powershell
   $rulepak = Get-DlpSensitiveInformationTypeRulePackage -Identity "Employee ID Custom Rule Pack"
   ```

3. [Set-Content](/powershell/module/microsoft.powershell.management/set-content) cmdlet을 실행하여 사용자 지정 규칙 패키지를 XML 파일로 내보냅니다.

   ```powershell
   Set-Content -Path "XMLFileAndPath" -Encoding Byte -Value $rulepak.SerializedClassificationRuleCollection
   ```

   이 예제에서는 규칙 패키지를 C:\My Documents 폴더의 ExportedRulePackage.xml 파일로 내보냅니다.

   ```powershell
   Set-Content -Path "C:\My Documents\ExportedRulePackage.xml" -Encoding Byte -Value $rulepak.SerializedClassificationRuleCollection
   ```

#### <a name="step-2-modify-the-sensitive-information-type-in-the-exported-xml-file"></a>2단계: 내보낸 XML 파일의 중요한 정보 유형 수정

XML 파일의 중요한 정보 유형 및 파일의 기타 요소는 이 항목의 앞부분에 설명되어 있습니다.

#### <a name="step-3-import-the-updated-xml-file-back-into-the-existing-rule-package"></a>3단계: 기존 규칙 패키지에 업데이트된 XML 파일 다시 가져오기

업데이트된 XML을 기존 규칙 패키지로 가져오려면 [Set-DlpSensitiveInformationTypeRulePackage](/powershell/module/exchange/set-dlpsensitiveinformationtyperulepackage) cmdlet을 사용합니다.

```powershell
Set-DlpSensitiveInformationTypeRulePackage -FileData ([Byte[]]$(Get-Content -Path "C:\My Documents\External Sensitive Info Type Rule Collection.xml" -Encoding Byte -ReadCount 0))
```

구문과 매개 변수에 대한 자세한 내용은 [설정-DlpSensitiveInformationTypeRulePackage](/powershell/module/exchange/set-dlpsensitiveinformationtyperulepackage)를 참조하세요.


## <a name="more-information"></a>추가 정보

- [데이터 손실 방지에 대해 알아보기](dlp-learn-about-dlp.md)

- [중요한 정보 유형 엔터티 정의](sensitive-information-type-entity-definitions.md)

- [DLP 함수가 찾는 항목](what-the-dlp-functions-look-for.md)

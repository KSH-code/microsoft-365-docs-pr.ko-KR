---
title: PowerShell을 사용하여 사용자 지정 중요한 정보 유형 제거
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
description: PowerShell을 사용하여 사용자 지정 중요한 정보 유형을 제거하는 방법을 학습
ms.openlocfilehash: 9365eeff6100b16c94b9fa09b06dc51b272b60a6
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2021
ms.locfileid: "59218815"
---
# <a name="remove-a-custom-sensitive-information-type-using-powershell"></a>PowerShell을 사용하여 사용자 지정 중요한 정보 유형 제거



규정 준수 센터 PowerShell에서 사용자 지정 중요한 정보 유형을 제거하는 두 가지 방법이 있습니다.

- **개별 사용자 지정 중요한 정보 유형** 제거: [PowerShell을](sit-modify-a-custom-sensitive-information-type-in-powershell.md#modify-a-custom-sensitive-information-type-using-powershell)사용하여 사용자 지정 중요한 정보 유형 수정에 설명된 방법을 사용합니다. 사용자 지정 중요한 정보 유형이 포함된 사용자 지정 규칙 패키지를 내보내고, XML 파일에서 중요한 정보 유형을 제거하고, 업데이트된 XML 파일을 기존 사용자 지정 규칙 패키지로 다시 가져올 수 있습니다.

- **사용자 지정 규칙 패키지 및 여기에 포함된 모든 사용자 지정 중요한 정보 유형 제거**: 이 방법은 이 섹션에 설명되어 있습니다.

> [!NOTE]
> 사용자 지정 중요한 정보 유형을 제거하기 전에 DLP 정책이나 Exchange 메일 흐름 규칙(전송 규칙이라고도 함)이 중요한 정보 유형을 계속 참조하지 않는 것을 확인합니다.

1. [규정 준수 센터 PowerShell에 연결하기](/powershell/exchange/exchange-online-powershell)

2. 사용자 지정 규칙 패키지를 제거하려면 [Remove-DlpSensitiveInformationTypeRulePackage](/powershell/module/exchange/remove-dlpsensitiveinformationtyperulepackage) cmdlet을 사용합니다.

   ```powershell
   Remove-DlpSensitiveInformationTypeRulePackage -Identity "RulePackageIdentity"
   ```

   Name 값(모든 언어) 또는 `RulePack id` (GUID) 값을 사용하여 규칙 패키지를 식별할 수 있습니다.

   이 예제에서는 "Employee ID Custom Rule Pack"이라는 규칙 패키지를 제거합니다.

   ```powershell
   Remove-DlpSensitiveInformationTypeRulePackage -Identity "Employee ID Custom Rule Pack"
   ```

   구문과 매개 변수에 대한 자세한 내용은 [제거-DlpSensitiveInformationTypeRulePackage](/powershell/module/exchange/remove-dlpsensitiveinformationtyperulepackage)를 참조하세요.

3. 사용자 지정 중요한 정보 유형을 성공적으로 제거했는지 확인하려면 다음 단계를 수행합니다.

   - [DlpSensitiveInformationTypeRulePackage](/powershell/module/exchange/get-dlpsensitiveinformationtyperulepackage) cmdlet을 실행하고 이 규칙 패키지가 더 이상 나열되지 않는지 확인합니다.

     ```powershell
     Get-DlpSensitiveInformationTypeRulePackage
     ```

   - [DlpSensitiveInformationType](/powershell/module/exchange/get-dlpsensitiveinformationtype) cmdlet을 실행하여 제거된 규칙 패키지에서 더 이상 중요한 정보 유형이 나열되지 않는지 확인합니다.

     ```powershell
     Get-DlpSensitiveInformationType
     ```

     사용자 지정 중요한 정보 유형의 경우 게시자 속성 값은 Microsoft Corporation이 아닌 다른 값이 됩니다.

   - \<Name\>(을)를 중요한 정보 유형의 이름 값(예: 직원 ID)으로 바꾸고 [Get-DlpSensitiveInformationType](/powershell/module/exchange/get-dlpsensitiveinformationtype) cmdlet을 실행하여 중요한 정보 유형이 더 이상 나열되지 않는지 확인합니다.

     ```powershell
     Get-DlpSensitiveInformationType -Identity "<Name>"
     ```

## <a name="more-information"></a>추가 정보

- [데이터 손실 방지에 대해 알아보기](dlp-learn-about-dlp.md)

- [중요한 정보 유형 엔터티 정의](sensitive-information-type-entity-definitions.md)

- [DLP 함수가 찾는 항목](what-the-dlp-functions-look-for.md)

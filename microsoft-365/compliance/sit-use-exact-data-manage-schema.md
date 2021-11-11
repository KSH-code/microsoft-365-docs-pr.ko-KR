---
title: 정확한 데이터 일치 Schema 관리
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
ms.date: ''
localization_priority: Normal
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: 정확한 데이터 일치 schema를 편집하거나 제거하는 방법을 배워야 합니다.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 7fb535f08b178cf934ec7586579a00725747a3ce
ms.sourcegitcommit: 8410a49995a084e4cc9b3f7286c8d506b7a85d79
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/11/2021
ms.locfileid: "60914857"
---
# <a name="manage-your-exact-data-match-schema"></a>정확한 데이터 일치 Schema 관리

## <a name="editing-the-schema-for-edm-based-classification-manually"></a>수동으로 EDM 기반 분류에 대한 Schema 편집

EDM 기반 분류에 사용되는 필드를 변경하는 등  EDMedm.xml파일을 변경하려는 경우 다음 단계를 수행합니다.

> [!TIP]
> 구성 가능한 일치를 활용하기 위해 EDM Schema 및 중요한 정보 테이블 원본 파일을 **변경할 수 있습니다.** 구성된 경우, EDM은 항목을 평가할 때 대소문자 차이 및 일부 구분 기호를 무시합니다. 이렇게 하면 XML 스키마와 중요한 데이터 파일을 더 쉽게 정의할 수 있습니다. 자세한 내용은 [caseInsensitive 및 ignoredDelimiters](sit-get-started-exact-data-match-create-schema.md#using-the-caseinsensitive-and-ignoreddelimiters-fields)필드 사용을 참조합니다.

1. 파일 **edm.xml** 편집합니다(정확한 데이터 일치 기반의 중요한 정보 유형에 대한 [Schema](sit-get-started-exact-data-match-create-schema.md#create-the-schema-for-exact-data-match-based-sensitive-information-types)만들기에 설명된 파일).

2. [보안 및 준수 센터 PowerShell](/powershell/exchange/connect-to-scc-powershell)의 연결 절차를 사용하여 보안 및 준수 센터에 연결

3. 데이터베이스 스키마를 업데이트하려면 다음과 같은 cmdlet을 한 번에 하나씩 실행하십시오:

      ```powershell
      $edmSchemaXml=Get-Content .\\edm.xml -Encoding Byte -ReadCount 0
      Set-DlpEdmSchema -FileData $edmSchemaXml -Confirm:$true
      ```

      다음과 같이 확인하라는 메시지가 표시됩니다.

      > 확인
      >
      > 이 작업을 수행하시겠습니까?
      >
      > 'patientrecords' 데이터 저장소의 새로운 EDM 스키마를 업데이트합니다.
      >
      > \[Y\] 예 \[A\] 모두 예 \[N\] 아니요 \[L\] 모두 아니요 \[?\] 도움말(기본값: "Y"):

      > [!TIP]
      > 확인하지 않고 변경 사항을 적용하려면, 3단계에서 Set-DlpEdmSchema -FileData $edmSchemaXml 대신 이 cmdlet을 사용하십시오.

      > [!NOTE]
      > EDMSchema를 추가 사항으로 업데이트하는 데 10~60분이 소요될 수 있습니다. 추가 기능을 사용하는 단계를 실행하기 전에 업데이트가 완료되어야 합니다.->

## <a name="removing-the-schema-for-edm-based-classification-manually"></a>수동으로 EDM 기반 분류에 대한 스마마 제거

EDM 기반 분류에 사용하려는 스마마를 제거하려면 다음 단계를 수행합니다.

1. [보안 및 준수 센터 PowerShell](/powershell/exchange/connect-to-scc-powershell)의 연결 절차를 사용하여 보안 및 준수 센터에 연결

2. 다음 PowerShell cmdlet을 실행하여 "patient records"의 데이터 저장소 이름을 제거할 데이터 저장소 이름으로 변경합니다(예로 patientrecords 저장소 사용).

      ```powershell
      Remove-DlpEdmSchema -Identity 'patientrecords'
      ```

      다음을 확인하라는 메시지가 표시됩니다.

      > 확인
      >
      > 이 작업을 수행하시겠습니까?
      >
      > 'patientrecords' 데이터 저장소의 EDM 스키마를 제거합니다.
      >
      > \[Y\] 예 \[A\] 모두 예 \[N\] 아니요 \[L\] 모두 아니요 \[?\] 도움말(기본값: "Y"):

      > [!TIP]
      >  확인하지 않고 변경 사항을 적용하려면, 2단계에서 Remove-DlpEdmSchema -Identity patientrecords -Confirm:$false 대신 이 cmdlet을 사용하십시오.

### <a name="edit-or-delete-the-edm-schema-with-the-wizard"></a>마법사를 사용하여 EDM schema 편집 또는 삭제

1. 개방형 **준수 센터**  >  **데이터 분류** 정확한 데이터가  >  **일치합니다.**

2. **EDM schemas 를 선택 합니다.**

3. 편집할 EDM SIT를 선택 합니다.

4. **EDM schema 편집 또는** 플라이아웃에서 **EDM schema** 삭제를 선택 합니다.

> [!IMPORTANT]
> 스키마를 제거하려면 해당 스키마가 EDM에 중요한 정보 유형과 이미 연결되어 있는 경우 먼저 EDM에 중요한 정보 유형을 삭제한 후 스키마를 삭제할 수 있습니다.
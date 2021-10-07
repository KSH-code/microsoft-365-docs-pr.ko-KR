---
title: 감사 로그 레코드 내보내기, 구성 및 보기
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
ms.localizationpriority: medium
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: 0d4d0f35-390b-4518-800e-0c7ec95e946c
ms.custom: seo-marvel-apr2020
description: 이 문서에서는 감사 로그 레코드를 내보내고 구성하고 보는 Microsoft 365 있습니다.
ms.openlocfilehash: 630a40652d6208aba465961f2e414e331b78ab0c
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60201172"
---
# <a name="export-configure-and-view-audit-log-records"></a>감사 로그 레코드 내보내기, 구성 및 보기

감사 로그를 검색하고 검색 결과를 CSV 파일로 다운로드한 후 파일에는 각 이벤트에 대한 추가 정보가 포함된 **AuditData** 열이 포함되어 있습니다. 이 열의 데이터는 *property:value* 쌍으로 구성된 여러 속성이 들어 있는 JSON 개체로 서식이 설정됩니다. **AuditData** 열의 JSON 개체에 있는 각 속성을 여러 열로 분할하여 각 속성에 자체 열을 Excel 쿼리 편집기에서 JSON 변환 기능을 사용할 수 있습니다. 이렇게 하면 이러한 속성 중 하나 이상을 정렬하고 필터링할 수 있으며, 이를 통해 원하는 특정 감사 데이터를 빠르게 찾을 수 있습니다.

## <a name="step-1-export-audit-log-search-results"></a>1단계: 감사 로그 검색 결과 내보내기

첫 번째 단계는 감사 로그를 검색한 다음 결과를 CSV(콤보로 구분된 값) 파일로 로컬 컴퓨터로 내보내는 것입니다.
  
1. 감사 로그 [검색을 실행하고](search-the-audit-log-in-security-and-compliance.md#search-the-audit-log) 필요한 경우 원하는 결과가 표시될 때까지 검색 기준을 다시 정의합니다.

2. 결과 **내보내기 를** 클릭하고 모든 결과 **다운로드를 선택합니다.** 

   ![모든 결과 다운로드를 클릭합니다.](../media/ExportAuditSearchResults.png)

   이 옵션은 1단계에서 시작한 감사 로그 검색에서 모든 감사 레코드를 내보내고 감사 로그에서 CSV 파일로 원시 데이터를 다운로드하는 옵션입니다. 

   창 아래쪽에 CSV 파일을 열거나 저장할지 묻는 메시지가 표시됩니다. 

3. 다른 **> 저장을** 클릭하고 CSV 파일을 로컬 컴퓨터에 저장합니다. 많은 검색 결과를 다운로드하는 데는 시간이 오래 걸리게 됩니다. 일반적으로 모든 활동 또는 광범위한 날짜 범위를 검색할 때 이 경우에 해당합니다. CSV 파일 다운로드가 완료되면 창 아래쪽에 메시지가 표시됩니다.

   ![CSV 파일 다운로드가 완료될 때 표시되는 메시지입니다.](../media/ExportAuditSearchResultsFinish.png)

> [!NOTE]
  > 단일 감사 로그 검색에서 최대 50,000의 항목을 CSV 파일로 다운로드할 수 있습니다. 50,000개의 항목이 CSV 파일로 다운로드되면 검색 조건에 맞는 이벤트가 50,000개 이상 있다고 가정할 수 있습니다. 이 제한을 초과하여 내보내기하려면 날짜 범위를 사용하여 감사 로그 레코드 수를 줄이려고 합니다. 50,000개 이상의 항목을 내보내기 위해 더 작은 날짜 범위로 여러 번 검색을 실행해야 할 수 있습니다.

## <a name="step-2-format-the-exported-audit-log-using-the-power-query-editor"></a>2단계: 파워 쿼리 편집기를 사용하여 내보낼 감사 로그 서식 지정

다음 단계는 Power Query Editor의 JSON 변환 기능을 사용하여 Excel 열에 있는 JSON 개체의  각 속성을 자체 열로 분할하는 것입니다. 그런 다음 열을 필터링하여 특정 속성의 값에 따라 레코드를 볼 수 있습니다. 이를 통해 원하는 특정 감사 데이터를 빠르게 찾을 수 있습니다.

1. 2019년 또는 2019년 Excel Office 365 Excel 통합 문서의 새 통합 Excel 2016.

2. 데이터 **탭의** 데이터 변환 데이터 **&** 그룹에서 **텍스트/CSV 를 클릭합니다.**

    ![데이터 탭에서 텍스트/CSV를 클릭합니다.](../media/JSONTransformOpenCSVFile.png)

3. 1단계에서 다운로드한 CSV 파일을 열 수 있습니다.

4. 표시되는 창에서 데이터 **변환을 클릭합니다.**

   ![데이터 변환을 클릭합니다.](../media/JSONOpenPowerQuery.png)

   CSV 파일이 쿼리 **편집기 에서 열립니다.** 열에는 **CreationDate,** **UserIds,** **Operations** 및 **AuditData의** 네 개의 열이 있습니다. **AuditData 열은** 여러 속성을 포함하는 JSON 개체입니다. 다음 단계에서는 JSON 개체의 각 속성에 대한 열을 만듭니다.

5. **AuditData** 열에서 제목을 마우스 오른쪽 단추로 클릭하고 **변환을** 클릭한 다음 **JSON 을 클릭합니다.** 

   ![AuditData 열을 마우스 오른쪽 단추로 클릭하고 변환을 클릭한 다음 JSON을 선택합니다.](../media/JSONTransform.png)

6. **AuditData** 열의 오른쪽 위 모서리에서 확장 아이콘을 클릭합니다.

   ![AuditData 열에서 확장 아이콘을 클릭합니다.](../media/JSONTransformExpandIcon.png)

   **AuditData** 열의 JSON 개체에 있는 속성의 일부 목록이 표시됩니다.

7. 자세한 **정보 로드를** 클릭하여 **AuditData** 열의 JSON 개체에 있는 모든 속성을 표시합니다.

   ![JSON 개체의 모든 속성을 표시하려면 더 로드를 클릭합니다.](../media/JSONTransformLoadJSONProperties.png)

   포함하지 않는 속성 옆의 확인란을 선택하지 않습니다. 조사에 유용하지 않은 열을 제거하면 감사 로그에 표시되는 데이터 양을 줄이는 것이 좋습니다. 

   > [!NOTE]
   > 이전 스크린샷에 표시된 JSON 속성(더 로드를 클릭한 후)은 CSV 파일의 처음 1,000개 행에서 **AuditData** 열에 있는 속성을 기반으로 합니다.  처음 1,000개 행 다음에 레코드에 서로 다른 JSON 속성이 있는 경우 **AuditData** 열이 여러 열로 분할될 때 이러한 속성과 해당 열이 포함되지 않습니다. 이를 방지하려면 감사 로그 검색을 다시 실행하고 반환되는 레코드 수를 줄이면 검색 조건을 좁힐 수 있습니다. 또 다른 해결 작업은 **AuditData** 열에서 JSON 개체를 변환하기 전에 위의 5단계를 수행하기 전에 **Operations** 열의 항목을 필터링하여 행 수를 줄이는 것입니다.

   > [!TIP]
   > AuditData.AffectedItems와 같은 목록 내에서 특성을 보려면  특성을 끌어올 열의 오른쪽 위 모서리에 있는 확장 아이콘을 클릭한 다음 새 행으로 확장을 **선택합니다.**  이 목록에서 레코드가 표시되고 열의 오른쪽 위 모서리에 있는 확장 아이콘을 클릭하고 특성을 확인한 다음 보거나 추출할 레코드를 선택할 수 있습니다. 

8. 선택한 각 JSON 속성에 대해 추가된 열의 제목 서식을 지정하기 위해 다음 중 하나를 선택합니다.

    - JSON 속성의 이름을 열 이름으로 사용하기 위해 원래 열 이름을 **prefix로** 사용 확인란의 선택을 언합니다. 예를 들어 **RecordType 또는** **SourceFileName입니다.**

    - 열 이름에 AuditData prefix를 추가하기 위해 원래 열 이름을 **prefix로** 사용 확인란을 선택된 그대로 두고, 열 이름에 AuditData를 추가합니다. 예를 들어 **AuditData.RecordType 또는** **AuditData.SourceFileName입니다.**

9. **확인** 을 클릭합니다.

    **AuditData 열은** 여러 열로 분할됩니다. 각 새 열은 AuditData JSON 개체의 속성에 해당합니다. 열의 각 행에는 속성 값이 들어 있습니다. 속성에 값이 없는 경우 *null* 값이 표시됩니다. 이 Excel 값이 null인 셀은 비어 있습니다.
  
10. 홈 **탭에서** 로드  & 닫기를 클릭하여 파워 쿼리 편집기를 닫고 변환된 CSV 파일을 통합 문서의 Excel 니다.

## <a name="use-powershell-to-search-and-export-audit-log-records"></a>PowerShell을 사용하여 감사 로그 레코드 검색 및 내보내기

Microsoft 365 규정 준수 센터 감사 로그 검색 도구를 사용하는 대신 Exchange Online PowerShell에서 [Search-UnifiedAuditLog](/powershell/module/exchange/search-unifiedauditlog) cmdlet을 사용하여 감사 로그 검색 결과를 CSV 파일로 내보낼 수 있습니다. 그런 다음 2단계에 설명된 절차에 따라 Power Query 편집기를 사용하여 감사 로그의 형식을 지정합니다. PowerShell cmdlet을 사용할 때의 한 가지 이점은 *RecordType* 매개 변수를 사용하여 특정 서비스에서 이벤트를 검색할 수 있는 것입니다. 다음은 PowerShell을 사용하여 감사 레코드를 CSV 파일로 내보내는 몇 가지 예로, Power Query 편집기를 사용하여 2단계에 설명된 바와 같이 **AuditData** 열의 JSON 개체를 변환할 수 있습니다.

이 예제에서는 다음 명령을 실행하여 공유 작업과 관련된 SharePoint 반환합니다.

```powershell
$auditlog = Search-UnifiedAuditLog -StartDate 06/01/2019 -EndDate 06/30/2019 -RecordType SharePointSharingOperation
```

```powershell
$auditlog | Select-Object -Property CreationDate,UserIds,RecordType,AuditData | Export-Csv -Path c:\AuditLogs\PowerShellAuditlog.csv -NoTypeInformation
```

검색 결과는 CreationDate, UserIds, RecordType, AuditData의 네 개의 열을 포함하는 *PowerShellAuditlog라는* CSV 파일로 내보낼 수 있습니다.

레코드 형식의 이름 또는 열어 값도 *RecordType* 매개 변수의 값으로 사용할 수 있습니다. 레코드 유형 이름 및 해당 열문 값 목록은 관리 활동 API Office 365 *AuditLogRecordType* [테이블을 참조하세요.](/office/office-365-management-api/office-365-management-activity-api-schema#enum-auditlogrecordtype---type-edmint32)

*RecordType* 매개 변수에는 단일 값만 포함할 수 있습니다. 다른 레코드 유형에 대한 감사 레코드를 검색하기 위해 이전의 두 명령을 다시 실행하여 다른 레코드 유형을 지정하고 원본 CSV 파일에 해당 결과를 추가해야 합니다. 예를 들어 다음 두 명령을 실행하여 동일한 날짜 범위의 SharePoint 파일 활동을 파일 PowerShellAuditlog.csv 합니다.

```powershell
$auditlog = Search-UnifiedAuditLog -StartDate 06/01/2019 -EndDate 06/30/2019 -RecordType SharePointFileOperation
```

```powershell
$auditlog | Select-Object -Property CreationDate,UserIds,RecordType,AuditData | Export-Csv -Append -Path c:\AuditLogs\PowerShellAuditlog.csv -NoTypeInformation
```

## <a name="tips-for-exporting-and-viewing-the-audit-log"></a>팁 로그를 내보내고 보는 데 사용할 수 있는 사용자 수

다음은 JSON 변환 기능을 사용하여 **AuditData** 열을 여러 열로 분할하기 전과 후에 감사 로그를 내보내고 보는 몇 가지 팁과 예입니다.

- **RecordType 열을 필터링하여** 특정 서비스 또는 기능 영역의 레코드만 표시합니다. 예를 들어 SharePoint 공유와 관련된 이벤트를 표시하려면 **14(공유** 활동에서 트리거된 레코드의 열 SharePoint 선택합니다. **RecordType** 열에 표시되는 열 열 값에 해당하는 서비스 목록은 감사 로그의 [자세한 속성을 참조하세요.](detailed-properties-in-the-office-365-audit-log.md)

- 작업 **열을 필터링하여** 특정 작업에 대한 레코드를 표시합니다. 감사 로그 검색 도구의 감사 로그 검색 도구에서 검색 가능한 작업에 해당하는 대부분의 작업 Microsoft 365 규정 준수 센터 감사 로그 검색의 "감사된 활동" [섹션을 참조하세요.](search-the-audit-log-in-security-and-compliance.md#audited-activities)

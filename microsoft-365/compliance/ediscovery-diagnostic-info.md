---
title: EDiscovery 진단 정보 수집
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.custom:
- seo-marvel-apr2020
description: Microsoft 지원 사례에 대 한 eDiscovery 진단 정보를 수집 하는 방법에 대해 알아봅니다.
ms.openlocfilehash: 107309748e2f27b50be5f8e8fc76afcb693989f9
ms.sourcegitcommit: dab50e1cc5bba920720b80033c93457f5ca1c330
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/07/2020
ms.locfileid: "48944399"
---
# <a name="collect-ediscovery-diagnostic-information"></a>EDiscovery 진단 정보 수집

Microsoft 기술 지원 엔지니어가 핵심 eDiscovery 또는 고급 eDiscovery와 관련 된 지원 사례를 열 때 발생 하는 문제에 대 한 특정 정보가 필요한 경우가 있습니다. 이 문서에서는 엔지니어가 문제를 조사 하 고 해결할 수 있도록 진단 정보를 수집 하는 방법에 대 한 지침을 제공 합니다. 일반적으로 Microsoft 지원 엔지니어가이 정보를 수집할 필요가 없습니다.

> [!IMPORTANT]
> 이 문서에서 설명 하는 cmdlet 및 진단 정보의 출력에는 조직의 소송 또는 내부 조사에 대 한 중요 한 정보가 포함 될 수 있습니다. Microsoft 지원에 원시 진단 정보를 보내기 전에 정보를 검토 하 고 중요 한 정보 (예: 이름 또는 파티에 대 한 기타 정보)를 교체 하 여 소송 또는 조사로 교정 해야 합니다 `XXXXXXX` . 이 방법을 사용 하는 경우 해당 정보가 redacted Microsoft 지원 엔지니어 에게도 제공 됩니다.

## <a name="collect-diagnostic-information-for-core-ediscovery"></a>핵심 eDiscovery에 대 한 진단 정보 수집

핵심 eDiscovery에 대 한 진단 정보 수집은 cmdlet 기반 이므로 보안 & 준수 센터 PowerShell을 사용 해야 합니다. 다음 PowerShell 예제에서는 cmdlet을 실행 한 다음 지정 된 텍스트 파일에 출력을 저장 합니다. 대부분의 지원 사례에서는 다음 명령 중 하나를 실행 해야 합니다.

다음 cmdlet을 실행 하려면 [보안 & 준수 센터 </span> PowerShell에 연결](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell)합니다. 연결 되 면 다음 명령 중 하나 이상을 실행 하 고 자리 표시자를 실제 개체 이름으로 바꿉니다.

생성 된 텍스트 파일을 검토 한 후 중요 한 정보를 redacting Microsoft 고객 지원 엔지니어에 게 보냅니다.

> [!NOTE]
> 이 섹션의 명령을 실행 하 여 Microsoft 365 준수 센터의 **콘텐츠 검색** 페이지에 나열 된 검색 및 내보내기에 대 한 진단 정보를 수집할 수도 있습니다.

### <a name="collect-information-about-searches"></a>검색에 대 한 정보 수집

다음 명령은 중요 eDiscovery 사례와 연결 된 검색 또는 콘텐츠 검색 관련 문제를 조사할 때 유용한 정보를 수집 합니다.

```powershell
Get-ComplianceSearch "<Search name>" | FL > "ComplianceSearch.txt"
```

### <a name="collect-information-about-search-actions"></a>검색 작업에 대 한 정보 수집

다음 명령은 중요 eDiscovery 사례와 연결 된 콘텐츠 검색 또는 검색 결과를 미리 보거나 내보내거나 삭제 하 여 문제를 조사 하기 위한 정보를 수집 합니다. **내보내기 탭에** 나열 된 내보내기를 클릭 하 여 검색 작업의 이름을 확인할 수 있습니다. 미리 보기 및 지우기 작업의 이름을 확인 하려면 **new-compliancesearchaction** cmdlet을 실행 하 여 모든 작업 목록을 표시할 수 있습니다. 검색 작업 이름의 형식은 `_Preview` `_Export` `_Purge` 해당 검색의 이름에 추가, 또는 이름을 통해 생성 됩니다.

```powershell
Get-ComplianceSearchAction "<Search action name>" | FL > "ComplianceSearchAction.txt"
```

### <a name="collect-information-about-ediscovery-holds"></a>EDiscovery 보류에 대 한 정보 수집

핵심 eDiscovery 사례와 연결 된 eDiscovery 보류가 예상 대로 작동 하지 않는 경우 다음 명령을 실행 하 여 eDiscovery 보존에 대 한 케이스 보류 정책 및 관련 케이스 보류 규칙에 대 한 정보를 수집 합니다. 다음 명령에 포함 된 *서비스 케이스 보류 정책 이름은* eDiscovery 보류의 이름과 동일 합니다. 이 이름은 핵심 eDiscovery 사례의 **보류** 탭에서 확인할 수 있습니다.

```powershell
Get-CaseHoldPolicy "<Case hold policy name>" | %{"--CaseHoldPolicy--";$_|FL;"--CaseHoldRule--";Get-CaseHoldRule -Policy $_.Name | FL} > "eDiscoveryCaseHold.txt"
```

### <a name="collect-all-case-information"></a>모든 사례 정보 수집

Microsoft 지원 서비스에서 문제를 조사 하는 데 필요한 정보가 명확 하지 않을 수 있습니다. 이러한 상황에서는 핵심적인 eDiscovery 사례에 대 한 모든 진단 정보를 수집할 수 있습니다. 다음 명령의 *핵심 ediscovery 사례 이름은* Microsoft 365 준수 센터의 **핵심 ediscovery** 페이지에 표시 되는 사례 이름과 동일 합니다.

```powershell
Get-ComplianceCase "<Core eDiscovery case name>"| %{"$($_.Name)";"`t==Searches==";Get-ComplianceSearch -Case $_.Name | FL;"`t==Search Actions==";Get-ComplianceSearchAction -Case $_.Name |FL;"`t==Holds==";Get-CaseHoldPolicy -Case $_.Name | %{$_|FL;"`t`t ==$($_.Name) Rules==";Get-CaseHoldRule -Policy $_.Name | FL}} > "eDiscoveryCase.txt"
```

## <a name="collect-diagnostic-information-for-advanced-ediscovery"></a>고급 eDiscovery에 대 한 진단 정보 수집

고급 eDiscovery 사례의 **설정** 탭에서는 사례에 대 한 진단 정보를 빠르게 복사할 수 있습니다. 진단 정보는 클립보드에 저장 되므로 텍스트 파일에 붙여 넣고 Microsoft 지원으로 보낼 수 있습니다.

1. 로 이동한 [https://compliance.microsoft.com](https://compliance.microsoft.com/) 다음 **모두 표시 > EDiscovery > 고급** 을 클릭 합니다.

2. 사례를 선택 하 고 **설정** 탭을 클릭 합니다.

3. **사례 정보** 에서 **선택을** 클릭 합니다.

4. 플라이 아웃 페이지에서 **진단 정보 복사** 를 클릭 하 여 정보를 클립보드로 복사 합니다.

5. 메모장에서 텍스트 파일을 열고 텍스트 파일에 정보를 붙여 넣습니다.

6. 텍스트 파일을 저장 하 고 이름을 해당 이름 `AeD Diagnostic Info YYYY.MM.DD` (예:)으로 변경 `AeD Diagnostic Info 2020.11.03` 합니다.

파일을 검토 한 후 중요 한 정보를 redacting Microsoft 고객 지원 엔지니어가 해당 사례를 사용 하 게 됩니다.

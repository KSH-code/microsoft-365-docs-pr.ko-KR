---
title: eDiscovery 진단 정보 수집
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
description: Microsoft 지원 사례에 대한 eDiscovery 진단 정보를 수집하는 방법에 대해 자세히 알아보습니다.
ms.openlocfilehash: 107309748e2f27b50be5f8e8fc76afcb693989f9
ms.sourcegitcommit: dab50e1cc5bba920720b80033c93457f5ca1c330
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/07/2020
ms.locfileid: "48944399"
---
# <a name="collect-ediscovery-diagnostic-information"></a>eDiscovery 진단 정보 수집

경우에 따라 Microsoft 지원 엔지니어가 Core eDiscovery 또는 Advanced eDiscovery와 관련된 지원 사례를 열 때 해당 문제와 관련된 특정 정보를 요구합니다. 이 문서에서는 지원 엔지니어가 문제를 조사하고 해결하는 데 도움이 되는 진단 정보를 수집하는 방법에 대한 지침을 제공합니다. 일반적으로 Microsoft 기술 지원 엔지니어에게 요청이 제공될 때까지는 이 정보를 수집할 필요가 없습니다.

> [!IMPORTANT]
> 이 문서에 설명된 cmdlet 및 진단 정보의 출력에는 조직의 소송 또는 내부 조사에 대한 중요한 정보가 포함되어 있을 수 있습니다. Microsoft 지원에 원시 진단 정보를 보내기 전에 정보를 검토하고 중요한 정보(예: 소송 또는 조사 당사자에 대한 이름 또는 기타 정보)를 대체하여 이를 재배치해야 `XXXXXXX` 합니다. 또한 이 방법을 사용하면 Microsoft 기술 지원 엔지니어에게 정보가 업데이트된 것으로 표시됩니다.

## <a name="collect-diagnostic-information-for-core-ediscovery"></a>Core eDiscovery에 대한 진단 정보 수집

Core eDiscovery에 대한 진단 정보를 수집하는 것은 cmdlet 기반이기 때문에 보안 및 준수 & PowerShell을 사용해야 합니다. 다음 PowerShell 예제에서는 cmdlet을 실행한 다음 출력을 지정된 텍스트 파일에 저장합니다. 대부분의 지원 사례에서는 이러한 명령 중 하나만 실행하면 됩니다.

다음 cmdlet을 실행하기 위해 보안 및 준수 [& PowerShell에 연결합니다. </span> ](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell) 연결한 후 다음 명령 중 하나 이상을 실행하고 개체 HOLDERS를 실제 개체 이름으로 바꾸어야 합니다.

생성된 텍스트 파일을 검토하고 중요한 정보를 편집한 후 사례에 대해 작업하는 Microsoft 기술 지원 엔지니어에게 전송합니다.

> [!NOTE]
> 이 섹션의 명령을 실행하여 Microsoft 365 규정 준수 센터의  콘텐츠 검색 페이지에 나열된 검색 및 내보내기에 대한 진단 정보를 수집할 수도 있습니다.

### <a name="collect-information-about-searches"></a>검색에 대한 정보 수집

다음 명령은 콘텐츠 검색 또는 Core eDiscovery 사례와 관련된 검색과 관련된 문제를 조사할 때 유용한 정보를 수집합니다.

```powershell
Get-ComplianceSearch "<Search name>" | FL > "ComplianceSearch.txt"
```

### <a name="collect-information-about-search-actions"></a>검색 작업에 대한 정보 수집

다음 명령은 콘텐츠 검색 또는 Core eDiscovery 사례와 연결된 검색의 결과 미리 보기, 내보내기 또는 제거와 관련된 문제를 조사하기 위해 정보를 수집합니다. 내보내기 탭에 나열된 내보내기를 클릭하여 검색 작업의 이름을 **식별할 수** 있습니다. 미리 보기 및 삭제 작업의 이름을 식별하기 위해 **Get-ComplianceSearchAction** cmdlet을 실행하여 모든 작업 목록을 표시할 수 있습니다. 검색 작업 이름의 형식은 해당 검색의 이름을 추가하거나 추가하여 `_Preview` `_Export` `_Purge` 생성됩니다.

```powershell
Get-ComplianceSearchAction "<Search action name>" | FL > "ComplianceSearchAction.txt"
```

### <a name="collect-information-about-ediscovery-holds"></a>eDiscovery 보류에 대한 정보 수집

Core eDiscovery 사례와 연결된 eDiscovery 보류가 예상대로 작동하지 않는 경우 다음 명령을 실행하여 eDiscovery 보류에 대한 케이스 보류 정책 및 관련 케이스 보류 규칙에 대한 정보를 수집합니다. 다음 *명령의* 케이스 보류 정책 이름은 eDiscovery 보류의 이름과 같습니다. Core eDiscovery  사례의 보류 탭에서 이 이름을 식별할 수 있습니다.

```powershell
Get-CaseHoldPolicy "<Case hold policy name>" | %{"--CaseHoldPolicy--";$_|FL;"--CaseHoldRule--";Get-CaseHoldRule -Policy $_.Name | FL} > "eDiscoveryCaseHold.txt"
```

### <a name="collect-all-case-information"></a>모든 사례 정보 수집

Microsoft 지원 서비스에서 문제를 조사하는 데 필요한 정보가 분명하지 않은 경우도 있습니다. 이 경우 Core eDiscovery 사례에 대한 모든 진단 정보를 수집할 수 있습니다. 다음 *명령의 Core eDiscovery* 사례 이름은 Microsoft 365 규정 준수 센터의 **Core eDiscovery** 페이지에 표시되는 사례의 이름과 동일합니다.

```powershell
Get-ComplianceCase "<Core eDiscovery case name>"| %{"$($_.Name)";"`t==Searches==";Get-ComplianceSearch -Case $_.Name | FL;"`t==Search Actions==";Get-ComplianceSearchAction -Case $_.Name |FL;"`t==Holds==";Get-CaseHoldPolicy -Case $_.Name | %{$_|FL;"`t`t ==$($_.Name) Rules==";Get-CaseHoldRule -Policy $_.Name | FL}} > "eDiscoveryCase.txt"
```

## <a name="collect-diagnostic-information-for-advanced-ediscovery"></a>Advanced eDiscovery에 대한 진단 정보 수집

Advanced  eDiscovery 사례의 설정 탭을 사용하면 사례에 대한 진단 정보를 빠르게 복사할 수 있습니다. 진단 정보는 클립보드에 저장되어 텍스트 파일에 붙여넣고 Microsoft 지원에 보낼 수 있습니다.

1. Go to [https://compliance.microsoft.com](https://compliance.microsoft.com/) and then click Show all > **eDiscovery > Advanced.**

2. 사례를 선택하고 설정 **탭을** 클릭합니다.

3. 사례 **정보에서** 선택을 **클릭합니다.**

4. 플라이아웃 페이지에서 진단 **정보** 복사를 클릭하여 정보를 클립보드에 복사합니다.

5. 메모장에서 텍스트 파일을 연 다음 텍스트 파일에 정보를 붙여 넣습니다.

6. 텍스트 파일을 저장하고 예를 들어 다음과 같이 이름을 `AeD Diagnostic Info YYYY.MM.DD` `AeD Diagnostic Info 2020.11.03` 지정합니다.

파일을 검토하고 중요한 정보를 시정하는 Microsoft 기술 지원 엔지니어에게 전송합니다.

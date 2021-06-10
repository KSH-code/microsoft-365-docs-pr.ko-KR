---
title: Microsoft Defender for Office 365
f1.keywords:
- NOCSH
ms.author: dansimp
author: MSFTTracyp
manager: dansimp
audience: ITPro
ms.topic: article
ms.date: 05/05/2021
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: 탐색기 또는 실시간 검색을 사용하여 위협을 효율적으로 조사하고 대응합니다.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 7ab7b5731d121106d930868b03330d4ac7befd77
ms.sourcegitcommit: de5fce90de22ba588e75e1a1d2e87e03b9e25ec7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/10/2021
ms.locfileid: "52300218"
---
# <a name="threat-explorer-and-real-time-detections-basics"></a>위협 탐색기 및 실시간 감지 기본 정보

이 문서의 내용

- [위협 탐색기 및 실시간 검색 간의 차이점](#differences-between-threat-explorer-and-real-time-detections)<br/>
- [필수 라이선스 및 사용 권한](#required-licenses-and-permissions)

> [!NOTE]
> 이 문서는 위협 탐색기(탐색기) **,** 전자 메일 보안 및 **탐색기** 및 실시간 검색 기본(예: 도구 간 차이점 및 작동에 필요한 사용 권한)에 대한 **3개** 문서 시리즈의 일부입니다.  이 시리즈의 다른 두 문서는 위협 탐색기에서 위협 [헌팅](threat-hunting-in-threat-explorer.md) 및 위협 탐색기를 사용하는 전자 메일 [보안입니다.](email-security-in-microsoft-defender.md)

이 문서에서는 위협 탐색과 실시간 검색 보고 간의 차이점과 필요한 라이선스 및 사용 권한에 대해 설명합니다.

**적용 대상**
- [Office 365용 Microsoft Defender 플랜 1 및 플랜 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

조직에 microsoft [Defender for Office 365](defender-for-office-365.md)권한이 있는 경우 [](#required-licenses-and-permissions)위협 탐색기(탐색기) 또는 실시간  검색을 사용하여 위협을 감지하고 치료할 수 있습니다. 

보안 & 준수 센터에서 위협 **관리로** 이동한 다음   탐색기 또는 실시간 검색  **을 선택 합니다.**

<br>

****

|Microsoft Defender for Office 365 요금제 2를 사용하면 다음을 볼 수 있습니다.|Microsoft Defender for Office 365 요금제 1을 사용하면 다음을 볼 수 있습니다.|
|---|---|
|![위협 탐색기](../../media/threatmgmt-explorer.png)|![실시간 탐지](../../media/threatmgmt-realtimedetections.png)|
|

다음 도구를 사용하여 다음을 수행할 수 있습니다.

- 보안 기능에서 검색된 맬웨어를 Microsoft 365 참조합니다.
- 피싱 URL을 보고 판정 데이터를 클릭합니다.
- 탐색기 보기에서 자동화된 조사 및 응답 프로세스를 시작하십시오.
- 악성 전자 메일 조사 등

자세한 내용은 [위협 탐색기를 사용하여 전자 메일 보안을 참조하세요.](email-security-in-microsoft-defender.md)

## <a name="differences-between-threat-explorer-and-real-time-detections"></a>위협 탐색기 및 실시간 검색 간의 차이점

- *실시간 검색은* 계획 1에 대한 Defender에서 Office 365 보고 도구입니다. *위협 탐색기는* 계획 2용 Defender에서 사용할 수 있는 위협 Office 365 도구입니다.
- 실시간 검색 보고서를 사용하면 검색을 실시간으로 볼 수 있습니다. 위협 탐색기도 이 작업을 수행하지만 공격 캠페인 강조 표시와 같은 특정 공격에 대한 추가 세부 정보를 제공하며 보안 운영 팀에 위협을 수정하는 기능을 제공합니다(자동화된 조사 및 대응 조사 트리거 [포함).](automated-investigation-response-office.md)
- 모든 *전자 메일* 보기는 위협 탐색기에서 사용할 수 있지만 실시간 검색 보고서에는 포함되지 않습니다.
- 다양한 필터링 기능 및 수정 작업이 위협 탐색기에 포함되어 있습니다. 자세한 내용은 [Microsoft Defender for Office 365 Service Description: Feature availability across Defender for Office 365 참조하세요.](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#feature-availability-across-advanced-threat-protection-atp-plans)

## <a name="required-licenses-and-permissions"></a>필수 라이선스 및 사용 권한

탐색기 또는 실시간 Office 365 사용하려면 Microsoft [Defender가](defender-for-office-365.md) 있어야 합니다.

- 그러나 Explorer는 요금제 2용 Defender에만 Office 365 포함되어 있습니다.
- 실시간 검색 보고서는 Plan 1의 Defender에 Office 365 포함되어 있습니다.

보안 운영 팀은 사용자에 대해 Defender를 통해 보호해야 하는 모든 사용자에 대해 Office 365 탐색기 및 실시간 검색에 사용이 허가된 사용자의 검색 데이터가 표시되어 있어야 합니다.

탐색기 또는  실시간 검색을 보고 사용하려면 다음이 있어야 합니다.

- 보안 및 준수 &:

  - 조직 관리
  - 보안 관리자(Azure Active Directory 관리 센터에서 할당할 수 있습니다. <https://aad.portal.azure.com> )
  - 보안 읽기 권한자

- 다음 Exchange Online:

  - 조직 관리
  - 보기 전용 조직 관리
  - 보기 전용 받는 사람
  - 준수 관리

역할 및 사용 권한에 대한 자세한 내용은 다음 리소스를 참조합니다.

- [보안 및 준수 센터의 사용 권한](permissions-in-the-security-and-compliance-center.md)
- [Exchange Online의 기능 사용 권한](/exchange/permissions-exo/feature-permissions)
- [Exchange Online PowerShell](/powershell/exchange/exchange-online-powershell)

## <a name="more-information"></a>추가 정보
- [위협 탐색기는 전자 메일 엔터티 페이지에서 전자 메일 세부 정보를 수집합니다.](mdo-email-entity-page.md)
- [배달된 악성 전자 메일 찾기 및 조사](investigate-malicious-email-that-was-delivered.md)
- [SharePoint Online, OneDrive 및 파일에서 검색된 악성 Microsoft Teams](mdo-for-spo-odb-and-teams.md)
- [위협 방지 상태 보고서](view-email-security-reports.md#threat-protection-status-report)
- [Microsoft Threat Protection의 자동화된 조사 및 대응](automated-investigation-response-office.md)
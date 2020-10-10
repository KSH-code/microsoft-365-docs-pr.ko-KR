---
title: Microsoft Threat Protection의 고급 구하기 쿼리 결과에 대해 작업 수행
description: 고급 구하기 쿼리 결과에서 위협과 영향을 받는 자산에 빠르게 주소 만들기
keywords: 고급 구하기, 위협 검색, 사이버 위협 사냥, microsoft threat protection, microsoft 365, mtp, m365, search, query, 원격 분석, 작업 수행
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365-initiative-m365-defender
ms.topic: article
ms.openlocfilehash: 3d2df325198c420cb2444a74b6c3507657355012
ms.sourcegitcommit: 5e1b8c959a081022826fb09358730096248507ed
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/09/2020
ms.locfileid: "48412097"
---
# <a name="take-action-on-advanced-hunting-query-results"></a>고급 구하기 쿼리 결과에 대해 작업 수행

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**적용 대상:**
- Microsoft 위협 방지

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

강력 하 고 종합적인 작업 옵션을 사용 하 여 [고급 구하기](advanced-hunting-overview.md) 에서 찾은 위협과 공격에 노출 된 자산을 빠르게 포함할 수 있습니다. 이러한 옵션을 사용 하 여 다음을 수행할 수 있습니다.

- 장치에서 다양 한 작업 수행
- 파일 격리

## <a name="required-permissions"></a>필요한 사용 권한
고급 구하기를 통해 조치를 취할 수 있으려면 [장치에 대 한 재구성 작업을 제출할](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/user-roles#permission-options)수 있는 권한이 있는 MICROSOFT Defender ATP 역할이 필요 합니다. 작업을 수행할 수 없는 경우 전역 관리자에 게 다음 사용 권한을 부여 하는 것에 대해 문의 하세요.

*활성 수정 작업 > 위협 및 취약성 관리-업데이트 관리 처리*

## <a name="take-various-actions-on-devices"></a>장치에서 다양 한 작업 수행
쿼리 결과에서 열로 식별 되는 장치에 대해 다음 작업을 수행할 수 있습니다 `DeviceId` .

- 영향을 받는 장치를 감염을 포함 하거나 공격을 이동 하지 못하도록 차단 laterally
- 자세한 법적 정보를 얻기 위한 조사 패키지 수집
- 최신 보안 인텔리전스 업데이트를 사용 하 여 위협 검색 및 제거를 위한 바이러스 검사 실행
- 장치 및 기타 영향을 받는 장치에서 위협을 확인 하 고 수정 하는 자동화 된 조사 시작
- 앱 실행을 Microsoft 서명 된 실행 파일로 제한 하 여 맬웨어 또는 기타 신뢰할 수 없는 실행 파일을 통한 위협 작업을 방지 합니다.

이러한 응답 작업을 Microsoft Defender ATP를 통해 수행 하는 방법에 대 한 자세한 내용은 [장치에 대 한 응답 작업 정보를 참조](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts)하세요.
   
## <a name="quarantine-files"></a>파일 격리
파일에 *격리* 작업을 배포 하 여 오류가 발생 하면 자동으로 격리 되도록 할 수 있습니다. 이 작업을 선택할 때 다음 열 중에서 선택 하 여 쿼리 결과에서 격리 될 파일을 식별할 수 있습니다.

- `SHA1` — 대부분의 고급 구하기 테이블에서이는 기록 된 작업의 영향을 받은 파일의 SHA-1입니다. 예를 들어 파일을 복사한 경우 복사한 파일을 복사 합니다.
- `InitiatingProcessSHA1` — 대부분의 고급 구하기 테이블에서 기록 된 작업 시작을 담당 하는 파일입니다. 예를 들어 하위 프로세스가 시작 된 경우 상위 프로세스입니다. 
- `SHA256` -열로 식별 되는 파일에 해당 하는 SHA-256입니다 `SHA1` .
- `InitiatingProcessSHA256` -열로 식별 되는 파일에 해당 하는 SHA-256입니다 `InitiatingProcessSHA1` .

격리 작업을 수행 하는 방법과 파일을 복원 하는 방법에 대 한 자세한 내용은 [파일에 대 한 응답 작업 정보를 참조](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/respond-file-alerts)하세요.

>[!NOTE]
>파일을 찾아 격리 하기 위해 쿼리 결과에 `DeviceId` 장치 식별자로 값도 포함 해야 합니다.  

## <a name="take-action"></a>작업 수행
설명 된 작업을 수행 하려면 쿼리 결과에서 하나 이상의 레코드를 선택 하 고 **작업 수행**을 선택 합니다. 마법사는 원하는 작업을 선택 하 여 전송 하는 프로세스를 안내 합니다.

![레코드를 검사 하기 위한 패널이 있는 선택한 레코드의 이미지](../../media/mtp-ah/ah-take-actions.png)

## <a name="review-actions-taken"></a>수행한 작업 검토
각 작업은 action **center** [action center](mtp-action-center.md)  >  **History** ([security.microsoft.com/action-center/history](https://security.microsoft.com/action-center/history))의 작업 센터에 개별적으로 기록 됩니다. 작업 센터로 이동 하 여 각 작업의 상태를 확인 합니다.
 
## <a name="related-topics"></a>관련 항목
- [고급 헌팅 개요](advanced-hunting-overview.md)
- [쿼리 언어 배우기](advanced-hunting-query-language.md)
- [쿼리 결과 작업](advanced-hunting-query-results.md)
- [스키마의 이해](advanced-hunting-schema-tables.md)
- [알림 센터 개요](mtp-action-center.md)

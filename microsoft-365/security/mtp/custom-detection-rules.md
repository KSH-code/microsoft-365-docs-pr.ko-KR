---
title: Microsoft Threat Protection에서 사용자 지정 검색 규칙 만들기 및 관리
description: 고급 검색 쿼리를 기반으로 사용자 지정 검색 규칙을 만들고 관리 하는 방법에 대해 알아봅니다.
keywords: 고급 구하기, 위협 검색, 사이버 위협 사냥, microsoft threat protection, microsoft 365, mtp, m365, 검색, 쿼리, 원격 분석, 사용자 지정 감지, 규칙, 스키마, kusto, microsoft 365, Microsoft Threat Protection, RBAC, 사용 권한, Microsoft Defender ATP
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
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: adb8c7dfa0050ef2eb0d59e1e55d07da7aaa3f39
ms.sourcegitcommit: 3b2fdf159d7dd962493a3838e3cf0cf429ee2bf2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "42931755"
---
# <a name="create-and-manage-custom-detections-rules"></a>사용자 지정 검색 규칙 만들기 및 관리

**적용 대상:**
- Microsoft 위협 방지

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

[고급](advanced-hunting-overview.md) 검색 쿼리를 기반으로 작성 된 사용자 지정 감지 규칙을 사용 하면 의심 스러운 위반 작업과 잘못 구성 된 끝점을 비롯 한 다양 한 이벤트 및 시스템 상태를 사전에 모니터링할 수 이러한 항목은 일치 하는 모든 경우에 알림을 생성 하 고 응답 작업을 수행 하 여 정기적인 간격으로 실행 되도록 설정할 수 있습니다.

## <a name="required-permissions-for-managing-custom-detections"></a>사용자 지정 검색을 관리 하는 데 필요한 사용 권한

사용자 지정 검색을 관리 하려면 다음 역할 중 하나를 할당 받아야 합니다.

- **보안 관리자** — 보안 관리자 또는 보안 관리자 역할은 Microsoft 365 보안 센터 및 다양 한 포털 및 서비스에서 다양 한 보안 설정을 관리 하는 데 사용할 수 있는 [Azure Active Directory 역할](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#security-administrator) 입니다.

- **보안 운영자** — 보안 운영자 역할은 경고를 관리 하 고 Microsoft 365 보안 센터의 모든 정보를 포함 하 여 보안 관련 기능에 대 한 전역 읽기 전용 액세스 권한이 있는 [Azure Active Directory 역할](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#security-administrator) 입니다. 이 역할은 Microsoft Defender ATP에서 RBAC (역할 기반 액세스 제어)가 해제 된 경우에만 사용자 지정 검색을 관리 하기에 충분 합니다. RBAC를 구성한 경우에는 Microsoft Defender ATP에 대 한 **보안 설정 관리** 권한도 필요 합니다.

**전역 관리자** 는 필요한 권한을 관리 하기 위해 다음을 수행할 수 있습니다.

- **Roles**역할 > **보안 관리자**아래의 [Microsoft 365 관리 센터](https://admin.microsoft.com/) 에서 **보안 관리자** 또는 **보안 운영자** 역할을 할당 합니다.
-  >  **설정****사용**권한 > **역할**아래의 [microsoft defender Security Center](https://securitycenter.windows.com/) 에서 microsoft defender ATP에 대 한 RBAC 설정을 확인 합니다. 해당 하는 역할을 선택 하 여 **보안 설정 관리** 권한을 할당 합니다.

> [!NOTE]
> RBAC가 설정 된 경우 사용자 지정 검색을 관리 하려면 **보안 운영자** 에 게 MICROSOFT Defender ATP의 **보안 설정 관리** 권한이 있어야 합니다.

## <a name="create-a-custom-detection-rule"></a>사용자 지정 검색 규칙 만들기
### <a name="1-prepare-the-query"></a>1. 쿼리를 준비 합니다.

Microsoft 365 보안 센터에서 **고급 구하기** 로 이동 하 여 기존 쿼리를 선택 하거나 새 쿼리를 만듭니다. 새 쿼리를 사용할 때 쿼리를 실행 하 여 오류를 식별 하 고 가능한 결과를 파악 합니다.

#### <a name="required-columns-in-the-query-results"></a>쿼리 결과의 필수 열
사용자 지정 검색 규칙을 만들려면 쿼리가 다음 열을 반환 해야 합니다.

- `Timestamp`
- 다음 장치, 사용자 또는 사서함 열 중 하나에 해당 합니다.
    - `DeviceId`
    - `DeviceName`
    - `RemoteDeviceName`
    - `RecipientEmailAddress`
    - `SenderFromAddress`(봉투 보낸 사람 또는 반환 경로 주소)
    - `SenderMailFromAddress`(전자 메일 클라이언트에 의해 표시 되는 보낸 사람 주소)
    - `RecipientObjectId`
    - `AccountSid`
    - `InitiatingProcessAccountSid`
    - `InitiatingProcessAccountUpn`
    - `InitiatingProcessAccountObjectId`
>[!NOTE]
>새 테이블이 [고급 구하기 스키마](advanced-hunting-schema-tables.md)에 추가 되 면 추가 엔터티에 대 한 지원이 추가 됩니다.

결과를 사용자 지정 하거나 집계 하기 위해 `project` or `summarize` 연산자를 사용 하지 않는 것과 같은 단순한 쿼리는 일반적으로 이러한 공통 열을 반환 합니다.

좀 더 복잡 한 쿼리가 이러한 열을 반환 하 게 하는 다양 한 방법이 있습니다. 예를 들어와 `DeviceId`같은 열에 따라 엔터티에 대해 집계 하 고 개수를 계산 하려는 경우에는 각 고유 `Timestamp` `DeviceId`항목을 포함 하는 최근 이벤트에서 가져오는 방식으로 반환할 수 있습니다.

아래 예제 쿼리는 바이러스 백신 검색이 포함 된 고유 컴퓨터`DeviceId`()의 수를 계산 하 고이 수를 사용 하 여 검색 수가 5 개 이상인 컴퓨터만 찾습니다. 이 메서드는 가장 `Timestamp`최근 개체를 반환 `summarize` 하기 위해 `arg_max` 함수와 함께 연산자를 사용 합니다.

```kusto
DeviceEvents
| where Timestamp > ago(7d)
| where ActionType == "AntivirusDetection"
| summarize Timestamp = max(Timestamp), count() by DeviceId
| where count_ > 5
```
### <a name="2-create-new-rule-and-provide-alert-details"></a>2. 새 규칙을 만들고 알림 세부 정보를 제공 합니다.

쿼리 편집기에서 쿼리를 사용 하 여 **검색 규칙 만들기** 를 선택 하 고 다음 알림 세부 정보를 지정 합니다.

- **검색 이름** — 검색 규칙의 이름
- **빈도** — 쿼리를 실행 하 고 작업을 수행 하기 위한 간격입니다. [아래 추가 지침 보기](#rule-frequency)
- **알림 제목** — 규칙에 의해 트리거된 경고와 함께 표시 되는 제목입니다.
- **심각도** — 구성 요소나 작업의 잠재적 위험을 규칙으로 식별
- **범주** -규칙에 따라 식별 되는 위협 구성 요소 또는 활동
- **MITRE at&t&접시 헤드 기술** - [MITRE at&t&접시 프레임 워크](https://attack.mitre.org/) 에 설명 된 것 처럼 규칙으로 식별 되는 하나 이상의 공격 기법
- **설명** — 규칙으로 식별 되는 구성 요소 또는 작업에 대 한 자세한 정보 
- **권장 작업** — 응답 자가 경고에 대해 취할 수 있는 추가 작업

#### <a name="rule-frequency"></a>규칙 빈도
저장 하면 새로 만들거나 편집한 사용자 지정 검색 규칙이 즉시 실행 되 고 최근 30 일 동안의 일치 여부를 확인 합니다. 그런 다음 일정 간격으로 규칙을 다시 실행 하 고 선택한 빈도에 따라 기간을 lookback 합니다.

- **24 시간** 마다-24 시간 마다 실행 되며 지난 30 일 동안의 데이터를 확인 합니다.
- **12 시간 마다** -12 시간 마다 실행 되며 지난 24 시간 동안의 데이터를 확인 합니다.
- **3 시간** 마다-3 시간 마다 실행 되며 지난 6 시간 동안의 데이터를 확인 합니다.
- **1 시간 마다** -매시간 실행 되며 지난 2 시간 동안의 데이터를 확인 합니다.

검색을 모니터링할 간격을 일치 시키는 빈도를 선택 하 고, 조직에서 경고에 응답할 수 있는 용량을 고려 합니다.

### <a name="3-choose-the-impacted-entities"></a>3. 영향을 받는 엔터티를 선택 합니다.
영향을 받는 주요 엔터티나 해당 엔터티를 찾을 것으로 예상 되는 쿼리 결과의 열을 식별 합니다. 예를 들어 쿼리는 보낸 사람 (`SenderFromAddress` 또는 `SenderMailFromAddress`) 및 받는 사람 (`RecipientEmailAddress`) 주소를 반환할 수 있습니다. 이러한 어떤 열이 영향을 받는 주요 엔터티를 나타내는 것을 확인 하면 서비스에서 관련 경고를 집계 하 고 인시던트와 대상 응답 작업을 결합할 수 있습니다.

각 엔터티 유형 (사서함, 사용자 또는 장치)에 대해 열을 하나만 선택할 수 있습니다. 쿼리에 의해 반환 되지 않는 열은 선택할 수 없습니다.

### <a name="3-specify-actions-on-files-or-machines"></a>3. 파일 또는 컴퓨터에 대 한 동작을 지정 합니다.
사용자 지정 검색 규칙은 쿼리에서 반환 되는 파일이 나 컴퓨터에 대해 자동으로 작업을 수행할 수 있습니다.

#### <a name="actions-on-machines"></a>컴퓨터에 대 한 작업
이러한 작업은 쿼리 결과 `DeviceId` 열에 있는 컴퓨터에 적용 됩니다.
- **컴퓨터 격리** -MICROSOFT Defender ATP를 사용 하 여 전체 네트워크 격리를 적용 하 여 시스템이 어떤 응용 프로그램 또는 서비스에도 연결 되지 않도록 합니다. [Microsoft Defender ATP 컴퓨터 격리에 대해 자세히 알아보기](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts#isolate-machines-from-the-network)
- **수집 조사 패키지** -ZIP 파일에서 컴퓨터 정보를 수집 합니다. [Microsoft Defender ATP 조사 패키지에 대해 자세히 알아보기](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts#collect-investigation-package-from-machines)
- **바이러스 검사 실행** -컴퓨터에서 전체 Windows Defender 바이러스 검사를 수행 합니다.
- **시작 조사** -컴퓨터에서 [자동화 된 조사](mtp-autoir.md) 를 시작 합니다.

#### <a name="actions-on-files"></a>파일 작업
이 탭을 선택 하면 쿼리 결과 `SHA1`의 `InitiatingProcessSHA1` `SHA256`,, 또는 `InitiatingProcessSHA256` 열에 있는 파일에서 **파일 격리** 작업이 수행 됩니다. 이 동작은 현재 위치에서 파일을 삭제 하 고 격리에 복사본을 배치 합니다.

> [!NOTE]
> 사용자 지정 검색 규칙에 대 한 allow 또는 block 작업은 현재 Microsoft Threat Protection에서 지원 되지 않습니다.

### <a name="4-set-the-rule-scope"></a>4. 규칙 범위를 설정 합니다.
범위를 설정 하 여 규칙에 포함 되는 장치를 지정 합니다. 범위는 장치를 확인 하는 규칙에 영향을 주며 사서함과 사용자 계정 또는 id만 검사 하는 규칙에는 영향을 주지 않습니다.

범위를 설정 하는 경우 다음을 선택할 수 있습니다.

- 모든 장치
- 특정 장치 그룹

범위에 있는 장치의 데이터만 쿼리 됩니다. 또한 해당 장치 에서만 작업을 수행 합니다.

### <a name="5-review-and-turn-on-the-rule"></a>5. 규칙을 검토 하 고 켭니다.
규칙을 검토 한 후 **만들기** 를 클릭 하 여 저장 합니다. 사용자 지정 검색 규칙이 즉시 실행 됩니다. 구성 된 빈도에 따라 다시 실행 하 여 일치 여부를 확인 하 고 경고를 생성 하 고 응답 작업을 수행 합니다.

## <a name="manage-existing-custom-detection-rules"></a>기존 사용자 지정 검색 규칙 관리
기존 사용자 지정 검색 규칙 목록을 확인 하 고, 이전 실행을 확인 하 고, 트리거된 경고를 검토할 수 있습니다. 요청에 대해 규칙을 실행 하 여 수정할 수도 있습니다.

### <a name="view-existing-rules"></a>기존 규칙 보기

기존의 모든 사용자 지정 검색 규칙을 보려면 **사냥** > **사용자 지정**감지로 이동 합니다. 다음 실행 정보와 함께 모든 규칙이 페이지에 나열 됩니다.

- **마지막 실행** -쿼리 일치를 확인 하기 위해 규칙을 마지막으로 실행 한 시기 및 경고 생성
- **마지막 실행 상태** -규칙이 성공적으로 실행 되었는지 여부
- **다음 실행** -예약 된 다음 실행
- **상태** -규칙이 설정 또는 해제 되었는지 여부

### <a name="view-rule-details-modify-rule-and-run-rule"></a>규칙 세부 정보 보기, 규칙 수정 및 규칙 실행

사용자 지정 검색 규칙에 대 한 포괄적인 정보를 보려면 **사냥** > **사용자 지정 감지**의 규칙 목록에서 규칙의 이름을 선택 합니다. 이렇게 하면 경고, 실행 상태 및 범위에 대 한 세부 정보를 비롯 하 여 규칙에 대 한 일반 정보를 포함 하는 사용자 지정 검색 규칙에 대 한 페이지가 열립니다. 또한 트리거된 경고 및 트리거된 작업의 목록만 제공 합니다.

![사용자 지정 검색 규칙 세부 정보 페이지](../../media/custom-detection-details.png)<br>
*사용자 지정 검색 규칙 세부 정보*

또한이 페이지의 규칙에 대해 다음 작업을 수행할 수 있습니다.

- **실행** -규칙을 즉시 실행 합니다. 또한 다음 실행에 대 한 간격이 다시 설정 됩니다.
- **편집** -쿼리를 변경 하지 않고 규칙 수정
- **수정 쿼리** -고급 검색에서 쿼리를 편집 합니다.
- **설정**끄기-규칙을 사용 하도록 설정 하거나 실행 되지 않도록 합니다.**Turn off**  / 
- **삭제** -규칙을 해제 하 고 제거 합니다.

### <a name="view-and-manage-triggered-alerts"></a>트리거된 알림 보기 및 관리

규칙 세부 정보 화면 (**사냥** > **사용자 지정** > 검색 **[규칙 이름]**)에서 **트리거된 경고** 로 이동 하 여 규칙과 일치 하는 항목에 의해 생성 된 경고 목록을 확인 합니다. 경고를 선택 하 여 해당 경고에 대 한 세부 정보를 확인 하 고 해당 경고에 대해 다음 작업을 수행 합니다.

- 상태 및 분류 (참 또는 거짓 경고)를 설정 하 여 경고를 관리 합니다.
- 인시던트에 경고 연결
- 고급 구하기에 대 한 경고를 트리거한 쿼리 실행

### <a name="review-actions"></a>작업 검토
규칙 세부 정보 화면 (**사냥** > **사용자 지정** > 검색 **[규칙 이름]**)에서 **트리거된 작업** 으로 이동 하 여 규칙에 대 한 일치 항목을 기준으로 수행한 작업 목록을 확인 합니다.

>[!TIP]
>테이블의 항목에 대 한 정보를 빠르게 확인 하 고 작업을 수행 하려면 표 왼쪽에 있는 선택 열인 [&#10003;]을 사용 합니다.

## <a name="related-topic"></a>관련 항목
- [사용자 지정 검색 개요](custom-detections-overview.md)
- [고급 헌팅 개요](advanced-hunting-overview.md)
- [고급 헌팅 쿼리 언어 알아보기](advanced-hunting-query-language.md)

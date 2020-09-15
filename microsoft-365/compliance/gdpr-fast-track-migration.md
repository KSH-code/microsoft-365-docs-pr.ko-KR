---
title: GDPR
description: Microsoft 기술 참고 자료 — 삭제 요청 제출용 FastTrack 마이그레이션 도구 집합
keywords: FastTrack 마이그레이션, Microsoft 365 Education, Microsoft 365 설명서, GDPR
localization_priority: Priority
Robots: NOFOLLOW,NOINDEX
ms.prod: microsoft-365-enterprise
ms.topic: article
f1.keywords:
- NOCSH
ms.author: mohitku
author: MohitKumar
manager: laurawi
audience: itpro
ms.collection:
- GDPR
- M365-security-compliance
titleSuffix: Microsoft GDPR
ms.openlocfilehash: 10a983297640ac4b65aaf181ef35ac19918e74fe
ms.sourcegitcommit: 27daadad9ca0f02a833ff3cff8a574551b9581da
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2020
ms.locfileid: "47547391"
---
# <a name="fasttrack-migration-toolset-for-submitting-delete-request"></a>삭제 요청 제출용 FastTrack 마이그레이션 도구 집합

## <a name="toolset-purpose"></a>도구 집합 용도

현재 FastTrack 마이그레이션에 연결된 고객의 경우, 사용자 계정을 삭제하면 Microsoft FastTrack 팀이 보유하는 데이터 복사본이 삭제되지 않습니다. FastTrack 팀은 오직 마이그레이션 완료 목적으로 복사본을 보유합니다. 마이그레이션하는 동안 Microsoft FastTrack 팀이 데이터 복사본도 삭제하게 하려면 이 도구 집합을 통해 요청을 제출하세요. 일반 업무 과정에서 Microsoft FastTrack은 마이그레이션이 완료되면 모든 데이터 복사본을 삭제합니다.

### <a name="supported-platforms"></a>지원되는 플랫폼

Microsoft는 Windows 플랫폼 및 PowerShell 콘솔에서 이 도구 집합의 최초 릴리스를 지원합니다. 이 도구 집합은 다음의 알려진 플랫폼을 지원합니다.

***테이블 1 — 이 도구 집합에서 지원되는 플랫폼***

****

|PowerShell 버전|Windows 7|Windows 8|Windows 10|Windows Server 2012|Windows Server 2016|
|:---:|:---:|:---:|:---:|:---:|:---:|
|5.0|지원되지 않음|않음|지원됨|지원됨|않음|
|5.1|지원되지 않음|않음|지원됨|지원됨|지원됨|
|

### <a name="obtaining-the-toolset"></a>도구 집합 획득

이 도구 집합은 PowerShell 콘솔 응용 프로그램의 PowerShell 갤러리에서 사용할 수 있습니다. cmdlet 모듈의 위치를 찾고 로드하려면 먼저 PowerShell을 관리자 모드로 열어서 모듈을 설치할 수 있는 적절한 권한을 획득합니다. 이전에 PowerShell을 사용하지 않은 경우 Windows 작업 막대로 이동하여 검색 상자에 “PowerShell”을 입력합니다. 마우스 오른쪽 단추를 사용하여 콘솔 앱을 선택하고 **관리자 권한으로 실행**을 선택한 다음 **예**를 클릭하여 Windows PowerShell을 실행합니다.

![PowerShell — 관리자 권한으로 실행](../media/fasttrack-powershell_image.png)

![PowerShell — 앱을 변경할 수 있도록 허용](../media/fasttrack-run-powershell_image.png)

콘솔이 열려 있으므로 스트립트 실행에 관한 사용 권한을 설정해야 합니다. 스크립트를 실행할 수 있도록 다음 명령을 입력합니다.

```powershell
Set-ExecutionPolicy -ExecutionPolicy Bypass -Scope Process
```

관리자 판단에 따라 범위를 변경할 수 있으므로 이 작업을 확인하라는 메시지가 표시됩니다.

***실행 정책 설정***

![PowerShell에서 실행 정책 변경 설정](../media/powershell-set-execution-policy_image.png)

이제 콘솔이 스크립트를 허용하도록 설정되었으므로 다음 명령을 실행하여 모듈을 설치합니다.

```powershell
Install-Module -Name Microsoft.FastTrack -Repository PSGallery -WarningAction SilentlyContinue -Force
```

### <a name="prerequisites-for-module"></a>모듈의 필수 구성 요소

이 모듈을 성공적으로 실행하려는 경우 종속 모듈이 설치되어 있지 않으면 먼저 설치해야 합니다. PowerShell을 다시 시작해야 할 수도 있습니다.

DSR을 제출하려면 Office 365 자격 증명을 사용하여 로그인해야 합니다. 적절한 자격 증명을 입력하면 전역 관리자 상태의 유효성을 검사하고 테넌트 정보를 수집합니다.

```powershell
Login-FastTrackAccount -ApiKey <API Key provided by FastTrack MVM>
```

성공적으로 로그인하면 현재 PowerShell 세션의 나머지에 대해 FastTrack 모듈과 함께 사용하기 위해 자격 증명 및 키가 저장됩니다.

상업 환경 이외의 클라우드 환경에 연결해야 하는 경우 다음 유효한 환경 중 하나를 사용하여 *로그인* 명령에 *-Environment*를 추가해야 합니다.

- AzureCloud
- AzureChinaCloud
- AzureGermanCloud
- AzureUSGovernmentCloud

```powershell
Login-FastTrackAccount -ApiKey <API Key provided by FastTrack MVM> -Environment <cloud environment>
```

DSR 요청을 제줄하려면 다음 명령을 실행합니다.

```powershell
Submit-FastTrackGdprDsrRequest -DsrRequestUserEmail SubjectUserEmail@mycompany.com
```

성공하면, cmdlet에서 트랜잭션 ID 개체를 반환합니다. 트랜잭션 ID를 유지하세요.

#### <a name="checking-the-status-of-a-request-transaction"></a>요청 트랜잭션의 상태 확인

이전에 가져온 트랜잭션 ID를 사용하여 다음 함수를 실행합니다.

```powershell
Get-FastTrackGdprDsrRequest -TransactionID "YourTransactionID"
```

#### <a name="transaction-status-codes"></a>트랜잭션 상태 코드

|트랜잭션|상태|
|---|---|
|**만든 날짜**|요청이 생성되었습니다.|
|**실패**|요청을 만들지 못했습니다. 다시 제출하거나 지원 팀에 문의하세요.|
|**완료**|요청이 완료되어 삭제되었습니다.|
|

<!-- original version: **Created**  Request has been created<br/>**Failed** Request failed to create, please resubmit, or contact support<br/>**Completed** Request has been completed and sanitized -->

## <a name="learn-more"></a>자세한 정보

[Microsoft 보안 센터](https://www.microsoft.com/trust-center/privacy/gdpr-overview)

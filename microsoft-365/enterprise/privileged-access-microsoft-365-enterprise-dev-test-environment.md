---
title: Microsoft 365 Enterprise 테스트 환경에 대한 권한이 부여된 액세스 관리
ms.author: robmazz
author: robmazz
manager: laurawi
ms.date: 09/21/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: Ent_O365
ms.custom: Ent_TLGs
description: Microsoft 365 Enterprise 테스트 환경을 권한이 부여 된 액세스 관리를 사용 하도록 설정 하려면이 테스트 랩 가이드를 사용 합니다.
ms.openlocfilehash: 5f1a416a12171504af110ec62b9a7882143263e6
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/28/2018
ms.locfileid: "26869727"
---
# <a name="privileged-access-management-for-your-microsoft-365-enterprise-test-environment"></a>Microsoft 365 Enterprise 테스트 환경에 대한 권한이 부여된 액세스 관리

이 문서의 지침을과 함께 Microsoft 365 기업 테스트 환경에서 보안을 강화 하기 권한이 부여 된 액세스 관리를 구성 합니다.

![Microsoft 클라우드의 테스트 랩 가이드](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> [여기](https://aka.ms/m365etlgstack)를 클릭하여 Microsoft 365 Enterprise 테스트 랩 가이드 스택의 모든 문서에 대한 가상 맵을 확인할 수 있습니다.
  
## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a>1 단계: Microsoft 365 Enterprise 테스트 환경을 구축합니다

최소 요구 사항을 경량 방식으로 액세스 권한을된 관리를 구성 하려면 [경량 기본 구성](lightweight-base-configuration-microsoft-365-enterprise.md)의 지시를 따릅니다.
  
시뮬레이션 된 엔터프라이즈에서 권한이 부여 된 액세스 관리를 구성 하려는 경우 [통과 인증](pass-through-auth-m365-ent-test-environment.md)에 대 한 지침을 따릅니다.
  
> [!NOTE]
> 권한이 부여 된 액세스 관리를 테스트 하지 않아도 인터넷에 연결 하는 시뮬레이션 된 인트라넷을 포함 하는 시뮬레이션 된 엔터프라이즈 테스트 환경 및 Windows Server AD 포리스트에 대 한 디렉터리 동기화 합니다. 여기에 제공 하는 옵션으로 테스트할 수 있도록 권한 관리에 액세스 하 고 일반적인 조직을 대표 하는 환경에서 사용해 합니다. 

## <a name="phase-2-configure-privileged-access-management"></a>2 단계: 액세스 권한을된 관리 구성

이 단계에서 승인자 그룹을 구성 및 Microsoft 365 기업 테스트 환경에 대 한 액세스 권한을된 관리를 사용 하도록 설정 합니다. 추가 세부 정보 및 권한 개요에 대 한 관리 액세스 [Office 365에서 권한이 부여 된 액세스 관리](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-overview)를 참조 하십시오.

설정 하 고 Office 365 조직에서 액세스 권한을된 사용 하려면 다음이 단계를 수행 합니다.

- [1 단계: 승인자의 그룹 만들기](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-configuration#step-1---create-an-approvers-group)

    권한 액세스를 사용 하 여를 시작 하기 전에 관리자 권한 및 권한 있는 작업에 대 한 액세스에 대 한 수신 요청에 대 한 승인 권한을 갖고 결정 합니다. 승인자 그룹의 구성원 인 모든 사용자 액세스 요청 승인 됩니다. Office 365의 메일 사용이 가능한 보안 그룹을 만들어 사용 하도록 설정 됩니다. 테스트 환경에서 "승인자가 액세스 권한이 부여 된" 이라는 새 보안 그룹을 만들고 추가 "3" 이전에 이전 테스트 랩 가이드 단계에서 만든 사용자입니다.

- [2 단계: 사용 권한이 부여 된 액세스](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-configuration#step-2---enable-privileged-access)

    액세스 권한을된 명시적으로 켜져 있어야 Office 365의 기본 승인자 그룹 및 액세스 권한을된 관리 액세스 제어에서 제외 하려는 시스템 계정 집합을 포함 해야 합니다. 이 가이드의 3 단계를 시작 하기 전에 Office 365 조직에 대 한 액세스 권한을된 사용 하도록 설정 해야 합니다.

## <a name="phase-3-verify-that-approval-is-required-for-elevated-and-privileged-tasks"></a>3 단계: 승인 관리자 권한 및 권한 있는 작업에 대 한 필수 인지 확인
이 단계에서 권한이 부여 된 액세스 정책이 작동 하 고 사용자가 정의 된 관리자 권한 및 권한 있는 작업을 실행에 대 한 승인 필요를 확인 합니다.

### <a name="test-ability-to-execute-a-task-not-defined-in-a-privileged-access-policy"></a>권한이 부여 된 액세스 정책에 정의 되지 않은 작업을 실행할 수 있는 기능을 테스트 합니다.

먼저, 테스트 환경에서 전역 관리자 권한으로 구성 된 사용자의 자격 증명을 가진 Exchange Management PowerShell에 연결 하 고 새 저널 규칙을 생성 하려고 합니다. [New-journalrule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/new-journalrule?view=exchange-ps) 작업 현재 조직에 대 한 액세스 권한을된 정책에 정의 되지 않았습니다.

1. 로컬 컴퓨터에서 열고에 로그인은 Exchange Online 원격 PowerShell 모듈 **Microsoft Corporation**에서 > 전역 관리자를 사용 하 여**Microsoft Exchange Online 원격 PowerShell 모듈** 테스트 환경에 대 한 계정입니다.

2. Exchange 관리 Powershell에서 조직에 대 한 새 저널 규칙을 만듭니다.

```
New-JournalRule -Name "JournalRule1" -Recipient joe@contoso.onmicrosoft.com -JournalEmailAddress barbara@adatum.com -Scope Global -Enabled $true
```
4. 새 저널 규칙이 성공적으로 만들어졌는지 Exchange Management PowerShell 보기입니다.

### <a name="create-a-new-privileged-access-policy-for-the-new-journalrule-task"></a>New-journalrule 작업에 대 한 새 권한이 부여 된 액세스 정책 만들기

> [!NOTE]
> 단계 1과 2이이 가이드의 2 단계에서에서 아직 완료 되지 않은, 있는지 팔 로우 테스트 환경에 대 한 액세스 권한을된 사용 하도록 설정 하 고 "권한 액세스 승인자" 라는 승인자의 그룹을 만드는 단계를 수 있습니다.

1. 테스트 환경에 대 한 전역 관리자 계정 자격 증명을 사용 하 여 [Microsoft 365 관리 센터](https://portal.office.com) 에 로그인 합니다.

2. 관리 센터에서 **설정**으로 이동 > **보안 및 개인정보** > **권한이 부여 된 액세스**합니다.

3. **관리 액세스 정책 및 요청을**선택 합니다.

4. **정책을 구성을** 선택 하 고 **정책 추가**선택 합니다.

5. 드롭다운 필드에서 선택 하거나 다음 값을 입력 합니다.
    
    **정책 유형**: 작업

    **정책 범위**: Exchange

    **정책 이름**: 새 저널 규칙

    **승인 유형**: manual (영문)

    **승인 그룹**: 권한이 부여 된 액세스 승인자

6. **만들고 다음 **닫기**** 를 선택 합니다. 완벽 하 게 구성 하 고 사용을 정책에 대 한 몇 분정도 걸릴 수 있습니다. 다음 단계에서 승인 요구 사항을 테스트 하기 전에 완벽 하 게 사용할 수 정책에 대 한 시간을 허용 해야 합니다.

### <a name="test-approval-requirement-for-the-new-journalrule-task-defined-in-a-privileged-access-policy"></a>권한이 부여 된 액세스 정책에 정의 된 New-journalrule 작업에 대 한 승인 요구 사항 테스트

1. 로컬 컴퓨터에서 열고에 로그인은 Exchange Online 원격 PowerShell 모듈 **Microsoft Corporation**에서 > **Microsoft Exchange Online 원격 PowerShell 모듈** 을 사용 하 여 전역 관리자를 사용 하 여 테스트를 위한 계정 환경입니다.

2. Exchange 관리 Powershell에서 조직에 대 한 새 저널 규칙을 만듭니다.

```
New-JournalRule -Name "JournalRule2" -Recipient user1@<your subscription domain> -JournalEmailAddress user1@<your subscription domain> -Scope Global -Enabled $true
```
3. Exchange 관리 PowerShell의 "권한 부족" 오류를 참조 하십시오.

```
Insufficient permissions. Please raise an elevated access request for this task.
    + CategoryInfo          : NotSpecified: (:) [], LocalizedException
    + FullyQualifiedErrorId : [Server=CY1PR00MB0220,RequestId=7b8c7470-ddd0-4528-a01e-5e20ecc9bd54,TimeStamp=9/19/2018
    7:38:34 PM] [FailureCategory=Cmdlet-LocalizedException] 882BD051
    + PSComputerName        : outlook.office365.com
```

### <a name="request-access-to-create-a-new-journal-rule-using-the-new-journalrule-task"></a>New-journalrule 작업을 사용 하 여 새 저널 규칙 만들기에 대 한 액세스를 요청 합니다.

1. 테스트 환경에 대 한 전역 관리자 계정을 사용 하 여 [Microsoft 365 관리 센터](https://portal.office.com) 에 로그인 합니다.

2. 관리 센터에서 **설정**으로 이동 > **보안 및 개인정보** > **권한이 부여 된 액세스**합니다.

3. **관리 액세스 정책 및 요청을**선택 합니다.

4. **새 요청**을 선택 합니다. 드롭다운 필드에서 조직에 대 한 적절 한 값을 선택 합니다.

    **요청 유형**: 작업

    **범위 요청**: Exchange

    **에 대 한 요청**: 새 저널 규칙

    **기간 (시간)**: 2

    **설명**: 새 저널 규칙을 만들 수 있는 사용 권한 요청

5. **저장** 한 다음 **닫기**를 선택 합니다. 전자 메일을 통해 승인자의 그룹에 사용자의 요청을 전송 됩니다.

### <a name="approve-privileged-access-request-for-the-creation-of-a-new-journal-rule"></a>새 저널 규칙을 만들기에 대 한 액세스 권한을된 요청을 승인

1. 사용자 3에 대 한 자격 증명을 사용 하 여 테스트 환경 (테스트 환경에서 "승인자가 액세스 권한이 있는" 보안 그룹의 구성원)에서 [Microsoft 365 관리 센터](https://portal.office.com) 에 로그인 합니다.

2. 관리 센터에서 **설정**으로 이동 > **보안 및 개인정보** > **권한이 부여 된 액세스**합니다.

3. **관리 액세스 정책 및 요청을**선택 합니다.

4. 대기 중인 요청을 선택 하 고 **승인** 새 저널 규칙을 만들려면 전역 관리자 계정에 대 한 액세스 권한을 부여 하려면 선택 합니다. 전역 관리자 계정 (요청 하는 사용자)에 승인 부여 했는지 확인 알림 전자 메일을 전송 됩니다.  

### <a name="test-creating-a-new-journal-rule-with-privileged-access-approved-for-the-new-journalrule-task"></a>테스트 New-journalrule 작업에 대 한 승인 액세스 권한이 있는 새 저널 규칙 만들기 (영문)

1. 로컬 컴퓨터에서 열고에 로그인은 Exchange Online 원격 PowerShell 모듈 **Microsoft Corporation**에서 > 전역 관리자를 사용 하 여**Microsoft Exchange Online 원격 PowerShell 모듈** 테스트 환경에 대 한 계정입니다.

2. Exchange 관리 Powershell에서 조직에 대 한 새 저널 규칙을 만듭니다.

```
New-JournalRule -Name "JournalRule2" -Recipient user1@<your subscription domain> -JournalEmailAddress user1@<your subscription domain> -Scope Global -Enabled $true
```
3. 새 저널 규칙이 성공적으로 만들어졌는지 Exchange Management PowerShell 보기입니다.

## <a name="next-step"></a>다음 단계

추가 [정보 보호](m365-enterprise-test-lab-guides.md#information-protection) 기능 및 기능 테스트 환경에서 살펴봅니다.

## <a name="see-also"></a>참고 항목

[Microsoft 365 Enterprise 테스트 랩 가이드](m365-enterprise-test-lab-guides.md)

[Microsoft 365 Enterprise 배포](deploy-microsoft-365-enterprise.md)

[Microsoft 365 Enterprise 설명서](https://docs.microsoft.com/microsoft-365-enterprise/)
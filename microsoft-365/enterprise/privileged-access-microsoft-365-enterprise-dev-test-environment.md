---
title: Microsoft 365 Enterprise 테스트 환경에 대한 권한이 부여된 액세스 관리
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
- M365-security-compliance
ms.custom: Ent_TLGs
description: 이 테스트 랩 가이드를 사용 하 여 Microsoft 365 Enterprise Test environment 권한 있는 액세스 관리를 사용 하도록 설정 합니다.
ms.openlocfilehash: f701f3f8f74036966de2c516d662ef77341f4842
ms.sourcegitcommit: b424ea039c5915975f3efce8793bfc8dd2fdf906
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/07/2019
ms.locfileid: "38033613"
---
# <a name="privileged-access-management-for-your-microsoft-365-enterprise-test-environment"></a>Microsoft 365 Enterprise 테스트 환경에 대한 권한이 부여된 액세스 관리

이 문서의 지침을 사용 하 여 Microsoft 365 Enterprise 테스트 환경에서 보안을 강화 하도록 권한이 부여 된 액세스 관리를 구성 합니다.

![Microsoft 클라우드의 테스트 랩 가이드](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> [여기](https://aka.ms/m365etlgstack)를 클릭하여 Microsoft 365 Enterprise 테스트 랩 가이드 스택의 모든 문서에 대한 가상 맵을 확인할 수 있습니다.
  
## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a>1 단계: Microsoft 365 Enterprise 테스트 환경 구축

최소 요구 사항에 따라 간단한 방식으로 권한 있는 액세스 관리를 구성 하려는 경우에는 [간단한 기본 구성](lightweight-base-configuration-microsoft-365-enterprise.md)의 지침을 따릅니다.
  
시뮬레이트된 엔터프라이즈에서 권한이 부여 된 액세스 관리를 구성 하려면 [통과 인증](pass-through-auth-m365-ent-test-environment.md)의 지침을 따르세요.
  
> [!NOTE]
> 권한 있는 액세스 관리를 테스트 하는 경우에는 AD DS 포리스트에 대 한 인터넷 및 디렉터리 동기화에 연결 된 시뮬레이트된 인트라넷을 포함 하는 시뮬레이트된 엔터프라이즈 테스트 환경이 필요 하지 않습니다. 이 옵션은 권한 있는 액세스 관리를 테스트 하 고 일반적인 조직을 나타내는 환경에서 테스트해 볼 수 있도록 여기에서 제공 됩니다. 

## <a name="phase-2-configure-privileged-access-management"></a>2 단계: 권한 있는 액세스 관리 구성

이 단계에서는 승인자 그룹을 구성 하 고 Microsoft 365 Enterprise 테스트 환경에 대해 권한이 부여 된 액세스 관리를 사용 하도록 설정 합니다. 권한 있는 액세스 관리에 대 한 자세한 내용 및 개요는 [Office 365의 권한이 부여 된 액세스 관리](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-overview)를 참조 하세요.

Office 365 조직에서 권한 있는 액세스를 설정 및 사용 하려면 다음 단계를 수행 합니다.

- [1 단계: 승인자 그룹 만들기](https://docs.microsoft.com/microsoft-365/compliance/privileged-access-management-configuration#step-1-create-an-approvers-group)

    권한 액세스 사용을 시작 하기 전에 권한 상승 및 권한 있는 작업에 대 한 수신 요청 액세스에 대 한 승인 기관을 사용자에 게 결정 합니다. 승인자 그룹에 속하는 모든 사용자는 액세스 요청을 승인할 수 있습니다. 이 기능은 Office 365에서 메일 사용이 가능한 보안 그룹을 만들어 사용할 수 있습니다. 테스트 환경에 "권한이 부여 된 액세스 승인자" 라는 새 보안 그룹을 만들고 이전 테스트 랩 가이드 단계에서 만든 "사용자 3"을 추가 합니다.

- [2 단계: 권한 있는 액세스 사용](https://docs.microsoft.com/microsoft-365/compliance/privileged-access-management-configuration#step-2-enable-privileged-access)

    권한 있는 액세스는 Office 365에서 기본 승인자 그룹을 사용 하 고 권한 있는 액세스 관리 액세스 제어에서 제외할 시스템 계정 집합을 포함 하 여 명시적으로 설정 해야 합니다. 이 가이드의 3 단계를 시작 하기 전에 Office 365 조직에서 권한이 부여 된 액세스를 사용 하도록 설정 해야 합니다.

## <a name="phase-3-verify-that-approval-is-required-for-elevated-and-privileged-tasks"></a>3 단계: 관리자 권한 및 권한 있는 작업에 대 한 승인이 필요한 지 확인

이 단계에서는 권한이 부여 된 액세스 정책이 작동 하 고 있는지 확인 하 고 사용자에 게 권한 상승 및 권한이 부여 된 작업을 실행 하기 위한 승인을 받아야 합니다.

### <a name="test-ability-to-execute-a-task-not-defined-in-a-privileged-access-policy"></a>권한 있는 액세스 정책에 정의 되지 않은 작업을 실행 하는 테스트 기능

먼저 테스트 환경에서 전역 관리자로 구성 된 사용자의 자격 증명을 사용 하 여 Exchange 관리 PowerShell에 연결한 다음 새 저널 규칙을 만들려고 합니다. [Set-journalrule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/new-journalrule?view=exchange-ps) 작업은 현재 조직에 대해 권한이 부여 된 액세스 정책에 정의 되어 있지 않습니다.

1. 로컬 컴퓨터에서 테스트 환경의 전역 관리자 계정을 사용 하 여 **microsoft Corporation** > **microsoft exchange online 원격 powershell** 모듈의 Exchange online 원격 powershell 모듈을 열고 로그인 합니다.

2. Exchange 관리 Powershell에서 조직에 대 한 새 저널 규칙을 만듭니다.

```ExchangeManagementPowerShell
New-JournalRule -Name "JournalRule1" -Recipient joe@contoso.onmicrosoft.com -JournalEmailAddress barbara@adatum.com -Scope Global -Enabled $true
```

4. Exchange 관리 PowerShell에서 새 저널 규칙을 성공적으로 만들었는지 확인 합니다.

### <a name="create-a-new-privileged-access-policy-for-the-new-journalrule-task"></a>새 Set-journalrule 작업에 대 한 새 권한 있는 액세스 정책 만들기

> [!NOTE]
> 이 가이드의 2 단계에 나와 있는 1 ~ 2 단계를 아직 완료 하지 않은 경우 다음 단계에 따라 승인자 그룹 "권한 액세스 승인자"를 만들고 테스트 환경에서 권한이 부여 된 액세스를 사용 하도록 설정 해야 합니다.

1. 자격 증명을 사용 하 여 [Microsoft 365 관리 센터](https://admin.microsoft.com) 에 로그인 테스트 환경에 대 한 전역 관리자 계정입니다.

2. 관리 센터에서 **설정** > **보안 & 개인 정보** > **권한이 부여 된 액세스**로 이동 합니다.

3. **액세스 정책 및 요청 관리를**선택 합니다.

4. 정책 **구성을** 선택 하 고 **정책 추가**를 선택 합니다.

5. 드롭다운 필드에서 다음 값을 선택 하거나 입력 합니다.

    **정책 유형**: 작업

    **정책 범위**: Exchange

    **정책 이름**: 새 저널 규칙

    **승인 유형**: 수동

    **승인 그룹**: 권한 있는 액세스 승인자

6. **만들기** 를 선택한 다음 **닫기를**선택 합니다. 정책을 완전히 구성 및 사용 하도록 설정 하는 데 몇 분 정도 걸릴 수 있습니다. 다음 단계에서 승인 요구 사항을 테스트 하기 전에 정책을 완전히 사용 하도록 설정할 시간을 허용 해야 합니다.

### <a name="test-approval-requirement-for-the-new-journalrule-task-defined-in-a-privileged-access-policy"></a>권한 있는 액세스 정책에 정의 된 Set-journalrule 작업에 대 한 승인 요구 사항 테스트

1. 로컬 컴퓨터에서 테스트 환경에 대 한 전역 관리자 계정을 사용 하 여 **microsoft Corporation** > **microsoft exchange online 원격 powershell 모듈** 의 Exchange online 원격 powershell 모듈을 열고 로그인 합니다.

2. Exchange 관리 Powershell에서 조직에 대 한 새 저널 규칙을 만듭니다.

```ExchangeManagementPowerShell
New-JournalRule -Name "JournalRule2" -Recipient user1@<your subscription domain> -JournalEmailAddress user1@<your subscription domain> -Scope Global -Enabled $true
```

3. Exchange 관리 PowerShell에서 "Insuffient 사용 권한" 오류 보기:

```ExchangeManagementPowerShell
Insufficient permissions. Please raise an elevated access request for this task.
    + CategoryInfo          : NotSpecified: (:) [], LocalizedException
    + FullyQualifiedErrorId : [Server=CY1PR00MB0220,RequestId=7b8c7470-ddd0-4528-a01e-5e20ecc9bd54,TimeStamp=9/19/2018
    7:38:34 PM] [FailureCategory=Cmdlet-LocalizedException] 882BD051
    + PSComputerName        : outlook.office365.com
```

### <a name="request-access-to-create-a-new-journal-rule-using-the-new-journalrule-task"></a>Set-journalrule 작업을 사용 하 여 새 저널 규칙을 만들도록 액세스 요청

1. 테스트 환경에 대 한 전역 관리자 계정을 사용 하 여 [Microsoft 365 관리 센터](https://admin.microsoft.com) 에 로그인 합니다.

2. 관리 센터에서 **설정** > **보안 & 개인 정보** > **권한이 부여 된 액세스**로 이동 합니다.

3. **액세스 정책 및 요청 관리를**선택 합니다.

4. **새 요청**을 선택 합니다. 드롭다운 필드에서 조직에 적합 한 값을 선택 합니다.

    **요청 유형**: 작업

    **요청 범위**: Exchange

    **요청**: 새 저널 규칙

    **기간 (시간)**: 2

    **설명**: 새 저널 규칙을 만드는 권한을 요청 합니다.

5. **저장** 을 선택한 다음 **닫기를**선택 합니다. 요청은 전자 메일을 통해 승인자 그룹에 전송 됩니다.

### <a name="approve-privileged-access-request-for-the-creation-of-a-new-journal-rule"></a>새 저널 규칙 만들기에 대 한 권한 있는 액세스 요청 승인

1. 테스트 환경의 사용자 3에 대 한 자격 증명 (테스트 환경에서 "권한이 부여 된 액세스 승인자" 보안 그룹의 구성원)을 사용 하 여 [Microsoft 365 관리 센터](https://admin.microsoft.com) 에 로그인 합니다.

2. 관리 센터에서 **설정** > **보안 & 개인 정보** > **권한이 부여 된 액세스**로 이동 합니다.

3. **액세스 정책 및 요청 관리를**선택 합니다.

4. 대기 중인 요청을 선택 하 고 **승인을** 선택 하 여 새 저널 규칙을 만들 전역 관리자 계정에 대 한 액세스 권한을 부여 합니다. 승인이 부여 되었음을 확인 하는 알림 전자 메일은 전역 관리자 계정 (요청 사용자)으로 전송 됩니다.  

### <a name="test-creating-a-new-journal-rule-with-privileged-access-approved-for-the-new-journalrule-task"></a>Set-journalrule 작업에 대해 승인 된 액세스 권한을 사용 하 여 새 저널 규칙 만들기 테스트

1. 로컬 컴퓨터에서 테스트 환경의 전역 관리자 계정을 사용 하 여 **microsoft Corporation** > **microsoft exchange online 원격 powershell** 모듈의 Exchange online 원격 powershell 모듈을 열고 로그인 합니다.

2. Exchange 관리 Powershell에서 조직에 대 한 새 저널 규칙을 만듭니다.

```ExchangeManagementPowerShell
New-JournalRule -Name "JournalRule2" -Recipient user1@<your subscription domain> -JournalEmailAddress user1@<your subscription domain> -Scope Global -Enabled $true
```

3. Exchange 관리 PowerShell에서 새 저널 규칙을 성공적으로 만들었는지 확인 합니다.

## <a name="next-step"></a>다음 단계

테스트 환경에서 추가 [정보 보호](m365-enterprise-test-lab-guides.md#information-protection) 기능에 대해 알아봅니다.

## <a name="see-also"></a>참고 항목

[Microsoft 365 Enterprise 테스트 랩 가이드](m365-enterprise-test-lab-guides.md)

[Microsoft 365 Enterprise 배포](deploy-microsoft-365-enterprise.md)

[Microsoft 365 Enterprise 설명서](https://docs.microsoft.com/microsoft-365-enterprise/)
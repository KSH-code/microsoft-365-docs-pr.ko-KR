---
title: 엔터프라이즈용 Microsoft 365 테스트 환경에 대한 권한 있는 액세스 관리
f1.keywords:
- NOCSH
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
description: 이 테스트 랩 가이드를 사용하여 엔터프라이즈용 Microsoft 365 테스트 환경을 권한 있는 액세스 관리를 사용하도록 설정할 수 있습니다.
ms.openlocfilehash: e9684ebd2aa147049dadfbda9408257ff801aff0
ms.sourcegitcommit: eac5d9f759f290d3c51cafaf335a1a1c43ded927
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "50126420"
---
# <a name="privileged-access-management-for-your-microsoft-365-for-enterprise-test-environment"></a>엔터프라이즈용 Microsoft 365 테스트 환경에 대한 권한 있는 액세스 관리

*이 테스트 랩 가이드는 엔터프라이즈용 Microsoft 365 및 Office 365 Enterprise 테스트 환경에 모두 사용할 수 있습니다.*

이 문서에서는 엔터프라이즈용 Microsoft 365 테스트 환경에서 보안을 강화하도록 권한이 부여된 액세스 관리를 구성하는 방법을 설명합니다.

기본 액세스 관리 구성에는 다음 세 단계가 있습니다.
- [1단계: 엔터프라이즈용 Microsoft 365 테스트 환경 구축](#phase-1-build-out-your-microsoft-365-for-enterprise-test-environment)
- [2단계: 권한 있는 액세스 관리 구성](#phase-2-configure-privileged-access-management)
- [3단계: 권한 상승 및 권한 있는 작업에 승인이 필요한지 확인](#phase-3-verify-that-approval-is-required-for-elevated-and-privileged-tasks)

![Microsoft 클라우드의 테스트 랩 가이드](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> 엔터프라이즈용 Microsoft 365 테스트 랩 가이드 스택의 모든 문서에 대한 시각적 맵은 [엔터프라이즈용 Microsoft 365](../downloads/Microsoft365EnterpriseTLGStack.pdf)테스트 랩 가이드 스택으로 이동하세요.
  
## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a>1단계: 엔터프라이즈용 Microsoft 365 테스트 환경 구축

최소 요구 사항과 함께 경량 방식으로 권한 있는 액세스 관리를 구성하려면 Lightweight [base 구성의](lightweight-base-configuration-microsoft-365-enterprise.md)지침을 따릅니다.
  
시뮬레이트된 엔터프라이즈에서 권한이 부여된 액세스 관리를 구성하려는 경우 통과 인증의 [지침을 따릅니다.](pass-through-auth-m365-ent-test-environment.md)
  
>[!NOTE]
>권한이 부여된 액세스 관리를 테스트하는 데는 시뮬레이트된 엔터프라이즈 테스트 환경이 필요하지 않습니다. 여기에는 Active Directory 도메인 서비스 포리스트에 대한 디렉터리 동기화 및 인터넷에 연결된 시뮬레이트된 인트라넷이 포함됩니다. 권한 있는 액세스 관리를 테스트하고 일반적인 조직을 나타내는 환경에서 실험할 수 있도록 여기에 옵션으로 제공됩니다.

## <a name="phase-2-configure-privileged-access-management"></a>2단계: 권한 있는 액세스 관리 구성

이 단계에서는 승인자 그룹을 구성하고 엔터프라이즈용 Microsoft 365 테스트 환경에 대해 권한이 부여된 액세스 관리를 사용하도록 합니다. 권한 있는 액세스 관리에 대한 추가 세부 정보 및 개요는 [Privileged 액세스 관리를 참조하십시오.](../compliance/privileged-access-management-overview.md)

조직에서 권한이 부여된 액세스를 설정하고 사용하기 위해 다음 단계를 수행합니다.

#### <a name="step-1-create-an-approvers-group"></a>[1단계: 승인자 그룹 만들기](../compliance/privileged-access-management-configuration.md#step-1-create-an-approvers-group)

권한이 부여된 액세스 사용을 시작하기 전에 승격된 작업 및 권한 있는 작업에 대한 액세스에 대한 들어오는 요청에 대한 승인 권한이 있는 사용자를 결정하십시오. 승인자 그룹의 일부인 모든 사용자는 액세스 요청을 승인할 수 있습니다. 권한이 부여된 액세스를 사용하려면 Microsoft 365에서 메일 사용이 가능한 보안 그룹을 만들어야 합니다. 테스트 환경에서 새 보안 그룹 이름을 "Privileged Access Approvers"로 지정하고 이전 테스트 랩 가이드 단계에서 이전에 만든 "사용자 3"을 추가합니다.

#### <a name="step-2-enable-privileged-access"></a>[2단계: 권한 있는 액세스 사용](../compliance/privileged-access-management-configuration.md#step-2-enable-privileged-access)

기본 승인자 그룹을 사용하여 Microsoft 365에서 권한 있는 액세스를 명시적으로 설정해야 하고 권한 있는 액세스 관리 액세스 제어에서 제외하려는 시스템 계정 집합을 포함해야 합니다. 이 가이드의 3단계를 시작하기 전에 조직에서 권한이 부여된 액세스를 사용하도록 설정해야 합니다.

## <a name="phase-3-verify-that-approval-is-required-for-elevated-and-privileged-tasks"></a>3단계: 권한 상승 및 권한 있는 작업에 승인이 필요한지 확인

이 단계에서는 권한이 부여된 액세스 정책이 작동하고 있으며 사용자가 정의된 권한 상승 및 권한 있는 작업을 실행하기 위해 승인이 필요한지 확인해야 합니다.

### <a name="test-the-ability-to-execute-a-task-not-defined-in-a-privileged-access-policy"></a>권한이 부여된 액세스 정책에 정의되지 않은 작업을 실행하는 기능을 테스트합니다.

먼저 테스트 환경에서 전역 관리자로 구성된 사용자의 자격 증명을 사용하여 Exchange 관리 PowerShell에 연결하고 새 저널 규칙을 만들도록 시도합니다. [New-JournalRule](/powershell/module/exchange/new-journalrule) 작업은 현재 조직에 대한 권한이 부여된 액세스 정책에 정의되어 있지 않습니다.

1. 로컬 컴퓨터에서 **Microsoft Corporation의** Exchange Online 원격 PowerShell 모듈을 열고 Microsoft Exchange Online 환경의 전역 관리자 계정을 사용하여  >  **원격 PowerShell 모듈에** 로그인합니다.

1. Exchange 관리 PowerShell에서 조직에 대한 새 저널 규칙을 생성합니다.

   ```ExchangeManagementPowerShell
   New-JournalRule -Name "JournalRule1" -Recipient joe@contoso.onmicrosoft.com -JournalEmailAddress barbara@adatum.com -Scope Global -Enabled $true
   ```

1. Exchange 관리 PowerShell에서 새 저널 규칙이 만들어졌습니다.

### <a name="create-a-new-privileged-access-policy-for-the-new-journalrule-task"></a>새 권한 있는 액세스 정책 만들기 작업에 New-JournalRule 권한 있는 액세스 정책 만들기

>[!NOTE]
>이 가이드의 2단계에서 1단계와 2단계를 아직 완료하지 않은 경우 단계에 따라 "권한 액세스 승인자"라는 승인자 그룹을 만들어 테스트 환경에서 권한이 부여된 액세스를 사용하도록 설정해야 합니다.

1. 테스트 환경의 전역 관리자 계정 자격 증명을 사용하여 [Microsoft 365](https://admin.microsoft.com) 관리 센터에 로그인합니다.

2. 관리 센터에서 개인 **정보** 보호  >  **권한 & 설정**  >  **보안으로 이동합니다.**

3. 액세스 **정책 및 요청 관리 선택.**

4. 정책 **구성을** 선택한 다음 정책 **추가를 선택합니다.**

5. 드롭다운 필드에서 다음 값을 선택하거나 입력합니다.

    **정책 유형**: 작업

    **정책 범위**: Exchange

    **정책 이름:** 새 저널 규칙

    **승인 유형**: 수동

    **승인 그룹**: 권한이 부여된 액세스 승인자

6. **Create(만들기)를** 선택한 다음 **닫기(닫기)를 선택합니다.** 정책을 완전히 구성하고 사용하도록 설정하는 데 몇 분 정도 걸릴 수 있습니다. 다음 단계에서 승인 요구 사항을 테스트하기 전에 정책을 완전히 사용하도록 설정하는 데 필요한 시간을 허용해야 합니다.

### <a name="test-approval-requirement-for-the-new-journalrule-task-defined-in-a-privileged-access-policy"></a>권한 있는 액세스 정책에 정의된 New-JournalRule 작업에 대한 승인 요구 사항 테스트

1. 로컬 컴퓨터에서 테스트 환경에 대한 전역 관리자 계정을 사용하여 **Microsoft Corporation** Microsoft Exchange Online 원격 PowerShell 모듈의 Exchange Online 원격  >  **PowerShell** 모듈을 열고 로그인합니다.

2. Exchange 관리 PowerShell에서 조직에 대한 새 저널 규칙을 생성합니다.

   ```ExchangeManagementPowerShell
   New-JournalRule -Name "JournalRule2" -Recipient user1@<your subscription domain> -JournalEmailAddress user1@<your subscription domain> -Scope Global -Enabled $true
   ```

3. Exchange 관리 PowerShell에서 "사용 권한 부족" 오류를 본다.

   ```ExchangeManagementPowerShell
   Insufficient permissions. Please raise an elevated access request for this task.
       + CategoryInfo          : NotSpecified: (:) [], LocalizedException
       + FullyQualifiedErrorId : [Server=CY1PR00MB0220,RequestId=7b8c7470-ddd0-4528-a01e-5e20ecc9bd54,TimeStamp=9/19/2018
       7:38:34 PM] [FailureCategory=Cmdlet-LocalizedException] 882BD051
       + PSComputerName        : outlook.office365.com
   ```

### <a name="request-access-to-create-a-new-journal-rule-using-the-new-journalrule-task"></a>새 저널 규칙을 만들 수 있도록 액세스 New-JournalRule 요청

1. 테스트 환경에 대한 전역 관리자 계정을 사용하여 [Microsoft 365](https://admin.microsoft.com) 관리 센터에 로그인합니다.

2. 관리 센터에서 개인 **정보** 보호  >  **권한 & 설정**  >  **보안으로 이동합니다.**

3. 액세스 **정책 및 요청 관리 선택.**

4. 새 **요청을 선택합니다.** 드롭다운 필드에서 조직에 적합한 값을 선택합니다.

    **요청 유형**: 작업

    **요청 범위**: Exchange

    **요청:** 새 저널 규칙

    **기간(시간)**: 2

    **설명**: 새 저널 규칙을 만들 수 있는 권한 요청

5. **저장을** 선택한 다음 **닫기 를 선택합니다.** 요청은 전자 메일을 통해 승인자 그룹으로 전송됩니다.

### <a name="approve-privileged-access-request-for-the-creation-of-a-new-journal-rule"></a>새 저널 규칙 만들기에 대한 권한 있는 액세스 요청 승인

1. 테스트 환경의 사용자 3에 대한 자격 증명을 사용하여 [Microsoft 365](https://admin.microsoft.com) 관리 센터에 로그인합니다(테스트 환경에서 "권한이 부여된 액세스 승인자" 보안 그룹의 구성원).

2. 관리 센터에서 개인 **정보** 보호  >  **권한 & 설정**  >  **보안으로 이동합니다.**

3. 액세스 **정책 및 요청 관리 선택.**

4. 보류 중인 요청을 선택한 다음 **승인을** 선택하여 전역 관리자 계정에 대한 액세스 권한을 부여하여 새 저널 규칙을 만들 수 있습니다. 전역 관리자 계정(요청하는 사용자)은 승인이 허용된 전자 메일 확인을 받게 됩니다.

### <a name="test-creating-a-new-journal-rule-with-privileged-access-approved-for-the-new-journalrule-task"></a>권한 있는 액세스가 승인된 새 저널 규칙 만들기 New-JournalRule 테스트

1. 로컬 컴퓨터에서 **Microsoft Corporation의** Exchange Online 원격 PowerShell 모듈을 열고 Microsoft Exchange Online 환경의 전역 관리자 계정을 사용하여  >  **원격 PowerShell 모듈에** 로그인합니다.

1. Exchange 관리 PowerShell에서 조직에 대한 새 저널 규칙을 생성합니다.

   ```ExchangeManagementPowerShell
   New-JournalRule -Name "JournalRule2" -Recipient user1@<your subscription domain> -JournalEmailAddress user1@<your subscription domain> -Scope Global -Enabled $true
   ```

1. Exchange 관리 PowerShell에서 새 저널 규칙이 만들어졌습니다.

## <a name="next-step"></a>다음 단계

테스트 환경에서 [추가 정보](m365-enterprise-test-lab-guides.md#information-protection) 보호 기능을 살펴보아야 합니다.

## <a name="see-also"></a>참고 항목

[엔터프라이증용 Microsoft 365 테스트 랩 가이드](m365-enterprise-test-lab-guides.md)

[엔터프라이즈용 Microsoft 365 개요](microsoft-365-overview.md)

[기업용 Microsoft 365 설명서](/microsoft-365-enterprise/)

---
title: 감독 정책 구성
description: 내부 또는 외부 검토자에 의해 검사할 직원 커뮤니케이션을 캡처하도록 Office 365에서 통신 감독 정책을 구성합니다.
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: Admin
ms.topic: article
f1_keywords:
- ms.o365.cc.SupervisoryReview
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MET150
- MOE150
titleSuffix: Office 365 Compliance
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 74244b5288043a1d1bc62e0ae09ee8c25ff7d4e1
ms.sourcegitcommit: 27daadad9ca0f02a833ff3cff8a574551b9581da
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2020
ms.locfileid: "47546780"
---
# <a name="configure-supervision-policies-in-office-365"></a>Office 365에서 감독 정책 구성

>[!IMPORTANT]
>2020년 2월 Microsoft 365 규정 준수의 커뮤니케이션 규정 준수가 릴리스된 후 Office 365의 감독은 사용 중지됩니다. 감독 정책은 더 이상 만들 수 없습니다. 정책은 결국 읽기 전용 액세스의 연장된 후에 제거됩니다.
>
>감독을 사용하는 경우 다음에 유의해야 합니다.
>
>- 2020년 6월 15일부터 테넌트는 새 감독 정책을 만들 수 없습니다.
>- 2020년 8월 31일부터 기존 정책은 새 메시지 캡처를 중지합니다.
>- 2020년 10월 26일부터 기존 정책이 삭제됩니다.
>
>현재 Office 365에서 감독을 탐색하거나 사용하고 있는 고객이 훨씬 [](communication-compliance.md) 풍부한 지능형 기능 집합으로 커뮤니케이션 모니터링 또는 규정 요구 사항을 해결하기 위해 새로운 통신 준수 솔루션을 사용하는 것이 능동적으로 권장됩니다.

감독 정책을 사용하여 내부 또는 외부 검토자에 의해 검사할 직원 커뮤니케이션을 캡처합니다. 감독 정책이 조직의 통신을 모니터링하는 데 도움이 되는 방법에 대한 자세한 내용은 [Office 365의](supervision-policies.md)감독 정책을 참조하세요.

>[!NOTE]
>감독 정책에 따라 모니터링되는 사용자는 Microsoft 365 E5 준수 라이선스, 고급 준수 추가 기능의 Office 365 Enterprise E3 라이선스가 있어야 합니다. 또는 Office 365 Enterprise E5 구독에 포함되거나 Microsoft 365 E5 구독에 포함되어 있어야 합니다.
>기존 Enterprise E5 요금제가 없는 경우 감독을 시도하려는 경우 [Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279)평가판을 등록할 수 있습니다.
  
다음 단계에 따라 조직에서 감독을 설정하고 사용하세요.
  
- **1단계(선택 사항)**: [감독을 위한 그룹 설정](#step-1-set-up-groups-for-supervision-optional)

    감독 정책 사용을 시작하기 전에 검토된 커뮤니케이션이 필요한 사용자와 검토를 수행할 인원을 결정하십시오. 소수의 사용자만 시작하여 감독의 작동 방식에 대해 보고 싶은 경우 지금 그룹 설정을 건너뛸 수 있습니다.

- **2단계(필수)**: [조직에서](#step-2-make-supervision-available-in-your-organization-required) 감독을 사용할 수 있도록 설정

    정책을 설정할 수 있도록 감독 검토 역할 그룹에 자신을 추가합니다. 이 역할이 할당된 모든  사람은 보안 및 준수 센터의 감독 & 수 있습니다. 검토 가능한 전자 메일이 Exchange Online에서 호스팅된 경우 각 검토자는 Exchange Online에 대한 원격 [PowerShell](https://docs.microsoft.com/powershell/exchange/disable-access-to-exchange-online-powershell)액세스 권한이 있어야 합니다.

- **3단계(선택 사항)**: 사용자 지정 중요한 정보 유형 및 [사용자 지정 키워드 사전 만들기](#step-3-create-custom-sensitive-information-types-and-custom-keyword-dictionaries-optional)

    감독 정책에 대한 사용자 지정 중요한 정보 유형 또는 사용자 지정 키워드 사전이 필요한 경우 감독 마법사를 시작하기 전에 만들어야 합니다.

- **4단계(필수)**: 감독 [정책 설정](#step-4-set-up-a-supervision-policy-required)

    보안 및 준수 센터에서 & 정책을 만들 수 있습니다. 이러한 정책은 조직에서 검토할 커뮤니케이션을 정의하고 검토를 수행하는 대상을 지정합니다. 커뮤니케이션에는 전자 메일 및 Microsoft Teams 통신, 제3자 플랫폼 통신(예: Facebook, Twitter 등)이 포함됩니다. 조직에서 만든 감독 정책은 Microsoft 365 구독의 통신 감독에서 지원되지 않습니다.

- **5단계(선택 사항)**: [통신 감독 정책 테스트](#step-5-test-your-supervision-policy-optional)

    감독 정책을 테스트하여 감독 정책이 원하는 경우와 같은 기능을 하는지 검사합니다. 규정 준수 전략이 표준을 충족하는지 보장하는 것이 중요합니다.

## <a name="step-1-set-up-groups-for-supervision-optional"></a>1단계: 감독을 위한 그룹 설정(선택 사항)

 감독 정책을 만들 때 통신을 검사한 사용자와 검토를 수행하는 사용자 정의합니다. 정책에서 전자 메일 주소를 사용하여 개인 또는 사용자 그룹을 식별합니다. 설정을 간소화하기 위해 통신을 검사한 사용자에 대한 그룹과 해당 통신을 검토하는 사용자에 대한 그룹을 만들 수 있습니다. 그룹을 사용하는 경우 여러 가지가 필요할 수 있습니다. 예를 들어 서로 다른 두 사용자 그룹 간의 통신을 모니터링하거나 감독되지 않을 그룹을 지정하려는 경우를 예로 들 수 있습니다.

다음 차트를 사용하여 조직의 통신 감독 정책에 대한 그룹을 구성할 수 있습니다.

| **정책 구성원** | **지원되는 그룹** | **미지원 그룹** |
|:-----|:-----|:-----|
|감독된 사용자 <br> 감독되지 않는 사용자 | 메일 그룹 <br> Microsoft 365 그룹 | 동적 메일 그룹 |
| 검토자 | 메일 사용 가능 보안 그룹  | 메일 그룹 <br> 동적 메일 그룹 |
  
관리되는 사용자에 대해 Microsoft 365 그룹을 선택하면 정책은 공유 사서함 및 그룹과 연결된 Microsoft Teams 채널의 콘텐츠를 모니터링합니다. 메일 목록을 선택하면 정책이 개별 사용자 사서함을 모니터링합니다.

대규모 엔터프라이즈 조직에서 감독되는 사용자를 관리하려면 대규모 그룹에서 모든 사용자를 모니터링해야 할 수 있습니다. PowerShell을 사용하여 할당된 그룹에 대한 전역 감독 정책에 대한 메일 그룹을 구성할 수 있습니다. 이렇게 하면 단일 정책을 사용하여 수천 명의 사용자를 모니터링하고 새 직원이 조직에 가입할 때 감독 정책을 업데이트할 수 있습니다.

1. 다음 속성을 [](https://docs.microsoft.com/powershell/module/exchange/new-distributiongroup) 사용하여 전역 감독 정책에 대한 전용 메일 그룹을 만드시다. 이 메일 그룹이 다른 목적이나 다른 Office 365 서비스에 사용되지 않는지 확인

    - **MemberDepartRestriction = Closed**. 사용자가 메일 그룹에서 자신을 제거할 수 없는지 확인
    - **MemberJoinRestriction = Closed**. 사용자가 메일 그룹에 자신을 추가할 수 없는지 확인
    - **ModerationEnabled = True**. 이 그룹에 전송된 모든 메시지에 승인이 적용되고 그룹이 감독 정책 구성 외부에서 통신하는 데 사용되지 않는지 확인

    ```PowerShell
    New-DistributionGroup -Name <your group name> -Alias <your group alias> -MemberDepartRestriction 'Closed' -MemberJoinRestriction 'Closed' -ModerationEnabled $true
    ```

2. 사용되지 않는 [Exchange](https://docs.microsoft.com/Exchange/recipients/mailbox-custom-attributes?view=exchserver-2019&viewFallbackFrom=exchonline-ww) 사용자 지정 특성을 선택하여 조직의 감독 정책에 추가된 사용자를 추적합니다.

3. 다음과 같은 PowerShell 스크립트를 일정에 따라 실행하여 감독 정책에 사용자를 추가합니다.

    ```PowerShell
    $Mbx = (Get-Mailbox -RecipientTypeDetails UserMailbox -ResultSize Unlimited -Filter {CustomAttribute9 -eq $Null})
    $i = 0
    ForEach ($M in $Mbx) 
    {
      Write-Host "Adding" $M.DisplayName
      Add-DistributionGroupMember -Identity <your group name> -Member $M.DistinguishedName -ErrorAction SilentlyContinue
      Set-Mailbox -Identity $M.Alias -<your custom attribute name> SRAdded 
      $i++
    }
    Write-Host $i "Mailboxes added to supervisory review distribution group."
    ```

그룹 설정에 대한 자세한 내용은 다음을 참조하세요.

- [메일 그룹 만들기 및 관리](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-distribution-groups/manage-distribution-groups)
- [메일 사용 가능 보안 그룹 관리](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-mail-enabled-security-groups)
- [Microsoft 365 그룹 개요](https://docs.microsoft.com/office365/admin/create-groups/office-365-groups?view=o365-worldwide)

## <a name="step-2-make-supervision-available-in-your-organization-required"></a>2단계: 조직에서 감독을 사용할 수 있도록 설정(필수)

보안 **및** 준수 센터에서 감독을 메뉴 옵션으로 사용할 & 관리 검토 관리자 역할이 할당되어야 합니다.
  
이렇게 하여 자신을 관리 검토 역할 그룹의 구성원으로 추가하거나 역할 그룹을 만들 수 있습니다.
  
### <a name="add-members-to-the-supervisory-review-role-group"></a>관리 검토 역할 그룹에 구성원 추가

1. 조직의 [https://protection.office.com](https://protection.office.com) 관리자 계정에 대한 자격 증명을 사용하여 로그인합니다.

2. 보안 및 & 센터에서 사용 **권한으로 이동 합니다.**

3. 관리 **검토 역할** 그룹을 선택하고 편집 아이콘을 클릭합니다.

4. 구성원 **섹션에서** 조직에 대한 통신 감독을 관리하려는 인원을 추가합니다.

### <a name="create-a-new-role-group"></a>새 역할 그룹 만들기

1. 조직의 [https://protection.office.com/permissions](https://protection.office.com/permissions) 관리자 계정에 대한 자격 증명을 사용하여 로그인합니다.

2. 보안 및 & 센터에서 사용 권한으로 이동한 다음 추가()를  **+** 클릭합니다.

3. 역할 **섹션에서** 추가()를 클릭하고 아래로 스크롤하여 관리 검토 **+** **관리자로 스크롤합니다.** 역할 그룹에 이 역할을 추가합니다.

4. 구성원 **섹션에서** 조직에 대한 통신 감독을 관리하려는 인원을 추가합니다.

역할 그룹 및 사용 권한에 대한 자세한 내용은 준수 센터의 사용 [권한을 참조하세요.](../security/office-365-security/permissions-in-the-security-and-compliance-center.md)

### <a name="enable-remote-powershell-access-for-reviewers-if-email-is-hosted-on-exchange-online"></a>검토자에 대해 원격 PowerShell 액세스 사용(전자 메일이 Exchange Online에 호스트된 경우)

1. Exchange Online [PowerShell 액세스 사용](https://docs.microsoft.com/powershell/exchange/disable-access-to-exchange-online-powershell)또는 사용 안 하도록 설정의 지침을 따르는 합니다.

## <a name="step-3-create-custom-sensitive-information-types-and-custom-keyword-dictionaries-optional"></a>3단계: 사용자 지정 중요한 정보 유형 및 사용자 지정 키워드 사전 만들기(선택 사항)

감독 정책 마법사에서 기존 사용자 지정 중요한 정보 유형 또는 사용자 지정 키워드 사전을 선택하려면 먼저 필요한 경우 이러한 항목을 만들어야 합니다.

### <a name="create-custom-keyword-dictionarylexicon-optional"></a>사용자 지정 키워드 사전/사전 만들기(선택 사항)

메모장과 같은 텍스트 편집기를 사용하여 감독 정책에서 모니터링할 키워드 용어가 포함된 파일을 만들 수 있습니다. 각 용어가 별도의 줄에 있는지 확인하여 **유니코드/UTF-16(Little Endian)** 형식으로 파일을 저장합니다.

### <a name="create-custom-sensitive-information-types"></a>사용자 지정 중요한 정보 유형 만들기

1. 새 중요한 정보 유형을 만들고 보안 및 준수 센터에서 사용자 지정 & 추가합니다. 분류 **중요한** \> **정보 유형으로 이동하고** 새 중요한 정보 유형 마법사의 **단계를 따릅니다.** 여기서 다음을 할 수 있습니다.

    - 중요한 정보 유형에 대한 이름 및 설명 정의
    - 근접성, 신뢰 수준 및 기본 패턴 요소 정의
    - 일치하는 요소에 대한 요구 사항으로 사용자 지정 사전 가져오기
    - 선택을 검토하고 중요한 정보 유형 만들기

    자세한 내용은 사용자 지정 중요한 정보 유형 [만들기](create-a-custom-sensitive-information-type.md) 및 키워드 [사전 만들기를 참조하세요.](create-a-keyword-dictionary.md)

    사용자 지정 사전/사전을 만든 후 [Get-DlpKeywordDictionary](https://docs.microsoft.com/powershell/module/exchange/get-dlpkeyworddictionary) cmdlet을 사용하여 구성된 키워드를 보거나 [Set-DlpKeywordDictionary](https://docs.microsoft.com/powershell/module/exchange/set-dlpkeyworddictionary) cmdlet을 사용하여 용어를 추가 및 제거할 수 있습니다.

## <a name="step-4-set-up-a-supervision-policy-required"></a>4단계: 감독 정책 설정(필수)
  
1. 조직의 [https://protection.office.com](https://protection.office.com) 관리자 계정에 대한 자격 증명을 사용하여 로그인합니다.

2. 보안 및 & 센터에서 **감독을 선택합니다.**
  
3. **만들기를** 선택하고 마법사에 따라 정책 구성을 설정합니다. 마법사를 사용하여 다음을 실행합니다.

    - 정책에 이름과 설명을 지정합니다.
    - 제외할 사용자 또는 그룹 선택을 포함하여 감독할 사용자 또는 그룹을 선택 합니다.
    - 감독 정책 조건을 [정의합니다.](supervision-policies.md#ConditionalSettings) 메시지 주소, 키워드, 파일 형식 및 크기 일치 조건에서 선택할 수 있습니다.
    - 중요한 정보 유형을 포함할지 선택하십시오. 여기서 기본 및 사용자 지정 중요한 정보 유형을 선택할 수 있습니다.
    - 비방성 언어 모델을 사용하도록 설정하려면 선택 합니다. 전자 메일 메시지 본문에 보내거나 받은 부적절한 언어를 검색합니다.
    - 검토할 통신 비율을 정의합니다.
    - 정책에 대한 검토자 선택 검토자는 개별 사용자 또는 메일 사용이 가능한 [보안 그룹일 수 있습니다.](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-mail-enabled-security-groups#create-a-mail-enabled-security-group) 모든 검토자는 Exchange Online에 호스트된 사서함이 있어야 합니다.
    - 정책 선택을 검토하고 정책을 생성합니다.

## <a name="step-5-test-your-supervision-policy-optional"></a>5단계: 감독 정책 테스트(선택 사항)

통신 감독 정책을 만든 후 정의한 조건이 정책에 의해 제대로 적용되고 있는지 테스트하는 것이 좋습니다. 감독 정책에 중요한 정보 유형이 포함된 경우 [DLP(데이터](create-test-tune-dlp-policy.md) 손실 방지) 정책을 테스트할 수도 있습니다. 다음 단계에 따라 감독 정책을 테스트합니다.

1. 테스트할 정책에 정의된 감독된 사용자로 로그인한 전자 메일 클라이언트 또는 Microsoft Teams를 여는 경우
2. 감독 정책에서 정의한 기준을 충족하는 전자 메일 또는 Microsoft Teams 채팅을 전송합니다. 키워드, 첨부 파일 크기, 도메인 등이 될 수 있습니다. 정책에서 구성된 조건부 설정이 너무 제한적이거나 너무 무의미한지 확인합니다.

    >[!NOTE]
    >정의된 정책이 적용된 전자 메일은 거의 실시간으로 처리되고 정책이 구성된 직후 테스트할 수 있습니다. Microsoft Teams의 채팅은 정책에서 완전히 처리되는 데 최대 24시간이 걸릴 수 있습니다. 

3. 통신 감독 정책에 지정된 검토자로 Microsoft 365에 로그인합니다. 사용자 **지정** 정책 열기 감독으로 이동하여  >    >   정책에 대한 보고서를 볼 수 있습니다.


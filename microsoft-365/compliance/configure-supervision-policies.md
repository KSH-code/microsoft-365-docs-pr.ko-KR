---
title: 감독 정책 구성
description: 내부 또는 외부 검토자가 검사할 수 있도록 직원 통신을 캡처하기 위해 Office 365에서 통신 감독 정책을 구성 합니다.
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
ms.openlocfilehash: 9cbde149419320495e3848867846322733cb56f9
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/05/2020
ms.locfileid: "44033658"
---
# <a name="configure-supervision-policies-in-office-365"></a>Office 365에서 감독 정책 구성

>[!IMPORTANT]
>Microsoft 365 준수에서의 통신 준수 릴리스 (2020 년 2 월), Office 365의 감독은 폐기 되 고 있습니다. 감독 정책은 더 이상 만들 수 없으며 읽기 전용 권한이 확장 된 후에는 결국 정책이 제거 됩니다.
>
>감독을 사용 하는 경우 다음 사항을 염두에 두어야 합니다.
>
>- 6 월 2020 15 일부 터 테 넌 트에는 새 감독 정책을 만들 수 없습니다.
>- 2020 년 8 월 31 일부터 기존 정책이 새 메시지 캡처를 중지 합니다.
>- 26th 년 10 월 2020까지 기존 정책이 삭제 됩니다.
>
>현재 Office 365의 감독을 탐험 하거나 사용 하는 고객은 새로운 [통신 준수](communication-compliance.md) 솔루션을 사용 하 여 통신 모니터링 또는 규정 요구 사항을 보다 풍부한 지능형 기능 집합으로 처리 하도록 합니다.

감독 정책을 사용 하 여 내부 또는 외부 검토자가 검사할 직원 통신을 캡처할 수 있습니다. 감독 정책을 통해 조직의 통신을 모니터링 하는 방법에 대 한 자세한 내용은 [Office 365의 감독 정책을](supervision-policies.md)참조 하세요.

>[!NOTE]
>감독 정책에 따라 모니터링 되는 사용자에 게는 Microsoft 365 E5 준수 라이선스, 고급 준수 추가 기능이 포함 된 Office 365 Enterprise E3 라이선스 또는 Office 365 Enterprise E5 구독에 포함 되거나 Microsoft 365 E5 구독에 포함 되어 있어야 합니다.
>기존 Enterprise E5 요금제가 없고, 감독을 려 고 하는 경우 [Office 365 Enterprise e 5의 평가판에 등록할](https://go.microsoft.com/fwlink/p/?LinkID=698279)수 있습니다.
  
조직에서 감독을 설정 및 사용 하려면 다음 단계를 수행 합니다.
  
- **1 단계 (옵션)**: [감독을 위한 그룹 설정](#step-1-set-up-groups-for-supervision-optional)

    감독 정책을 사용 하기 전에 의사 소통을 검토 하 고 검토를 수행 해야 하는 사람을 결정 합니다. 소수의 사용자만을 시작 하 여 감독의 작동 방식을 확인 하려는 경우 지금 그룹 설정 건너뛰기를 건너뛸 수 있습니다.

- **2 단계 (필수 사항)**: [조직에서 감독을 사용할 수 있도록 설정](#step-2-make-supervision-available-in-your-organization-required)

    정책을 설정할 수 있도록 자신을 관리 검토 역할 그룹에 추가 합니다. 이 역할이 할당 된 모든 사용자는 보안 & 준수 센터의 **감독** 페이지에 액세스할 수 있습니다. 다시 볼 수 있는 전자 메일이 Exchange Online에서 호스팅되는 경우 각 검토자 [에 게 Exchange online에 대 한 원격 PowerShell 액세스](https://docs.microsoft.com/powershell/exchange/exchange-online/disable-access-to-exchange-online-powershell)권한이 있어야 합니다.

- **3 단계 (선택 사항)**: [사용자 지정 중요 한 정보 유형 및 사용자 지정 키워드 사전 만들기](#step-3-create-custom-sensitive-information-types-and-custom-keyword-dictionaries-optional)

    감독 정책에 대 한 사용자 지정 중요 한 정보 유형 또는 사용자 지정 키워드 사전이 필요한 경우에는 감독 마법사를 시작 하기 전에 만들어야 합니다.

- **4 단계 (필수 사항)**: [감독 정책 설정](#step-4-set-up-a-supervision-policy-required)

    보안 & 준수 센터에서 감독 정책을 만듭니다. 이러한 정책은 조직에서 검토할 대상이 되는 통신을 정의 하 고 검토를 수행 하는 사람을 지정 합니다. 통신에는 전자 메일 및 Microsoft 팀 통신과 타사 플랫폼 통신 (예: Facebook, Twitter 등)이 포함 됩니다. 조직에서 만든 감독 정책은 Microsoft 365 구독의 통신 감독에서 지원 되지 않습니다.

- **5 단계 (선택 사항)**: [통신 감독 정책 테스트](#step-5-test-your-supervision-policy-optional)

    감독 정책을 테스트 하 여 원하는 대로 작동 하는지 확인 합니다. 규정 준수 전략이 표준을 충족 하는지 확인 하는 것이 중요 합니다.

## <a name="step-1-set-up-groups-for-supervision-optional"></a>1 단계: 감독에 대 한 그룹 설정 (선택 사항)

 감독 정책을 만들 때는 통신을 검사 하 고 검토를 수행 하는 사람을 정의 합니다. 정책에서는 전자 메일 주소를 사용 하 여 개인 이나 사용자 그룹을 식별 합니다. 설정을 간소화 하기 위해 통신을 검토 하는 사용자를 위해 통신이 검색 되 고 그룹이 있는 사용자를 위해 그룹을 만들 수 있습니다. 그룹을 사용 하는 경우 몇 가지 필요할 수 있습니다. 예를 들어 서로 다른 두 사용자 그룹 간의 통신을 모니터링 하거나 감독 하지 않을 그룹을 지정 하려는 경우

다음 차트를 사용 하 여 통신 감독 정책에 맞게 조직의 그룹을 구성 하는 데 도움이 됩니다.

| **정책 구성원** | **지원 되는 그룹** | **지원 되지 않는 그룹** |
|:-----|:-----|:-----|
|감독 사용자 <br> 감독 되지 않은 사용자 | 메일 그룹 <br> Microsoft 365 그룹 | 동적 메일 그룹 |
| 가 | 메일 사용 가능 보안 그룹  | 메일 그룹 <br> 동적 메일 그룹 |
  
감독 되는 사용자에 대해 Microsoft 365 그룹을 선택 하면 정책이 공유 사서함의 콘텐츠 및 해당 그룹과 연결 된 Microsoft 팀 채널을 모니터링 합니다. 메일 그룹을 선택 하는 경우 정책은 개별 사용자 사서함을 모니터링 합니다.

대규모 엔터프라이즈 조직에서 감독 사용자를 관리 하려면 대규모 그룹의 모든 사용자를 모니터링 해야 할 수 있습니다. PowerShell을 사용 하 여 할당 된 그룹에 대 한 전역 감독 정책에 대 한 메일 그룹을 구성할 수 있습니다. 이를 통해 단일 정책을 사용 하는 수천 명의 사용자를 모니터링 하 고 조직에 새 직원이 참가할 때 감독 정책을 업데이트할 수 있습니다.

1. 다음 속성을 사용 하 여 전역 감독 정책에 대 한 전용 [메일 그룹](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/new-distributiongroup?view=exchange-ps) 을 만듭니다 .이 메일 그룹이 다른 목적이 나 기타 Office 365 서비스에 사용 되지 않는지 확인 합니다.

    - **MemberDepartRestriction = 닫힘** 사용자가 메일 그룹에서 자신을 제거할 수 없도록 합니다.
    - **Memberjoinrestriction = 닫힘** 사용자가 메일 그룹에 자신을 추가할 수 없도록 합니다.
    - **ModerationEnabled = True** 이 그룹으로 전송 되는 모든 메시지에 대 한 승인이 가능 하며, 해당 그룹이 감독 정책 구성 외부에서 통신 하는 데 사용 되 고 있지는 않은지 확인 합니다.

    ```PowerShell
    New-DistributionGroup -Name <your group name> -Alias <your group alias> -MemberDepartRestriction 'Closed' -MemberJoinRestriction 'Closed' -ModerationEnabled $true
    ```

2. 조직의 감독 정책에 추가한 사용자를 추적 하려면 사용 되지 않는 [Exchange 사용자 지정 특성](https://docs.microsoft.com/Exchange/recipients/mailbox-custom-attributes?view=exchserver-2019&viewFallbackFrom=exchonline-ww) 을 선택 합니다.

3. 다음 PowerShell 스크립트를 반복 된 일정에 따라 실행 하 여 감독 정책에 사용자를 추가 합니다.

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

그룹을 설정 하는 방법에 대 한 자세한 내용은 다음을 참조 하십시오.

- [메일 그룹 만들기 및 관리](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-distribution-groups/manage-distribution-groups)
- [메일 사용 가능 보안 그룹 관리](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-mail-enabled-security-groups)
- [Microsoft 365 그룹 개요](https://docs.microsoft.com/office365/admin/create-groups/office-365-groups?view=o365-worldwide)

## <a name="step-2-make-supervision-available-in-your-organization-required"></a>2 단계: 조직에서 감독을 사용할 수 있도록 설정 (필수)

보안 & 준수 센터에서 **감독** 을 메뉴 옵션으로 사용할 수 있도록 하려면 관리 검토 관리자 역할이 할당 되어야 합니다.
  
이렇게 하려면 자신을 관리 검토 역할 그룹의 구성원으로 추가 하거나 역할 그룹을 만들 수 있습니다.
  
### <a name="add-members-to-the-supervisory-review-role-group"></a>관리 검토 역할 그룹에 구성원 추가

1. 조직의 관리자 [https://protection.office.com](https://protection.office.com) 계정에 대 한 자격 증명을 사용 하 여 로그인 합니다.

2. 보안 & 준수 센터에서 **사용 권한**으로 이동 합니다.

3. **관리 검토** 역할 그룹을 선택한 다음 편집 아이콘을 클릭 합니다.

4. **구성원** 섹션에서 조직에 대 한 통신 감독을 관리 하려는 사용자를 추가 합니다.

### <a name="create-a-new-role-group"></a>새 역할 그룹 만들기

1. 조직의 관리자 [https://protection.office.com/permissions](https://protection.office.com/permissions) 계정에 대 한 자격 증명을 사용 하 여 로그인 합니다.

2. 보안 & 준수 센터에서 **사용 권한** 으로 이동한 다음 추가 (**+**)를 클릭 합니다.

3. **역할** 섹션에서 추가 (**+**)를 클릭 하 고 아래로 스크롤하여 **관리 검토 관리자**를 선택 합니다. 이 역할을 역할 그룹에 추가 합니다.

4. **구성원** 섹션에서 조직에 대 한 통신 감독을 관리 하려는 사용자를 추가 합니다.

역할 그룹 및 사용 권한에 대 한 자세한 내용은 [준수 센터의 사용 권한을](../security/office-365-security/permissions-in-the-security-and-compliance-center.md)참조 하세요.

### <a name="enable-remote-powershell-access-for-reviewers-if-email-is-hosted-on-exchange-online"></a>검토자에 대해 원격 PowerShell 액세스 사용 (전자 메일이 Exchange Online에서 호스트 되는 경우)

1. [사용 또는 사용 안 함 Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/disable-access-to-exchange-online-powershell)에 대 한 지침을 따릅니다.

## <a name="step-3-create-custom-sensitive-information-types-and-custom-keyword-dictionaries-optional"></a>3 단계: 사용자 지정 중요 한 정보 유형 및 사용자 지정 키워드 사전 만들기 (선택 사항)

감독 정책 마법사에서 기존 사용자 지정 중요 한 정보 유형 또는 사용자 지정 키워드 사전을 선택 하려면 먼저 필요한 경우 이러한 항목을 만들어야 합니다.

### <a name="create-custom-keyword-dictionarylexicon-optional"></a>사용자 지정 키워드 사전/어휘 만들기 (선택 사항)

메모장과 같은 텍스트 편집기를 사용 하 여 감독 정책에서 모니터링할 키워드 용어를 포함 하는 파일을 만듭니다. 각 용어가 별도의 줄에 있는지 확인 하 고 파일을 **유니코드/u t f-16 (꼬마)** 형식으로 저장 합니다.

### <a name="create-custom-sensitive-information-types"></a>사용자 지정 중요 한 정보 유형 만들기

1. 보안 & 준수 센터에서 새 중요 한 정보 유형을 만들고 사용자 지정 사전을 추가 합니다. **중요 한 정보** 유형 **분류** \> 로 이동 하 여 **새 중요 한 정보 유형 마법사**의 단계를 따릅니다. 여기에서 다음을 수행 합니다.

    - 중요 한 정보 유형에 대 한 이름 및 설명 정의
    - 근접성, 신뢰 수준 및 주 패턴 요소 정의
    - 일치 요소에 대 한 요구 사항으로 사용자 지정 사전 가져오기
    - 선택 항목 검토 및 중요 한 정보 유형 만들기

    자세한 내용은 [사용자 지정 중요 한 정보 유형 만들기](create-a-custom-sensitive-information-type.md) 및 [키워드 사전 만들기](create-a-keyword-dictionary.md) 를 참조 하세요.

    사용자 지정 사전/어휘를 만든 후에는 [DlpKeywordDictionary](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-dlp/get-dlpkeyworddictionary) cmdlet을 사용 하 여 구성 된 키워드를 보거나 [DlpKeywordDictionary](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-dlp/set-dlpkeyworddictionary) cmdlet에서 용어를 추가 및 제거할 수 있습니다.

## <a name="step-4-set-up-a-supervision-policy-required"></a>4 단계: 감독 정책 설정 (필수)
  
1. 조직의 관리자 [https://protection.office.com](https://protection.office.com) 계정에 대 한 자격 증명을 사용 하 여 로그인 합니다.

2. 보안 & 준수 센터에서 **감독**을 선택 합니다.
  
3. **만들기** 를 선택 하 고 마법사의 지시에 따라 정책 구성을 설정 합니다. 마법사를 사용 하 여 다음을 수행할 수 있습니다.

    - 정책에 이름과 설명을 지정 합니다.
    - 제외할 사용자 또는 그룹 선택을 비롯 하 여 감독할 사용자 또는 그룹을 선택 합니다.
    - 감독 정책 [조건을](supervision-policies.md#ConditionalSettings)정의 합니다. 메시지 주소, 키워드, 파일 형식 및 크기 일치 조건에서 선택할 수 있습니다.
    - 중요 한 정보 유형을 포함 하 고 싶은 경우 선택 합니다. 여기에서 기본 및 사용자 지정 중요 한 정보 유형을 선택할 수 있습니다.
    - 공격적인 언어 모델을 사용 하도록 설정 하려면 선택 합니다. 이는 전자 메일 메시지 본문에서 보내거나 받은 부적절 한 언어를 감지 합니다.
    - 검토할 통신의 비율을 정의 합니다.
    - 정책에 대 한 검토자를 선택 합니다. 검토자는 개별 사용자 또는 [메일 사용이 가능한 보안 그룹이](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-mail-enabled-security-groups#create-a-mail-enabled-security-group)될 수 있습니다. 모든 검토자에 게 Exchange Online에서 호스트 되는 사서함이 있어야 합니다.
    - 정책 선택을 검토 하 고 정책을 만듭니다.

## <a name="step-5-test-your-supervision-policy-optional"></a>5 단계: 감독 정책 테스트 (선택 사항)

통신 감독 정책을 만든 후에는 테스트를 통해 정의한 조건이 정책에 의해 적절 하 게 적용 되는지 확인 하는 것이 좋습니다. 또한 감독 정책에 중요 한 정보 유형이 포함 되어 있는 경우 [DLP (데이터 손실 방지) 정책을 테스트할](create-test-tune-dlp-policy.md) 수도 있습니다. 다음 단계에 따라 감독 정책을 테스트 합니다.

1. 테스트할 정책에 정의 된 감독 된 사용자로 로그인 한 전자 메일 클라이언트 또는 Microsoft 팀을 엽니다.
2. 감독 정책에 정의한 기준을 충족 하는 전자 메일 또는 Microsoft 팀 채팅을 보냅니다. 키워드, 첨부 파일 크기, 도메인 등이 될 수 있습니다. 정책에서 구성 된 조건부 설정이 너무 제한적일 또는 너무 lenient 인지 확인 합니다.

    >[!NOTE]
    >정의 된 정책이 적용 되는 전자 메일은 거의 실시간으로 처리 되며 정책이 구성 된 직후에 테스트할 수 있습니다. Microsoft 팀의 채팅에는 정책에서 전체 프로세스를 수행 하는 데 최대 24 시간이 걸릴 수 있습니다. 

3. 통신 감독 정책에 지정 된 검토자에 게 Microsoft 365에 로그인 합니다. *사용자 지정 정책이* > **열려** 있는 **감독** > 을 탐색 하 여 정책에 대 한 보고서를 확인 합니다.


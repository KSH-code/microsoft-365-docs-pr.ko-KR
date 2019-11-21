---
title: Microsoft 365에 대 한 통신 준수 구성 (미리 보기)
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
description: 검토를 위해 직원 통신을 구성 하는 통신 준수 정책을 설정 합니다.
ms.openlocfilehash: 0a830914a22968119d836e2190a6f133d91fd305
ms.sourcegitcommit: 5f96fa472cbdca30c2cfe24d66c9c6fcaedb1a6b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/20/2019
ms.locfileid: "38755606"
---
# <a name="configure-communication-compliance-for-microsoft-365-preview"></a>Microsoft 365에 대 한 통신 준수 구성 (미리 보기)

> [!IMPORTANT]
> 이 항목은 Microsoft 365 구독의 통신 준수 구성에 적용 됩니다. Office 365 구독에 대 한 감독 정책을 구성 하려면 [office 365에 대 한 감독 구성을](supervision-policies.md)참조 하십시오.

통신 준수 정책을 사용 하 여 내부 또는 외부 검토자가 검사할 직원 통신을 캡처할 수 있습니다. 통신 준수 정책을 통해 조직의 통신을 모니터링 하는 방법에 대 한 자세한 내용은 [Microsoft 365의 통신 준수 정책을](communication-compliance.md)참조 하세요.

> [!NOTE]
> 통신 준수 정책에 따라 모니터링 되는 사용자에 게는 Microsoft 365 E5 준수 라이선스, 고급 준수 추가 기능이 포함 된 Office 365 Enterprise E3 라이선스 또는 Office 365 Enterprise E5 구독에 포함 되어 있어야 합니다.
> 기존 Enterprise E5 요금제가 없고 통신 준수를 시도 하려는 경우 [Office 365 Enterprise e 5의 평가판에 등록할](https://go.microsoft.com/fwlink/p/?LinkID=698279)수 있습니다.
  
Microsoft 365 조직에서 통신 준수를 설정 및 사용 하려면 다음 단계를 수행 합니다.
  
- **1 단계 (옵션)**: [통신 준수를 위한 그룹 설정](#step-1-set-up-groups-for-communication-compliance-optional) 

    통신 준수를 시작 하기 전에 연락이 검토 되 고 검토를 수행 하는 사용자를 결정 합니다. 소수의 사용자만을 시작 하 여 통신 준수의 작동 방식을 확인 하려면 지금은 그룹 설정을 건너뛰어도 됩니다.

- **2 단계 (필수 사항)**: [조직에서 통신 준수를 사용할 수 있도록 설정](#step-2-make-communication-compliance-available-in-your-organization-required)

    정책을 설정할 수 있도록 자신을 **관리 검토 관리자** 역할에 추가 합니다. 또한 **관리 검토 관리자**, **사례 관리** 및 역할이 일치 하는 메시지에 대해 조사 및 업데이트 관리 작업을 수행 하는 사용자 또는 그룹에 대 한 역할을 **검토** 하는 그룹을 만들어야 합니다. 이러한 역할이 할당 된 모든 사용자는 Microsoft 365 준수 센터의 **통신 준수** 페이지에 액세스할 수 있습니다. 다시 볼 수 있는 전자 메일이 Exchange Online에서 호스팅되는 경우 각 검토자 [에 게 Exchange online에 대 한 원격 PowerShell 액세스](https://docs.microsoft.com/powershell/exchange/exchange-online/disable-access-to-exchange-online-powershell)권한이 있어야 합니다.

- **3 단계 (필수 사항)**: [통신 준수 정책 설정](#step-3-create-a-communication-compliance-policy-required)

    Microsoft 365 준수 센터에서 통신 준수 정책을 만듭니다. 이러한 정책은 조직에서 검토할 대상이 되는 통신을 정의 하 고 검토를 수행 하는 사람을 지정 합니다. 통신에는 전자 메일, Microsoft 팀, 비즈니스용 Skype 및 타사 플랫폼 통신 (예: Facebook, Twitter 등)이 포함 됩니다.

- **4 단계 (선택 사항)**: [직원 공지 서식 파일 만들기](#step-4-create-employee-notice-templates-optional)

    사용자 지정 공지 서식 파일을 만들어 정책 일치에 대 한 업데이트 관리 옵션으로 직원에 게 전자 메일 알림을 보낼 수 있습니다.

- **5 단계 (선택 사항)**: [통신 준수 정책 테스트](#step-5-test-your-communication-compliance-policy-optional)

    통신 준수 정책을 테스트 하 여 원하는 대로 작동 하는지 확인 합니다. 규정 준수 전략이 표준을 충족 하는지 확인 하는 것이 중요 합니다.

## <a name="step-1-set-up-groups-for-communication-compliance-optional"></a>1 단계: 통신 준수를 위한 그룹 설정 (선택 사항)

 통신 준수 정책을 만들 때 통신을 검토 하 고 검토를 수행 하는 사람을 정의 합니다. 정책에서는 전자 메일 주소를 사용 하 여 개인 이나 사용자 그룹을 식별 합니다. 설정을 단순화 하기 위해 통신을 검토 한 사용자에 대 한 그룹을 만들고 해당 통신을 검토할 사용자에 대 한 그룹을 만들 수 있습니다. 그룹을 사용 하는 경우 몇 가지 필요할 수 있습니다. 예를 들어 서로 다른 두 사용자 그룹 간의 통신을 모니터링 하거나 감독 하지 않을 그룹을 지정 하려는 경우

다음 차트를 사용 하 여 조직의 통신 준수 정책에 맞게 그룹을 구성 하는 방법을 확인할 수 있습니다.

| **정책 구성원** | **지원 되는 그룹** | **지원 되지 않는 그룹** |
|:-----|:-----|:-----|
|감독 사용자 <br> 감독 되지 않은 사용자 | 메일 그룹 <br> Office 365 그룹 | 동적 메일 그룹 |
| 가 | 메일 사용 가능 보안 그룹  | 메일 그룹 <br> 동적 메일 그룹 |
  
감독 되는 사용자에 대 한 Office 365 그룹을 선택 하면 정책이 공유 Office 365 사서함의 콘텐츠 및 해당 그룹과 연결 된 Microsoft 팀 채널을 모니터링 합니다. 메일 그룹을 선택 하는 경우 정책은 개별 사용자 사서함을 모니터링 합니다.

그룹을 설정 하는 방법에 대 한 자세한 내용은 다음을 참조 하십시오.

- [메일 그룹 만들기 및 관리](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-distribution-groups/manage-distribution-groups)
- [메일 사용 가능 보안 그룹 관리](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-mail-enabled-security-groups)
- [Office 365 그룹 개요](https://docs.microsoft.com/office365/admin/create-groups/office-365-groups?view=o365-worldwide)

## <a name="step-2-make-communication-compliance-available-in-your-organization-required"></a>2 단계: 조직에서 통신 준수를 사용할 수 있도록 설정 (필수)

Microsoft 365 준수 센터에서 **통신 준수** 를 메뉴 옵션으로 사용할 수 있도록 하려면 **관리 검토 관리자** 역할이 할당 되어야 합니다. 또한 정책 일치가 있는 메시지를 조사 하 고 수정 하려면 **관리 검토 관리자**, **사례 관리** 및 **검토** 역할을 사용 하 여 검토자를 위한 그룹을 만들어야 합니다.

### <a name="create-a-new-role-group"></a>새 역할 그룹 만들기

1. Office 365 [https://compliance.microsoft.com](https://compliance.microsoft.com) 조직의 관리자 계정에 대 한 자격 증명을 사용 하 여 로그인 합니다.

2. Microsoft 365 준수 센터에서 **사용 권한**으로 이동 합니다. Office 365에서 역할을 보고 관리 하는 링크를 선택 합니다.

3. **만들기**를 선택합니다.

4. **이름** 필드에서 새 역할 그룹에 이름을 지정 합니다.  Select **Next**. 

5. **역할 선택을** 선택 하 고 **추가**를 선택 합니다. **관리 검토 관리자**, **사례 관리**및 **검토**에 대 한 확인란을 선택 하 고 **추가** 및 **완료**를 선택 합니다.  Select **Next**. 

6. **구성원 선택을** 선택 하 고 **추가**를 선택 합니다. 정책을 만들 모든 사용자 및 그룹에 대 한 확인란을 선택 하 고 정책 일치가 포함 된 메시지를 관리 한 다음 **추가** 및 **완료**를 선택 합니다.  Select **Next**. 

7. 마칠 **역할 그룹 만들기** 를 선택 합니다.

역할 그룹 및 사용 권한에 대 한 자세한 내용은 [준수 센터의 사용 권한을](../security/office-365-security/protect-against-threats.md)참조 하세요.

## <a name="step-3-create-a-communication-compliance-policy-required"></a>3 단계: 통신 준수 정책 만들기 (필수)
  
1. Microsoft 365 [https://compliance.microsoft.com](https://compliance.microsoft.com) 조직의 관리자 계정에 대 한 자격 증명을 사용 하 여 로그인 합니다.

2. Microsoft 365 준수 센터에서 **통신 준수**를 선택 합니다.
  
3. **정책** 탭을 선택 합니다.

4. **정책 만들기** 를 선택 하 여 템플릿에서 새 정책을 만들고 구성 하거나 사용자 지정 정책을 만들고 구성 합니다.

    정책을 만들기 위해 정책 템플릿을 선택 하는 경우 다음을 수행 합니다.

    - 정책 이름을 확인 하거나 업데이트 합니다. 정책을 만든 후에는 정책 이름을 변경할 수 없습니다.
    - 제외할 사용자 또는 그룹 선택을 비롯 하 여 감독할 사용자 또는 그룹을 선택 합니다.
    - 정책에 대 한 검토자를 선택 합니다. 검토자는 개별 사용자 또는 [메일 사용이 가능한 보안 그룹이](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-mail-enabled-security-groups#create-a-mail-enabled-security-group)될 수 있습니다. 모든 검토자에 게 Exchange Online에서 호스트 되는 사서함이 있어야 합니다.
    - 정책에 적용할 제한 된 조건 필드 (일반적으로 중요 한 정보 유형 또는 키워드 사전)를 선택 합니다.

    정책 마법사를 사용 하 여 사용자 지정 정책을 만드는 경우 다음을 수행 합니다.

    - 정책에 이름과 설명을 지정 합니다. 정책을 만든 후에는 정책 이름을 변경할 수 없습니다.
    - 조직의 모든 사용자, 특정 사용자 및 그룹, 제외 하려는 기타 사용자 및 그룹을 선택 하는 방식으로 감독할 사용자 또는 그룹을 선택 합니다. -
    - 정책에 대 한 검토자를 선택 합니다. 검토자는 개별 사용자 또는 [메일 사용이 가능한 보안 그룹이](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-mail-enabled-security-groups#create-a-mail-enabled-security-group)될 수 있습니다. 모든 검토자에 게 Exchange Online에서 호스트 되는 사서함이 있어야 합니다.
    - Exchange, Microsoft 팀 또는 비즈니스용 Skype를 포함 하 여 검색할 통신 채널을 선택 합니다. 또한 Microsoft 365에서 커넥터를 구성한 경우 타사 출처를 검색 하도록 선택 합니다.
    - 인바운드, 아웃 바운드 또는 내부 통신을 포함 하 여 모니터링할 통신 방향을 선택 합니다.
    - 통신 준수 정책 [조건을](communication-compliance-feature-reference.md#ConditionalSettings)정의 합니다. 메시지 주소, 키워드, 파일 형식 및 크기 일치 조건에서 선택할 수 있습니다.
    - 중요 한 정보 유형을 포함 하 고 싶은 경우 선택 합니다. 여기에서 기본 및 사용자 지정 중요 한 정보 유형을 선택할 수 있습니다. 기존 사용자 지정 중요 한 정보 유형 또는 사용자 지정 키워드 사전 선택 통신 준수 정책 마법사에서 필요한 경우 마법사를 실행 하기 전에 이러한 항목을 만들 수 있습니다. 필요한 경우 통신 준수 정책 마법사 내에서 새 중요 한 정보 유형을 만들 수도 있습니다.
    - 공격적인 언어 모델을 사용 하도록 설정 하려면 선택 합니다. 이는 전자 메일 메시지 본문에서 보내거나 받은 부적절 한 언어를 감지 합니다.
    - 검토할 통신의 비율을 정의 합니다.
    - 정책 선택을 검토 하 고 정책을 만듭니다.

5. 서식 파일을 사용 하는 경우 **정책 만들기** 또는 사용자 지정 정책 마법사를 사용할 때 **제출을** 선택 합니다.

6. 정책이 활성화 되 고 통신이 캡처될 시기에 대 한 지침과 함께 **정책이 만들어졌습니다** . 페이지가 표시 됩니다.

## <a name="step-4-create-employee-notice-templates-optional"></a>4 단계: 직원 공지 서식 파일 만들기 (선택 사항)

관련 직원에 게 미리 알림 메시지를 보내 정책 경고에 응답 하는 옵션을 설정 하려면 조직에 공지 서식 파일을 하나 이상 만들어야 합니다. 공지 수정 프로세스의 일부로 알림 서식 파일 필드를 편집 하 고 각 통신 준수 정책에 대해 사용자 지정 된 공지 서식 파일을 만드는 것이 좋습니다.

1. Microsoft 365 [https://compliance.microsoft.com](https://compliance.microsoft.com) 조직의 관리자 계정에 대 한 자격 증명을 사용 하 여 로그인 합니다.

2. Microsoft 365 준수 센터에서 **통신 준수**로 이동 합니다.

3. **공지 템플릿** 탭을 선택한 다음 **공지 템플릿 만들기**를 선택 합니다.

4. **공지 서식 파일 수정** 페이지에서 다음 필드를 작성 합니다.

    - 주의 서식 파일 이름 (필수)
    - 보내기 (필수)
    - 참조 및 숨은 참조 (선택 사항)
    - 제목 (필수)
    - 메시지 본문 (필수)

5. **저장** 을 선택 하 여 알림 서식 파일을 만들고 저장 합니다.

## <a name="step-5-test-your-communication-compliance-policy-optional"></a>5 단계: 통신 준수 정책 테스트 (선택 사항)

통신 준수 정책을 만든 후에는 테스트를 수행 하 여 정의한 조건이 정책에 의해 적절 하 게 적용 되는지 확인 하는 것이 좋습니다. 또한 통신 준수 정책에 중요 한 정보 유형이 포함 되어 있는 경우 [DLP (데이터 손실 방지) 정책을 테스트할](create-test-tune-dlp-policy.md) 수도 있습니다. 테스트할 통신을 캡처할 수 있도록 정책에 대 한 정품 인증을 제공 해야 합니다.

다음 단계에 따라 통신 준수 정책을 테스트 합니다.

1. 테스트할 정책에 정의 된 감독 된 사용자로 로그인 한 전자 메일 클라이언트 또는 Microsoft 팀을 엽니다.
2. 통신 준수 정책에 정의한 기준을 충족 하는 전자 메일 또는 Microsoft 팀 채팅을 보냅니다. 키워드, 첨부 파일 크기, 도메인 등이 될 수 있습니다. 정책에서 구성 된 조건부 설정이 너무 제한적일 또는 너무 lenient 인지 확인 합니다.

    > [!NOTE]
    > 모든 원본 채널의 통신은 정책에서 완전히 처리 되는 데 최대 24 시간이 걸릴 수 있습니다.

3. 통신 준수 정책에 지정 된 검토자에 게 Microsoft 365에 로그인 합니다. 정책에 대 한 경고를 보려면 **통신 준수** > **알림과** 이동 합니다.

4. 업데이트 관리 컨트롤을 사용 하 여 경고를 수정 하 고 경고가 제대로 확인 되는지 확인 합니다.

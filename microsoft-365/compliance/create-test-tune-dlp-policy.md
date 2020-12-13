---
title: DLP 정책 만들기, 테스트 및 조정
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
audience: Admin
ms.topic: article
f1_keywords:
- ms.o365.cc.NewPolicyFromTemplate
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
search.appverid:
- MET150
ms.custom:
- seo-marvel-mar2020
ms.assetid: 59414438-99f5-488b-975c-5023f2254369
description: 이 문서에서는 조직의 요구에 따라 DLP 정책을 만들고 테스트하고 조정하는 방법을 배우게 됩니다.
ms.openlocfilehash: 9b43899969ab0fdc5d67b051db36c0b245f7811e
ms.sourcegitcommit: 47de4402174c263ae8d70c910ca068a7581d04ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/12/2020
ms.locfileid: "49663195"
---
# <a name="create-test-and-tune-a-dlp-policy"></a>DLP 정책 만들기, 테스트 및 조정

DLP(데이터 손실 방지)를 사용하면 중요한 정보가 실수로 공유되거나 의도치 않은 공유를 방지할 수 있습니다.

DLP는 전자 메일 메시지와 파일에서 신용 카드 번호와 같은 중요한 정보를 검사합니다. DLP를 사용하면 중요한 정보를 검색하고 다음 작업을 취할 수 있습니다.

- 감사 목적으로 이벤트 기록
- 전자 메일을 보내거나 파일을 공유하는 최종 사용자에게 경고 표시
- 전자 메일 또는 파일 공유가 차단됩니다.

## <a name="permissions"></a>권한

DLP 정책을 만드는 규정 준수 팀 구성원에게는 준수 센터에 대한 사용 권한이 필요합니다. 기본적으로 테넌트 관리자는 규정 준수 관리자 및 기타 사용자 액세스 권한을 부여할 수 있습니다. 다음 단계를 따릅니다.
  
1. Microsoft 365에서 그룹을 생성하고 규정 준수 책임자를 추가하십시오.
    
2. 보안 &amp; 준수 센터의 **사용 권한** 페이지에서 역할 그룹을 생성하십시오. 

3. 역할 그룹을 만드는 동안  역할 선택 섹션을 사용하여 역할 그룹에 DLP 준수 관리 역할을 **추가합니다.**
    
4. **구성원 선택** 섹션을 사용하여 이전에 만든 Microsoft 365 그룹을 역할 그룹에 추가합니다.

보기 전용 **DLP 준수 관리** 역할을 사용하여 DLP 정책 및 DLP 보고서에 대한 보기 전용 권한이 있는 역할 그룹을 만들 수 있습니다.

더 자세한 내용은 [Office 365 준수 센터 액세스 권한 부여하기](../security/office-365-security/grant-access-to-the-security-and-compliance-center.md)를 참고하십시오.
  
이러한 사용 권한은 정책을 적용하지 않는 DLP 정책을 만들고 적용하는 데 필요합니다.

## <a name="how-sensitive-information-is-detected-by-dlp"></a>DLP에서 중요한 정보를 검색하는 방법

DLP는 특정 키워드와 일치하는 패턴에 대한 근접성 같은 다른 지표와 함께 정규식(RegEx) 패턴 일치를 통해 중요한 정보를 검색합니다. 예를 들어 VISA 신용 카드 번호는 16자리입니다. 그러나 1111-1111-1111-1111, 1111 1111 1111 1111 1111 또는 1111111111111111111111111111111111111111111111111111111111111111과 같은 다양한 방식으로 이러한 숫자를 기록할 수 있습니다.

16자리 문자열이 반드시 신용 카드 번호일 필요는 없습니다. 이 문자열은 지원 센터 시스템의 티켓 번호 또는 하드웨어 일련 번호일 수 있습니다. 신용 카드 번호와 무해한 16자리 문자열의 차이를 확인하기 위해 숫자가 다양한 신용 카드 브랜드의 알려진 패턴과 일치하는지 확인하는 계산(체크 um)이 수행됩니다.

DLP가 신용 카드 만료 날짜일 수 있는 "VISA" 또는 "AMEX"과 같은 키워드를 찾는 경우 DLP는 해당 데이터를 사용하여 문자열이 신용 카드 번호인지 여부를 결정하는 데 도움이 됩니다.

즉, DLP는 전자 메일에서 이러한 두 텍스트 문자열 간의 차이를 인식할 수 있을 만큼 스마트합니다.

- "새 노트북을 주문할 수 있습니다. 내 VISA 번호 1111-1111-1111-1111, 만료 11/22를 사용하여 예상 배달 날짜를 보낼 수 있습니다."
- "내 노트북 일련 번호는 2222-2222-2222-2222이고 2010년 11월에 구입했습니다. 내 여행비가 아직 승인되지 않았나요?"

각 [정보 유형이](sensitive-information-type-entity-definitions.md) 검색되는 방법을 설명하는 중요한 정보 유형 엔터티 정의를 참조하세요.

## <a name="where-to-start-with-data-loss-prevention"></a>데이터 손실 방지로 시작하는 위치

데이터 누출 위험이 완전히 명확하지 않은 경우 DLP 구현을 정확히 시작해야 하는 위치를 해결하기가 어렵습니다. 다행히 DLP 정책을 "테스트 모드"로 실행하여 켜기 전에 효율성과 정확성을 측정할 수 있습니다.

Exchange Online에 대한 DLP 정책은 Exchange 관리 센터를 통해 관리할 수 있습니다. 그러나 보안 및 준수 센터를 통해 모든 & DLP 정책을 구성할 수 있으므로 이 문서의 데모에 사용할 수 있습니다. 보안 & 준수 센터에서 데이터 손실 방지 정책 아래에 DLP **정책을 찾을 수**  >  **있습니다.** 시작할 **정책** 만들기를 선택 합니다.

Microsoft 365는 정책을 만드는 데 사용할 수 있는 [다양한 DLP](what-the-dlp-policy-templates-include.md) 정책 템플릿을 제공합니다. 오스트레일리아 비즈니스라고 합니다. 오스트레일리아에서 템플릿을 필터링하고 재무, 의료 및 건강 및 개인 정보 보호를 선택할 수 있습니다.

![국가 또는 지역 선택 옵션](../media/DLP-create-test-tune-choose-country.png)

이 데모에서는 오스트레일리아 세금 파일 번호(TFN) 및 운전 면허 번호의 정보 유형을 포함하는 오스트레일리아 PII(개인 식별 정보) 데이터를 선택하게 됩니다.

![정책 템플릿 선택 옵션](../media/DLP-create-test-tune-choose-policy-template.png)

새 DLP 정책에 이름을 지정합니다. 기본 이름은 DLP 정책 템플릿과 일치하지만 동일한 템플릿에서 여러 정책을 만들 수 있기 때문에 보다 설명적인 이름을 선택해야 합니다.

![정책 이름을 지정하는 옵션](../media/DLP-create-test-tune-name-policy.png)

정책을 적용할 위치를 선택하세요. DLP 정책은 Exchange Online, SharePoint Online 및 비즈니스용 OneDrive에 적용할 수 있습니다. 모든 위치에 적용하도록 이 정책을 구성한 그대로 떠날 것입니다.

![모든 위치 선택 옵션](../media/DLP-create-test-tune-choose-locations.png)

첫 번째 정책 **설정 단계에서** 지금의 기본값을 적용합니다. DLP 정책을 사용자 지정할 수 있지만 기본값은 시작할 수 있는 좋은 위치입니다.

![보호할 콘텐츠 형식을 사용자 지정하는 옵션](../media/DLP-create-test-tune-default-customization-settings.png)

다음을 클릭하면 추가 사용자 지정 옵션이 있는  추가 정책 설정 페이지가 표시됩니다. 방금 테스트하는 정책의 경우 조정을 시작할 수 있는 위치는 다음과 같습니다.

- 이제 정책 팁을 해제했습니다. 이 단계는 단지 테스트만 하고 사용자에게 아무것도 표시하지 않고 싶지 않은 경우 취할 수 있는 적절한 단계입니다. 정책 팁은 DLP 정책을 위반할 것 같은 경고를 사용자에게 표시합니다. 예를 들어 Outlook 사용자는 첨부한 파일에 신용 카드 번호가 포함되어 있으며 전자 메일이 거부될 것 같은 경고가 표시됩니다. 정책 팁의 목표는 비규준 행동이 발생하기 전에 중지하는 것입니다.
- 또한 인스턴스 수를 10개에서 1로 줄이면 이 정책은 데이터의 대량 공유가 아니라 오스트레일리아 PII 데이터 공유를 검색합니다.
- 또한 문제 보고서 전자 메일에 다른 받는 사람을 추가합니다.

![추가 정책 설정](../media/DLP-create-test-tune-more-policy-settings.png)

마지막으로 이 정책을 처음에 테스트 모드에서 실행하도록 구성했습니다. 테스트 모드에서 정책 팁을 사용하지 않도록 설정하는 옵션도 있습니다. 이렇게 하면 정책에서 정책 팁을 사용할 수 있는 유연성을 제공하지만 테스트 중에 정책 팁을 표시하거나 표시하지 않습니다.

![정책을 먼저 테스트하는 옵션](../media/DLP-create-test-tune-test-mode.png)

마지막 검토 화면에서 **만들기를** 클릭하여 정책 만들기를 완료합니다.

## <a name="test-a-dlp-policy"></a>DLP 정책 테스트

새 DLP 정책은 약 1시간 이내에 적용됩니다. 일반 사용자 활동에 의해 트리거될 때까지 기다리거나 직접 트리거할 수 있습니다. 이전에서는 DLP [](sensitive-information-type-entity-definitions.md)일치를 트리거하는 방법에 대한 정보를 제공하는 중요한 정보 유형 엔터티 정의에 연결했습니다.

예를 들어 이 문서에 대해 만든 DLP 정책은 오스트레일리아 세금 파일 번호(TFN)를 검색합니다. 설명서에 따라 일치는 다음 기준에 따라 결정됩니다.

![호주 세금 파일 번호에 대한 설명서](../media/DLP-create-test-tune-Australia-Tax-File-Number-doc.png)
 
TFN 검색을 다소 흐리게 보여 주기 위해 "세금 파일 번호"라는 단어와 근접한 9자리 문자열이 있는 전자 메일은 문제 없이 통과됩니다. DLP 정책이 트리거되지 않는 이유는 9자리 문자열이 무해한 숫자 문자열이 아니라 유효한 TFN을 나타내는 체크 아웃을 전달해야 하기 때문에입니다.

![체크 um을 통과하지 않는 호주 세금 파일 번호](../media/DLP-create-test-tune-email-test1.png)

이와 비교하여 "Tax file number"라는 단어와 체크 체크 um을 전달하는 유효한 TFN이 있는 전자 메일은 정책을 트리거합니다. 여기서 사용하는 레코드의 경우 사용 중이던 TFN은 정품 TFN이 아닌 유효한 TFN을 생성하는 웹 사이트에서 생성되었습니다. 이러한 사이트는 DLP 정책을 테스트할 때 가장 일반적인 실수 중 하나는 유효하지 않은 가짜 번호를 사용하므로 매우 유용합니다.(따라서 정책을 트리거하지는 않습니다).

![수표를 전달하는 호주 세금 파일 번호](../media/DLP-create-test-tune-email-test2.png)

문제 보고서 전자 메일에는 검색된 중요한 정보의 유형, 검색된 인스턴스 수 및 검색의 신뢰 수준이 포함됩니다.

![감지된 세금 파일 번호를 표시하는 문제 보고서](../media/DLP-create-test-tune-email-incident-report.png)

테스트 모드에서 DLP 정책을 그대로 두고 문제 보고서 전자 메일을 분석하는 경우 DLP 정책의 정확성과 DLP 정책이 적용될 때의 효율성에 대해 느끼기 시작할 수 있습니다. 문제 보고서 외에도 [DLP](view-the-dlp-reports.md) 보고서를 사용하여 테넌트 전체의 정책 일치에 대한 집계된 보기를 볼 수 있습니다.

## <a name="tune-a-dlp-policy"></a>DLP 정책 조정

정책 적중을 분석할 때 정책의 행동 방법을 조정해야 할 수 있습니다. 간단한 예로, 전자 메일의 한 TFN이 문제가 아니라고 판단할 수 있지만(데모를 위해 계속 진행할 수 있지만, 둘 이상의 인스턴스가 문제인 경우) 확인할 수 있습니다. 여러 인스턴스는 직원이 HR 데이터베이스에서 외부 계정 서비스로 CSV 내보내기 전자 메일을 보내는 등 위험한 시나리오일 수 있습니다. 검색하고 차단하는 것이 좋습니다.

보안 & 준수 센터에서 기존 정책을 편집하여 행동을 조정할 수 있습니다.

![정책 편집 옵션](../media/DLP-create-test-tune-edit-policy.png)
 
정책이 특정 워크로드 또는 특정 사이트 및 계정에만 적용될 수 있도록 위치 설정을 조정할 수 있습니다.

![특정 위치를 선택하는 옵션](../media/DLP-create-test-tune-edit-locations.png)

또한 정책 설정을 조정하고 요구에 맞게 규칙을 편집할 수도 있습니다.

![규칙 편집 옵션](../media/DLP-create-test-tune-edit-rule.png)

DLP 정책 내에서 규칙을 편집할 때 다음을 변경할 수 있습니다.

- 규칙을 트리거하는 중요한 데이터의 인스턴스 유형 및 수를 포함한 조건입니다.
- 수행되는 작업(예: 콘텐츠에 대한 액세스 제한)
- 전자 메일 클라이언트 또는 웹 브라우저에서 사용자에게 표시되는 정책 팁인 사용자 알림입니다.
- 사용자가 전자 메일 또는 파일 공유를 계속할지 여부를 결정하는 사용자 오버라이드입니다.
- 관리자에게 알리기 위해 인시던트 보고서

![규칙의 일부를 편집하는 옵션](../media/DLP-create-test-tune-editing-options.png)

이 데모의 경우 정책에 사용자 알림을 추가했습니다(적절한 사용자 인식 교육 없이 이 작업을 주의하세요), 사용자가 업무 정당성으로 정책을 다시 정당화하거나 가음성으로 표시하여 정책을 다시 사용할 수 있도록 허용했습니다. 조직의 정책에 대한 추가 정보를 포함하거나 사용자에게 질문이 있는 경우 지원에 문의하라는 메시지를 표시하려는 경우 전자 메일 및 정책 팁 텍스트를 사용자 지정할 수도 있습니다.

![사용자 알림 및 오버라이드에 대한 옵션](../media/DLP-create-test-tune-user-notifications.png)

이 정책에는 볼륨과 볼륨이 낮은 볼륨을 처리하기 위한 두 가지 규칙이 포함되어 있으므로 원하는 작업으로 두 규칙을 모두 편집해야 합니다. 특성에 따라 사례를 다르게 처리하기 위한 기회입니다. 예를 들어 볼륨이 낮은 위반에 대해 다시금을 허용하지만 볼륨 위반이 많은 경우 다시 시정을 허용하지 않을 수 있습니다.

![볼륨이 큰 규칙 1개 및 볼륨이 적은 규칙 1개](../media/DLP-create-test-tune-two-rules.png)

또한 정책을 위반하는 콘텐츠에 대한 액세스를 실제로 차단하거나 제한하려면 규칙에 대한 작업을 구성해야 합니다.

![콘텐츠에 대한 액세스를 제한하는 옵션](../media/DLP-create-test-tune-restrict-access-action.png)

이러한 변경 내용을 정책 설정에 저장한 후 정책의 기본 설정 페이지로 돌아가서 정책이 테스트 모드에 있는 동안 사용자에게 정책 팁을 표시하는 옵션도 사용하도록 설정해야 합니다. 이는 생산성에 영향을 미치는 너무 많은 오판정을 위험을 감수하지 않고 최종 사용자에게 DLP 정책을 도입하고 사용자 인식 교육을 하는 효과적인 방법입니다.

![테스트 모드에서 정책 팁을 표시하는 옵션](../media/DLP-create-test-tune-show-policy-tips.png)

서버 쪽(또는 원하는 경우 클라우드 쪽)에서는 다양한 처리 간격으로 인해 변경이 즉시 적용되지 않을 수 있습니다. 사용자에게 새 정책 팁을 표시하는 DLP 정책을 변경하는 경우 사용자는 Outlook 클라이언트에서 변경 내용이 즉시 적용되지 않을 수 있습니다. 이 변경 내용은 24시간마다 확인됩니다. 테스트 속도를 향상하려면 이 레지스트리 수정을 사용하여 [PolicyNudges](https://support.microsoft.com/en-au/help/2823261/changes-to-a-data-loss-prevention-policy-don-t-take-effect-in-outlook?__hstc=18650278.46377037dc0a82baa8a30f0ef07a7b2f.1538687978676.1538693509953.1540315763430.3&__hssc=18650278.1.1540315763430&__hsfp=3446956451)키에서 마지막 다운로드 타임스탬프를 지우면 됩니다. Outlook은 다음에 다시 시작하고 전자 메일 메시지 작성을 시작할 때 최신 정책 정보를 다운로드합니다.

정책 팁을 사용하도록 설정한 경우 사용자는 Outlook에서 팁을 보기 시작하고 발생할 때 가짓 긍정을 보고할 수 있습니다.

![가짓 긍정 보고 옵션이 있는 정책 팁](../media/DLP-create-test-tune-policy-tip-in-outlook.png)

## <a name="investigate-false-positives"></a>가짓 긍정 조사

DLP 정책 템플릿이 바로 완벽한 것은 아니며, 사용자 환경에서 일부 가짓 긍정이 발생하게 될 가능성이 높기 때문에 정책을 적절하게 테스트하고 조정하는 데 시간을 들이고 DLP 배포를 쉽게 하는 것이 매우 중요합니다.

다음은 가짓 긍정의 예입니다. 이 전자 메일은 무해합니다. 사용자가 전자 메일 서명을 포함하여 자신의 휴대폰 번호를 다른 사람에게 제공합니다.

![가짓 긍정 정보를 표시하는 전자 메일](../media/DLP-create-test-tune-false-positive-email.png)
 
그러나 사용자에게 전자 메일에 중요한 정보, 특히 오스트레일리아 운전 면허 번호가 포함되어야 하다는 경고가 정책 팁에 표시됩니다.

![정책 팁에서 가짓 긍정 보고 옵션](../media/DLP-create-test-tune-policy-tip-closeup.png)

사용자는 가짓 긍정을 보고할 수 있으며, 관리자가 발생한 이유를 살펴 볼 수 있습니다. 문제 보고서 전자 메일에서 전자 메일은 가긍성으로 플래그가 지정됩니다.

![가긍성 표시 문제 보고서](../media/DLP-create-test-tune-false-positive-incident-report.png)

이 드라이버의 라이선스 사례는 한 가지 좋은 예입니다. 이 가양성의 원인은 "호주 운전 면허증" 유형이 9자리 문자열(10자리 문자열의 일부인 문자열도 포함)에 의해 트리거되는 것이고 키워드 "australia nsw"와의 근접성은 300자 이내이기 때문에(대/미분). 따라서 사용자가 수도에 있기 때문에 전화 번호와 전자 메일 서명에 의해 트리거됩니다.


한 가지 옵션은 정책에서 오스트레일리아 운전 면허 정보 유형을 제거하는 것입니다. DLP 정책 템플릿의 일부이기 때문에 이 템플릿에 있지만 강제로 사용할 수 없습니다. If you're only interested in Tax File Numbers and not driver's licenses, you can just remove it. 예를 들어 정책의 볼륨이 적은 규칙에서 제거하지만 여러 드라이버 라이선스 목록이 계속 검색될 수 있도록 볼륨이 높은 규칙에 그대로 두면 됩니다.

![규칙에서 중요한 정보 유형을 삭제하는 옵션](../media/DLP-create-test-tune-delete-low-volume-rule.png)
 
또 다른 옵션은 인스턴스 수를 늘리기만 하여 적은 수의 드라이버 라이선스가 여러 인스턴스가 있을 때만 검색되는 것입니다.

![인스턴스 수를 편집하는 옵션](../media/DLP-create-test-tune-edit-instance-count.png)

인스턴스 수를 변경하는 것 외에도 일치 정확도(또는 신뢰도)를 조정할 수 있습니다. 중요한 정보 유형에 여러 패턴이 있는 경우 규칙이 특정 패턴과만 일치하도록 규칙에서 일치 정확도를 조정할 수 있습니다. 예를 들어 가짓 긍정을 줄이기 위해 신뢰 수준이 가장 높은 패턴만 일치하게 규칙의 일치 정확도를 설정할 수 있습니다. 신뢰도 계산 방법을 이해하는 것은 약간 까다롭지만(이 게시물의 범위를 벗어남), 신뢰 수준을 사용하여 규칙을 조정하는 방법에 대한 좋은 [설명은 다음과 같은 것입니다.](data-loss-prevention-policies.md#match-accuracy)

마지막으로, 좀 더 고급화하려는 경우 중요한 정보 유형을 사용자 지정할 수 있습니다. 예를 들어 호주 운전 면허 번호에 [](sensitive-information-type-entity-definitions.md#australia-drivers-license-number)대한 키워드 목록에서 "Australia NSW"를 제거하여 위의 가긍성 트리거를 제거할 수 있습니다. XML 및 PowerShell을 사용하여 이 작업을 하는 방법에 대한 자세한 내용은 기본 제공 중요한 정보 유형 사용자 [지정을 참조하세요.](customize-a-built-in-sensitive-information-type.md)

## <a name="turn-on-a-dlp-policy"></a>DLP 정책 켜기

DLP 정책이 중요한 정보 유형을 정확하고 효과적으로 감지하고 최종 사용자가 현재 적용되고 있는 정책을 사용할 준비가 된 것이 만족스러우면 정책을 사용하도록 설정할 수 있습니다.

![정책을 켜는 옵션](../media/DLP-create-test-tune-turn-on-policy.png)
 
정책이 언제 적용될지 기다리는 경우 Security [& Compliance Center PowerShell에](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell) 연결하고 [Get-DlpCompliancePolicy cmdlet을](https://docs.microsoft.com/powershell/module/exchange/get-dlpcompliancepolicy) 실행하여 DistributionStatus를 볼 수 있습니다.

![PowerShell에서 cmdlet 실행](../media/DLP-create-test-tune-PowerShell.png)

DLP 정책을 켜고 나면 자신의 최종 테스트를 몇 가지 실행하여 예상되는 정책 작업이 발생하고 있는지를 확인해야 합니다. 신용 카드 데이터와 같은 것을 테스트하려는 경우 체크 아웃을 통과하고 정책을 트리거하는 샘플 신용 카드 또는 기타 개인 정보를 생성하는 방법에 대한 정보가 있는 웹 사이트가 온라인에서 있습니다.

사용자 다시 적용을 허용하는 정책은 정책 팁의 일부로 사용자에게 해당 옵션을 제공합니다.

![사용자 오버라이드를 허용하는 정책 팁](../media/DLP-create-test-tune-override-option.png)

콘텐츠를 제한하는 정책은 정책 팁의 일부로 사용자에게 경고를 표시하고 전자 메일을 보내지 못하도록 합니다.

![콘텐츠가 제한되는 정책 팁](../media/DLP-create-test-tune-restrict-warning.png)

## <a name="summary"></a>요약

데이터 손실 방지 정책은 모든 유형의 조직에 유용합니다. 일부 DLP 정책 테스트는 정책 팁, 최종 사용자 다시 설정 및 문제 보고서와 같은 컨트롤로 인해 위험 수준이 낮은 연습입니다. 일부 DLP 정책을 조용히 테스트하여 조직에서 이미 발생한 위반 유형을 확인한 다음 가음성 비율이 낮은 정책을 만들어 사용자에게 허용 및 허용되지 않는 내용을 교육한 다음 DLP 정책을 조직에 롤아웃할 수 있습니다.

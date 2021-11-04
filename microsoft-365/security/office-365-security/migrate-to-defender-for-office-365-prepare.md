---
title: '1단계: 준비를 Office 365 Microsoft Defender로 마이그레이션'
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: Admin
ms.date: ''
ms.topic: conceptual
ms.localizationpriority: medium
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
ms.custom: migrationguides
description: 타사 보호 서비스 또는 장치에서 Microsoft Defender로 마이그레이션하기 위한 사전 Office 365 단계입니다.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: c079fbe808b59ef95663ae8a5af6b3913db49eb9
ms.sourcegitcommit: dc26169e485c3a31e1af9a5f495be9db75c49760
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60779127"
---
# <a name="migrate-to-microsoft-defender-for-office-365---phase-1-prepare"></a>마이그레이션을 위해 Microsoft Defender로 Office 365 - 1단계: 준비

**적용 대상**
- [Office 365용 Microsoft Defender 플랜 1 및 플랜 2](defender-for-office-365.md)

<br>

|![1단계: 준비.](../../media/phase-diagrams/prepare.png) <br> 1 단계: 준비|[![2 단계: 설정](../../media/phase-diagrams/setup.png)](migrate-to-defender-for-office-365-setup.md) <br> [2 단계: 설정](migrate-to-defender-for-office-365-setup.md)|[![3 단계: 온보딩](../../media/phase-diagrams/onboard.png)](migrate-to-defender-for-office-365-onboard.md) <br> [3 단계: 온보딩](migrate-to-defender-for-office-365-onboard.md)|
|---|---|---|
|*여기 있습니다!*|||

**1단계:** Microsoft **[Defender로의](migrate-to-defender-for-office-365.md#the-migration-process)** 마이그레이션 준비를 Office 365! 이 마이그레이션 단계에는 다음 단계가 포함됩니다. 변경하기 전에 먼저 기존 보호 서비스의 설정을 인벤토리에 추가해야 합니다. 그렇지 않으면 순서에 따라 나머지 단계를 수행하면 됩니다.

1. [기존 보호 서비스의 설정 인벤토리](#inventory-the-settings-at-your-existing-protection-service)
2. [다음에서 기존 보호 구성을 Microsoft 365](#check-your-existing-protection-configuration-in-microsoft-365)
3. [메일 라우팅 구성 확인](#check-your-mail-routing-configuration)
4. [메시지를 수정하는 기능을 Microsoft 365](#move-features-that-modify-messages-into-microsoft-365)
5. [스팸 및 대량 사용자 환경 정의](#define-spam-and-bulk-user-experiences)
6. [우선 순위 계정 식별 및 지정](#identify-and-designate-priority-accounts)

## <a name="inventory-the-settings-at-your-existing-protection-service"></a>기존 보호 서비스의 설정 인벤토리

기존 보호 서비스의 설정, 규칙, 예외 등의 전체 인벤토리는 구독을 취소한 후 정보에 액세스할 수 없는 경우가 좋기 때문에 좋은 생각입니다.

**그러나 Defender에서 기존 사용자 지정을 자동으로 또는 임의로 모두 다시 만들지 않는 것이 매우 Office 365.** 더 이상 필요하지, 관련성 또는 기능이 없는 설정을 도입하는 것이 좋습니다. 더 나쁜 경우 이전 사용자 지정 중 일부가 실제로 사용자 지정을 위해 Defender에서 보안 Office 365.

에디터용 Defender의 기본 기능 및 동작을 테스트하고 관찰하면 Office 365 결국 필요한 다시 설정이 결정됩니다. 기존 보호 서비스의 설정을 다음 범주로 분류하는 것이 유용할 수 있습니다.

- **연결 또는** 콘텐츠 필터링: 이러한 사용자 지정 내용의 대부분이 Defender에서 필요하지 Office 365.
- **비즈니스 라우팅:** 다시 만들야 하는 대부분의 사용자 지정은 이 범주에 속할 수 있습니다. 예를 들어 이러한 설정을 스푸핑 인텔리전스에 Microsoft 365 메일 흐름 규칙Exchange 커넥터 및 예외라고도 합니다.

이전 설정을 Microsoft 365 사용자 구성원이 계속 증가하는 파일럿 단계와 조직의 비즈니스 요구 사항과 보안 고려 사항의 균형을 조정하는 관찰 기반 조정이 수반되는 워터플로 접근 방식이 권장됩니다.

## <a name="check-your-existing-protection-configuration-in-microsoft-365"></a>다음에서 기존 보호 구성을 Microsoft 365

앞서 말했듯이 타사 보호 서비스를 사용하는 경우에도 Microsoft 365 메일에 대한 모든 보호 기능을 완전히 해제할 수 없습니다. 따라서 조직에서 일부 전자 메일 보호 Microsoft 365 구성하는 것은 비정상적이지 않습니다. 예제:

- 과거에는 타사 보호 서비스를 사용하지 Microsoft 365. 현재 무시 중인 일부 보호 기능을 Microsoft 365 구성할 수 있습니다. 그러나 이러한 설정은 "전화 걸기"를 통해 사용자 환경의 보호 기능을 사용하도록 설정할 때 Microsoft 365.
- 기존 보호 서비스를 통해 허용된 가음성(Microsoft 365 좋은 메일) 또는 거짓 부정(잘못된 메일 허용)에 대한 보호를 강화할 수 있습니다.

기존 보호 기능의 Microsoft 365 더 이상 필요하지 않은 설정을 제거하거나 간소화하는 것이 좋습니다. 몇 년 전에 요구된 규칙 또는 정책 설정은 조직을 위험에 노출하고 의도하지 않은 보호 간격을 만들 수 있습니다.

## <a name="check-your-mail-routing-configuration"></a>메일 라우팅 구성 확인

- 모든 종류의 복잡한 라우팅(예: 중앙 집중식 [](/exchange/transport-options)메일 전송)을 사용하는 경우 라우팅을 단순화하고 철저하게 문서화하는 것을 고려해야 합니다. 외부 홉은 특히 Microsoft 365 받은 후에 구성 및 문제 해결을 복잡하게 할 수 있습니다.

- 아웃바운드 및 릴레이 메일 흐름은 이 문서에서 다루지 않습니다. 그러나 다음 단계 중 하나 이상을 수행해야 할 수 있습니다.
  - 전자 메일을 보내는 데 사용하는 모든 도메인에 적절한 SPF 레코드가 있는지 확인 자세한 내용은 [스푸핑을 방지할 수 있도록 SPF 설정](set-up-spf-in-office-365-to-help-prevent-spoofing.md)을 참조하세요.
  - DKIM 로그인을 설정하는 것이 Microsoft 365. 자세한 내용은 [DKIM을 사용하여](use-dkim-to-validate-outbound-email.md)아웃바운드 전자 메일 유효성 검사를 참조하세요.
  - 전자 메일에서 직접 메일을 라우팅하지 Microsoft 365 아웃바운드 커넥터를 제거하거나 변경하여 라우팅을 변경해야 합니다.

- 이 Microsoft 365 사용하여 전자 메일 서버에서 전자 메일을 릴레이하는 것 자체는 복잡한 프로젝트일 수 있습니다. 간단한 예로는 대부분의 메시지를 내부 받는 사람에게 보내고 대량 메일에 사용되지 않는 소수의 앱 또는 장치를 들 수 있습니다. 자세한 [내용은 이](/exchange/mail-flow-best-practices/how-to-set-up-a-multifunction-device-or-application-to-send-email-using-microsoft-365-or-office-365) 가이드를 참조하세요. 보다 광범위한 환경은 더욱 신심해야 합니다. 받는 사람이 스팸으로 볼 수 있는 마케팅 전자 메일 및 메시지는 허용되지 않습니다.

- Defender for Office 365 DMARC 보고서를 집계하는 기능이 없습니다. [MISA(Microsoft Intelligent Security Association)](https://www.microsoft.com/misapartnercatalog) 카탈로그를 방문하여 타사에 대한 DMARC 보고를 제공하는 타사 공급업체를 Microsoft 365.

## <a name="move-features-that-modify-messages-into-microsoft-365"></a>메시지를 수정하는 기능을 Microsoft 365

메시지를 수정하는 사용자 지정 또는 기능을 모든 사용자 지정 또는 기능으로 전송해야 Microsoft 365. 예를 들어 기존 보호 서비스는 외부 보낸 사람이 보낸 메시지의 제목 또는 메시지 본문에 **External** 태그를 추가합니다.

기존 보호 서비스에서 이 기능을 사용하지 않도록 설정하지 않은 경우 다음과 같은 부정적인 결과를 기대할 수 Microsoft 365.

- DKIM이 중단될 수 있습니다.
- [스푸핑 인텔리전스가](anti-spoofing-protection.md) 제대로 작동하지 않습니다.
- 가음성(양호한 것으로 표시된 좋은 메일)이 높게 표시될 수 있습니다.

이 기능을 Microsoft 365 옵션을 사용할 수 있습니다.

- 외부 [Outlook 전화](https://techcommunity.microsoft.com/t5/exchange-team-blog/native-external-sender-callouts-on-email-in-outlook/ba-p/2250098)걸기 기능 및 첫 번째 연락처 보안 [팁을 제공합니다.](set-up-anti-phishing-policies.md#first-contact-safety-tip)
- 메일 흐름 규칙(전송 규칙)입니다. 자세한 내용은 의 조직 전체 메시지 고지, 서명, 머리글 또는 [머리글을 Exchange Online.](/exchange/security-and-compliance/mail-flow-rules/disclaimers-signatures-footers-or-headers)

## <a name="account-for-any-active-phishing-simulations"></a>활성 피싱 시뮬레이션 계정

활성 타사 피싱 시뮬레이션이 있는 경우 메시지, 링크 및 첨부 파일이 해당 피싱에 대해 Defender에 의해 피싱으로 식별되지 않도록 Office 365. 자세한 내용은 고급 배달 정책에서 타사 피싱 시뮬레이션 [구성을 참조하세요.](configure-advanced-delivery.md#use-the-microsoft-365-defender-portal-to-configure-third-party-phishing-simulations-in-the-advanced-delivery-policy)

## <a name="define-spam-and-bulk-user-experiences"></a>스팸 및 대량 사용자 환경 정의

- **정크** 메일 폴더로의 정크 메일 배달 비교: 악의적이며 위험할 수 있는 메시지에 대한 자연스럽고 권장되는 대응은 메시지를 차단하는 것입니다. 그러나 사용자가 스팸, 대량 메일(회색 메일)과 같이 덜 유해한 메시지를 처리하게 하려는 *방법* 이러한 유형의 메시지를 사용자 정크 메일 폴더로 배달해야 하나요?

  표준 보안 설정을 사용하여 일반적으로 이러한 덜 위험한 유형의 메시지를 정크 메일 폴더로 전달합니다. 이 동작은 사용자가 정크 메일 폴더에서 누락된 메시지를 확인할 수 있으며 이러한 메시지를 직접 전달할 수 있는 많은 소비자 전자 메일 제공과 유사합니다. 또는 사용자가 의도적으로 뉴스레터 또는 마케팅 메일에 등록한 경우 자신의 사서함에 대한 보낸 사람 구독을 취소하거나 차단하도록 선택할 수 있습니다.

  그러나 많은 엔터프라이즈 사용자는 정크 메일 폴더에 있는 메일을 거의(있는 경우) 사용하게 됩니다. 대신 이러한 엔터프라이즈 사용자는 누락된 메시지에 대한 검사를 하는 데 사용됩니다. Quarantine에서는 메시지를 보고 해제하는 데 필요한 사용 권한, 알림 빈도 및 알림 메시지의 문제를 소개합니다.

  - DKIM(Domain Keys Identified Mail)이 중단됩니다.
  - [스푸핑 인텔리전스가](anti-spoofing-protection.md) 제대로 작동하지 않습니다.
  - 가음성(양호한 것으로 표시된 좋은 메일)이 높게 표시될 수 있습니다.

  궁극적으로, 전자 메일이 정크 메일 폴더로 배달되지 않도록 하려는 경우를 위해 정크 메일 폴더로의 배달을 차단할지 결정해야 합니다. 하지만 확실한 점은, Office 365용 Defender의 환경이 사용자가 사용한 환경과 다른 경우 사용자에게 알리고 기본 교육을 제공해야 합니다. 파일럿에서 학습을 통합하고 사용자가 전자 메일 배달을 위한 새로운 동작을 준비할 수 있도록 합니다.

- **대량 메일 및 원치** 않는 대량 메일 필요: 많은 보호 시스템을 통해 사용자가 대량 전자 메일을 직접 허용하거나 차단할 수 있습니다. 이러한 설정은 이러한 설정으로 쉽게 마이그레이션되지 Microsoft 365 때문에 VIP 및 해당 직원과 함께 작업하여 기존 구성을 Microsoft 365.

  오늘날에는 Microsoft 365 원본에 따라 일부 대량 메일(예: 뉴스레터)을 안전한 것으로 고려합니다. 이러한 "안전한" 원본의 메일은 현재 대량으로 표시되지 않습니다(대량 불만 수준 또는 BCL은 0 또는 1이기 때문에 이러한 원본의 메일을 전역적으로 차단하기가 어렵습니다). 대부분의 사용자에 대해 해결 방법은 이러한 대량 메시지의 구독을 개별적으로 취소하거나 보낸 Outlook 차단하는 것입니다. 그러나 일부 사용자는 대량 메시지 자체의 차단 또는 수신을 원하지 않습니다.

  대량 전자 메일을 필터링하는 메일 흐름 규칙은 VIP 사용자가 이를 직접 관리하지 않을 때 유용할 수 있습니다. 자세한 내용은 메일 흐름 규칙을 사용하여 대량 전자 [메일 필터링을 참조하세요.](/exchange/security-and-compliance/mail-flow-rules/use-rules-to-filter-bulk-mail.md)

## <a name="identify-and-designate-priority-accounts"></a>우선 순위 계정 식별 및 지정

이 기능을 사용할 수  있는 경우  우선 순위 계정 및 사용자 태그를 사용하면 사용자가 보고서에서 눈에 띄게 Microsoft 365 중요한 사용자를 식별하는 데 도움이 될 수 있습니다. 자세한 내용은 Microsoft [Defender에서](user-tags.md) 사용자 태그 for Office 365 우선 순위 계정 관리 및 [모니터링을 참조하세요.](/microsoft-365/admin/setup/priority-accounts)

## <a name="next-step"></a>다음 단계

**축하합니다!** You have completed the **Prepare** phase of your [migration to Microsoft Defender for Office 365!](migrate-to-defender-for-office-365.md#the-migration-process)

- [2단계: 설치로 진행합니다.](migrate-to-defender-for-office-365-setup.md)

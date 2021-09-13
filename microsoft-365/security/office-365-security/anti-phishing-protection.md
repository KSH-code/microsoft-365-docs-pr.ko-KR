---
title: 피싱 방지 보호 기능
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 75af74b2-c7ea-4556-a912-8c48e07271d3
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
ms.custom:
- TopSMBIssues
- seo-marvel-apr2020
description: 관리자는 EOP(Exchange Online Protection) 및 Microsoft Defender for Office 365.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 2a28e2ecc45be941dbd6e346f9918e1692357840
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2021
ms.locfileid: "59218125"
---
# <a name="anti-phishing-protection-in-microsoft-365"></a>2016년 8월의 피싱 방지 Microsoft 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**적용 대상**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Office 365용 Microsoft Defender 플랜 1 및 플랜 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

*피싱* 은 메시지에 포함된 중요한 정보를 훔치려고 하는 합법적인 발신자 또는 신뢰할 수 있는 발신자가 보낸 것 같은 전자 메일 공격입니다. 특정 범주의 피싱이 있습니다. 예시:

- **스피어 피싱은** 대상 받는 사람(일반적으로 공격자가 받는 사람을 정정한 후)에 맞게 특별히 조정된 포커스가 있는 사용자 지정 콘텐츠를 사용 합니다.

- **웨일링** 최대 효과를 위해 조직 내의 임원 또는 기타 높은 가치의 대상을 대상으로 합니다.

- **BEC(비즈니스** 전자 메일 손상)는 신뢰할 수 있는 보낸 사람(재무 책임자, 고객, 신뢰할 수 있는 파트너 등)을 사용하여 받는 사람을 속여 지급을 수령하거나 자금을 이체하거나 고객 데이터를 노출하게 합니다. [이 비디오](https://www.youtube.com/watch?v=8Kn31h9HwIQ&list=PL3ZTgFEc7LystRja2GnDeUFqk44k7-KXf&index=2)를 시청하여 자세히 확인하세요.

- **데이터를 암호화하고** 암호를 해독하기 위해 지급을 요구하는 랜섬웨어는 거의 항상 피싱 메시지에서 시작됩니다. 피싱 방지 보호는 암호화된 파일의 암호를 해독하는 데 도움이 되지 않지만 랜섬웨어 캠페인과 관련된 초기 피싱 메시지를 탐지하는 데 도움이 됩니다. 랜섬웨어 공격으로부터 복구하는 데 대한 자세한 내용은 랜섬웨어 공격에서 복구를 [Microsoft 365.](recover-from-ransomware.md)

공격의 복잡성이 증가함에 따라 학습된 사용자가 정교한 피싱 메시지를 식별하기도 어렵습니다. 다행히 EOP(Exchange Online Protection) 및 Microsoft Defender for Office 365 도움이 될 수 있습니다.

## <a name="anti-phishing-protection-in-eop"></a>EOP의 피싱 방지 보호 기능

EOP(Microsoft 365 Microsoft Defender for Office 365 없는 조직)에는 피싱 위협으로부터 조직을 보호하는 데 도움이 되는 기능이 포함되어 있습니다.

- **스푸핑** 인텔리전스: 스푸핑 인텔리전스 정보를 사용하여 검색된 스푸핑된 보낸 사람(외부 및 내부 도메인의 메시지)을 검토하고 검색된 보낸 사람이 수동으로 허용 또는 차단됩니다. 자세한 내용은 [EOP의 스푸핑 인텔리전스 인사이트](learn-about-spoof-intelligence.md)를 참조하세요.

- **EOP의** 피싱 방지 정책: 스푸핑 인텔리전스를 켜거나 끄고, Outlook 보낸 사람 식별을 설정 또는 해제하고, 차단된 스푸핑된 보낸 사람에 대한 작업을 지정합니다. 자세한 내용은 EOP에서 피싱 방지 [정책 구성을 참조하세요.](configure-anti-phishing-policies-eop.md)

- **테넌트 허용/차단 목록에서 스푸핑된 보낸 사람 허용 또는 차단**: 스푸핑 인텔리전스 인사이트에서 평가 결과를 재정의하면 스푸핑된 보낸 사람은 테넌트 허용/차단 목록의 **스푸핑** 탭에만 나타나는 수동 허용 또는 차단 항목이 됩니다. 스푸핑 인텔리전스에 의해 탐지되기 전에 스푸핑 발신자에 대한 허용 또는 차단 항목을 수동으로 만들 수도 있습니다. 자세한 내용은 [EOP에서 테넌트 허용/차단 목록 관리](tenant-allow-block-list.md)를 참조하세요.

- **암시적** 전자 메일 인증: EOP는 보낸 사람 신뢰도, 보낸 사람 기록, 받는 사람 기록, 동작 분석 및 위조된 보낸 사람을 식별하는 데 도움이 되는 기타 고급 기술을 사용하여 인바운드 전자 [메일(SPF,](set-up-spf-in-office-365-to-help-prevent-spoofing.md) [DKIM](use-dkim-to-validate-outbound-email.md)및 [DMARC)에](use-dmarc-to-validate-email.md)대한 표준 전자 메일 인증 검사를 향상합니다. 자세한 내용은 [Microsoft 365의 전자 메일 인증](email-validation-and-authentication.md)을 참조하세요.

## <a name="additional-anti-phishing-protection-in-microsoft-defender-for-office-365"></a>Office 365용 Microsoft Defender의 추가 피싱 방지 보호 기능

Office 365용 Microsoft Defender에는 피싱 방지 기능이 추가로 포함되어 있습니다.

- **Microsoft Defender for Office 365** 피싱 방지 정책: 특정 메시지 보낸 사람 및 보낸 사람 도메인, 사서함 인텔리전스 설정 및 조정 가능한 고급 피싱 임계값에 대한 가장 보호 설정을 구성합니다. 자세한 내용은 [Microsoft Defender에서](configure-mdo-anti-phishing-policies.md)피싱 방지 정책 구성을 Office 365. EOP의 피싱 방지 정책과 Defender for Office 365 피싱 방지 정책 간의 차이점에 대한 자세한 내용은 [Microsoft 365.](set-up-anti-phishing-policies.md)
- **캠페인 보기:** 기계 학습 및 기타추론은 전체 서비스 및 조직에 대한 피싱 공격과 관련된 메시지를 식별하고 분석합니다. 자세한 내용은 Microsoft [Defender for Office 365.](campaigns.md)
- **공격 시뮬레이션 교육:** 관리자는 가짜 피싱 메시지를 만들어 교육 도구로 내부 사용자에게 보낼 수 있습니다. 자세한 내용은 피싱 공격 [시뮬레이트를 참조하세요.](attack-simulation-training.md)

## <a name="other-anti-phishing-resources"></a>기타 피싱 방지 리소스

- 최종 사용자의 경우: 피싱 스키마 및 기타 형태의 온라인 사기로부터 자신을 [보호합니다.](https://support.microsoft.com/office/be0de46a-29cd-4c59-aaaf-136cf177d593)

- [피싱 Microsoft 365](how-office-365-validates-the-from-address.md)주소의 유효성을 검사하는 방법

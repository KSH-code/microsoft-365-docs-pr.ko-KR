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
description: 관리자는 EOP(Exchange Online Protection) 및 Office 365용 Microsoft Defender의 피싱 방지 보호 기능에 대해 배울 수 있습니다.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: b0ca7a83e8e8d66bd58fddfc46f53df32f4f623c
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51073604"
---
# <a name="anti-phishing-protection-in-microsoft-365"></a>Microsoft 365의 피싱 방지 보호 기능

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**적용 대상**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Office 365용 Microsoft Defender 플랜 1 및 플랜 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

*피싱은* 합법적인 보낸 사람이나 신뢰할 수 있는 보낸 사람이 보낸 것으로 나타나는 메시지의 중요한 정보를 도용하는 전자 메일 공격입니다. 특정 범주의 피싱이 있습니다. 예시:

- **스피어 피싱은** 대상 받는 사람(일반적으로 공격자가 받는 사람을 정정한 후)에 맞게 특별히 조정된 포커스가 있는 사용자 지정 콘텐츠를 사용 합니다.

- **래링은** 최대 효과를 위해 조직 내의 임원 또는 기타 높은 가치의 대상을 대상으로 합니다.

- **BEC(비즈니스** 전자 메일 손상)는 신뢰할 수 있는 보낸 사람(재무 책임자, 고객, 신뢰할 수 있는 파트너 등)을 사용하여 받는 사람을 속여 지급을 수령하거나 자금을 이체하거나 고객 데이터를 노출하게 합니다.

- **데이터를 암호화하고** 암호를 해독하기 위해 지급을 요구하는 랜섬웨어는 거의 항상 피싱 메시지에서 시작됩니다. 피싱 방지 보호는 암호화된 파일의 암호를 해독하는 데 도움이 될 수 없지만 랜섬웨어 캠페인과 연결된 초기 피싱 메시지를 검색하는 데 도움이 될 수 있습니다. 랜섬웨어 공격으로부터 복구하는 데 대한 자세한 내용은 [Microsoft 365의 랜섬웨어 공격에서 복구를 참조하세요.](recover-from-ransomware.md)

공격의 복잡성이 증가함에 따라 학습된 사용자가 정교한 피싱 메시지를 식별하기도 어렵습니다. 다행히 EOP(Exchange Online Protection)와 Office 365용 Microsoft Defender의 추가 기능은 도움이 될 수 있습니다.

## <a name="anti-phishing-protection-in-eop"></a>EOP의 피싱 방지 보호 기능

EOP(즉, Office 365용 Microsoft Defender가 없는 Microsoft 365 조직)에는 피싱 위협으로부터 조직을 보호하는 데 도움이 되는 기능이 포함되어 있습니다.

- **스푸핑 인텔리전스**: 내부 및 외부 도메인의 보낸 사람으로부터 스푸핑된 메시지를 검토하고 해당 보낸 사람을 허용하거나 차단합니다. 자세한 내용은 [EOP에서 스푸핑 인텔리전스 구성을 참조하세요.](learn-about-spoof-intelligence.md)

- **EOP의** 피싱 방지 정책: 스푸핑 인텔리전스를 켜거나 끄고, Outlook에서 확인되지 않은 보낸 사람 ID를 켜거나 끄고, 차단된 스푸핑된 보낸 사람에 대한 작업(정크 메일 폴더 또는 정크 메일 폴더로 이동)을 지정합니다. 자세한 내용은 EOP에서 피싱 방지 [정책 구성을 참조하세요.](configure-anti-phishing-policies-eop.md)

- **암시적** 전자 메일 인증: EOP는 보낸 사람 신뢰도, 보낸 사람 기록, 받는 사람 기록, 동작 분석 및 위조된 보낸 사람을 식별하는 데 도움이 되는 기타 고급 기술을 사용하여 인바운드 전자 [메일(SPF,](set-up-spf-in-office-365-to-help-prevent-spoofing.md) [DKIM](use-dkim-to-validate-outbound-email.md)및 [DMARC)에](use-dmarc-to-validate-email.md)대한 표준 전자 메일 인증 검사를 향상합니다. 자세한 내용은 [Microsoft 365의 전자 메일 인증](email-validation-and-authentication.md)을 참조하세요.

## <a name="additional-anti-phishing-protection-in-microsoft-defender-for-office-365"></a>Office 365용 Microsoft Defender의 추가 피싱 방지 보호 기능

Office 365용 Microsoft Defender에는 추가 고급 피싱 방지 기능이 포함되어 있습니다.

- **Microsoft Defender for Office 365의** 피싱 방지 정책: 새 사용자 지정 정책을 만들고, 가장 방지 설정(사용자 및 도메인을 가장으로부터 보호), 사서함 인텔리전스 설정 및 조정 가능한 고급 피싱 임계값을 구성합니다. 자세한 내용은 [Office 365용 Microsoft Defender에서](configure-atp-anti-phishing-policies.md)피싱 방지 정책 구성을 참조하세요. EOP의 피싱 방지 정책과 Office 365용 Defender의 피싱 방지 정책 간의 차이점에 대한 자세한 내용은 [Microsoft 365의](set-up-anti-phishing-policies.md)피싱 방지 정책을 참조하세요.

- **캠페인 보기:** 기계 학습 및 기타추론은 전체 서비스 및 조직에 대한 피싱 공격과 관련된 메시지를 식별하고 분석합니다. 자세한 내용은 [Office 365용 Microsoft Defender의 캠페인 보기를 참조하세요.](campaigns.md)

- **공격 시뮬레이터:** 관리자는 가짜 피싱 메시지를 만들어 교육 도구로 내부 사용자에게 보낼 수 있습니다. 자세한 내용은 [Microsoft Defender for Office 365의 공격 시뮬레이터를 참조하세요.](attack-simulator.md)

## <a name="other-anti-phishing-resources"></a>기타 피싱 방지 리소스

- 최종 사용자의 경우: 피싱 스키마 및 기타 형태의 온라인 사기로부터 자신을 [보호합니다.](https://support.microsoft.com/office/be0de46a-29cd-4c59-aaaf-136cf177d593)

- [Microsoft 365에서](how-office-365-validates-the-from-address.md)피싱을 방지하기 위해 시작 주소의 유효성을 검사하는 방법

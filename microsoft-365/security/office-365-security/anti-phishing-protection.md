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
ms.service: O365-seccomp
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
description: 관리자는 EOP (Exchange Online Protection)의 피싱 방지 보호 기능 및 Office 용 Microsoft Defender 365의 정보를 확인할 수 있습니다.
ms.openlocfilehash: 51c539a47f1c137dbacbfaaf63212e1bb115860c
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/03/2020
ms.locfileid: "48844515"
---
# <a name="anti-phishing-protection-in-microsoft-365"></a>Microsoft 365의 피싱 방지 보호 기능

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


*피싱은* 적법 하거나 신뢰할 수 있는 보낸 사람 으로부터 온 것 처럼 보이는 메시지의 중요 한 정보를 도용 하는 전자 메일 공격입니다. 특정 종류의 피싱이 있습니다. 예:

- **스피어 피싱은** 중요 한 사용자 지정 된 콘텐츠 (일반적으로 공격자가 받는 사람을 검사 한 후)를 사용 합니다.

- **Whaling** 은 최대의 효과를 위해 임원 또는 조직 내의 다른 높은 가치 표적에 연결 됩니다.

- **BEC (비즈니스 전자 메일 손상)** 은 위조 된 보낸 사람 (금융 관리자, 고객, 신뢰할 수 있는 파트너 등)을 사용 하 여 받는 사람이 대금을 승인 하거나 자금을 전송 하거나 고객 데이터를 드러내는 것을 유도할 수 있습니다.

- 데이터를 암호화 하 고 해당 암호를 해독 하기 위한 지불을 요청 하는 **랜 섬 웨어** 는 피싱 메시지에서 거의 항상 시작 됩니다. 피싱 방지 보호는 암호화 된 파일의 암호를 해독 하는 데 도움이 되지만, 랜 섬 웨어 캠페인과 연결 된 초기 피싱 메시지를 검색 하는 데 도움이 될 수 있습니다. 랜 섬 웨어 공격에서 복구 하는 방법에 대 한 자세한 내용은 [Microsoft 365에서 랜 섬 웨어 공격 으로부터 복구](recover-from-ransomware.md)를 참조 하세요.

공격에 대 한 복잡성이 증가 함에 따른 숙련 된 사용자가 복잡 한 피싱 메시지를 식별 하기는 어렵습니다. 다행 스럽게도 EOP (Exchange Online Protection) 및 Office 용 Microsoft Defender 365의 추가 기능은 도움이 될 수 있습니다.

## <a name="anti-phishing-protection-in-eop"></a>EOP의 피싱 방지 보호 기능

EOP (예: microsoft Defender for Office 365가 없는 Microsoft 365 조 직) 피싱 위협 으로부터 조직을 보호 하는 데 도움이 되는 기능이 포함 되어 있습니다.

- **스푸핑 인텔리전스** : 내부 및 외부 도메인의 보낸 사람으로부터 스푸핑된 메시지를 검토하고 해당 보낸 사람을 허용하거나 차단합니다. 자세한 내용은 [Configure 스푸핑이 intelligence IN EOP](learn-about-spoof-intelligence.md)을 참조 하십시오.

- **EOP의 피싱 방지 정책** : 스푸핑 인텔리전스를 설정 하거나 해제 하 고, Outlook에서 인증 되지 않은 보낸 사람 id를 설정/해제 하 고, 차단 된 스푸핑된 보낸 사람 (정크 메일 폴더 또는 격리로 이동)에 대 한 작업을 지정 합니다. 자세한 내용은 [EOP에서 피싱 방지 정책 구성을](configure-anti-phishing-policies-eop.md)참조 하세요.

- **암시적 전자 메일 인증** : [EOP에서는 위조](set-up-spf-in-office-365-to-help-prevent-spoofing.md)된 보낸 사람을 식별 하는 데 도움이 되는 보낸 [DMARC](use-dmarc-to-validate-email.md)사람 신뢰도, 보낸 사람 기록, 받는 사람 기록, 행태 분석 및 기타 고급 기법을 사용 하 여 인바운드 전자 메일에 대 한 표준 전자 메일 인증 [확인을 향상](use-dkim-to-validate-outbound-email.md)시킵니다. 자세한 내용은 [Microsoft 365의 전자 메일 인증](email-validation-and-authentication.md)을 참조하세요.

## <a name="additional-anti-phishing-protection-in-microsoft-defender-for-office-365"></a>Microsoft Defender for Office 365의 추가 피싱 방지 보호 기능

Office 365 용 Microsoft Defender에는 다음과 같은 추가 및 고급 피싱 방지 기능이 포함 되어 있습니다.

- **Office 용 Microsoft Defender의 피싱 방지 정책 365** : 새 사용자 지정 정책을 만들고, 가장 설정이 구성 된 경우 (가장에서 사용자 및 도메인 보호), 사서함 인텔리전스 설정 및 조정 가능한 고급 피싱 임계값 자세한 내용은 [Office 용 Microsoft Defender 365에서 피싱 방지 정책 구성을](configure-atp-anti-phishing-policies.md)참조 하세요. EOP의 피싱 방지 정책과 Office 365의 Defender 피싱 방지 정책 간의 차이점에 대 한 자세한 내용은 [Microsoft 365의 피싱 방지 정책을](set-up-anti-phishing-policies.md)참조 하세요.

- **캠페인 보기** : 기계 학습 및 기타 휴리스틱 전체 서비스 및 조직에 대해 통합 된 피싱 공격과 관련 된 메시지를 식별 하 고 분석 합니다. 자세한 내용은 [Microsoft Defender For Office 365의 캠페인 보기](campaigns.md)를 참조 하세요.

- **Attack 시뮬레이터** : 관리자는 가짜 피싱 메시지를 만들고 교육 도구로 내부 사용자에 게 보낼 수 있습니다. 자세한 내용은 [Microsoft Defender For Office 365의 Attack 시뮬레이터](attack-simulator.md)를 참조 하세요.

## <a name="other-anti-phishing-resources"></a>기타 피싱 방지 리소스

- 최종 사용자는 [피싱 체계 및 기타 형태의 온라인 사기 행위를 방지할](https://support.microsoft.com/office/be0de46a-29cd-4c59-aaaf-136cf177d593)수 있습니다.

- [Microsoft 365에서 보낸 사람 주소의 유효성을 검사 하 여 피싱을 방지 하는 방법](how-office-365-validates-the-from-address.md)입니다.

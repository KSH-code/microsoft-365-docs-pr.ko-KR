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
ms.custom:
- TopSMBIssues
- seo-marvel-apr2020
description: 관리자는 EOP(Exchange Online Protection) 및 Office 365 ATP(Office 365 Advanced Threat Protection)의 피싱 방지 보호 기능에 대해 알아보세요.
ms.openlocfilehash: 5594c4e7033ab70a622403bca7759cd4b89f111a
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/20/2020
ms.locfileid: "46827448"
---
# <a name="anti-phishing-protection-in-microsoft-365"></a>Microsoft 365의 피싱 방지 보호 기능

*피싱은 적법하거나* 신뢰할 수 있는 보낸 사람이 보는 메시지에 중요한 정보를 도용하려는 전자 메일 공격입니다. 피싱의 특정 범주가 있습니다. 예제:

- **스피어 피싱은** 특히 대상이 지정된 받는 사람에게 맞춤화된 매우 중요하고 사용자 지정된 콘텐츠를 사용합니다(일반적으로 공격자가 받는 사람을 수정한 후).

- **Whaling은** 최대 효과를 위해 조직 내 중역 또는 다른 높은 가치 대상으로 지시됩니다.

- **BEC(Business Email Compromise)는 수신자를** 대금 결제, 자금 전송 또는 고객 데이터를 노출하는 노력에 위조된 발신자(금전적 사업자, 고객, 신뢰할 수 있는 파트너 등)를 사용합니다.

- 사용자의 데이터를 암호화하고 암호 해수에 대한 지급을 하는 **Ransomware는** 거의 항상 피싱 메일로 시작합니다. 피싱 방지 보호 기능은 암호화된 파일의 암호해를 해독하는 데 도움이 되지는 않지만, 이 기능은 리저지 위협과 연결된 초기 피싱 메시지를 감지하는 데 도움이 됩니다. 랜웨어 공격으로부터 복구하는 방법에 대한 자세한 내용은 [Microsoft 365에서 랜웨어 공격으로부터 복구를 참조하세요.](recover-from-ransomware.md)

이로 해결되면서 공격의 복잡성이 높아지면서 학습된 사용자가 정교한 피싱 메시지를 식별하기가 더어도 어렵습니다. 다가, EOP(Exchange Online Protection) 및 Office 365 ATP(Advanced Threat Protection)의 추가 기능으로도 도달할 수 있습니다.

## <a name="anti-phishing-protection-in-eop"></a>EOP의 피싱 방지 보호 기능

EOP(즉, ATP가 없는 Microsoft 365 조직)에는 피싱 위협으로부터 조직을 보호하는 데 도움이 되는 기능이 포함되어 있습니다.

- **스푸핑 인텔리전스**: 내부 및 외부 도메인의 보낸 사람으로부터 스푸핑된 메시지를 검토하고 해당 보낸 사람을 허용하거나 차단합니다. 자세한 내용은 [EOP에서 스푸핑 인텔리전스 구성을 참조하세요.](learn-about-spoof-intelligence.md)

- **EOP의 피싱 방지**정책 : 스푸핑 인텔리전스를 설정 또는 해제하고, Outlook의 인증되지 않은 발신자 식별을 설정 또는 해제하며, 차단된 스푸핑된 발신자(정크 메일 폴더 또는 격리로 이동)에 대한 작업을 지정합니다. 자세한 내용은 [EOP에서 피싱 방지 정책 구성을 참조하세요.](configure-anti-phishing-policies-eop.md)

- **암시적 전자 메일 인증**: EOP는 보낸 사람[신뢰도,](set-up-spf-in-office-365-to-help-prevent-spoofing.md) [DKIM](use-dkim-to-validate-outbound-email.md)보낸 사람 기록, 받는 사람 기록, 행동 분석 및 기타 고급 기술을 사용하여 인바운드 전자 메일에 대한 표준 전자 메일 [인증](use-dmarc-to-validate-email.md)확인을 향상하며, 위조된 보낸 사람을 식별하는 데 도움이 됩니다. 자세한 내용은 [Microsoft 365의 전자 메일 인증](email-validation-and-authentication.md)을 참조하세요.

## <a name="additional-anti-phishing-protection-in-office-365-atp"></a>Office 365 ATP의 추가 피싱 방지 보호 기능

Office 365 ATP에는 추가 기능과 고급 피싱 방지 기능이 있습니다.

- **ATP 피싱 방지 정책: 새 사용자**지정 정책을 만들고, 가장 방지 설정 구성(사용자 및 도메인을 가장으로부터 보호), 사서함 인텔리전스 설정 및 조정 가능한 고급 피싱 임계값. 자세한 내용은 [Microsoft 365에서 ATP 피싱 방지 정책 구성을 참조하세요.](configure-atp-anti-phishing-policies.md) 피싱 방지 정책과 ATP 피싱 방지 정책 간의 차이점에 대한 자세한 내용은 Microsoft 365의 피싱 방지 [정책을 참조하세요.](set-up-anti-phishing-policies.md)

- **캠페인 보기:** 기계 학습 및 기타 추론은 전체 서비스 및 조직에 대해 조화된 피싱 공격과 연려되는 메시지를 식별하고 분석합니다. 자세한 내용은 [Office 365 ATP의 캠페인 보기를 참조하세요.](campaigns.md)

- **공격 시뮬레이터**: 관리자는 가조피 피싱 메시지를 만들고 교육 도구로 내부 사용자에게 보낼 수 있습니다. 자세한 내용은 [Office 365 ATP의 공격 시뮬레이터를 참조하세요.](attack-simulator.md)

## <a name="other-anti-phishing-resources"></a>기타 피싱 방지 리소스

- 최종 사용자의 경우: 피싱 구성표 및 기타 온라인 [사기 양식으로부터 사용자를 보호합니다.](https://support.microsoft.com/office/be0de46a-29cd-4c59-aaaf-136cf177d593)

- [Microsoft 365가 From 주소의 유효성을 검사하여 피싱을 방지하는 방법입니다.](how-office-365-validates-the-from-address.md)

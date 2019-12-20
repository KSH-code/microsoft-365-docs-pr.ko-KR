---
title: Office 365 보안 사고 대응
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 04/27/2018
audience: ITPro
ms.topic: overview
ms.collection:
- o365_security_incident_response
- M365-security-compliance
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
description: 이 해결 방법은 Office 365에서 가장 일반적인 사이버 보안 공격과 그에 대응하는 방법에 대해 설명합니다.
ms.openlocfilehash: c55a5d561fec4219d29926036842836174b790da
ms.sourcegitcommit: 6ae69c40bafa6aef633789c3df0fa20590bdcf40
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/20/2019
ms.locfileid: "40823830"
---
# <a name="office-365-security-incident-response"></a>Office 365 보안 사고 대응

 **요약**: 이 해결 방법은 Office 365에서 가장 일반적인 사이버 보안 공격에 대한 지표와 주어진 공격을 확실하게 확인하는 방법 및 대응하는 방법에 대해 설명합니다.

## <a name="overview"></a>개요

모든 사이버 공격을 막을 수 있는 것은 아닙니다. 공격자는 계속해서 방어 전략에 대한 새로운 약점을 찾고 있거나 이전 약점을 악용하고 있습니다. 공격을 인식하는 방법을 알면 보다 신속하게 대처하여 보안 사고의 기간을 단축시킬 수 있습니다.

이 문서 시리즈는 Office 365에서 특정 유형의 공격이 어덯게 보이는지 파악하는 데 도움을 줍니다. 다음 사항을 이해하기 위한 빠른 진입점입니다.

- 공격이란 무엇인가와 작동 방식

- 확인을 위해 IOC(침해 지표)라고 하는 신호 및 해당 신호를 찾는 방법

- 공격을 확실하게 확인하는 방법

- 공격을 제거하고 향후에 조직을 더욱 효과적으로 보호기 위해 수행하는 단계

- 각 공격 유형에 관한 자세한 정보 링크

시간이 지남에 따라 더 많은 문서가 추가되기 때문에 매월 다시 확인하세요.

## <a name="detect-and-remediate-articles"></a>문서 검색 및 수정

- [Office 365에서 불법 동의 권한 부여 검색 및 교정](detect-and-remediate-illicit-consent-grants.md)

- [Office 365에서 Outlook 규칙 및 사용자 지정 양식 주입 공격 감지 및 재구성](detect-and-remediate-outlook-rules-forms-attack.md)

## <a name="incident-response-articles"></a>인시던트 대응 문서

- [Office 365에서 손상된 이메일 계정에 응답](responding-to-a-compromised-email-account.md)

## <a name="secure-office-365-like-a-cybersecurity-pro"></a>사이버 보안 전문가와 같은 Office 365 보안

Office 365 구독에는 데이터 및 사용자를 보호하는 데 사용할 수있는 강력한 보안 기능이 함께 제공됩니다.  [Office 365 보안 로드맵: - 최초 30일, 90일 및 그 이후의 최우선 순위](security-roadmap.md)를 사용하여 Microsoft에서 권장하는 Office 365 테넌트 보안을 구현합니다.

- 처음 30일 이내에 수행 할 작업  이러한 작업들은 즉각적인 영향을 미치며 사용자에게 영향을 미치지 않습니다.

- 90일 이내에 수행해야 할 작업 이러한 작업들은 계획하고 구현하는 데 다소 시간이 걸리지만 보안 태세를 갖추는 데 큰 도움이 됩니다.

- 90일 초과 이러한 향상된 기능은 처음 90일간의 작업에서 구축됩니다.

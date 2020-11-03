---
title: 데이터 개인 정보 규정에 대 한 id, 장치 및 위협 보호 사용
ms.author: bcarter
author: brendacarter
f1.keywords:
- NOCSH
manager: laurawi
ms.date: 06/09/2020
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
- m365solution-infoprotection
- m365solution-scenario
ms.custom: ''
description: Microsoft 365의 id, 장치 및 위협 보호 서비스를 통해 개인 데이터 위반을 방지 합니다.
ms.openlocfilehash: 321b60efbdabe62b14502df4a16dd2dcec4b9cef
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/03/2020
ms.locfileid: "48847181"
---
# <a name="use-identity-device-and-threat-protection-for-data-privacy-regulation"></a>데이터 개인 정보 규정에 대 한 id, 장치 및 위협 보호 사용

Microsoft 365에서는 조직에서 데이터 개인 정보 관련 규정 준수 규정을 준수 하는 데 사용할 수 있는 다양 한 id, 장치 및 위협 보호 기능을 제공 합니다. 이 문서에서는 이러한 분야에 필요한 데이터 개인 정보 규정에 대해 설명 하 고, 구현 요구 사항을 해결 하는 데 도움이 되는 자세한 정보에 대 한 링크와 함께 관련 Microsoft 365 기능 및 서비스의 목록을 제공 합니다.

## <a name="how-identity-device-and-threat-protection-relate-to-data-privacy-regulation"></a>Id, 장치 및 위협 보호와 데이터 개인 정보 규정의 관계

데이터 개인 정보 규정은 해당 복구 단위에 따라 달라 지는 하지만, 다음을 나타내는 GDPR의 문서 5 (1) (f)에서 해당 사용자의 통화에 대 한 에센스를 embodied 합니다. 

- 개인 데이터는 무단 또는 불법적 처리, 우발적 손실, 파괴 또는 손상에 대 한 보호, 적절 한 기술 또는 조직적 조치 (' 무결성 및 기밀성 ')를 포함 하 여 개인 데이터에 대 한 적절 한 보안을 보장 하는 방식으로 처리 됩니다.

개인 데이터 침해는 종종 관리 또는 최종 사용자 계정 손상 및 악의적인 시스템 액세스로 인해 발생 합니다. 예를 들어 관리자 계정 해킹으로 인해 고객 신용 카드 번호나 기타 개인 정보를 exfiltration 할 수 있습니다. 준수 관리자에 게 제공 되는 Microsoft 365에서 사용할 수 있는 일반적으로 권장 되는 모든 id, 장치 및 위협 방지는 준수 점수에 반영 될 수 있습니다.

## <a name="using-the-results-of-your-assessment-work-and-compliance-manager"></a>평가 작업 및 준수 관리자의 결과 사용

준수 관리자는 다음 범주를 사용 하는 id, 장치 및 위협 보호를 포함 합니다.

- **제어 액세스** 범주에 해당 하는 id입니다.
- 장치가 **장치 관리** 범주에 해당 합니다.
- 위협 방지는 **위협 으로부터 보호** 범주에 해당 합니다.
 
4 가지 주요 데이터 개인 정보 규정을 준수 하는 샘플 집합에서 이러한 기능을 선택 하는 경우 적합성 관리자는 90 개선 작업을 지정 하며, 대부분의 경우 "27"로 점수가 증가 합니다. 이러한 대규모 번호는 이러한 범주에 대 한 준수 관리자에 의해 호출 되기 때문에 참조를 위해 여기에 나열 되는 몇 가지 일반적인 항목이 나와 있습니다.

다음과 같은 작업을 수행할 수 있는 id 및 **제어 액세스** 범주에 [azure Active DIRECTORY (azure AD)](https://azure.microsoft.com/services/active-directory/) 를 사용 합니다.

- Replay 방지 인증 구현 ("중간자" 공격을 막기 위해)
- 레거시 인증을 차단합니다.
- 사용자 위험 및 사용자 로그인 위험 정책을 구성 합니다.
- 관리자 및 비관리자를 위해 조건부 액세스 및 MFA (multi-factor authentication)를 사용 하도록 설정 합니다.
- 암호 정책을 구성 하 고 적용 합니다.
- Azure AD 권한 Id 관리를 사용 하 여 권한 있는 계정에 대 한 액세스를 제한 합니다.
- 종료 시 액세스를 사용 하지 않도록 설정
- 감사 사용자 계정 및 상태 변경
- 역할 그룹 및 관리 변경 내용을 검토 합니다.

장치 및 **장치 관리** 범주에 대해 [Microsoft Endpoint Manager](https://www.microsoft.com/microsoft-365/microsoft-endpoint-manager) 를 사용 하 여 다음을 수행할 수 있습니다.

- 깨진 및 루트 모바일 장치를 차단 합니다.
- 모바일 장치 관리를 위해 Intune을 구성 합니다.
- Android, iOS, macOS 및 Windows 장치에 대 한 준수 정책 만들기
- Android, iOS, macOS 및 Windows 장치에 대 한 장치 구성 프로필을 만듭니다.
- IOS 및 Windows에 대 한 앱 보호 정책을 만듭니다.
- 잠금 화면을 사용 하 여 정보 숨기기
- 모바일 장치에 대 한 암호 정책 구현
- 비활성 상태가 되 면 모바일 장치가 잠길 수 있도록 요구 합니다.
- 여러 로그인 오류가 발생 하면 모바일 장치에서 데이터를 정리 해야 합니다.

다음 작업을 수행할 수 있는 **위협 으로부터 보호** 범주에 대해 [Exchange Online Protection 및 Office 365 용 Microsoft Defender](../security/office-365-security/office-365-atp.md) 를 사용 합니다.

- 보낸 사람 인증 (SPF, DMARC 및 DKIM)을 사용 하도록 설정 합니다.
- Microsoft Defender for Office 365-피싱 방지 정책을 설정 합니다.
- 안전한 첨부 파일을 구현 합니다.
- 안전한 링크를 구현 합니다.
- 맬웨어 검색 및 응답 정책을 구현 합니다.
- 아웃 바운드 및 인바운드 스팸 정책을 구현 합니다.

### <a name="references"></a>참조가

- [일반 ID 및 장치 액세스 정책](../security/office-365-security/identity-access-policies.md)
- [Office 365에서 위협 으로부터 보호](https://support.office.com/article/protect-against-threats-in-office-365-b10023f6-f30f-45d3-b3ad-b71aa4aa0d58)
- [안전한 첨부 파일](../security/office-365-security/atp-safe-attachments.md)
- [안전한 링크](../security/office-365-security/atp-safe-links.md)
- [안전한 문서](../security/office-365-security/safe-docs.md)

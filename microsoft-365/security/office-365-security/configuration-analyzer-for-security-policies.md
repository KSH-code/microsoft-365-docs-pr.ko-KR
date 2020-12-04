---
title: 보안 정책에 대한 구성 분석기
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.reviewer: ''
ms.date: ''
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: 관리자는 구성 분석기를 사용하여 표준 보호 및 엄격한 보호 미리 설정 보안 정책 아래에 있는 보안 정책을 찾아 수정하는 방법을 배울 수 있습니다.
ms.openlocfilehash: 7d02a6f83ceb06eb56039b449890fd90712c76e5
ms.sourcegitcommit: d81c7cea85af6ad5fef81d3c930514a51464368c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/04/2020
ms.locfileid: "49572540"
---
# <a name="configuration-analyzer-for-protection-policies-in-eop-and-microsoft-defender-for-office-365"></a>EOP 및 Office 365용 Microsoft Defender의 보호 정책에 대한 구성 분석기

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


> [!NOTE]
> 이 항목에 설명된 기능은 미리 보기에 있으며, 일부 조직에서는 사용할 수 없는 기능으로, 변경될 수 있습니다. 릴리스 일정에 대한 자세한 내용은 [Microsoft 365 로드맵을 참조하십시오.](https://www.microsoft.com/microsoft-365/roadmap?filters=&searchterms=config%2Canalyzer)

보안 및 준수 & 센터의 구성 분석기는 설정이 미리 설정된 보안 정책의 표준 보호 및 엄격한 보호 프로필 설정 아래에 있는 보안 정책을 찾고 수정할 수 있는 중앙 [위치를 제공합니다.](preset-security-policies.md)

구성 분석기에서는 다음과 같은 유형의 정책을 분석합니다.

- **EOP(Exchange Online Protection)** 정책: Exchange Online 사서함이 있는 Microsoft 365 조직과 Exchange Online 사서함이 없는 독립 실행형 EOP 조직이 포함됩니다.
  
  - [스팸 방지 정책.](configure-your-spam-filter-policies.md)
  - [맬웨어 방지 정책](configure-anti-malware-policies.md).
  - [EOP 피싱 방지 정책.](set-up-anti-phishing-policies.md#spoof-settings)

- **Office 365용 Microsoft Defender** 정책: 여기에는 Microsoft 365 E5 또는 Office 365용 Defender 추가 기능 구독이 있는 조직이 포함됩니다.

  - Office 365용 Microsoft Defender의 피싱 방지 정책에는 다음이 포함됩니다.

    - EOP [피싱](set-up-anti-phishing-policies.md#spoof-settings) 방지 정책에서 사용할 수 있는 동일한 스푸핑 설정입니다.
    - [가장 설정](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)
    - [고급 피싱 임계값](set-up-anti-phishing-policies.md#advanced-phishing-thresholds-in-anti-phishing-policies-in-microsoft-defender-for-office-365)

  - [안전한 링크 정책](set-up-atp-safe-links-policies.md).

  - [안전한 첨부 파일 정책.](set-up-atp-safe-attachments-policies.md)

기준으로 사용되는 **표준** 및 **엄격한** 정책 설정 값은 [EOP 및 Office 365용 Microsoft Defender](recommended-settings-for-eop-and-office365-atp.md)보안에 대한 권장 설정에 설명되어 있습니다.

## <a name="what-do-you-need-to-know-before-you-begin"></a>시작하기 전에 알아야 할 내용은 무엇인가요?

- <https://protection.office.com/>에서 보안 및 준수 센터를 엽니다. 구성 분석기 **페이지로** 직접 이동하려면 <https://protection.office.com/configurationAnalyzer> .

- Exchange Online PowerShell에 연결하려면 [Exchange Online PowerShell에 연결](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)을 참조하세요.

- 이 문서의 절차를 수행하려면 먼저 보안 및 준수 & 사용 권한을 할당해야 합니다.
  - 구성 분석기를 사용하여 **and** 보안 정책을 업데이트하려면 **조직** 관리 또는 보안 관리자 역할 그룹의 **구성원이** 되어야 합니다.
  - 구성 분석기에 대한 읽기 전용 액세스 권한을 사용하려면 **Global Reader** 전역 읽기 사용자 또는 보안 읽기 권한이 있는 역할 그룹의 **구성원이** 되어야 합니다.

  자세한 내용은 [보안 및 준수 센터의 사용 권한](permissions-in-the-security-and-compliance-center.md)을 참조하세요.

  **참고**:

  - Microsoft 365 관리 센터에서 해당 Azure Active Directory 역할에 사용자를 추가하면 사용자에게 보안 & _and_ 준수 센터에서 필요한 사용 권한과 Microsoft 365의 다른 기능에 대한 사용 권한이 부여됩니다. 자세한 내용은 [관리자 역할 정보](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles)를 참조하세요.
  - [또한 Exchange Online의](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) 보기 **전용 조직** 관리 역할 그룹은 기능에 대한 읽기 전용 액세스를 제공합니다.

## <a name="use-the-configuration-analyzer-in-the-security--compliance-center"></a>보안 및 준수 센터에서 구성 & 사용

보안 & 준수 센터에서 **위협 관리** 정책 구성 \> **Policy** \> **분석기로 이동합니다.**

![위협 관리 정책 페이지의 구성 분석기 위젯 \>](../../media/configuration-analyzer-widget.png)

구성 분석기에는 두 개의 기본 탭이 있습니다.

- **설정 및 권장** 사항: 표준 또는 엄격을 선택하고 이러한 설정을 기존 보안 정책과 비교합니다. 결과에서 표준 또는 엄격과 같은 수준으로 설정 값을 조정할 수 있습니다.

- **구성 드리프트 분석 및 기록:** 이 보기를 통해 시간의 따라 정책 변경 내용을 추적할 수 있습니다.

### <a name="setting-and-recommendations-tab-in-the-configuration-analyzer"></a>구성 분석기에서 설정 및 추천 탭

기본적으로 표준 보호 프로필과 비교할 때 탭이 열립니다. Strict 추천 보기를 클릭하여 Strict protection 프로필 비교로 전환할 **수 있습니다.** 다시 전환하려면 표준 권장 **사항 보기를 선택합니다.**

![구성 분석기에서 설정 및 권장 사항 보기](../../media/configuration-analyzer-settings-and-recommendations-view.png)

기본적으로 정책 **그룹/설정** 이름 열에는 다양한 유형의 보안 정책과 개선해야 하는 설정 수(있는 경우)의 축소된 보기가 포함되어 있습니다. 정책 유형은 다음입니다.

- **스팸 방지**
- **피싱 방지**
- **맬웨어 방지**
- **ATP 안전한 첨부** 파일(구독에 Office 365용 Microsoft Defender가 포함된 경우)
- **ATP 안전한** 링크(구독에 Office 365용 Microsoft Defender가 포함된 경우)

기본 보기에서는 모든 것이 축소됩니다. 각 정책 옆에는 정책의 비교 결과(수정할 수 있는)와 표준 또는 엄격 보호 프로필에 대한 해당 정책의 설정(수정할 수 없는)이 요약됩니다. 비교할 보호 프로필에 대한 다음 정보가 표시됩니다.

- **녹색:** 모든 기존 정책의 모든 설정은 최소한 보호 프로필만큼 안전합니다.
- **Amber:** 기존 정책의 소수의 설정은 보호 프로필만큼 안전하지 않습니다.
- **빨간색:** 기존 정책의 많은 설정이 보호 프로필만큼 안전하지 않습니다. 이 설정은 여러 정책의 몇 가지 설정일 수도 있을 수도 있습니다.

선호하는 비교를 위해 모든 설정이 권장 사항을 **따르는 텍스트가** \<**Standard** or **Strict**\> **표시됩니다.** 그렇지 않으면 변경할 권장 설정 수가 표시됩니다.

정책 **그룹/설정** 이름을 확장하면 주의가 필요한 각 특정 정책의 모든 정책 및 관련 설정이 표시됩니다. 또는 특정 유형의 정책(예: 스팸 방지)을 확장하여 주의가 필요한 정책 유형에서 해당 설정만 볼 수 있습니다. **Anti-spam**

비교에 개선에 대한 권장 사항(녹색)이 없는 경우 정책을 확장하면 아무 것도 표시됩니다. 개선을 위한 권장 사항(빨강 또는 빨강)이 있는 경우 주의가 필요한 설정이 표시될 수 있으며 해당 정보는 다음 열에 표시됩니다.

- 주의가 필요한 설정의 이름입니다. 예를 들어 이전 스크린샷에서 스팸 방지 정책의 대량 전자 메일 **임계값입니다.**

- **정책**: 설정이 포함된 영향을 받는 정책의 이름입니다.

- **적용:** 영향을 받는 정책이 적용되는 사용자 수입니다.

- **현재 구성**: 설정의 현재 값입니다.

- **마지막으로 수정한** 날짜: 정책을 마지막으로 수정한 날짜입니다.

- **권장** 사항 : 표준 또는 엄격한 보호 프로필의 설정 값입니다. 정책의 설정 값을 보호 프로필의 권장 값과 일치하게 변경하려면 채택을 **클릭합니다.** 변경에 성공하면 다음 메시지가 **표시됩니다. 추천이 성공적으로 채택됩니다.** 새로 **고침을** 클릭하여 감소된 추천 수와 결과에서 특정 설정/정책 행을 제거합니다.

### <a name="configuration-drift-analysis-and-history-tab-in-the-configuration-analyzer"></a>구성 분석기에서 구성 드리프트 분석 및 기록 탭

이 탭에서는 사용자 지정 보안 정책에 적용한 변경 내용을 추적할 수 있습니다. 기본적으로 다음과 같은 정보가 표시됩니다.

- **마지막으로 수정한 날짜**
- **수정한 사용자**
- **설정 이름**
- **정책**
- **Type**

결과를 필터링하려면 **필터** 를 클릭합니다. 필터 **Filters** 플라이아웃이 나타나면 다음 필터에서 선택할 수 있습니다.

- **시작 시간** 및 **종료 시간(날짜)**
- **표준 보호** 또는 **엄격한 보호**

결과를 .csv 파일로 내보내려면 내보내기 를 **클릭합니다.**

![구성 분석기에서 구성 드리프트 분석 및 기록 보기](../../media/configuration-analyzer-configuration-drift-analysis-view.png)

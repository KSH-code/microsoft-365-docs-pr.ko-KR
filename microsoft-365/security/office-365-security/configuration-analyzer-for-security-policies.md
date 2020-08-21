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
description: 관리자는 구성 분석기를 사용하여 표준 보호 및 고급 보호 사전 요구 사항이 사전 설정된 보안 정책 아래에 있는 설정이 포함된 보안 정책을 찾아서 수정하는 방법에 대해 학습할 수 있습니다.
ms.openlocfilehash: 4515efcd73d40eae93523c6ef139553420e48677
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/20/2020
ms.locfileid: "46825776"
---
# <a name="configuration-analyzer-for-protection-policies-in-eop-and-office-365-atp"></a>EOP 및 Office 365 ATP의 보호 정책에 대한 구성 분석기

> [!NOTE]
> 이 항목에서 설명하는 기능은 미리 보기에 제공되고 모든 조직에서 사용할 수 없는 기능으로 변경될 수 있습니다.

보안 & 준수 센터의 구성 분석기는 미리 설정된 보안 정책의 표준 보호 및 Strict 보호 프로필 설정 아래에 있는 설정을 포함하는 보안 정책을 찾아 수정하는 중앙 [위치를 제공합니다.](preset-security-policies.md)

구성 분석기에서는 다음과 같은 유형의 정책이 분석됩니다.

- **EOP(Exchange Online Protection) 정책**: Exchange Online 사서함과 함께 Microsoft 365 조직과 Exchange Online 사서함이 없는 독립 실행형 EOP 조직이 포함됩니다.
  
  - [스팸 방지 정책.](configure-your-spam-filter-policies.md)
  - [맬웨어 방지 정책.](configure-anti-malware-policies.md)
  - [EOP 피싱 방지 정책.](set-up-anti-phishing-policies.md#spoof-settings)

- **Office 365 ADVANCED Threat Protection(ATP) 정책:** 여기에는 Microsoft 365 E5 또는 Office 365 ATP 추가 기능 구독을 사용하는 조직이 포함됩니다.

  - 다음을 포함하는 ATP 피싱 방지 정책:

    - [EOP피싱 방지 정책에서](set-up-anti-phishing-policies.md#spoof-settings) 사용할 수 있는 것과 동일한 스푸핑 설정
    - [가장 설정](set-up-anti-phishing-policies.md#impersonation-settings-in-atp-anti-phishing-policies)
    - [고급 피싱 임계값](set-up-anti-phishing-policies.md#advanced-phishing-thresholds-in-atp-anti-phishing-policies)

  - [안전한 링크 정책.](recommended-settings-for-eop-and-office365-atp.md#safe-links-policy-settings-in-custom-policies-for-specific-users)

  - [안전 첨부 파일 정책.](recommended-settings-for-eop-and-office365-atp.md#safe-attachments-policy-settings-in-custom-policies-for-specific-users)

**기준으로** **사용되는 표준 및 Strict** 정책 설정 값은 [EOP 및 Office 365 ATP 보안에 대한 권장 설정에 설명되어 있습니다.](recommended-settings-for-eop-and-office365-atp.md)

## <a name="what-do-you-need-to-know-before-you-begin"></a>시작하기 전에 알아야 할 내용은 무엇인가요?

- <https://protection.office.com/>에서 보안 및 준수 센터를 엽니다. 구성 분석기 페이지로 **직접 이동하려면** 다음을 사용합니다. <https://protection.office.com/configurationAnalyzer>

- Exchange Online PowerShell에 연결하려면 [Exchange Online PowerShell에 연결](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)을 참조하세요.

- 이 항목의 절차를 수행하려면 먼저 사용 권한을 할당받아야 합니다.

  - 구성 분석기를 **사용하여 보안** 정책을 업데이트하려면 다음 역할 그룹 중 하나의 구성원이어야 합니다.

    - [보안 및 준수 센터](permissions-in-the-security-and-compliance-center.md)의 **조직 관리** 또는 **보안 관리자**
    - [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups)의 **조직 관리** 및 **예방 조치 관리**

  - 구성 분석기에 대한 읽기 전용 액세스를 위해는 다음 역할 그룹 중 하나의 구성원이어야 합니다.

    - [보안 및 준수 센터](permissions-in-the-security-and-compliance-center.md)의 **보안 읽기**
    - [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups)의 **보기 전용 조직 관리**

## <a name="use-the-configuration-analyzer-in-the-security--compliance-center"></a>보안 및 준수 센터에서 구성 & 사용

보안 센터 & 보안 센터에서 위협 관리 **정책 구성** \> **분석기로** \> **이동합니다.**

![위협 관리 정책 페이지의 구성 분석기 \> 위산](../../media/configuration-analyzer-widget.png)

구성 분석기에는 다음과 같은 두 개의 기본 탭이 있습니다.

- **설정 및 권장 사항:** 표준 또는 Strict를 선택하여 해당 설정을 기존 보안 정책과 비교합니다. 결과에서 설정 값을 조정하여 표준 또는 Strict와 동일한 수준으로 만들 수 있습니다.

- **구성 참고: 이 보기를**사용하면 시간에 따라 구성 분석기 결과를 기반으로 정책에 적용한 변경 내용을 추적할 수 있습니다.

### <a name="setting-and-recommendations-tab-in-the-configuration-analyzer"></a>구성 분석기의 설정 및 권장 사항 탭

기본적으로 탭은 표준 보호 프로필과 비교시 열립니다. Strict 권장 사항 보기를 클릭하여 Strict Protection **프로필을 비교할 수 있습니다.** 다시 전환하려면 표준 **권장 사항 보기를 선택합니다.**

![구성 분석기의 설정 및 추천 보기](../../media/configuration-analyzer-settings-and-recommendations-view.png)

기본적으로 정책 **그룹/설정 이름 열에는** 다양한 유형의 보안 정책에 대한 축소된 보기와 해당 정책에서 개선이 필요한(있는 경우) 설정 수가 표시됩니다. 정책 의 유형은 다음과 같습니다.

- **스팸 방지**
- **피싱 방지**
- **맬웨어 방지**
- **ATP 안전한 첨부** 파일(구독에 ATP가 포함된 경우)
- **ATP 안전한 링크(구독에** ATP가 포함된 경우)

기본 보기에서는 모든 내용이 축소되어 있습니다. 각 정책 옆에 정책(수정할 수 있는 정책)의 비교 결과가 요약되어 있고 표준 또는 Strict Protection 프로필(수정할 수 않음)에 대한 해당 정책의 설정이 표시됩니다. 작업을 마표할 수 있습니다.

- **녹색:** 모든 기존 정책의 모든 설정은 비교하고 있는 보호 프로필만으로 안전합니다.
- **20월:** 기존 정책에 있는 적은 수의 설정이 비교중인 보호 프로필만으로 안전하지 않습니다.
- **Red:** 비교하고 있는 보호 프로필만으로는 기존 정책의 많은 설정이 안전하지 않습니다. 이러한 설정은 여러 정책이나 하나의 정책의 여러 설정일 수 있습니다.

즐겨 사용하는 비교의 경우 텍스트가 표시됩니다. 모든 설정이 **추천 항목을** \<**Standard** or **Strict**\> **따르는 경우** 그렇지 않으면 변경할 권장 설정 수를 볼 수 있습니다.

정책 **그룹/설정 이름을 확장하면**주의가 필요한 각 특정 정책의 모든 정책 및 연결된 설정이 표시됩니다. 또는 특정 유형의 정책을 확장하여 **Anti-spam**주의가 필요한 정책 유형에서 이러한 설정만 볼 수 있습니다.

비교에 개선의 권장 사항이 없을 경우(녹색) 정책을 확장해도 아무 것도 나타지 않습니다. 향상을 위한 권장 사항이 있다면(월리전 또는 빨간색) 주의가 필요한 설정이 표시되고 해당 정보가 다음 열에 표시됩니다.

- 사용자의 등록이 필요한 설정 이름입니다. 예를 들어 이전 스크린샷에서는 스팸 **방지 정책의 대량 전자** 메일 임계값입니다.

- **Policy:** 설정을 포함하는 영향을 받는 정책의 이름입니다.

- **적용된**위치: 영향을 받은 정책을 적용한 사용자 수.

- **현재 구성:** 설정의 현재 가치입니다.

- **마지막으로 수정한**날짜: 정책을 마지막으로 수정한 날짜입니다.

- **권장 사항:** 표준 또는 비트릭스 보호 프로필의 설정 값입니다. 보호 프로필의 권장 값과 일치하도록 정책의 설정 값을 변경하려면 **Adopt를 클릭합니다.** 변경이 성공하면 추천 메시지가 표시될 **것입니다. 추천 항목이 성공적으로 채택되었습니다.** 새로 **고침을** 클릭하여 권장 사항 수를 줄이고 결과에서 특정 설정/정책 행의 제거를 확인합니다.

### <a name="configuration-drift-analysis-and-history-tab-in-the-configuration-analyzer"></a>구성 분석기의 구성 요소 분석 및 기록 탭

이 탭에서는 보안 분석기의 정보를 기반으로 사용자 지정 보안 정책에 적용한 변경 내용을 추적할 수 있습니다. 기본적으로 다음과 같은 정보가 표시됩니다.

- **마지막으로 수정한 날짜**
- **수정한 날짜**
- **설정 이름**
- **정책**
- **Type**

결과를 필터링하려면 **필터**를 클릭합니다. 표시되는 **필터** 플라이아웃의 다음 필터에서 선택할 수 있습니다.

- **시작 시간** 및 **종료 시간(날짜)**
- **표준 보호** **또는 보안**

결과를 .csv 파일로 내보내려면 내보내기를 **클릭합니다.**

![구성 분석기의 구성 요소 분석 및 기록 보기](../../media/configuration-analyzer-configuration-drift-analysis-view.png)

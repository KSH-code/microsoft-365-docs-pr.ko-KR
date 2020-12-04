---
title: Walkthrough - Spoof intelligence insight
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 59a3ecaf-15ed-483b-b824-d98961d88bdd
ms.collection:
- M365-security-compliance
description: 관리자는 스푸핑 인텔리전스 정보의 작동 방식에 대해 학습할 수 있습니다. SPF, DKIM 또는 DMARC(전자 메일 인증 확인)를 통과하지 않는 도메인에서 조직에 합법적으로 전자 메일을 보내는 보낸 사람이 있는지 빠르게 확인할 수 있습니다.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 6f5ebd0fd42d17354eeb1e03c946ac5446c3667c
ms.sourcegitcommit: d81c7cea85af6ad5fef81d3c930514a51464368c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/04/2020
ms.locfileid: "49572744"
---
# <a name="walkthrough---spoof-intelligence-insight-in-microsoft-defender-for-office-365"></a>Walkthrough - Spoof intelligence insight in Microsoft Defender for Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


Office 365용 Defender가 있는 Microsoft 365 조직에서는 스푸핑 인텔리전스 인사이트를 사용하여 사용자가 적법하게 사용되지 않은 전자 메일을 보내는 보낸 사람(SPF, DKIM 또는 DMARC 검사를 통과하지 않는 도메인의 메시지)을 빠르게 확인할 수 있습니다.

알려진 보낸 사람이 알려진 위치에서 스푸핑된 메시지를 보낼 수 있도록 허용하면 가음성(나쁜 것으로 표시된 좋은 전자 메일)을 줄일 수 있습니다. 허용된 스푸핑된 보낸 사람 모니터링을 통해 안전하지 않은 메시지가 조직에 도착하지 못하도록 추가 보안 계층을 제공합니다.

보고서 및 인사이트에 대한 자세한 내용은 보안 및 규정 준수 센터의 보고서 [및 & 참조하세요.](reports-and-insights-in-security-and-compliance.md)

이 Walkthrough is one of several for the Security & Compliance Center. 보고서 및 인사이트를 진행하는 데 대한 자세한 내용은 관련 항목 섹션의 walkthroughs in the [walkthroughs in](#related-topics) the Related topics(보고서 및 인사이트)를 참조하세요.

## <a name="what-do-you-need-to-know-before-you-begin"></a>시작하기 전에 알아야 할 내용은 무엇인가요?

- <https://protection.office.com/>에서 보안 및 준수 센터를 엽니다. 보안 대시보드 페이지로 직접 **이동하기 위해** 다음을 <https://protection.office.com/searchandinvestigation/dashboard> 사용하세요.

  보안 및 준수 센터에서 두 개 이상의 대시보드에서 스푸핑 인텔리전스 & 수 있습니다. 보고 있는 대시보드에 관계없이 인사이트는 동일한 세부 정보를 제공하며 동일한 작업을 빠르게 수행할 수 있도록 합니다.

- 이 문서의 절차를 수행하려면 먼저 보안 및 준수 & 사용 권한을 할당해야 합니다.
  - **조직 관리**
  - **보안 관리자**
  - **보안 읽기**
  - **전역 읽기**

  **참고:** Microsoft 365 관리 센터에서 해당 Azure Active Directory 역할에 사용자를 추가하면 사용자에게 보안 _and_ & 준수 센터의 필요한 사용 권한과 Microsoft 365의 다른 기능에 대한 사용 권한이 부여됩니다. 자세한 내용은 [관리자 역할 정보](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles)를 참조하세요.

- Office 365용 Microsoft Defender에서 피싱 방지 정책에서 스푸핑 인텔리전스를 사용하도록 설정하고 사용하지 않도록 설정할 수 있습니다. 자세한 내용은 [Office 365용 Microsoft Defender에서](configure-atp-anti-phishing-policies.md)피싱 방지 정책 구성을 참조하세요.

- 스푸핑 인텔리전스를 사용하여 사용자에게 확인되지 않은 메시지를 보내는 보낸 사람 모니터링 및 관리는 [Microsoft 365에서](learn-about-spoof-intelligence.md)스푸핑 인텔리전스 구성을 참조합니다.

## <a name="open-the-spoof-intelligence-insight-in-the-security--compliance-center"></a>보안 및 준수 센터에서 스푸핑 인텔리전스 & 열기

1. 보안 및 & 센터에서 위협 관리 **대시보드로** \> **이동하세요.**

2. **Insights** 행에서 다음 항목 중 하나를 찾아 봐야 합니다.

   - **스푸핑** 인텔리전스 사용 : 이 정보의 이름은 지난 **30일** 동안 인증에 실패한 스푸핑된 도메인입니다. 이 옵션이 기본값입니다.
   - **스푸핑** 인텔리전스를 사용할 **Enable Spoof Protection** 수 없습니다. 스푸핑 방지 사용이라는 정보의 정보를 확인하여 이를 클릭하면 스푸핑 인텔리전스를 사용하도록 설정할 수 있습니다.

3. 대시보드의 인사이트에는 다음 정보가 표시됩니다.

   ![스푸핑 인텔리전스 정보의 스크린샷](../../media/28aeabac-c1a1-4d16-9fbe-14996f742a9a.png)

   이 인사이트에는 두 가지 모드가 있습니다.

   - **인사이트** 모드: 스푸핑 인텔리전스를 사용하도록 설정하면 지난 30일 동안의 스푸핑 인텔리전스 기능의 영향을 수신한 메시지 수가 표시됩니다.

   - **모드의 경우:** 스푸핑 인텔리전스를 사용하지 않도록 설정하면 *would* 지난 30일 동안의 스푸핑 인텔리전스 기능에 의해 영향을 하게 될 메시지 수가 정보를 보여줍니다.

   어느 경우든 인사이트에 표시되는 스푸핑된 도메인은 의심스러운 **Suspicious domain pairs** 도메인 쌍과 의심하지 않는 도메인 쌍의 두 범주로 구분됩니다. **Non-suspicious domain pairs** 이러한 범주는 검토할 수 있는 세 가지 다른 버킷으로 세분화됩니다.

   도메인 **쌍은** 보내는 주소와 보내는 인프라의 조합입니다.

   - 보낸 사람 주소는 전자 메일 클라이언트의 보낸 사람 상자에 표시되는 보낸 사람 전자 메일 주소입니다. 이 주소를 주소라고도 `5322.From` 합니다.

   - 보내는 인프라 또는 보낸 사람이 보내는 IP 주소의 역방향 DNS PTR 레코드(PTR 레코드)의 조직 도메인입니다. 보내는 IP 주소에 PTR 레코드가 없는 경우 보낸 사람이 보내는 IP와 CIDR(/24)의 255.255.255.0 서브넷 마스크로 식별됩니다. 예를 들어 IP 주소가 192.168.100.100이면 보낸 사람 전체 IP 주소는 192.168.100.100/24입니다.

   **의심스러운** 도메인 쌍은 다음과 같습니다.

   - **높은 신뢰도** 스푸핑: 기록 전송 패턴 및 도메인의 신뢰도 점수를 기반으로 도메인이 스푸핑 중일 수 있으며 이러한 도메인의 메시지가 악의적일 가능성이 높습니다.

   - **보통** 신뢰도 스푸핑: 기록 전송 패턴 및 도메인의 신뢰도 점수를 기반으로 도메인이 스푸핑 중일 수 있으며 이러한 도메인에서 보낸 메시지가 합법적이라고 확신합니다. 가음성은 높은 신뢰도 스푸핑보다 이 범주에서 더 높습니다.

   - **의심스러운** 도메인 쌍(스푸핑 **포함):** 도메인이 명시적 전자 메일 인증 검사 [SPF,](how-office-365-uses-spf-to-prevent-spoofing.md) [DKIM](use-dkim-to-validate-outbound-email.md)및 [DMARC를](use-dmarc-to-validate-email.md)확인하지 못했습니다. 그러나 도메인은 암시적 전자 메일 인증 확인(복합 인증)을[통과했습니다.](email-validation-and-authentication.md#composite-authentication) 따라서 메시지에 대한 스푸핑 방지 작업이 수행하지 않습니다.

### <a name="view-detailed-information-about-suspicious-domain-pairs-from-the-spoof-intelligence-insight"></a>스푸핑 인텔리전스 정보에서 의심스러운 도메인 쌍에 대한 자세한 정보 보기

1. 스푸핑 인텔리전스 인사이트를 클릭하고 도메인 쌍(높음, 보통 또는 고가의 도메인 쌍)을 클릭합니다.

   **스푸핑 인텔리전스 정보 페이지가** 나타납니다. 이 페이지에는 조직에 확인되지 않은 전자 메일을 보내는 보낸 사람 목록이 표시됩니다.

   이 정보는 스푸핑된 메시지에 권한이 부여가 되거나 추가 조치를 취해야 하는지 여부를 결정하는 데 도움이 됩니다.

   메시지 수, 스푸핑이 마지막으로 검색된 날짜 등별로 정보를 정렬할 수 있습니다.

2. 테이블에서 항목을 선택하여 도메인 쌍에 대한 다양한 정보가 포함된 세부 정보 창을 열 수 있습니다. 이 정보에는 다음이 포함됩니다.
   - 이 경우 이유가 있습니다.
   - 해야 할 일.
   - 도메인 요약입니다.
   - 보낸 사람에 대한 WhoIs 데이터입니다.
   - 동일한 보낸 사람으로부터 테넌트에 비슷한 메시지가 표시됩니다.

   여기에서 **AllowedToSpoof** 수신 허용 - 보낸 사람 목록에서 도메인 쌍을 추가하거나 제거할 수도 있습니다.

   ![스푸핑 인텔리전스 정보 세부 정보 창의 도메인 스크린샷](../../media/03ad3e6e-2010-4e8e-b92e-accc8bbebb79.png)

### <a name="add-or-remove-a-domain-from-the-allowedtospoof-list"></a>AllowedToSpoof 목록에서 도메인 추가 또는 제거

도메인 쌍에 대한 스푸핑 인텔리전스 정보의 세부 정보 창에서 AllowedToSpoof(수신 허용 - 보낸 사람) 목록에서 도메인을 추가하거나 제거합니다. 토글을 그에 따라 설정하기만 합니다.

도메인 쌍을 허용하면 스푸핑된 도메인과 보내는 인프라의 *조합만* 허용됩니다. 모든 원본에서 스푸핑된 도메인의 전자 메일을 허용하지 않으며 도메인에 대한 보내는 인프라의 전자 메일을 허용하지 않습니다.

예를 들어 다음 도메인 쌍이 조직에 스푸핑된 메시지를 보낼 수 있도록 허용합니다.

- *스푸핑된 도메인*: gmail.com"
- *전송 인프라:* `tms.mx.com`

해당 도메인 쌍의 전자 메일만 스푸핑할 수 있습니다. 스푸핑을 시도하는 gmail.com 허용되지 않습니다. 스푸핑 인텔리전스를 통해 tms.mx.com 도메인의 메시지를 검사합니다.

## <a name="related-topics"></a>관련 항목

[Microsoft 365의 스푸핑 방지 보호 기능](anti-spoofing-protection.md)

---
title: 연습-스푸핑 인텔리전스 통찰력
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
description: 관리자는 스푸핑 인텔리전스 통찰력의 작동 방식을 확인할 수 있습니다. 전자 메일 인증 검사 (SPF, DKIM 또는 DMARC)를 통과 하지 않는 도메인에서 조직으로 합법적으로 전자 메일을 보내는 보낸 사람을 빠르게 확인할 수 있습니다.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 89a31c6df7c9b6e02f52ea414ceb6334427feab1
ms.sourcegitcommit: d7975c391e03eeb96e29c1d02e77d2a1433ea67c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/05/2020
ms.locfileid: "48920481"
---
# <a name="walkthrough---spoof-intelligence-insight-in-microsoft-defender-for-office-365"></a>연습-Microsoft Defender for Office 365의 스푸핑 인텔리전스 정보

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


Office 365 용 Defender가 포함 된 Microsoft 365 조 직에서 스푸핑 인텔리전스 정보를 사용 하 여 인증 되지 않은 전자 메일을 합법적으로 전송 하는 보낸 사람 (SPF, DKIM 또는 DMARC 검사를 통과 하지 않는 도메인의 메시지)을 빠르게 확인할 수 있습니다.

알려진 보낸 사람이 알려진 위치에서 스푸핑된 메시지를 전송 하도록 허용 하 여 가양성 (잘못 된 것으로 표시 된 전자 메일 양호)을 줄일 수 있습니다. 허용 된 스푸핑된 보낸 사람을 모니터링 하면 안전 하지 않은 메시지가 조직에 도착 하지 못하도록 방지 하는 추가 보안 계층을 제공 합니다.

보고서 및 insights에 대 한 자세한 내용은 [Security & 준수 센터의 reports and insights](reports-and-insights-in-security-and-compliance.md)를 참조 하십시오.

이 연습은 보안 & 준수 센터에 대 한 몇 가지 방법 중 하나입니다. 보고서 및 insights를 탐색 하는 방법에 대 한 자세한 내용은 [관련 항목](#related-topics) 섹션의 연습을 참조 하십시오.

## <a name="what-do-you-need-to-know-before-you-begin"></a>시작하기 전에 알아야 할 내용은 무엇인가요?

- <https://protection.office.com/>에서 보안 및 준수 센터를 엽니다. **보안 대시보드** 페이지로 바로 이동 하려면을 사용 <https://protection.office.com/searchandinvestigation/dashboard> 합니다.

  보안 & 준수 센터에서 둘 이상의 대시보드에서 스푸핑 인텔리전스 정보를 볼 수 있습니다. 현재 보고 있는 대시보드에 상관 없이, 통찰력은 동일한 세부 정보를 제공 하며 동일한 작업을 빠르게 수행할 수 있도록 합니다.

- 이 항목의 절차를 수행 하려면 먼저 사용 권한을 할당 받아야 합니다. 스푸핑 인텔리전스 이해를 사용 하려면 다음 역할 그룹 중 하나의 구성원 이어야 합니다.

  - [보안 및 준수 센터](permissions-in-the-security-and-compliance-center.md)의 **조직 관리** 또는 **보안 관리자**
  - [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups)의 **조직 관리** 및 **예방 조치 관리**
  - [보안 및 준수 센터](permissions-in-the-security-and-compliance-center.md)의 **보안 읽기**
  - [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups)의 **보기 전용 조직 관리**

- Office 365 용 Microsoft Defender의 피싱 방지 정책에서 스푸핑 인텔리전스를 사용 하도록 설정 하 고 사용 하지 않도록 설정 합니다. 자세한 내용은 [Office 용 Microsoft Defender 365에서 피싱 방지 정책 구성을](configure-atp-anti-phishing-policies.md)참조 하세요.

- 스푸핑 인텔리전스를 사용 하 여 인증 되지 않은 메시지를 보내는 보낸 사람을 모니터링 하 고 관리 하려면 [Microsoft 365에서 스푸핑 인텔리전스를 구성](learn-about-spoof-intelligence.md)합니다 .를 참조 하세요.

## <a name="open-the-spoof-intelligence-insight-in-the-security--compliance-center"></a>보안 & 준수 센터에서 스푸핑 인텔리전스 통찰력을 엽니다.

1. 보안 & 준수 센터에서 **위협 관리** \> **대시보드로 이동 합니다.**

2. **Insights** 행에서 다음 항목 중 하나를 찾습니다.

   - **스푸핑 인텔리전스를 사용 하도록 설정** 된 경우: 위장 된 도메인 이라는 것은 **최근 30 일의 인증에 실패 한** 것입니다. 이 옵션이 기본값입니다.
   - **스푸핑 지능 사용 안 함** : 명명 된 **스푸핑 보호 사용** 을 선택 하 고이를 클릭 하면 스푸핑 인텔리전스를 사용 하도록 설정할 수 있습니다.

3. 대시보드에 대 한 통찰력은 다음과 같은 정보를 보여 줍니다.

   ![스푸핑 인텔리전스 통찰력 스크린샷](../../media/28aeabac-c1a1-4d16-9fbe-14996f742a9a.png)

   이 통찰력에는 두 가지 모드가 있습니다.

   - **통찰력 모드** : 스푸핑 인텔리전스가 사용 하도록 설정 된 경우이 통찰력은 지난 30 일 동안 스푸핑 인텔리전스 기능으로 인해 영향을 받는 메시지 수를 보여 줍니다.

   - **If mode** : 스푸핑 인텔리전스를 사용 하지 않도록 설정 하면 지난 30 일 동안 스푸핑 인텔리전스 기능으로 인해 *영향을 받는 메시지 수* 를 확인할 수 있습니다.

   어느 방법을 사용 하 든, 파악에 표시 되는 스푸핑된 도메인은 **의심 스러운 도메인 쌍** 및 **의심 되지 않는 도메인 쌍** 으로 구분 됩니다. 이러한 범주는 검토할 세 가지 다른 버킷으로 세분화 됩니다.

   **도메인 쌍** 은 보낸 사람 주소와 보내는 인프라의 조합입니다.

   - 보낸 사람 주소는 전자 메일 클라이언트의 시작 상자에 표시 되는 보낸 사람의 전자 메일 주소입니다. 이 주소는 `5322.From` 주소 라고도 합니다.

   - 보내는 인프라 또는 보낸 사람은 보내는 IP 주소의 역방향 DNS 조회 (PTR 레코드)에 대 한 조직 도메인입니다. 보내는 IP 주소에 PTR 레코드가 없으면 보낸 사람은 255.255.255.0 서브넷 마스크가 CIDR 표기법 (/24) 인 보내는 IP로 식별 됩니다. 예를 들어 IP 주소가 192.168.100.100 이면 보낸 사람의 전체 IP 주소는 192.168.100.100/24가 됩니다.

   **의심 스러운 도메인 쌍** 은 다음과 같습니다.

   - **신뢰도가 높은 스푸핑** : 전송 패턴 및 도메인의 신뢰도 점수를 기반으로 하 여 도메인은 위조 되 고 이러한 도메인의 메시지가 악성이 될 가능성이 높습니다.

   - **일반 신뢰도 스푸핑** : 도메인의 과거 및 신뢰도 점수를 기반으로 하 여 도메인은 스푸핑 되 고 이러한 도메인에서 전송 된 메시지가 합법적 이라는 것을 알 수 있습니다. 가양성은 높은 신뢰도 위장 보다이 범주에 해당 합니다.

   - **의심 스러운 도메인 쌍** (자동 **복구 스푸핑** 포함): 도메인에서 명시적 전자 메일 인증 검사 [SPF](how-office-365-uses-spf-to-prevent-spoofing.md), [dkim](use-dkim-to-validate-outbound-email.md)및 [DMARC](use-dmarc-to-validate-email.md))를 실패 했습니다. 그러나 도메인은 암시적 전자 메일 인증 검사 ([복합 인증](email-validation-and-authentication.md#composite-authentication))를 통과 했습니다. 따라서 메시지에 대해 스푸핑 방지 동작이 수행 되지 않습니다.

### <a name="view-detailed-information-about-suspicious-domain-pairs-from-the-spoof-intelligence-insight"></a>스푸핑 인텔리전스 통찰력에서 의심 스러운 도메인 쌍에 대 한 세부 정보 보기

1. 스푸핑 인텔리전스 이해에서 도메인 쌍 (높음, 중간 또는 자동 복구)을 클릭 합니다.

   **스푸핑 인텔리전스** 정보 페이지가 표시 됩니다. 이 페이지에는 조직에 인증 되지 않은 전자 메일을 보내는 보낸 사람 목록이 표시 됩니다.

   이 정보는 스푸핑된 메시지에 대 한 권한이 부여 되었는지 또는 추가 작업을 수행 해야 하는지 여부를 확인 하는 데 도움이 됩니다.

   메시지 수, 스푸핑이 마지막으로 검색 된 날짜 등을 기준으로 정보를 정렬할 수 있습니다.

2. 테이블에서 항목을 선택 하 여 도메인 쌍에 대 한 다양 한 정보가 포함 된 세부 정보 창을 엽니다. 정보에는 다음이 포함 됩니다.
   - 이를 파악 한 이유입니다.
   - 수행 해야 하는 작업
   - 도메인 요약
   - 보낸 사람에 대 한 데이터를 WhoIs.
   - 동일한 보낸 사람의 테 넌 트에서 살펴본 유사한 메시지

   여기에서 **Allowedtospoof** 수신 허용-보낸 사람 목록에서 도메인 쌍을 추가 하거나 제거 하도록 선택할 수도 있습니다.

   ![스푸핑 인텔리전스 통찰력 세부 정보 창에 있는 도메인 스크린샷](../../media/03ad3e6e-2010-4e8e-b92e-accc8bbebb79.png)

### <a name="add-or-remove-a-domain-from-the-allowedtospoof-list"></a>AllowedToSpoof 목록에서 도메인 추가 또는 제거

도메인 쌍에 대 한 스푸핑 인텔리전스 통찰력의 세부 정보 창에서 AllowedToSpoof (수신 허용-보낸 사람) 목록에 도메인을 추가 하거나 제거 합니다. 이에 따라 토글을 설정 하기만 하면 됩니다.

도메인 쌍을 허용 하면 위장 *된 도메인과 보내는* 인프라를 함께 사용할 수 있습니다. 원본에서 위장 된 도메인의 전자 메일을 허용 하지 않으며 모든 도메인에 대해 보내는 인프라에서 전자 메일을 허용 하지 않습니다.

예를 들어 다음 도메인 쌍이 스푸핑된 메시지를 조직에 보낼 수 있도록 허용 합니다.

- *스푸핑된 도메인* : gmail.com "
- *보내는 인프라* `tms.mx.com` :

해당 도메인 쌍의 전자 메일만 스푸핑 될 수 있습니다. Gmail.com을 스푸핑할 다른 보낸 사람은 허용 되지 않습니다. Tms.mx.com의 다른 도메인에 있는 메시지는 스푸핑 인텔리전스를 통해 확인 됩니다.

## <a name="related-topics"></a>관련 항목

[Microsoft 365의 스푸핑 방지 보호 기능](anti-spoofing-protection.md)

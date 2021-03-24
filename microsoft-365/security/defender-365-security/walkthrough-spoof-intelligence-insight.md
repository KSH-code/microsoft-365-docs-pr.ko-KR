---
title: 연습 - 스푸핑 인텔리전스 인사이트
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: overview
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 59a3ecaf-15ed-483b-b824-d98961d88bdd
ms.collection:
- M365-security-compliance
description: 관리자는 스푸핑 인텔리전스 정보의 작동 방법을 배울 수 있습니다. SPF, DKIM 또는 DMARC(전자 메일 인증 확인)를 통과하지 않는 도메인에서 조직에 합법적으로 전자 메일을 보내는 보낸 사람이 있는지 빠르게 확인할 수 있습니다.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: d2b48b8540fb71404a0636120a5884d381b08cd1
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51070935"
---
# <a name="walkthrough---spoof-intelligence-insight-in-microsoft-defender-for-office-365"></a>Walkthrough - Spoof intelligence insight in Microsoft Defender for Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**적용 대상**
- [Office 365용 Microsoft Defender 플랜 1 및 플랜 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Office 365용 Defender가 있는 Microsoft 365 조직에서는 스푸핑 인텔리전스 인사이트를 사용하여 사용자가 합법적으로 확인되지 않은 전자 메일을 보내는 외부 보낸 사람(SPF, DKIM 또는 DMARC 검사를 통과하지 않는 도메인의 메시지)을 빠르게 확인할 수 있습니다.

알려진 외부 보낸 사람이 알려진 위치에서 스푸핑된 메시지를 보낼 수 있도록 허용하면 가음성(나쁜 것으로 표시된 좋은 전자 메일)을 줄일 수 있습니다. 허용된 스푸핑된 보낸 사람 모니터링을 통해 안전하지 않은 메시지가 조직에 도착하지 않도록 추가 보안 계층을 제공합니다.

보고서 및 인사이트에 대한 자세한 내용은 보안 및 준수 센터의 보고서 [및 & 참조하세요.](reports-and-insights-in-security-and-compliance.md)

이 Walkthrough is one of several for the Security & Compliance Center. 보고서 및 인사이트를 진행하는 데 대한 자세한 내용은 관련 항목 섹션의 Walkthroughs를 [참조하십시오.](#related-topics)

> [!NOTE]
> 스푸핑 인텔리전스 인사이트는 지난 7일간의 데이터를 보여줍니다. Exchange Online PowerShell의 [스푸핑](learn-about-spoof-intelligence.md) 인텔리전스 정책 및 해당 [Get-PhishFilterPolicy](/powershell/module/exchange/get-phishfilterpolicy) cmdlet은 지난 30일간의 데이터를 보여줍니다. [Get-SpoofMailReport는](/powershell/module/exchange/get-spoofmailreport) 최대 90일간의 데이터를 보여줍니다.

## <a name="what-do-you-need-to-know-before-you-begin"></a>시작하기 전에 알아야 할 내용은 무엇인가요?

- <https://protection.office.com/>에서 보안 및 준수 센터를 엽니다. 보안 대시보드 페이지로 직접 **이동하기 위해** 를 <https://protection.office.com/searchandinvestigation/dashboard> 사용하세요.

  보안 및 준수 센터의 두 개 이상의 대시보드에서 스푸핑 인텔리전스 & 있습니다. 보고 있는 대시보드에 관계없이 인사이트는 동일한 세부 정보를 제공하며 동일한 작업을 빠르게 수행할 수 있도록 합니다.

- 이 문서의 절차를 수행하려면 먼저 보안 및 준수 센터에서 사용 권한을 받아야 합니다.
  - **조직 관리**
  - **보안 관리자**
  - **보안 읽기**
  - **전역 읽기**

  자세한 내용은 [보안 및 준수 센터의 사용 권한](permissions-in-the-security-and-compliance-center.md)을 참조하세요.

  **참고:** Microsoft 365 관리 센터에서 해당 Azure Active Directory 역할에 사용자를 추가하면 사용자에게 보안  및 준수 센터에서 필요한 사용 & 권한과 Microsoft 365의 다른 기능에 대한 사용 권한이 부여됩니다. 자세한 내용은 [관리자 역할 정보](../../admin/add-users/about-admin-roles.md)를 참조하세요.

- Office 365용 Microsoft Defender의 피싱 방지 정책에서 스푸핑 인텔리전스를 사용하도록 설정하고 사용하지 않도록 설정할 수 있습니다. 스푸핑 인텔리전스가 기본적으로 사용됩니다. 자세한 내용은 [Office 365용 Microsoft Defender에서](configure-atp-anti-phishing-policies.md)피싱 방지 정책 구성을 참조하세요.

- 스푸핑 인텔리전스를 사용하여 사용자에게 확인되지 않은 메시지를 보내는 보낸 사람 모니터링 및 관리하기 위해 [Microsoft 365에서](learn-about-spoof-intelligence.md)스푸핑 인텔리전스 구성을 참조합니다.

## <a name="open-the-spoof-intelligence-insight-in-the-security--compliance-center"></a>보안 및 준수 센터에서 스푸핑 인텔리전스 & 열기

1. 보안 및 & 센터에서 위협 관리 **대시보드로** \> **이동하세요.**

2. **Insights 행에서** 다음 항목 중 하나를 찾아야 합니다.

   - **지난 7일** 동안의 스푸핑된 도메인 가능성 : 이 인사이트는 스푸핑 인텔리전스가 활성화되어 있는 것으로 나타냅니다(기본적으로 사용 가능).
   - **스푸핑** 보호 사용 : 이 인사이트는 스푸핑 인텔리전스가 사용되지 않도록 설정되어 있으며, 정보를 클릭하면 스푸핑 인텔리전스를 사용하도록 설정할 수 있습니다.

3. 대시보드의 인사이트에는 다음 정보가 표시됩니다.

   ![스푸핑 인텔리전스 정보의 스크린샷](../../media/28aeabac-c1a1-4d16-9fbe-14996f742a9a.png)

   이 인사이트에는 두 가지 모드가 있습니다.

   - **인사이트** 모드: 스푸핑 인텔리전스를 사용하도록 설정하면 지난 7일 동안의 스푸핑 인텔리전스 기능에 영향을 미치게 된 메시지 수가 표시됩니다.
   - **모드인 경우:** 스푸핑 인텔리전스를 사용하지 않도록 설정하면  지난 7일 동안의 스푸핑 인텔리전스 기능에 의해 영향을 났을 메시지 수가 인사이트에 표시됩니다.

   어느 경우든 인사이트에 표시되는 스푸핑된 도메인은 의심스러운  도메인과 의심하지 않는 도메인의 두 가지 범주로 **구분됩니다.**

   - **의심스러운 도메인은 다음과** 같습니다.

     - 높은 신뢰도 스푸핑: 기록 전송 패턴 및 도메인의 신뢰도 점수에 따라 도메인이 스푸핑하고 이러한 도메인의 메시지가 악의적일 가능성이 높습니다.

     - 보통 신뢰도 스푸핑: 이전 전송 패턴과 도메인의 신뢰도 점수를 기반으로 도메인이 스푸핑하고 이러한 도메인에서 보낸 메시지는 합법적이라고 신뢰합니다. 가음성은 높은 신뢰도 스푸핑보다 이 범주에서 더 높습니다.

   **의심스러운** 도메인이 아닌 도메인: 도메인이 명시적 전자 메일 인증 검사 [SPF,](how-office-365-uses-spf-to-prevent-spoofing.md) [DKIM](use-dkim-to-validate-outbound-email.md)및 [DMARC를](use-dmarc-to-validate-email.md)확인하지 못했습니다. 그러나 도메인이 암시적 전자 메일 인증[확인(복합 인증)을 통과했습니다.](email-validation-and-authentication.md#composite-authentication) 따라서 메시지에 대한 스푸핑 방지 작업이 수행하지 않습니다.

### <a name="view-detailed-information-about-suspicious-domains-from-the-spoof-intelligence-insight"></a>스푸핑 인텔리전스 인사이트에서 의심스러운 도메인에 대한 자세한 정보 보기

1. 스푸핑 인텔리전스  인사이트에서 의심스러운  도메인 또는 의심스러운 도메인을 클릭하여 스푸핑 인텔리전스 인사이트 **페이지로** 이동합니다. **스푸핑 인텔리전스 인사이트 페이지에는** 다음 정보가 포함되어 있습니다.

   - **스푸핑된 도메인**: 전자 메일 클라이언트의 시작 상자에  표시되는 스푸핑된 사용자의 도메인입니다. 이 주소를 `5322.From` 주소라고도 합니다.
   - **인프라:** 보내는 _인프라라고도 합니다._ 원본 전자 메일 서버의 IP 주소에 대한 역방향 DNS 검색(PTR 레코드)에 있는 도메인입니다. 원본 IP 주소에 PTR 레코드가 없는 경우 보내는 인프라는 \<source IP\> /24(예: 192.168.100.100/24)로 식별됩니다.
   - **메시지 수:** 지난 7일 이내에 지정된 스푸핑된 도메인을 포함하는 조직으로 보내는 인프라에서 조직으로 보내는 메시지 수입니다.
   - **마지막으로 확인한** 날짜: 스푸핑된 도메인이 포함된 보내는 인프라에서 메시지를 받은 마지막 날짜입니다.
   - **스푸핑 유형**: 이 값은 **External입니다.**
   - **스푸핑이 허용되는 경우:** 여기에 있는 값은 다음과 같습니다.
     - **예:** 스푸핑된 사용자의 도메인과 보내는 인프라의 조합에서 보낸 메시지는 허용될 수 있으며 스푸핑된 전자 메일로 처리되지 않습니다.
     - **No:** 스푸핑된 사용자의 도메인과 보내는 인프라의 조합에서 보낸 메시지가 스푸핑된 것으로 표시됩니다. 이 작업은 기본 피싱 방지 정책 또는 사용자 지정 피싱 방지 정책(기본값은 정크 메일 폴더로 메시지 이동)에 의해 **제어됩니다.**

     자세한 내용은 [Office 365용 Microsoft Defender에서](configure-atp-anti-phishing-policies.md)피싱 방지 정책 구성을 참조하세요.

2. 플라이아웃에서 도메인/보내는 인프라 쌍에 대한 세부 정보를 확인하려면 목록에서 항목을 선택합니다. 이 정보에는 다음이 포함됩니다.
   - 이 경우 이유가 있습니다.
   - 해야 할 일.
   - 도메인 요약입니다.
   - 보낸 사람에 대한 데이터입니다.
   - 동일한 보낸 사람으로부터 테넌트에 비슷한 메시지가 표시됩니다.

   여기에서 허용된 보낸 사람 스푸핑 허용 목록에서 도메인/보내는 인프라 쌍을 추가하거나 제거하도록 선택할 수도 있습니다.  그에 따라 토글을 설정하기만 합니다.

   ![스푸핑 인텔리전스 인사이트 세부 정보 창의 도메인 스크린샷](../../media/03ad3e6e-2010-4e8e-b92e-accc8bbebb79.png)

### <a name="adding-a-domain-to-the-allowed-to-spoof-list"></a>스푸핑 허용 목록에 도메인 추가

스푸핑 인텔리전스 인사이트에서 허용된 스푸핑 목록에 도메인을 추가하면 스푸핑된 도메인과 보내는 인프라의 조합만 허용됩니다.  모든 원본에서 스푸핑된 도메인의 전자 메일을 허용하지 않으며 도메인에 대한 보내는 인프라의 전자 메일을 허용하지 않습니다.

예를 들어 다음 도메인을 스푸핑 허용 목록에 허용합니다.

- **도메인**: gmail.com
- **인프라:** tms.mx.com

해당 도메인/보내는 인프라 쌍의 전자 메일만 스푸핑할 수 있습니다. 스푸핑을 시도하는 gmail.com 허용되지 않습니다. 다른 도메인의 메시지는 tms.mx.com 인텔리전스를 통해 확인됩니다.

## <a name="related-topics"></a>관련 항목

[Microsoft 365의 스푸핑 방지 보호 기능](anti-spoofing-protection.md)
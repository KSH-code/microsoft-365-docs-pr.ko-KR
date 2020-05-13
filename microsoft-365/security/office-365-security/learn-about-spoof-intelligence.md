---
title: 스푸핑 인텔리전스 구성
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 978c3173-3578-4286-aaf4-8a10951978bf
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: 관리자는 EOP (Exchange Online Protection)의 스푸핑 인텔리전스에 대해 자세히 알아보고, 특정 스푸핑된 보낸 사람을 허용 하거나 차단할 수 있습니다.
ms.openlocfilehash: 607c11d82a145828af736d8d1ecab1dff367f94d
ms.sourcegitcommit: 93c0088d272cd45f1632a1dcaf04159f234abccd
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/12/2020
ms.locfileid: "44206643"
---
# <a name="configure-spoof-intelligence-in-eop"></a>EOP에서 스푸핑 인텔리전스 구성

Exchange online 사서함이 없는 Microsoft 365 조직에서 사서함이 있는 EOP (exchange online Protection) 조직에서 인바운드 전자 메일 메시지는 EOP의 2018에서 자동으로 스푸핑 으로부터 보호 됩니다. EOP에서는 피싱에 대 한 조직의 전반적인 방어 과정에서 스푸핑 인텔리전스를 사용 합니다. 자세한 내용은 [EOP의 스푸핑 방지 보호](anti-spoofing-protection.md)를 참조 하세요.

보낸 사람이 전자 메일 주소를 위장 하면 조직의 도메인 중 하나의 사용자 또는 조직에 전자 메일을 보내는 외부 도메인의 사용자로 표시 됩니다. 스팸 또는 피싱 전자 메일을 보내도록 보낸 사람을 위장 하는 공격자는 차단 해야 합니다. 그러나 합법적인 보낸 사람이 스푸핑 되는 시나리오가 있습니다. 예시:

- 내부 도메인 스푸핑에 대 한 합법적인 시나리오:

  - 타사 보낸 사람 도메인을 사용 하 여 회사 설문을 위해 자신의 직원에 게 대량 메일을 보냅니다.

  - 외부 회사에서는 사용자를 대신 하 여 광고 또는 제품 업데이트를 생성 하 고 보냅니다.

  - 도우미는 정기적으로 조직 내의 다른 사용자에 게 전자 메일을 보내야 합니다.

  - 내부 응용 프로그램은 전자 메일 알림을 보냅니다.

- 외부 도메인 스푸핑에 대 한 합법적인 시나리오:

  - 보낸 사람이 메일링 리스트 라고도 하는 메일 그룹에 있고, 메일링 리스트에서 원본 보낸 사람 으로부터 메일 그룹의 모든 참가자에 게 전자 메일이 릴레이 됩니다.

  - 외부 회사는 다른 회사를 대신 하 여 전자 메일을 전송 합니다 (예: 자동화 된 보고서 또는 a-a-서비스 회사).

스푸핑 인텔리전스 및 특히 기본 (및 전용) 스푸핑 인텔리전스 정책에서는 합법적인 보낸 사람이 보낸 스푸핑된 전자 메일이 Microsoft 365 또는 외부 전자 메일 시스템의 스팸 필터에서 발견 되지 않도록 하 고 사용자를 스팸 또는 피싱 공격 으로부터 보호 하는 데 도움을 줍니다.

보안 & 준수 센터에서 또는 PowerShell (exchange online 사서함이 없는 조직에 대 한 사서함이 있는 Microsoft 365 조 직의 경우에는 exchange online의 사용 EOP powershell)에서 스푸핑 인텔리전스를 관리할 수 있습니다.

## <a name="what-do-you-need-to-know-before-you-begin"></a>시작하기 전에 알아야 할 내용은 무엇인가요?

- <https://protection.office.com/>에서 보안 및 준수 센터를 엽니다. **스팸 방지 설정** 페이지로 바로 이동하려면 <https://protection.office.com/antispam>을 사용하세요. **피싱 방지** 페이지로 바로 이동 하려면을 사용 <https://protection.office.com/antiphishing> 합니다.

- Exchange Online PowerShell에 연결하려면 [Exchange Online PowerShell에 연결하기](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell)를 참조하세요. Exchange Online Protection PowerShell에 연결하려면 [Exchange Online Protection PowerShell에 연결하기](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell)를 참조하세요.

- 이 절차를 수행하려면 먼저 사용 권한을 할당 받아야 합니다. 스푸핑 인텔리전스 정책을 수정 하거나 스푸핑 인텔리전스를 사용 하거나 사용 하지 않도록 설정 하려면 **조직 관리** 또는 **보안 관리자** 역할 그룹의 구성원 이어야 합니다. 스푸핑 인텔리전스 정책에 대 한 읽기 전용 액세스를 위해서는 **보안 독자** 역할 그룹의 구성원 이어야 합니다. 보안 및 규정 준수 센터의 역할 그룹에 대한 자세한 내용은 [보안 및 규정 준수 센터의 사용 권한](permissions-in-the-security-and-compliance-center.md)을 참조하세요.

- 스푸핑 인텔리전스에 대 한 권장 설정에 대해서는 [기본 피싱 방지 정책 설정을 EOP](recommended-settings-for-eop-and-office365-atp.md#eop-default-anti-phishing-policy-settings).

## <a name="use-the-security--compliance-center-to-manage-spoofed-senders"></a>보안 & 준수 센터를 사용 하 여 스푸핑된 보낸 사람 관리

> [!NOTE]
> Microsoft 365 Enterprise E5 구독이 있거나 Office 365 Advanced Threat Protection (Office 365 ATP) 추가 기능을 별도로 구매한 경우 [스푸핑 인텔리전스](walkthrough-spoof-intelligence-insight.md)정보를 통해 도메인을 위장 하는 보낸 사람을 관리할 수도 있습니다.

1. 보안 및 준수 센터에서 **위협 관리** \> **정책** \> **스팸 방지**로 이동합니다.

2. **스팸 방지 설정** 페이지에서 ![ 확장 아이콘 ](../../media/scc-expand-icon.png) 을 클릭 하 여 **스푸핑 인텔리전스 정책을**확장 합니다.

   ![스푸핑 인텔리전스 정책 선택](../../media/anti-spam-settings-spoof-intelligence-policy.png)

3. 다음 중 하나를 선택 합니다.

   - **새 보낸 사람 검토**
   - **이미 검토 한 보낸 사람 표시**

4. 이러한 보낸 사람이 사용자에 게 표시 되는 플라이 아웃 **을 스푸핑할 수 있는지 결정** 에서 다음 탭 중 하나를 선택 합니다.

   - **도메인**: 내부 도메인의 사용자를 보낸 사람에 게 위장 합니다.
   - **외부 도메인**: 외부 도메인의 사용자를 보낸 사람에 게 위장 합니다.

5. ![ ](../../media/scc-expand-icon.png) **스푸핑 허용?** 열에서 확장 아이콘을 클릭 합니다. 스푸핑된 보낸 사람을 허용 하려면 **예** 를 선택 하 고, 메시지를 스푸핑된로 표시 하려면 **아니요** 를 선택 합니다. 이 작업은 기본 피싱 방지 정책 또는 사용자 지정 ATP 피싱 방지 정책 (기본값은 **정크 메일 폴더로 메시지 이동**)에 의해 제어 됩니다. 자세한 내용은 [피싱 방지 정책에서 스푸핑 설정을](set-up-anti-phishing-policies.md#spoof-settings)참조 하십시오.

   ![스푸핑된 보낸 사람 플라이 아웃 및 보낸 사람이 스푸핑할 수 있는지 여부를 보여 주는 스크린샷](../../media/c0c062fd-f4a4-4d78-96f7-2c22009052bb.jpg)

   표시 되는 열 및 값은 다음 목록에 설명 되어 있습니다.

   - **스푸핑된 사용자**: 스푸핑 중인 사용자 계정입니다. `5322.From`전자 메일 클라이언트에 표시 되는 보낸 사람 주소 (주소 라고도 함)의 메시지 발신자입니다. 이 주소의 유효성은 SPF에서 검사 하지 않습니다.

     - **도메인** 탭에는 단일 전자 메일 주소가 포함 되어 있거나 원본 전자 메일 서버가 여러 사용자 계정을 위장 하는 경우 둘 **이상의**계정이 포함 됩니다.

     - **외부 도메인** 탭의 값에는 전체 전자 메일 주소가 아니라 스푸핑된 사용자의 도메인이 포함 됩니다.

   - **보내는 인프라**: 원본 전자 메일 서버의 IP 주소에 대 한 역방향 DNS 조회 (ptr 레코드) 또는 원본에 PTR 레코드가 없는 경우 ip 주소에서 찾은 도메인입니다.

     메시지 원본 및 메시지 보낸 사람에 대 한 자세한 내용은 [전자 메일 메시지 표준 개요](how-office-365-validates-the-from-address.md#an-overview-of-email-message-standards)를 참조 하세요.

   - **메시지**수: 보낸 인프라에서 이전 30 일 이내에 지정 된 스푸핑된 보낸 사람 또는 보낸 사람을 포함 하는 조직에 대 한 메시지의 개수입니다.

   - **사용자 불만**수: 지난 30 일 이내에이 보낸 사람에 대 한 사용자의 불만 사항입니다. 불만은 일반적으로 Microsoft에 대 한 정크 제출 형태입니다.

   - **인증 결과**: 다음 값 중 하나입니다.

      - **통과**: 보낸 사람이 SPF 또는 dkim (보낸 사람 전자 메일 인증 검사)를 통과 했습니다.
      - **실패**: 보낸 사람이 보낸 사람 인증 검사를 EOP 못했습니다.
      - **Unknown**: 이러한 검사의 결과를 알 수 없습니다.

   - **결정 설정 기준**: 보내는 인프라가 사용자를 스푸핑할 수 있는지 확인 한 사람을 표시 합니다.

       - **스푸핑 인텔리전스 정책** (자동)
       - **관리** (수동)

   - **마지막**확인: 스푸핑된 사용자를 포함 하는 보내는 인프라에서 메시지를 받은 마지막 날짜입니다.

   - **스푸핑할 수 있습니까?**: 여기에 표시 되는 값은 다음과 같습니다.

     - **Yes**: 스푸핑된 사용자 및 전송 인프라 조합의 메시지가 허용 되며 스푸핑된 전자 메일로 처리 되지 않습니다.

     - **No**: 스푸핑된 사용자 및 보내는 인프라의 조합에서 보낸 메시지가 스푸핑된로 표시 됩니다. 이 작업은 기본 피싱 방지 정책 또는 사용자 지정 ATP 피싱 방지 정책 (기본값은 **정크 메일 폴더로 메시지 이동**)에 의해 제어 됩니다. 자세한 내용은 다음 섹션을 참조 하십시오.

     - **일부 사용자** (**도메인 탭에만 해당** ): 보내는 인프라는 여러 사용자에 게 스푸핑 (일부 스푸핑된 사용자가 허용 되는 경우)을 위장 하며 나머지는 그렇지 않습니다. **자세한 정보** 탭을 사용 하 여 특정 주소를 확인 합니다.

6. 페이지 맨 아래에서 **저장**을 클릭 합니다.

## <a name="use-powershell-to-manage-spoofed-senders"></a>PowerShell을 사용 하 여 스푸핑된 보낸 사람 관리

스푸핑 인텔리전스에서 허용 및 수신 거부를 보려면 다음 구문을 사용 합니다.

```powershell
Get-PhishFilterPolicy [-AllowedToSpoof <Yes | No | Partial>] [-ConfidenceLevel <Low | High>] [-DecisionBy <Admin | SpoofProtection>] [-Detailed] [-SpoofType <Internal | External>]
```

이 예에서는 도메인의 사용자를 스푸핑할 수 있는 모든 보낸 사람에 대 한 자세한 정보를 반환 합니다.

```powershell
Get-PhishFilter -AllowedToSpoof Yes -Detailed -SpoofType Internal
```

구문과 매개 변수에 대 한 자세한 내용은 [get-phishfilterpolicy](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/get-phishfilterpolicy)를 참조 하십시오.

스푸핑 인텔리전스에서 허용 및 수신 거부를 구성 하려면 다음 단계를 수행 합니다.

1. **Get-phishfilterpolicy** cmdlet의 출력을 CSV 파일에 기록 하 여 검색 된 스푸핑된 보낸 사람의 현재 목록을 캡처합니다.

   ```powershell
   Get-PhishFilterPolicy -Detailed | Export-CSV "C:\My Documents\Spoofed Senders.csv"
   ```

2. CSV 파일을 편집 하 여 **SpoofedUser** (전자 메일 주소) 및 **allowedtospoof** (예 또는 아니요) 값을 추가 하거나 수정 합니다. 파일을 저장 하 고 파일을 읽은 다음 이름이 다음과 같은 변수로 저장 합니다 `$UpdateSpoofedSenders` .

   ```powershell
   $UpdateSpoofedSenders = Get-Content -Raw "C:\My Documents\Spoofed Senders.csv"
   ```

3. 이 변수를 사용 `$UpdateSpoofedSenders` 하 여 스푸핑 인텔리전스 정책을 구성 합니다.

   ```powershell
   Set-PhishFilterPolicy -Identity Default -SpoofAllowBlockList $UpdateSpoofedSenders
   ```

구문 및 매개 변수에 대 한 자세한 내용은 [get-phishfilterpolicy](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/set-phishfilterpolicy)를 참조 하십시오.

## <a name="use-the-security--compliance-center-to-configure-spoof-intelligence"></a>보안 & 준수 센터를 사용 하 여 스푸핑 인텔리전스 구성

스푸핑 인텔리전스에 대 한 구성 옵션은 [피싱 방지 정책의 스푸핑 설정](set-up-anti-phishing-policies.md#spoof-settings)에 설명 되어 있습니다.

기본 피싱 방지 정책 및 사용자 지정 정책 에서도 스푸핑 인텔리전스 설정을 구성할 수 있습니다. 구독에 따른 지침은 다음 항목 중 하나를 참조 하십시오.

- [EOP에서 피싱 방지 정책을 구성](configure-anti-phishing-policies-eop.md)합니다.

- [Microsoft 365에서 ATP 피싱 방지 정책을 구성](configure-atp-anti-phishing-policies.md)합니다.

## <a name="how-do-you-know-these-procedures-worked"></a>이 절차가 제대로 수행되었는지 어떻게 확인하나요?

스푸핑이 허용 되 고 스푸핑이 허용 되지 않는 보낸 사람과 스푸핑 인텔리전스를 구성 했으며 스푸핑 인텔리전스 설정을 구성 했는지 확인 하려면 다음 단계 중 하나를 사용 합니다.

- 보안 & 준수 센터에서 **위협 관리** \> **정책** \> **스팸 방지** \> 보기 **스푸핑 인텔리전스 정책** 으로 이동 하 여 \> **이미 검토 한 보낸 사람 표시** 선택에서 \> **도메인** 또는 **외부 도메인** 탭을 선택 하 고 보낸 사람에 대해 **스푸핑 허용 여부** 를 확인 합니다.

- PowerShell에서 다음 명령을 실행 하 여 허용 되 고 스푸핑이 허용 되지 않는 보낸 사람을 확인 합니다.

  ```powershell
  Get-PhishFilter -AllowedToSpoof Yes -SpoofType Internal
  Get-PhishFilter -AllowedToSpoof No -SpoofType Internal
  Get-PhishFilter -AllowedToSpoof Yes -SpoofType External
  Get-PhishFilter -AllowedToSpoof No -SpoofType External
  ```

- PowerShell에서 다음 명령을 실행 하 여 모든 스푸핑된 보낸 사람 목록을 CSV 파일로 내보냅니다.

   ```powershell
   Get-PhishFilterPolicy -Detailed | Export-CSV "C:\My Documents\Spoofed Senders.csv"
   ```

- Exchange Online 사서함이 있는 Microsoft 365 조 직에서 다음 단계 중 하나를 수행 합니다.

  - 보안 & 준수 센터에서 **위협 관리** \> **정책** \> **피싱 방지** \> **기본 정책을** 클릭 하 고 플라이 아웃의 세부 정보를 확인 합니다.

  - Exchange Online PowerShell에서 다음 명령을 실행 하 고 설정을 확인 합니다.

    ```PowerShell
    Get-AntiPhishPolicy -Identity "Office365 AntiPhish Default"
    ```

- Microsoft 365 ATP 조직에서 다음 단계 중 하나를 수행 합니다.

  - 보안 & 준수 센터에서 **위협 관리** \> **정책** \> **ATP 피싱 방지** 로 이동한 후 다음 단계 중 하나를 수행 합니다.

    - 목록에서 정책을 선택 합니다. 플라이 아웃이 나타나면 **스푸핑** 섹션에서 값을 확인 합니다.
    - **기본 정책을**클릭 합니다. 플라이 아웃이 나타나면 **스푸핑** 섹션에서 값을 확인 합니다.

  - Exchange Online PowerShell에서 Name을 \< \> Office365 AntiPhish Default로 바꾸거나 사용자 지정 ATP 피싱 방지 정책의 이름을 바꾼 후 다음 명령을 실행 하 고 설정을 확인 합니다.

    ```PowerShell
    Get-AntiPhishPolicy -Identity "<Name>"
    ```

## <a name="other-ways-to-manage-spoofing-and-phishing"></a>스푸핑 및 피싱 관리의 기타 방법

스푸핑 및 피싱 방지에 유심히 다음은 도메인에 대 한 보낸 사람 스푸핑을 확인 하 고 조직이 손상 되는 것을 방지 하는 데 관련 된 방법입니다.

- **스푸핑 메일 보고서**를 확인 합니다. 이 보고서를 자주 사용 하 여 스푸핑된 보낸 사람을 보고 관리 하는 데 도움을 받을 수 있습니다. 자세한 내용은 [스푸핑 감지 보고서](view-email-security-reports.md#spoof-detections-report)를 참조 하세요.

- SPF (Sender Policy Framework) 구성을 검토 합니다. SPF를 빠르게 도입하여 신속하게 구성하려면 [스푸핑 방지를 위해 Microsoft 365에서 SPF 설정](set-up-spf-in-office-365-to-help-prevent-spoofing.md)을 참조하세요. Office 365에서 SPF를 사용하는 방법이나 문제 해결 또는 비표준 배포(예: 하이브리드 배포)에 대한 자세한 내용은 [Office 365에서 SPF(Sender Policy Framework)를 사용하여 스푸핑을 차단하는 방법](how-office-365-uses-spf-to-prevent-spoofing.md)을 참조하세요.

- DKIM (DomainKeys 식별 된 메일) 구성을 검토 합니다. 공격자가 도메인에서 오는 것 처럼 표시 되는 메시지를 보내지 못하도록 하기 위해 SPF 및 DMARC 외에 DKIM을 사용 해야 합니다. DKIM을 사용하면 메시지 머리글에 있는 전자 메일 메시지에 디지털 서명을 첨부할 수 있습니다. 자세한 내용은 [DKIM을 사용 하 여 Office 365에서 사용자 지정 도메인에서 보낸 아웃 바운드 전자 메일의 유효성 검사](use-dkim-to-validate-outbound-email.md)를 참조 하세요.

- 도메인 기반 메시지 인증, 보고 및 적합성 (DMARC) 구성을 검토 합니다. SPF 및 DKIM과 함께 DMARC를 구현하면 스푸핑 및 피싱 전자 메일에 대한 추가 보호 기능이 제공됩니다. DMARC는 수신 메일 시스템이 사용자의 도메인에서 보낸 SPF 또는 DKIM 확인에 실패한 메시지에 대해 수행할 작업을 결정하는 데 도움을 줍니다. 자세한 내용은 [Office 365에서 DMARC을 사용 하 여 전자 메일의 유효성 검사를](use-dmarc-to-validate-email.md)참조 하세요.
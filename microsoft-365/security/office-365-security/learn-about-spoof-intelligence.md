---
title: 스푸핑 인텔리전스 구성
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: how-to
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
description: 관리자는 특정 스푸핑된 보낸 사람에 대해 허용하거나 차단할 수 있는 EOP(Exchange Online Protection)의 스푸핑 인텔리전스에 대해 학습할 수 있습니다.
ms.openlocfilehash: bc8ae2664acf96ea6cd4c20c2f9195db9b75b3da
ms.sourcegitcommit: 1beaf89d2faa32f11fe1613be2fa2b31c4bc4a91
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/08/2020
ms.locfileid: "49602124"
---
# <a name="configure-spoof-intelligence-in-eop"></a>EOP에서 스푸핑 인텔리전스 구성

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


Exchange Online 사서함이 없는 Microsoft 365 조직 또는 Exchange Online 사서함이 없는 독립 실행형 EOP(Exchange Online Protection) 조직에서 인바운드 전자 메일 메시지는 2018년 10월부로 EOP의 스푸핑으로부터 자동으로 보호됩니다. EOP는 피싱에 대한 조직의 전반적인 방어의 일부로 스푸핑 인텔리전스를 활용합니다. 자세한 내용은 EOP의 스푸핑 방지 보호 기능을 [참조하세요.](anti-spoofing-protection.md)

보낸 사람이 전자 메일 주소를 스푸핑하면 조직의 도메인 중 하나에 있는 사용자 또는 조직에 전자 메일을 보내는 외부 도메인의 사용자로 표시됩니다. 스팸 또는 피싱 전자 메일을 보내기 위해 보낸 사람 스푸핑하는 공격자는 차단해야 합니다. 그러나 합법적인 보낸 사람이 스푸핑하는 시나리오가 있습니다. 예시:

- 내부 도메인 스푸핑에 대한 합법적인 시나리오:

  - 타사 보낸 사람이 도메인을 사용하여 회사 설문 조사를 위해 직원에게 대량 메일을 보낼 수 있습니다.
  - 외부 회사에서 사용자 대신 광고 또는 제품 업데이트를 생성하고 전송합니다.
  - 도우미는 정기적으로 조직 내의 다른 사용자에 대한 전자 메일을 보내야 합니다.
  - 내부 응용 프로그램에서 전자 메일 알림을 전송합니다.

- 외부 도메인 스푸핑에 대한 합법적인 시나리오:

  - 보낸 사람이 메일링 목록(토론 목록)에 있으며, 메일링 목록은 원래 보낸 사람으로부터 메일링 목록의 모든 참가자에게 전자 메일을 릴레이합니다.
  - 외부 회사가 다른 회사를 대신하여 전자 메일을 전송합니다(예: 자동화된 보고서 또는 소프트웨어 as-a-service 회사).

스푸핑 인텔리전스 및 특히 기본(유일한) 스푸핑 인텔리전스 정책은 합법적인 보낸 사람이 보낸 스푸핑된 전자 메일이 EOP 스팸 필터 또는 외부 전자 메일 시스템에 걸려오지 않도록 하는 동시에 스팸 또는 피싱 공격으로부터 사용자를 보호하는 데 도움이 됩니다.

보안 및 준수 센터 또는 PowerShell(Exchange Online 사서함이 있는 Microsoft 365 조직용 Exchange Online PowerShell, Exchange Online 사서함이 없는 조직의 독립 실행형 EOP PowerShell)에서 스푸핑 인텔리전스를 관리할 수 있습니다. &

## <a name="what-do-you-need-to-know-before-you-begin"></a>시작하기 전에 알아야 할 내용은 무엇인가요?

- <https://protection.office.com/>에서 보안 및 준수 센터를 엽니다. **스팸 방지 설정** 페이지로 바로 이동하려면 <https://protection.office.com/antispam>을 사용하세요. 피싱 방지 **페이지로** 직접 이동하기 위해 다음을 <https://protection.office.com/antiphishing> 사용하세요.

- Exchange Online PowerShell에 연결하려면 [Exchange Online PowerShell에 연결](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)을 참조하세요. 독립 실행형 EOP PowerShell에 연결하려면 [Exchange Online Protection PowerShell에 연결](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell)을 참조하세요.

- 이 문서의 절차를 수행하려면 먼저 보안 및 준수 센터에서 사용 권한을 받아야 합니다.
  - 스푸핑 인텔리전스 정책을 수정하거나 스푸핑 인텔리전스를 사용하거나 **Organization Management** 사용하지 않도록 설정하려면 조직 관리 또는 보안 관리자 역할 그룹의 **구성원이** 되어야 합니다.
  - 스푸핑 인텔리전스 정책에 대한 읽기 전용 액세스 권한을 **Global Reader** 사용하려면 전역 읽기 또는 보안 읽기 권한이 있는 역할 그룹의 구성원이 **되거나,**

  자세한 내용은 [보안 및 준수 센터의 사용 권한](permissions-in-the-security-and-compliance-center.md)을 참조하세요.

  **참고**:

  - Microsoft 365 관리 센터의 해당 Azure Active Directory 역할에 사용자를 추가하면 사용자에게 보안 및 준수 센터에서 필요한 권한 _및_ Microsoft 365의 다른 기능에 대한 권한이 부여됩니다. 자세한 내용은 [관리자 역할 정보](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles)를 참조하세요.
  - [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups)의 **보기 전용 조직 관리** 역할 그룹에도 기능에 대한 읽기 전용 권한을 부여합니다.

- 스푸핑 인텔리전스에 대한 권장 설정은 EOP 기본 피싱 방지 정책 설정을 [참조하세요.](recommended-settings-for-eop-and-office365-atp.md#eop-default-anti-phishing-policy-settings)

## <a name="use-the-security--compliance-center-to-manage-spoofed-senders"></a>보안 및 & 센터를 사용하여 스푸핑된 보낸 사람 관리

> [!NOTE]
> Microsoft 365 Enterprise E5 구독이 있는 경우 또는 Office 365용 Microsoft Defender 추가 기능을 별도로 구입한 경우 스푸핑 인텔리전스 정보를 통해 도메인을 스푸핑하는 보낸 사람도 관리할 수 [있습니다.](walkthrough-spoof-intelligence-insight.md)

1. 보안 및 준수 센터에서 **위협 관리** \> **정책** \> **스팸 방지** 로 이동합니다.

2. 스팸 방지 **설정 페이지에서** 확장 아이콘을 클릭하여 ![ 스푸핑 인텔리전스 정책을 ](../../media/scc-expand-icon.png) **확장합니다.**

   ![스푸핑 인텔리전스 정책 선택](../../media/anti-spam-settings-spoof-intelligence-policy.png)

3. 다음 중 하나를 선택합니다.

   - **새 보낸 사람 검토**
   - **이미 검토한 보낸 사람 표시**

4. 이 보낸 **사람이** 나타나는 사용자 플라이아웃을 스푸핑할 수 있도록 허용할지 결정에서 다음 탭 중 하나를 선택합니다.

   - **도메인:** 보낸 사람이 내부 도메인의 사용자를 스푸핑합니다.
   - **외부 도메인**: 보낸 사람이 외부 도메인의 사용자를 스푸핑합니다.

5. 스푸핑 허용 열에서 확장 ![ ](../../media/scc-expand-icon.png) **아이콘을** 클릭합니다. **스푸핑된** 보낸 사람이 허용하도록 허용하거나 **아니요를** 선택하면 메시지를 스푸핑된 메시지로 표시하도록 할 수 있습니다. 이 작업은 기본 피싱 방지 정책 또는 사용자 지정 피싱 방지 정책에 의해 제어됩니다(기본값은 정크 메일 폴더로 메시지 **이동).** 자세한 내용은 피싱 방지 정책의 [스푸핑 설정을 참조하세요.](set-up-anti-phishing-policies.md#spoof-settings)

   ![스푸핑된 보낸 사람 플라이아웃 및 보낸 사람이 스푸핑을 허용하는지 여부를 보여 줄 수 있는 스크린샷](../../media/c0c062fd-f4a4-4d78-96f7-2c22009052bb.jpg)

   다음 목록에는 열과 값이 설명됩니다.

   - **스푸핑된 사용자**: 스푸핑되는 사용자 계정입니다. 전자 메일 클라이언트에 표시된 보낸 사람 주소(주소라고도 알려지음)의 메시지 보낸 `5322.From` 사람입니다. SPF에서 이 주소의 유효성을 확인하지 않습니다.

     - 도메인 **탭에서** 값에 단일 전자 메일 주소가 포함되거나 원본 전자 메일 서버가 여러 사용자 계정을 스푸핑하는 경우 이 값에는 두 개 이상의 전자 메일 주소가 **포함되어 있습니다.**

     - 외부 **도메인** 탭에서 값에는 전체 전자 메일 주소가 아니라 스푸핑된 사용자의 도메인이 포함되어 있습니다.

   - **보내는 인프라:** 원본 전자 메일 서버의 IP 주소의 역방향 DNS PTR 레코드에 있는 도메인입니다. 원본 IP 주소에 PTR 레코드가 없는 경우 보내는 인프라는 \<source IP\> /24(예: 192.168.100.100/24)로 식별됩니다.

     메시지 원본 및 메시지 보낸 사람에 대한 자세한 내용은 전자 메일 메시지 표준 [개요를 참조하십시오.](how-office-365-validates-the-from-address.md#an-overview-of-email-message-standards)

   - **메시지 #**: 지난 30일 이내에 지정된 스푸핑된 보낸 사람 또는 보낸 사람이 포함된 보내는 인프라에서 조직으로 보내는 메시지 수입니다.

   - **#of user complaints**: Complaints filed by your users filed against this sender within the last 30 days. 불만은 일반적으로 Microsoft에 정크 제출 형식입니다.

   - **인증 결과:** 다음 값 중 하나
      - **통과:** 보낸 사람이 SPF 또는 DKIM(보낸 사람 전자 메일 인증 검사)을 통과했습니다.
      - **실패:** 보낸 사람이 EOP 보낸 사람 인증 검사를 실패했습니다.
      - **알** 수 없음: 이러한 검사의 결과를 알 수 없습니다.

   - **결정 집합:** 보내는 인프라가 사용자를 스푸핑할 수 있도록 허용할지 결정한 사용자를 보여줍니다.
       - **스푸핑 인텔리전스** 정책(자동)
       - **관리자(수동)**

   - **마지막으로 확인한** 날짜: 스푸핑된 사용자가 포함된 보내는 인프라에서 메시지를 받은 마지막 날짜입니다.

   - **스푸핑이 허용되는 경우:** 여기에 있는 값은 다음과 같습니다.
     - **예:** 스푸핑된 사용자와 보내는 인프라의 조합에서 보낸 메시지는 허용될 수 있으며 스푸핑된 전자 메일로 처리되지 않습니다.
     - **아니요:** 스푸핑된 사용자와 보내는 인프라의 조합에서 보낸 메시지가 스푸핑된 것으로 표시됩니다. 이 작업은 기본 피싱 방지 정책 또는 사용자 지정 피싱 방지 정책에 의해 제어됩니다(기본값은 정크 메일 폴더로 메시지 **이동).** 자세한 내용은 다음 섹션을 참조하세요.

     - **일부** **사용자(도메인** 탭에만 해당): 보내는 인프라가 여러 사용자를 스푸핑하는 중입니다. 여기서 일부 스푸핑된 사용자가 허용되는 경우와 다른 사용자는 스푸핑되지 않습니다. 자세한 **탭을 사용하여** 특정 주소를 볼 수 있습니다.

6. 페이지 아래쪽에서 저장을 **클릭합니다.**

## <a name="use-powershell-to-manage-spoofed-senders"></a>PowerShell을 사용하여 스푸핑된 보낸 사람 관리

스푸핑 인텔리전스에서 허용 및 수신이 차단된 보낸 사람 보기를 위해 다음 구문을 사용 합니다.

```powershell
Get-PhishFilterPolicy [-AllowedToSpoof <Yes | No | Partial>] [-ConfidenceLevel <Low | High>] [-DecisionBy <Admin | SpoofProtection>] [-Detailed] [-SpoofType <Internal | External>]
```

이 예에서는 도메인의 사용자를 스푸핑할 수 있는 모든 보낸 사람에 대한 자세한 정보를 반환합니다.

```powershell
Get-PhishFilterPolicy -AllowedToSpoof Yes -Detailed -SpoofType Internal
```

구문과 매개 변수에 대한 자세한 내용은 [Get-PhishFilterPolicy를 참조하십시오.](https://docs.microsoft.com/powershell/module/exchange/get-phishfilterpolicy)

스푸핑 인텔리전스에서 허용 및 차단된 보낸 사람 구성을 구성하기 위해 다음 단계를 수행합니다.

1. **Get-PhishFilterPolicy** cmdlet의 출력을 CSV 파일에 기록하여 검색된 스푸핑된 보낸 사람의 현재 목록을 캡처합니다.

   ```powershell
   Get-PhishFilterPolicy -Detailed | Export-CSV "C:\My Documents\Spoofed Senders.csv"
   ```

2. CSV 파일을 편집하여 **SpoofedUser(전자** 메일 주소) 및 **AllowedToSpoof(예** 또는 아니요) 값을 추가하거나 수정합니다. 파일을 저장하고, 파일을 읽고, 다음 변수로 콘텐츠를 `$UpdateSpoofedSenders` 저장합니다.

   ```powershell
   $UpdateSpoofedSenders = Get-Content -Raw "C:\My Documents\Spoofed Senders.csv"
   ```

3. 변수를 `$UpdateSpoofedSenders` 사용하여 스푸핑 인텔리전스 정책을 구성합니다.

   ```powershell
   Set-PhishFilterPolicy -Identity Default -SpoofAllowBlockList $UpdateSpoofedSenders
   ```

구문과 매개 변수에 대한 자세한 내용은 [Set-PhishFilterPolicy를 참조하십시오.](https://docs.microsoft.com/powershell/module/exchange/set-phishfilterpolicy)

## <a name="use-the-security--compliance-center-to-configure-spoof-intelligence"></a>보안 및 & 센터를 사용하여 스푸핑 인텔리전스 구성

스푸핑 인텔리전스에 대한 구성 옵션은 피싱 방지 정책의 스푸핑 설정에 [설명되어 있습니다.](set-up-anti-phishing-policies.md#spoof-settings)

기본 피싱 방지 정책과 사용자 지정 정책에서 스푸핑 인텔리전스 설정을 구성할 수 있습니다. 구독을 기반으로 하는 지침은 다음 항목 중 하나를 참조하세요.

- [EOP에서 피싱 방지 정책을 구성합니다.](configure-anti-phishing-policies-eop.md)

- [Office 365용 Microsoft Defender에서](configure-atp-anti-phishing-policies.md)피싱 방지 정책을 구성합니다.

## <a name="how-do-you-know-these-procedures-worked"></a>이 절차가 제대로 수행되었는지 어떻게 확인하나요?

스푸핑이 허용 및 허용되지 않는 보낸 사람으로 스푸핑 인텔리전스를 구성하고 스푸핑 인텔리전스 설정을 구성한지 확인하려면 다음 단계를 수행합니다.

- 보안 & 준수 센터에서 위협 관리 **Threat management** 정책 스팸 방지 확장 스푸핑 \> **Policy** \> **Anti-spam** \> **인텔리전스** \> **Show me senders I already reviewed** \> **Your Domains** **External Domains** **Allowed to spoof?** 정책으로 이동하여 이미 검토한 보낸 사람 표시 또는 도메인 또는 외부 도메인 탭을 선택하고 스푸핑 허용 여부 확인을 선택합니다.

- PowerShell에서 다음 명령을 실행하여 스푸핑이 허용 및 스푸핑이 허용되지 않은 보낸 사람 보기

  ```powershell
  Get-PhishFilterPolicy -AllowedToSpoof Yes -SpoofType Internal
  Get-PhishFilterPolicy -AllowedToSpoof No -SpoofType Internal
  Get-PhishFilterPolicy -AllowedToSpoof Yes -SpoofType External
  Get-PhishFilterPolicy -AllowedToSpoof No -SpoofType External
  ```

- PowerShell에서 다음 명령을 실행하여 스푸핑된 모든 보낸 사람 목록을 CSV 파일로 내보낼 수 있습니다.

   ```powershell
   Get-PhishFilterPolicy -Detailed | Export-CSV "C:\My Documents\Spoofed Senders.csv"
   ```

- 보안 & 준수 센터에서 위협 **Threat management** 관리 정책 피싱 방지 또는 ATP 피싱 방지로 이동한 후 다음 단계 중 \> **Policy** \> **Anti-phishing** 하나를 수행합니다. **ATP anti-phishing**  

  - 목록에서 정책을 선택합니다. 플라이아웃이 나타나면 스푸핑 섹션의 값을 **검증합니다.**
  - 기본 **정책을 클릭합니다.** 플라이아웃이 나타나면 스푸핑 섹션의 값을 **검증합니다.**

- Exchange Online PowerShell에서 Office365 AntiPhish Default 또는 사용자 지정 정책의 이름으로 바꾸고 다음 명령을 실행하여 설정을 \<Name\> 확인합니다.

  ```PowerShell
  Get-AntiPhishPolicy -Identity "<Name>" | Format-List EnableAntiSpoofEnforcement,EnableUnauthenticatedSender,AuthenticationFailAction
  ```

## <a name="other-ways-to-manage-spoofing-and-phishing"></a>스푸핑 및 피싱을 관리하는 다른 방법

스푸핑 및 피싱 보호에 대해 신각해야 합니다. 다음은 보낸 사람이 도메인을 스푸핑하는 것을 확인하고 조직을 손상하는 것을 방지하는 관련 방법입니다.

- **스푸핑 메일 보고서를 검사합니다.** 이 보고서를 자주 사용하여 스푸핑된 보낸 사람 관리를 지원할 수 있습니다. 자세한 내용은 [스푸핑 검색 보고서를 참조하세요.](view-email-security-reports.md#spoof-detections-report)

- SPF(Sender Policy Framework) 구성을 검토합니다. SPF를 빠르게 도입하여 신속하게 구성하려면 [스푸핑 방지를 위해 Microsoft 365에서 SPF 설정](set-up-spf-in-office-365-to-help-prevent-spoofing.md)을 참조하세요. Office 365에서 SPF를 사용하는 방법이나 문제 해결 또는 비표준 배포(예: 하이브리드 배포)에 대한 자세한 내용은 [Office 365에서 SPF(Sender Policy Framework)를 사용하여 스푸핑을 차단하는 방법](how-office-365-uses-spf-to-prevent-spoofing.md)을 참조하세요.

- DomainKeys 식별 메일(DKIM) 구성을 검토합니다. SPF 및 DMARC 외에 DKIM을 사용하여 공격자가 도메인에서 보낸 것 같은 메시지를 보내지 못하도록 해야 합니다. DKIM을 사용하면 메시지 머리글에 있는 전자 메일 메시지에 디지털 서명을 첨부할 수 있습니다. 자세한 내용은 [DKIM을 사용하여 Office 365의](use-dkim-to-validate-outbound-email.md)사용자 지정 도메인에서 보낸 아웃바운드 전자 메일의 유효성을 검사합니다.

- 도메인 기반 메시지 인증, 보고 및 적합성(DMARC) 구성을 검토합니다. SPF 및 DKIM과 함께 DMARC를 구현하면 스푸핑 및 피싱 전자 메일에 대한 추가 보호 기능이 제공됩니다. DMARC는 수신 메일 시스템이 사용자의 도메인에서 보낸 SPF 또는 DKIM 확인에 실패한 메시지에 대해 수행할 작업을 결정하는 데 도움을 줍니다. 자세한 내용은 [DMARC를 사용하여 Office 365에서](use-dmarc-to-validate-email.md)전자 메일의 유효성을 검사합니다.

---
title: 사용자에 대한 타사 피싱 시뮬레이션 및 필터되지 않은 메시지의 SecOps 사서함 배달 구성
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
ms.custom: ''
description: 관리자는 EOP(Exchange Online Protection)의 고급 배달 정책을 사용하여 지원되는 특정 시나리오(타사 피싱 시뮬레이션 및 SecOps(보안 작업) 사서함으로 배달된 메시지)에서 필터링하지 말아야 하는 메시지를 식별하는 방법을 배울 수 있습니다.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: baea981e712a02bfffb6b664d4bb6a3d8c9b5ae5
ms.sourcegitcommit: b295c60d5aa69781a20c59b9cdf2ed91c62b21af
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/22/2021
ms.locfileid: "59481051"
---
# <a name="configure-the-delivery-of-third-party-phishing-simulations-to-users-and-unfiltered-messages-to-secops-mailboxes"></a>사용자에 대한 타사 피싱 시뮬레이션 및 필터되지 않은 메시지의 SecOps 사서함 배달 구성

**적용 대상**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Office 365용 Microsoft Defender 플랜 1 및 플랜 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

기본적으로 조직의 [](secure-by-default.md)보안을 유지하기 위해 EOP(Exchange Online Protection)는 맬웨어 또는 높은 신뢰도 피싱으로 식별된 메시지에 대해 수신 허용 목록 또는 필터링 우회를 허용하지 않습니다. 그러나 필터되지 않은 메시지를 배달해야 하는 특정 시나리오가 있습니다. 예제:

- **타사 피싱 시뮬레이션:** 시뮬레이션된 공격은 실제 공격이 조직에 영향을 미치기 전에 취약한 사용자를 식별하는 데 도움이 될 수 있습니다.
- **SecOps(보안 작업)** 사서함: 보안 팀에서 필터되지 않은 메시지를 수집 및 분석하는 데 사용하는 전용 사서함(좋음과 불량 모두)입니다.

이러한 특정 _시나리오에서_ 인바운드 Microsoft 365 필터링되지  않도록 하는 고급 배달 정책을 사용할 수 있습니다. <sup>\*</sup> 고급 배달 정책은 이러한 시나리오의 메시지가 다음 결과를 달성하도록 보장합니다.

- EOP 및 Microsoft Defender for Office 365 메시지에 대해 아무 작업도 수행하지 않습니다.<sup>\*</sup>
- 스팸 및 피싱에 [대한 ZAP(제로](zero-hour-auto-purge.md) 아워 제거)는 이러한 메시지에 대해 아무 작업도 수행하지 않습니다.<sup>\*</sup>
- [이러한 시나리오에서는](/microsoft-365/compliance/alert-policies#default-alert-policies) 기본 시스템 알림이 트리거되지 않습니다.
- [Defender for Defender의](office-365-air.md) AIR Office 365 메시지는 무시됩니다.
- 타사 피싱 시뮬레이션을 위한 구체적인 예는 다음과 같습니다.
  - [관리자 제출은](admin-submission.md) 메시지가 피싱 시뮬레이션 캠페인의 일부이자 실제 위협이 아니라는 자동 응답을 생성합니다. 경고와 AIR이 트리거되지 않습니다. 관리자 제출 환경은 이러한 메시지를 시뮬레이트된 위협으로 표시됩니다.
  - 사용자가 피싱 보고 추가 기능을 사용하여 [](enable-the-report-message-add-in.md)피싱 시뮬레이션 메시지를 보고하면 시스템에서 Outlook, 조사 또는 인시던트가 생성되지 않습니다. 메시지는 제출 페이지의 사용자가 보고한 메시지 탭에도 표시됩니다.
  - [금고 Defender for Office 365](safe-links.md) 클릭 시 이러한 메시지에서 구체적으로 식별된 URL을 차단하거나 검색하지 않습니다. URL은 계속 래핑되지만 차단되지는 않습니다.
  - [금고 For Defender에서](safe-attachments.md) Office 365 메시지의 첨부 파일은 확인하지 않습니다.

<sup>\*</sup> 맬웨어 필터링 또는 맬웨어에 대한 ZAP를 무시할 수 없습니다.

고급 배달 정책으로 식별된 메시지는 보안 위협이 아니기 때문에 메시지는 시스템 오버라이드로 표시됩니다. 관리자 환경은 피싱 시뮬레이션 시스템 재지정 또는 **SecOps** 사서함 시스템 재지정으로 인해 이러한 메시지를 보여 주게 됩니다.  관리자는 다음 환경의 이러한 시스템 다시 설정에 대해 필터링하고 분석할 수 있습니다.

- Office 365 계획 2에 대한 [Defender의](threat-explorer.md)위협 탐색기/실시간 검색:  관리자는 시스템 재지정 원본을 필터링하고 피싱 시뮬레이션 또는  **SecOps 사서함을** 선택할 수 있습니다.
- 위협 탐색기/실시간 검색의 전자 메일 엔터티 [페이지:](mdo-email-entity-page.md)관리자는 **Override(s)** 섹션의 테넌트  다시 정의에서  **SecOps** 사서함 또는 피싱 시뮬레이션에서 조직 정책에서 허용된 메시지를 볼 수 있습니다.
- [위협 방지](view-email-security-reports.md#threat-protection-status-report)상태 보고서: 관리자는  드롭다운 메뉴에서 시스템 다시 설정으로 데이터를 확인하여 필터링하고 피싱 시뮬레이션 시스템 다시 설정으로 인해 허용된 메시지를 확인하도록 선택할 수 있습니다. SecOps 사서함 다시 설정에서 허용되는 메시지를 확인하려면  이유별 차트 분석 드롭다운 메뉴에서 배달 위치별 차트 분석 **항목을** 선택할 수 있습니다.
- [Endpoint용 Microsoft Defender의](../defender-endpoint/advanced-hunting-overview.md)고급 헌팅: 피싱 시뮬레이션 및 SecOps 사서함 시스템 재지정은 EmailEvents의 OrgLevelPolicy 내에 옵션으로 표시됩니다.
- [캠페인 보기:](campaigns.md)관리자는  시스템 다시 설정 원본을  필터링하고 피싱 시뮬레이션 또는 **SecOps** 사서함을 선택할 수 있습니다.

## <a name="what-do-you-need-to-know-before-you-begin"></a>시작하기 전에 알아야 할 내용은 무엇인가요?

- <https://security.microsoft.com>에서 Microsoft 365 Defender 포털을 엽니다. 고급 배달 페이지로 직접 **이동하기 위해** 를 를 니다. <https://security.microsoft.com/advanceddelivery>

- 보안 및 준수 센터 PowerShell에 연결하려면 [보안 및 준수 센터 PowerShell에 연결](/powershell/exchange/connect-to-scc-powershell)을 참조하세요.

- 이 문서의 절차를 수행하려면 먼저 사용 권한을 할당해야 합니다.
  - 고급 배달 정책에서 구성된 설정을 만들거나 수정하거나 제거하려면 Microsoft 365 Defender **포털에서** **보안** 관리자 역할 그룹의 구성원이자 조직 관리  역할 그룹의 구성원인 **Exchange Online.**
  - 고급 배달 정책에 대한 읽기 전용 액세스 권한을 사용하려면  전역 읽기 사용자 또는 보안 읽기 권한이 있는 역할 그룹의 **구성원이** 해야 합니다.

  자세한 내용은 Microsoft 365 Defender [포털의](permissions-microsoft-365-security-center.md) 사용 권한 및 [Exchange Online.](/exchange/permissions-exo/permissions-exo)

  > [!NOTE]
  > 해당 Azure Active Directory 역할에 사용자를 추가하면 Microsoft 365 Defender 포털에서 필요한 사용 권한과  해당 역할의 다른 기능에 대한 사용 Microsoft 365. 자세한 내용은 [관리자 역할 정보](../../admin/add-users/about-admin-roles.md)를 참조하세요.

## <a name="use-the-microsoft-365-defender-portal-to-configure-secops-mailboxes-in-the-advanced-delivery-policy"></a>고급 Microsoft 365 Defender 포털을 사용하여 고급 배달 정책에서 SecOps 사서함 구성

1. Microsoft 365 Defender 포털의 규칙 섹션에서 **전자** 메일 & 공동 작업 정책 & 규칙 위협 정책 고급 \>  \>  \>  **배달로** 이동하세요.

2. 고급 배달 **페이지에서** **SecOps** 사서함 탭이 선택되어 있는지 확인한 후 다음 단계 중 하나를 수행합니다.
   - 편집 ![ 아이콘을 클릭합니다.](../../media/m365-cc-sc-edit-icon.png) **편집.**
   - 구성된 피싱 시뮬레이션이 없는 경우 추가 를 **클릭합니다.**

3. **SecOps** 사서함 편집 플라이아웃이 열리면 다음 단계 중 하나를 수행하여 SecOps 사서함으로 지정하려는 기존 Exchange Online 사서함을 입력합니다.
   - 상자를 클릭하고 사서함 목록을 확인한 다음 사서함을 선택합니다.
   - 상자에서 사서함의 식별자(이름, 표시 이름, 별칭, 전자 메일 주소, 계정 이름 등)를 입력하기 시작하고 결과에서 사서함(표시 이름)을 선택합니다.

     필요한 만큼 이 단계를 반복합니다. 메일 그룹은 허용되지 않습니다.

     기존 값을 제거하려면 제거를 클릭합니다. ![제거 아이콘.](../../media/m365-cc-sc-remove-selection-icon.png) 값 옆에 있습니다.

4. 작업을 마쳤으면 **저장** 을 클릭합니다.

구성한 SecOps 사서함 항목이 **SecOps** 사서함 탭에 표시됩니다. 변경하려면 편집 ![ 아이콘을 클릭합니다.](../../media/m365-cc-sc-edit-icon.png) **탭에서** 편집합니다.

## <a name="use-the-microsoft-365-defender-portal-to-configure-third-party-phishing-simulations-in-the-advanced-delivery-policy"></a>고급 Microsoft 365 Defender 포털을 사용하여 고급 배달 정책에서 타사 피싱 시뮬레이션 구성

1. Microsoft 365 Defender 포털의 규칙 섹션에서 **전자** 메일 & 공동 작업 정책 & 규칙 위협 정책 고급 \>  \>  \>  **배달로** 이동하세요.

2. 고급 배달 **페이지에서** 피싱  시뮬레이션 탭을 선택하고 다음 단계 중 하나를 수행합니다.
   - 편집 ![ 아이콘을 클릭합니다.](../../media/m365-cc-sc-edit-icon.png) **편집.**
   - 구성된 피싱 시뮬레이션이 없는 경우 추가 를 **클릭합니다.**

3. 열 **수 있는** 타사 피싱 시뮬레이션 플라이아웃 편집 플라이아웃에서 다음 설정을 구성합니다.

   - **도메인:** 이 설정을 확장하고 상자를 클릭하고 값을 입력한 다음 Enter를 누르거나 상자 아래에 표시되는 값을 선택하여 하나 이상의 전자 메일 주소 도메인(예: contoso.com)을 입력합니다. 필요한 만큼 이 단계를 반복합니다. 항목을 10개까지 추가할 수 있습니다.

     > [!NOTE]
     > 메시지의 SMTP 전송에 사용되는 주소(MAIL FROM 주소, P1 보낸 사람 또는 봉투 보낸 사람)나 피싱 시뮬레이션 공급업체에서 지정한 `5321.MailFrom` DomainKeys Identified  Mail(DKIM) 도메인의 도메인을 사용합니다.  

   - **IP** 보내기 : 이 설정을 확장하고 상자를 클릭하고 값을 입력한 다음 Enter를 누르거나 상자 아래에 표시되는 값을 선택하여 유효한 IPv4 주소를 하나 이상 입력합니다. 필요한 만큼 이 단계를 반복합니다. 항목을 10개까지 추가할 수 있습니다. 유효한 값은 다음과 같습니다.
     - 단일 IP: 예: 192.168.1.1.
     - IP 범위: 예: 192.168.0.1-192.168.0.254.
     - CIDR IP: 예: 192.168.0.1/25.
   - 허용할 시뮬레이션 **URL:** 이 설정을 확장하고 선택적으로 상자를 클릭하고 값을 입력한 다음 상자 아래에 표시되는 값을 선택하거나 입력하여 차단 또는 검색되지 않는 피싱 시뮬레이션 캠페인의 일부인 특정 URL을 입력합니다. 항목을 10개까지 추가할 수 있습니다. URL 구문 형식은 [테넌트 허용/차단 목록에 대한 URL 구문을 참조하세요.](tenant-allow-block-list.md#url-syntax-for-the-tenant-allowblock-list) 이러한 URL은 클릭 시 래핑되지만 차단되지는 않습니다.

   기존 값을 제거하려면 제거를 클릭합니다. ![제거 아이콘.](../../media/m365-cc-sc-remove-selection-icon.png) 값 옆에 있습니다.

   > [!NOTE]
   > 고급 배달에서 타사 피싱 시뮬레이션을 구성하려면 다음 정보를 제공해야 합니다.
   > 
   > - 다음 원본 중 하나 이상의 **Domain**
   >   - 주소(MAIL FROM 주소, P1 보낸 사람 또는 봉투 보낸 `5321.MailFrom` 사람)입니다.
   >   - DKIM 도메인.
   > - 하나 이상의 보내는 **IP .**
   > 
   > 선택적으로 시뮬레이션 메시지의 **URL이** 차단되지 않도록 시뮬레이션 URL을 포함할 수 있습니다.
   > 각 필드에 대해 최대 10개 항목을 지정할 수 있습니다.
   > 하나 이상의 Domain 및 One  Sending **IP에** 대한 일치가 있어야 하지만 값 간의 연결은 유지되지 않습니다.

4. 작업을 마치면 다음 단계 중 하나를 수행합니다.
   - **처음:** **추가를** 클릭한 다음 **닫기 를 클릭합니다.**
   - **기존 편집:** **저장을 클릭한** 다음 닫기 **를 클릭합니다.**

구성한 타사 피싱 시뮬레이션 항목이 피싱 시뮬레이션 **탭에** 표시됩니다. 변경하려면 편집 ![ 아이콘을 클릭합니다.](../../media/m365-cc-sc-edit-icon.png) **탭에서** 편집합니다.

## <a name="additional-scenarios-that-require-filtering-bypass"></a>필터링 우회가 필요한 추가 시나리오

고급 배달 정책이 도움이 될 수 있는 두 가지 시나리오 외에도 필터링을 무시해야 하는 다른 시나리오가 있습니다.

- **타사 필터:** 도메인의 MX 레코드가  메시지를 Office 365 경우(메시지가 먼저 다른 곳에 라우팅되는 [경우)](secure-by-default.md) 기본적으로 보안을 사용할 *수 없습니다.* 보호를 추가하려면 커넥터에 대해 향상된 필터링을 사용하도록 설정해야 합니다(목록 *건너뛰기라고도 합니다).* 자세한 내용은 [Manage mail flow using a third-party cloud service with Exchange Online.](/exchange/mail-flow-best-practices/manage-mail-flow-using-third-party-cloud) 커넥터에 대해 향상된 필터링을 사용하지 않는 경우 메일 흐름 규칙(전송 규칙)을 사용하여 타사 필터링으로 이미 평가된 메시지에 대해 Microsoft 필터링을 무시합니다. 자세한 내용은 메일 흐름 규칙을 사용하여 [메시지에서 SCL 설정을 참조하세요.](/exchange/security-and-compliance/mail-flow-rules/use-rules-to-set-scl.md)

- **검토 중의** 가양성: 관리자 제출을 통해 Microsoft에서 여전히 분석하고 [](admin-submission.md) 있는 특정 메시지를 일시적으로 허용하여 Microsoft에 잘못 잘못된 것으로 잘못 표시된 알려진 좋은 메시지(가양성)를 보고할 수 있습니다. 모든 재지정과 함께 **** 이러한 허용은 임시로 지정하는 것이 좋습니다.

## <a name="security--compliance-center-powershell-procedures-for-secops-mailboxes-in-the-advanced-delivery-policy"></a>고급 & 정책의 SecOps 사서함에 대한 보안 및 준수 센터 PowerShell 절차

보안 & 준수 센터 PowerShell에서 고급 배달 정책의 SecOps 사서함의 기본 요소는 다음입니다.

- **SecOps override 정책**: **\* -SecOpsOverridePolicy** cmdlet에 의해 제어됩니다.
- **SecOps는** **\* -SecOpsOverrideRule** cmdlet에 의해 제어됩니다.

이 동작의 결과는 다음과 같습니다.

- 먼저 정책을 만든 다음 규칙이 적용되는 정책을 식별하는 규칙을 생성합니다.
- PowerShell에서 정책을 제거하면 해당 규칙도 제거됩니다.
- PowerShell에서 규칙을 제거하면 해당 정책이 제거되지 않습니다. 해당 정책을 수동으로 제거해야 합니다.

### <a name="use-powershell-to-configure-secops-mailboxes"></a>PowerShell을 사용하여 SecOps 사서함 구성

PowerShell의 고급 배달 정책에서 SecOps 사서함을 구성하는 과정은 2단계 프로세스입니다.

1. SecOps 재지정 정책을 생성합니다.
2. 규칙이 적용되는 정책을 지정하는 SecOps 다시 지정 규칙을 생성합니다.

#### <a name="step-1-use-powershell-to-create-the-secops-override-policy"></a>1단계: PowerShell을 사용하여 SecOps 재지정 정책 만들기

SecOps 재지정 정책을 만들 수 있는 구문은 다음과 같습니다.

```powershell
New-SecOpsOverridePolicy -Name SecOpsOverridePolicy -SentTo <EmailAddress1>,<EmailAddress2>,...<EmailAddressN>
```

> [!NOTE]
> 지정한 Name 값에 관계없이 정책 이름은 _SecOpsOverridePolicy가_.

이 예에서는 SecOps 사서함 정책을 만듭니다.

```powershell
New-SecOpsOverridePolicy -Name SecOpsOverridePolicy -SentTo secops@contoso.com
```

구문과 매개 변수에 대한 자세한 내용은 [New-SecOpsOverridePolicy를 참조하십시오.](/powershell/module/exchange/new-secopsoverridepolicy)

#### <a name="step-2-use-powershell-to-create-the-secops-override-rule"></a>2단계: PowerShell을 사용하여 SecOps 재지정 규칙 만들기

이 예에서는 지정된 설정을 사용하여 SecOps 사서함 규칙을 만듭니다.

```powershell
New-SecOpsOverrideRule -Name SecOpsOverrideRule -Policy SecOpsOverridePolicy
```

> [!NOTE]
> 지정한 이름 값에 관계없이 규칙 이름은 _SecOpsOverrideRule이_ 됩니다. 여기서 은 고유한 GUID 값입니다(예: \<GUID\> \<GUID\> 6fed4b63-3563-495d-a481-b24a311f8329).

구문과 매개 변수에 대한 자세한 내용은 [New-SecOpsOverrideRule을 참조하십시오.](/powershell/module/exchange/new-secopsoverriderule)

### <a name="use-powershell-to-view-the-secops-override-policy"></a>PowerShell을 사용하여 SecOps 재지정 정책 보기

이 예에서는 SecOps 사서함 정책 하나만에 대한 자세한 정보를 반환합니다.

```powershell
Get-SecOpsOverridePolicy
```

구문과 매개 변수에 대한 자세한 내용은 [Get-SecOpsOverridePolicy 를 참조하십시오.](/powershell/module/exchange/get-secopsoverridepolicy)

### <a name="use-powershell-to-view-secops-override-rules"></a>PowerShell을 사용하여 SecOps 재지정 규칙 보기

이 예에서는 SecOps 재지정 규칙에 대한 자세한 정보를 반환합니다.

```powershell
Get-SecOpsOverrideRule
```

이전 명령은 하나의 규칙만 반환해야 하지만, 보류 중인 모든 규칙이 결과에 포함될 수도 있습니다.

이 예에서는 유효한 규칙(하나)과 잘못된 규칙을 식별합니다.

```powershell
Get-SecOpsOverrideRule | Format-Table Name,Mode
```

잘못된 규칙을 식별한 후 이 문서 의 의 2부에서 설명하는 **Remove-SecOpsOverrideRule** cmdlet을 사용하여 제거할 [수 있습니다.](#use-powershell-to-remove-secops-override-rules)

구문과 매개 변수에 대한 자세한 내용은 [Get-SecOpsOverrideRule 을 참조하십시오.](/powershell/module/exchange/get-secopsoverriderule)

### <a name="use-powershell-to-modify-the-secops-override-policy"></a>PowerShell을 사용하여 SecOps 다시 설정 정책 수정

SecOps 다시 설정 정책을 수정하려면 다음 구문을 사용 합니다.

```powershell
Set-SecOpsOverridePolicy -Identity SecOpsOverridePolicy [-AddSentTo <EmailAddress1>,<EmailAddress2>,...<EmailAddressN>] [-RemoveSentTo <EmailAddress1>,<EmailAddress2>,...<EmailAddressN>]
```

이 예에서는 `secops2@contoso.com` SecOps 재지정 정책에 추가합니다.

```powershell
Set-SecOpsOverridePolicy -Identity SecOpsOverridePolicy -AddSentTo secops2@contoso.com
```

> [!NOTE]
> 연결된 유효한 SecOps 재지정 규칙이 있는 경우 규칙의 전자 메일 주소도 업데이트됩니다.

구문과 매개 변수에 대한 자세한 내용은 [Set-SecOpsOverridePolicy를 참조하십시오.](/powershell/module/exchange/set-secopsoverridepolicy)

### <a name="use-powershell-to-modify-a-secops-override-rule"></a>PowerShell을 사용하여 SecOps 다시 설정 규칙 수정

**Set-SecOpsOverrideRule** cmdlet은 SecOps override 규칙의 전자 메일 주소를 수정하지 않습니다. SecOps 다시 설정 규칙에서 전자 메일 주소를 수정하려면 **Set-SecOpsOverridePolicy** cmdlet을 사용합니다.

구문과 매개 변수에 대한 자세한 내용은 [Set-SecOpsOverrideRule을 참조하십시오.](/powershell/module/exchange/set-secopsoverriderule)

### <a name="use-powershell-to-remove-the-secops-override-policy"></a>PowerShell을 사용하여 SecOps 재지정 정책 제거

이 예에서는 SecOps 사서함 정책 및 해당 규칙을 제거합니다.

```powershell
Remove-SecOpsOverridePolicy -Identity SecOpsOverridePolicy
```

구문과 매개 변수에 대한 자세한 내용은 [Remove-SecOpsOverridePolicy를 참조하십시오.](/powershell/module/exchange/remove-secopsoverridepolicy)

### <a name="use-powershell-to-remove-secops-override-rules"></a>PowerShell을 사용하여 SecOps 재지정 규칙 제거

SecOps 재지정 규칙을 제거하려면 다음 구문을 사용 합니다.

```powershell
Remove-SecOpsOverrideRule -Identity <RuleIdentity>
```

이 예제에서는 지정한 SecOps 다시 지정 규칙을 제거합니다.

```powershell
Remove-SecOpsOverrideRule -Identity SecOpsOverrideRule6fed4b63-3563-495d-a481-b24a311f8329
```

구문과 매개 변수에 대한 자세한 내용은 [Remove-SecOpsOverrideRule을 참조하십시오.](/powershell/module/exchange/remove-secopsoverriderule)

## <a name="security--compliance-center-powershell-procedures-for-third-party-phishing-simulations-in-the-advanced-delivery-policy"></a>고급 & 정책의 타사 피싱 시뮬레이션에 대한 보안 및 준수 센터 PowerShell 절차

보안 & 준수 센터 PowerShell에서 고급 배달 정책의 타사 피싱 시뮬레이션의 기본 요소는 다음입니다.

- **피싱 시뮬레이션은** **\* -PhishSimOverridePolicy** cmdlet에 의해 제어됩니다.
- **피싱 시뮬레이션은** **\* -PhishSimOverrideRule** cmdlet에 의해 제어됩니다.
- **허용(차단되지 않은)** 피싱 시뮬레이션 URL: **\* -TenantAllowBlockListItems** cmdlet에 의해 제어됩니다.

이 동작의 결과는 다음과 같습니다.

- 먼저 정책을 만든 다음 규칙이 적용되는 정책을 식별하는 규칙을 생성합니다.
- 정책과 규칙의 설정을 별도로 수정합니다.
- PowerShell에서 정책을 제거하면 해당 규칙도 제거됩니다.
- PowerShell에서 규칙을 제거하면 해당 정책이 제거되지 않습니다. 해당 정책을 수동으로 제거해야 합니다.

### <a name="use-powershell-to-configure-third-party-phishing-simulations"></a>PowerShell을 사용하여 타사 피싱 시뮬레이션 구성

PowerShell에서 타사 피싱 시뮬레이션을 구성하는 과정은 여러 단계로 진행됩니다.

1. 피싱 시뮬레이션 은(는) 정책에 대한 피싱 시뮬레이션을 만들 수 있습니다.
2. 다음을 지정하는 피싱 시뮬레이션 에라이드 규칙을 만들 수 있습니다.
   - 규칙이 적용되는 정책입니다.
   - 피싱 시뮬레이션 메시지의 원본 IP 주소입니다.
3. 선택적으로 허용해야 하는 피싱 시뮬레이션 URL(차단되거나 검색되지 않은)을 ID로 입력합니다.

#### <a name="step-1-use-powershell-to-create-the-phishing-simulation-override-policy"></a>1단계: PowerShell을 사용하여 피싱 시뮬레이션 의회 정책 만들기

이 예에서는 피싱 시뮬레이션 오버라이드 정책을 만듭니다.

```powershell
New-PhishSimOverridePolicy -Name PhishSimOverridePolicy
```

**참고:** 지정한 이름 값에 관계없이 정책 이름은 _PhishSimOverridePolicy가_.

구문과 매개 변수에 대한 자세한 내용은 [New-PhishSimOverridePolicy 를 참조하십시오.](/powershell/module/exchange/new-phishsimoverridepolicy)

#### <a name="step-2-use-powershell-to-create-the-phishing-simulation-override-rule"></a>2단계: PowerShell을 사용하여 피싱 시뮬레이션재해 규칙 만들기

다음 구문을 사용합니다.

```powershell
New-PhishSimOverrideRule -Name PhishSimOverrideRule -Policy PhishSimOverridePolicy -SenderDomainIs <Domain1>,<Domain2>,...<DomainN> -SenderIpRanges <IPAddressEntry1>,<IPAddressEntry2>,...<IPAddressEntryN>
```

지정한 이름 값에 관계없이 규칙 이름은 _PhishSimOverrideRule이_ 됩니다. 여기서 은 고유한 GUID 값입니다(예: \<GUID\> \<GUID\> a0eae53e-d755-4a42-9320-b9c6b55c5011).

유효한 IP 주소 항목은 다음 값 중 하나입니다.

- 단일 IP: 예: 192.168.1.1.
- IP 범위: 예: 192.168.0.1-192.168.0.254.
- CIDR IP: 예: 192.168.0.1/25.

이 예제에서는 지정된 설정을 사용하여 피싱 시뮬레이션 에지 적용 규칙을 만듭니다.

```powershell
New-PhishSimOverrideRule -Name PhishSimOverrideRule -Policy PhishSimOverridePolicy -SenderDomainIs fabrikam.com,wingtiptoys.com -SenderIpRanges 192.168.1.55
```

구문과 매개 변수에 대한 자세한 내용은 [New-PhishSimOverrideRule 을 참조하십시오.](/powershell/module/exchange/new-phishsimoverriderule)

#### <a name="step-3-optional-use-powershell-to-identify-the-phishing-simulation-urls-to-allow"></a>3단계: (선택 사항) PowerShell을 사용하여 허용할 피싱 시뮬레이션 URL 식별

다음 구문을 사용합니다.

```powershell
New-TenantAllowBlockListItems -Allow -ListType Url -ListSubType AdvancedDelivery -Entries "<URL1>","<URL2>",..."<URLN>" <[-NoExpiration] | [-ExpirationDate <DateTime>]>
```

URL 구문에 대한 자세한 내용은 [테넌트 허용/차단 목록의 URL 구문을 참조하세요.](tenant-allow-block-list.md#url-syntax-for-the-tenant-allowblock-list)

이 예에서는 만료되지 않은 지정된 타사 피싱 시뮬레이션 URL에 대한 URL 허용 항목을 추가합니다.

```powershell
New-TenantAllowBlockListItems -Allow -ListType Url -ListSubType AdvancedDelivery -Entries *.fabrikam.com -NoExpiration
```

구문과 매개 변수에 대한 자세한 내용은 [New-TenantAllowBlockListItems를 참조하십시오.](/powershell/module/exchange/new-tenantallowblocklistitems)

### <a name="use-powershell-to-view-the-phishing-simulation-override-policy"></a>PowerShell을 사용하여 피싱 시뮬레이션에 대한 정책 보기

이 예에서는 피싱 시뮬레이션 재지정 정책 하나에 대한 자세한 정보를 반환합니다.

```powershell
Get-PhishSimOverridePolicy
```

구문과 매개 변수에 대한 자세한 내용은 [Get-PhishSimOverridePolicy를 참조하십시오.](/powershell/module/exchange/get-phishsimoverridepolicy)

### <a name="use-powershell-to-view-phishing-simulation-override-rules"></a>PowerShell을 사용하여 피싱 시뮬레이션에 대한 규칙 보기

이 예제에서는 피싱 시뮬레이션 재지정 규칙에 대한 자세한 정보를 반환합니다.

```powershell
Get-PhishSimOverrideRule
```

이전 명령은 하나의 규칙만 반환해야 하지만, 보류 중인 모든 규칙이 결과에 포함될 수도 있습니다.

이 예에서는 유효한 규칙(하나)과 잘못된 규칙을 식별합니다.

```powershell
Get-PhishSimOverrideRule | Format-Table Name,Mode
```

잘못된 규칙을 식별한 후 이 문서 의 나중에 설명하는 바와 같이 **Remove-PhishSimOverrideRule** cmdlet을 사용하여 제거할 [수 있습니다.](#use-powershell-to-remove-phishing-simulation-override-rules)

구문과 매개 변수에 대한 자세한 내용은 [Get-PhishSimOverrideRule 을 참조하십시오.](/powershell/module/exchange/get-phishsimoverriderule)

### <a name="use-powershell-to-view-the-allowed-phishing-simulation-url-entries"></a>PowerShell을 사용하여 허용된 피싱 시뮬레이션 URL 항목 보기

허용된 피싱 시뮬레이션 URL을 보기 위해 다음 명령을 실행합니다.

```powershell
Get-TenantAllowBlockListItems -ListType Url -ListSubType AdvancedDelivery
```

구문과 매개 변수에 대한 자세한 내용은 [Get-TenantAllowBlockListItems를 참조하십시오.](/powershell/module/exchange/get-tenantallowblocklistitems)

### <a name="use-powershell-to-modify-the-phishing-simulation-override-policy"></a>PowerShell을 사용하여 피싱 시뮬레이션에 대한 정책 수정

피싱 시뮬레이션을 수정하려면 다음 구문을 사용합니다.

```powershell
Set-PhishSimOverridePolicy -Identity PhishSimOverridePolicy [-Comment "<DescriptiveText>"] [-Enabled <$true | $false>]
```

이 예에서는 피싱 시뮬레이션 오버라이드 정책을 사용하지 않도록 설정합니다.

```powershell
Set-PhishSimOverridePolicy -Identity PhishSimOverridePolicy -Enabled $false
```

구문과 매개 변수에 대한 자세한 내용은 [Set-PhishSimOverridePolicy를 참조하십시오.](/powershell/module/exchange/set-phishsimoverridepolicy)

### <a name="use-powershell-to-modify-phishing-simulation-override-rules"></a>PowerShell을 사용하여 피싱 시뮬레이션 수정 규칙 수정

피싱 시뮬레이션 수정 규칙을 수정하려면 다음 구문을 사용합니다.

```powershell
Set-PhishSimOverrideRule -Identity PhishSimOverrideRulea0eae53e-d755-4a42-9320-b9c6b55c5011 [-Comment "<DescriptiveText>"] [-AddSenderDomainIs <DomainEntry1>,<DomainEntry2>,...<DomainEntryN>] [-RemoveSenderDomainIs <DomainEntry1>,<DomainEntry2>,...<DomainEntryN>] [-AddSenderIpRanges <IPAddressEntry1>,<IPAddressEntry2>,...<IPAddressEntryN>] [-RemoveSenderIpRanges <IPAddressEntry1>,<IPAddressEntry2>,...<IPAddressEntryN>]
```

이 예에서는 다음 설정을 사용하여 지정된 피싱 시뮬레이션 에지 적용 규칙을 수정합니다.

- 도메인 항목을 추가 blueyonderairlines.com.
- IP 주소 항목 192.168.1.55를 제거합니다.

이러한 변경 내용은 기존 항목에 영향을 주지 않습니다.

```powershell
Set-PhishSimOverrideRule -Identity PhishSimOverrideRulea0eae53e-d755-4a42-9320-b9c6b55c5011 -AddSenderDomainIs blueyonderairlines.com -RemoveSenderIpRanges 192.168.1.55
```

구문과 매개 변수에 대한 자세한 내용은 [Set-PhishSimOverrideRule을 참조하십시오.](/powershell/module/exchange/set-phishsimoverriderule)

### <a name="use-powershell-to-modify-the-allowed-phishing-simulation-url-entries"></a>PowerShell을 사용하여 허용된 피싱 시뮬레이션 URL 항목 수정

URL 값은 직접 수정할 수 없습니다. 이 [문서에 설명된](#use-powershell-to-remove-the-allowed-phishing-simulation-url-entries) 기존 URL 항목을 제거하고 새 [URL](#step-3-optional-use-powershell-to-identify-the-phishing-simulation-urls-to-allow) 항목을 추가할 수 있습니다.

허용된 피싱 시뮬레이션 URL 항목의 다른 속성(예: 만료 날짜 또는 설명)을 수정하려면 다음 구문을 사용합니다.

```powershell
Set-TenantAllowBlockListItems <-Entries "<URL1>","<URL2>",..."<URLN>" | -Ids <Identity>> -ListType URL -ListSubType AdvancedDelivery <[-NoExpiration] | [-ExpirationDate <DateTime>]> [-Notes <String>]
```

URL _값(Entries_ 매개 변수) 또는 **Get-TenantAllowBlockListItems** cmdlet의 출력에서 Identity 값(Ids  매개 변수)으로 수정할 항목을 식별합니다.

이 예제에서는 지정한 항목의 만료 날짜를 수정합니다.

```powershell
Set-TenantAllowBlockListItems -ListType Url -ListSubType AdvancedDelivery –Entries "*.fabrikam.com" -ExpirationDate 9/11/2021
```

구문과 매개 변수에 대한 자세한 내용은 [Set-TenantAllowBlockListItems를 참조하십시오.](/powershell/module/exchange/set-tenantallowblocklistitems)

### <a name="use-powershell-to-remove-a-phishing-simulation-override-policy"></a>PowerShell을 사용하여 피싱 시뮬레이션에 대한 정책 제거

이 예에서는 피싱 시뮬레이션재해 정책 및 해당 규칙을 제거합니다.

```powershell
Remove-PhishSimOverridePolicy -Identity PhishSimOverridePolicy
```

구문과 매개 변수에 대한 자세한 내용은 [Remove-PhishSimOverridePolicy를 참조하십시오.](/powershell/module/exchange/remove-phishsimoverridepolicy)

### <a name="use-powershell-to-remove-phishing-simulation-override-rules"></a>PowerShell을 사용하여 피싱 시뮬레이션에 대한 규칙 제거

피싱 시뮬레이션 오버라이드 규칙을 제거하려면 다음 구문을 사용합니다.

```powershell
Remove-PhishSimOverrideRule -Identity <RuleIdentity>
```

이 예제에서는 지정한 피싱 시뮬레이션 에보라이드 규칙을 제거합니다.

```powershell
Remove-PhishSimOverrideRule -Identity PhishSimOverrideRulea0eae53e-d755-4a42-9320-b9c6b55c5011
```

구문과 매개 변수에 대한 자세한 내용은 [Remove-PhishSimOverrideRule을 참조하십시오.](/powershell/module/exchange/remove-phishsimoverriderule)

### <a name="use-powershell-to-remove-the-allowed-phishing-simulation-url-entries"></a>PowerShell을 사용하여 허용된 피싱 시뮬레이션 URL 항목 제거

기존 피싱 시뮬레이션 URL 항목을 제거하려면 다음 구문을 사용합니다.

```powershell
Remove-TenantAllowBlockListItems <-Entries "<URL1>","<URL2>",..."<URLN>" | -Ids <Identity>> -ListType URL -ListSubType AdvancedDelivery
```

URL _값(Entries_ 매개 변수) 또는 **Get-TenantAllowBlockListItems** cmdlet의 출력에서 Identity 값(Ids  매개 변수)으로 수정할 항목을 식별합니다.

이 예제에서는 지정한 항목의 만료 날짜를 수정합니다.

```powershell
Remove-TenantAllowBlockListItems -ListType Url -ListSubType AdvancedDelivery –Entries "*.fabrikam.com" -ExpirationDate 9/11/2021
```

구문과 매개 변수에 대한 자세한 내용은 [Remove-TenantAllowBlockListItems를 참조하십시오.](/powershell/module/exchange/remove-tenantallowblocklistitems)


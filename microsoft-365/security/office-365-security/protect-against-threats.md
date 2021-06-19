---
title: 위협에 대한 보호
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: Admin
ms.topic: overview
localization_priority: Normal
ms.date: 09/08/2020
search.appverid:
- MOE150
- MET150
ms.assetid: b10023f6-f30f-45d3-b3ad-b71aa4aa0d58
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: 관리자는 조직의 위협 방지에 대해 Microsoft 365 조직에 대해 사용하는 방법을 구성할 수 있습니다.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 407838c815a85ce7c73322a0de176970ee93e537
ms.sourcegitcommit: c70067b4ef9c6f8f04aca68c35bb5141857c4e4b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/19/2021
ms.locfileid: "53029612"
---
# <a name="protect-against-threats"></a>위협에 대한 보호

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**적용 대상**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Office 365용 Microsoft Defender 플랜 1 및 플랜 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

다음은 2016에 대한 Defender의 구성을 청크로 Office 365 빠른 시작 가이드입니다. 새로운 위협 방지 기능을 Office 365 시작 위치를 잘 모를 수도 있으며, 를 수행하여 가장 잘 알 수 있는 경우 이 지침을 검사 목록 및 시작점으로 사용하세요.

> [!IMPORTANT]
> **각 정책 종류에** 대한 초기 권장 설정이 포함되어 있습니다. 그러나 많은 옵션을 사용할 수 있으며 특정 조직의 요구에 맞게 설정을 조정할 수 있습니다. 정책 또는 변경 사항이 데이터 센터를 통해 작동하도록 약 30분 동안 허용합니다.

## <a name="requirements"></a>요구 사항

### <a name="subscriptions"></a>구독

위협 방지 기능은 모든 *Microsoft* 또는 Office 365 포함되어 있습니다. 그러나 일부 구독에는 고급 기능이 있습니다. 아래 표에는 이 문서에 포함된 보호 기능과 최소 구독 요구 사항이 나열됩니다.

> [!TIP]
> 감사를 켜는 지시 이외에 단계는 **EOP(맬웨어** 방지) 의 일부로 표시된 맬웨어 방지, 피싱 방지 및 스팸 방지를 Office 365 Exchange Online Protection 있습니다.  (에 대한 **Defender** for Office 365) EOP를 포함하고 빌드할 때까지 이 문서에서 이 Office 365 이상한 것처럼 보일 수 있습니다.

<br>

****

|보호 유형|구독 요구 사항|
|---|---|
|감사 로깅(보고 목적으로)|[Exchange Online](/office365/servicedescriptions/exchange-online-service-description/exchange-online-service-description)|
|맬웨어 방지 보호 기능|[](/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description) **Exchange Online Protection(EOP)**|
|피싱 방지 보호 기능|[EOP](/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)|
|스팸 방지 보호 기능|[EOP](/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)|
|제로 아워 자동 제거(전자 메일용)|[EOP](/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)|
|전자 메일 및 전자 메일 문서의 악의적인 URL 및 Office 파일 보호(Safe 링크 및 Safe 첨부 파일)|[Office 365용 Microsoft Defender](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)|
|작업 Safe, SharePoint, OneDrive 및 Microsoft Teams 설정|[Office 365용 Microsoft Defender](turn-on-mdo-for-spo-odb-and-teams.md)|
|지능형 피싱 방지 보호|[Office 365용 Microsoft Defender](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)|

### <a name="roles-and-permissions"></a>역할 및 사용 권한

정책에 대해 Defender를 Office 365 보안 및 준수 센터에서 [적절한 역할을 & 합니다.](/office365/servicedescriptions/office-365-platform-service-description/office-365-securitycompliance-center) 아래 표에서 이러한 작업을 수행할 수 있는 역할을 확인하세요.

<br>

****

|역할 또는 역할 그룹|자세한 내용을 알아보는 위치|
|---|---|
|전역 관리자|[Microsoft 365 관리자 역할 정보](../../admin/add-users/about-admin-roles.md)|
|보안 관리자|[Azure Active Directory의 관리자 역할 권한](/azure/active-directory/users-groups-roles/directory-assign-admin-roles)|
|Exchange Online 조직 관리|[Exchange Online의 사용 권한](/exchange/permissions-exo/permissions-exo) <p> 및 <p> [Exchange Online PowerShell](/powershell/exchange/exchange-online-powershell)|
|

자세한 내용은 [Security & Compliance Center의 사용 권한을 참조합니다.](permissions-in-the-security-and-compliance-center.md)

### <a name="turn-on-audit-logging-for-reporting-and-investigation"></a>보고 및 조사에 대한 감사 로깅 켜기

- 감사 로깅을 조기 시작합니다. 다음 단계 중 일부에 대해 **감사를 ON으로** 해야 합니다. 감사 로깅은 을(를) 포함 하는 [구독에서 사용할 Exchange Online.](/office365/servicedescriptions/exchange-online-service-description/exchange-online-service-description) 보안 대시보드, 전자 메일 보안 보고서 [](security-dashboard.md)및 탐색기 등의 위협 [](threat-explorer.md)방지 보고서에서 데이터를 확인하려면 감사 로깅이 에 있어야 *합니다.* [](view-email-security-reports.md) 자세한 내용은 감사 로그 검색 켜기 또는 [끄기 를 참조합니다.](../../compliance/turn-audit-log-search-on-or-off.md)

## <a name="part-1---anti-malware-protection-in-eop"></a>1부 - EOP의 맬웨어 방지 보호

맬웨어 방지에 대한 권장 설정에 대한 자세한 내용은 EOP 맬웨어 방지 정책 [설정 을 참조하세요.](recommended-settings-for-eop-and-office365.md#eop-anti-malware-policy-settings)

1. 을 를 열 <https://security.microsoft.com/antimalwarev2> 수 있습니다

2. **맬웨어 방지 페이지에서** 이름을 클릭하여  기본 정책이라는 정책을 선택합니다.

3. 정책 세부 정보 플라이아웃이 열리면 보호 설정 편집을 **클릭하고** 다음 설정을 구성합니다.
   - 공통 **첨부 파일 필터** 사용 을 선택하여 공통 첨부 파일 필터를 켜야 합니다. 파일 **형식 사용자 지정을 클릭하여** 파일 형식을 더 추가합니다.
   - **맬웨어에 대한 제로 아워 자동 제거 사용이 선택되어 있는지** 확인
   - 알림 섹션의 설정이 **선택되어 있는지** 확인합니다.

   작업을 마쳤으면 **저장** 을 클릭합니다.

4. 정책 세부 정보 플라이아웃으로 돌아와 **닫기** 를 클릭합니다.

맬웨어 방지 정책을 구성하는 방법에 대한 자세한 내용은 EOP에서 맬웨어 방지 [정책 구성을 참조하세요.](configure-anti-malware-policies.md)

## <a name="part-2---anti-phishing-protection-in-eop-and-defender-for-office-365"></a>2부 - EOP의 피싱 방지 보호 기능 및 EOP용 Defender Office 365

[피싱 방지 보호는](anti-phishing-protection.md) EOP를 포함 하는 [구독에서 사용할 수 있습니다.](/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description) 고급 피싱 방지 보호는 에 대한 [Defender에서](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)사용할 수 Office 365.

피싱 방지 정책에 대한 권장 설정에 대한 자세한 내용은 [EOP](recommended-settings-for-eop-and-office365.md#eop-anti-phishing-policy-settings) 피싱 방지 정책 설정 및 Microsoft Defender for [Office 365.](recommended-settings-for-eop-and-office365.md#anti-phishing-policy-settings-in-microsoft-defender-for-office-365)

다음 절차에서는 기본 피싱 방지 정책을 구성하는 방법을 설명합니다. 설정 Defender에서만 사용할 수 있는 Office 365 명확하게 표시됩니다.

1. 을 를 열 <https://security.microsoft.com/antiphishing> 수 있습니다

2. 피싱 **방지 페이지에서** 이름을 클릭하여 **Office365 AntiPhish Default(기본값)라는** 정책을 선택합니다.

3. 나타나는 정책 세부 정보 플라이아웃에서 다음 설정을 구성합니다.

   - **피싱 임계값 &** 보호 섹션:  보호 설정 편집을 클릭하고  보호 설정 편집 플라이아웃에서 다음 설정을 구성합니다. 이 플라이아웃이 열립니다.
     - **피싱 전자 메일 임계값:** <sup>\*</sup> **2 - 적극적(표준)** 또는 **3 - 보다 적극적(엄격)을** 선택합니다.
     - **가장 섹션:** <sup>\*</sup> 다음 값을 구성합니다.
       - 사용자가 **보호할** 수 있도록 설정을 선택하고 나타나는 **(nn)** 보낸 사람 관리 링크를 클릭한 다음 조직의 보드 구성원, CEO, CFO 및 기타 고위 리더와 같은 가장으로부터 보호하기 위해 내부 및 외부 보낸 사람 추가를 선택합니다.
       - 을 **보호하려면** 도메인 사용 을 선택한 다음 나타나는 다음 설정을 구성합니다.
         - 허용 **도메인의** 내부 보낸 사람(내 도메인 보기 클릭)을 가장에서 보호하려면 소유한 도메인 포함을 선택합니다.
         - 다른 도메인의 보낸 사람 보호하려면 사용자 지정 도메인 포함을 선택하고 나타나는 **관리(nn)** 사용자 지정 도메인 링크를 클릭한 다음 가장으로부터 보호할 다른 도메인을 추가합니다. 
     - **신뢰할** 수 있는 보낸 사람 및 도메인 추가 <sup>\*</sup> 섹션: **관리(nn)** 신뢰할 수 있는 보낸 사람 및 도메인을 클릭하여 필요한 경우 가장 보호로 보낸 사람 및 보낸 사람 도메인 예외를 구성합니다.
     - 사서함 인텔리전스 설정: 사서함 인텔리전스 사용 및 가장 방지를 위한 인텔리전스 사용이 <sup>\*</sup> 선택되어 있는지  확인합니다. 
     - **스푸핑 섹션:** **스푸핑 인텔리전스 사용이 선택되어 있는지** 확인

     작업을 마쳤으면 **저장** 을 클릭합니다.

   - **작업** 섹션: 작업 **편집을** 클릭하고 작업 편집 플라이아웃에서 열리도록 다음 **설정을** 구성합니다.
     - **메시지 작업** 섹션: 다음 설정을 구성합니다.
       - **가장된** 사용자로 메시지가 검색된 경우 : 메시지 을 선택하여 을 <sup>\*</sup> **선택합니다.**
       - **가장된** 도메인으로 메시지가 검색된 경우 : 메시지 을 선택하여 을 <sup>\*</sup> **선택합니다.**
       - **사서함 인텔리전스에서** 가장된 사용자를 검색하는 경우 : 받는 사람의 정크 메일 폴더로 메시지 이동(표준) 또는 메시지 검역(엄격)을 <sup>\*</sup> 선택합니다.  
       - **메시지가 스푸핑으로** 검색된 경우  : 받는 사람의 정크 메일 폴더로 메시지  이동(표준) 또는 메시지 검량(엄격)을 선택합니다.
     - **안전 팁 & 표시기** 섹션: 다음 설정을 구성합니다.
       - **첫 번째 연락처 보안 팁**: 선택(켜기)을 선택합니다.
       - **사용자 가장 표시** 보안 팁 <sup>\*</sup> : 선택(켜기)을 선택합니다.
       - **도메인 가장 표시** <sup>\*</sup> 보안 팁 : 선택(켜기)을 선택합니다.
       - **사용자 가장 비정상 문자** 보안 팁 <sup>\*</sup> : 선택(켜기)을 선택합니다.
       - **스푸핑에** 대해 확인되지 않은 보낸 사람에 대한 표시(?) : 선택(켜기)을 선택합니다.
       - **"via" 태그 표시**: 선택(켜기)입니다.

     작업을 마쳤으면 **저장** 을 클릭합니다.

   <sup>\*</sup>이 설정은 사용자용 Defender에서만 사용할 Office 365.

4. **저장을** 클릭한 다음 **닫기 클릭**

피싱 방지 정책을 구성하는 방법에 대한 자세한 내용은 [EOP에서](configure-anti-phishing-policies-eop.md) 피싱 방지 정책 구성 및 Microsoft [Defender에서](configure-mdo-anti-phishing-policies.md)피싱 방지 정책 구성을 Office 365.

## <a name="part-3---anti-spam-protection-in-eop"></a>3부 - EOP의 스팸 방지 보호 기능

스팸 방지에 대한 권장 설정에 대한 자세한 내용은 EOP 스팸 방지 정책 [설정 을 참조하세요.](recommended-settings-for-eop-and-office365.md#eop-anti-spam-policy-settings)

1. 을 를 열 <https://security.microsoft.com/antispam> 수 있습니다

2. 스팸 **방지 정책** 페이지에서 이름을 클릭하여 목록에서 스팸 방지 인바운드 정책(기본값)이라는 정책을 선택합니다. 

3. 나타나는 정책 세부 정보 플라이아웃에서 다음 단계를 수행합니다.
   - **스팸 속성 & 대량** 전자 메일 임계값: 스팸 임계값 및 속성 **편집을 클릭합니다.** 나타나는 **스팸 임계값** 및 속성 플라이아웃에서  대량 전자 메일 임계값을 5(Strict) 또는 6(표준)으로 설정합니다. 작업을 마쳤으면 **저장** 을 클릭합니다.
   - **허용 및 차단된 보낸** 사람 및 도메인 섹션: 허용된 보낸 사람 및 허용 도메인을 검토하거나 편집합니다.

4. 작업을 마쳤으면 **닫기** 를 클릭합니다.

스팸 방지 정책을 구성하는 방법에 대한 자세한 내용은 [EOP에서 스팸 방지 정책 구성을 참조하세요.](configure-your-spam-filter-policies.md)

## <a name="part-4---protection-from-malicious-urls-and-files-safe-links-and-safe-attachments-in-defender-for-office-365"></a>4부 - 악의적인 URL 및 파일로부터 보호(Safe Defender의 링크 및 Safe 첨부 Office 365 파일)

악성 URL 및 파일로부터 클릭 시간 보호는 Microsoft [Defender for](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)Office 365. 첨부 파일 및 링크 Safe [정책을](safe-attachments.md) [통해 Safe](safe-links.md) 설정됩니다.

### <a name="safe-attachments-policies-in-microsoft-defender-for-office-365"></a>Safe Microsoft Defender for Office 365

첨부 파일을 [Safe](safe-attachments.md)하나 이상의 링크 정책을 Safe.

1. 보안 및 [& 센터에서](https://protection.office.com)위협  관리 정책 ATP 및 첨부 Safe 를 선택한 다음 \>  \> 만들기를 **클릭합니다.**

2. 나타나는 **새** Safe 첨부 파일 정책 마법사에서 다음 설정을 구성합니다.

   - 이름 **상자에** `Block malware` 를 입력하고 다음 을 **클릭합니다.**

   - 설정 **페이지에서** 다음 설정을 구성합니다.
     - 첨부 Safe 알 수 **없는 맬웨어 응답 섹션에서** 차단 을 **선택하세요.**
     - 첨부 파일 **리디렉션 섹션에서** 리디렉션 사용 **옵션을 선택합니다.** 검색된 파일을 검토할 조직의 보안 관리자 또는 운영자의 전자 메일 주소를 지정합니다.

     **다음** 을 클릭합니다.

3. 적용 **대상** 페이지에서 조건 추가를 클릭하고 적용 대상인 경우 적용을 **선택합니다.** 받는 사람 도메인이 입니다. **추가를** 클릭하고 도메인 또는 도메인을 선택하고 **추가,** 완료를 클릭한 후 다음을 **클릭합니다.**

4. 설정을 검토하고 마친 을 **클릭합니다.**

### <a name="safe-links-policies-in-microsoft-defender-for-office-365"></a>Safe Microsoft Defender for Office 365

링크 Safe [설정하려면](safe-links.md)Safe 링크에 대한 전역 설정을 검토하고 편집하고 하나 이상의 Safe 만들 수 있습니다.

1. 보안 & 준수 [센터에서](https://protection.office.com)위협  관리 정책 ATP Safe 링크를 선택하고 전역 설정을 클릭한 후 다음 설정을 \>  \> 구성합니다. 

   - 다음에서 **Safe 사용 확인:** Office 365 응용 프로그램이 켜져 있습니다. ![ 토글합니다. ](../../media/scc-toggle-on.png)
   - **사용자가 링크를 클릭하는 Safe** 추적하지 않습니다. 사용자 클릭을 추적하려면 이 설정을 해제합니다. ![ 토글 끄기. ](../../media/scc-toggle-off.png)
   - **사용자가 원래 URL에 대한 안전한** 링크를 클릭할 수 없습니다. 이 설정이 켜져 있는지 확인합니다. ![ 토글합니다. ](../../media/scc-toggle-on.png)

   작업을 마쳤으면 **저장** 을 클릭합니다.

2. 기본 Safe 페이지로 돌아가서 만들기를 **클릭합니다.**

3. 나타나는 **링크 Safe** 만들기 정책 마법사에서 다음 설정을 구성합니다.

   - 이름 **상자에** 과 같은 이름을 입력하고 `Safe Links` 다음 을 **클릭합니다.**

   - 설정 **페이지에서** 다음 설정을 구성합니다.
     - **메시지에서 알 수 없는 악의적인 URL에** 대한 작업 선택: 을 **선택합니다.**
     - **에서 알 수 없는 URL** 또는 잠재적으로 악의적인 URL에 대한 작업을 Microsoft Teams : 을 **선택합니다.**
     - **조직 내에서 보낸 전자 메일 메시지에 안전한 링크 적용**
     - **메시지를 배달하기 전에 URL 검색이 완료될 때까지 기다렸다가**
     - **조직 내에서 보낸 전자 메일 메시지에 안전한 링크 적용**
     - **사용자가 원래 URL을 클릭할 수 있도록 허용 안 하세요.**

     **다음** 을 클릭합니다.

4. 적용 **대상** 페이지에서 조건 추가를 클릭하고 적용 대상인 경우 적용을 **선택합니다.** 받는 사람 도메인이 입니다. **추가를** 클릭하고 도메인 또는 도메인을 선택하고 **추가,** 완료를 클릭한 후 다음을 **클릭합니다.**

5. 설정을 검토하고 마친 을 **클릭합니다.**

자세한 내용은 [안전한 링크 정책 설정](set-up-safe-links-policies.md)을 참조하세요.

## <a name="part-5---verify-safe-attachments-for-sharepoint-onedrive-and-microsoft-teams-is-turned-on"></a>5부 - Safe, SharePoint, OneDrive 및 Microsoft Teams 첨부 파일이 켜져 있는지 확인

SharePoint, OneDrive 및 Teams 작업은 공동 작업을 위해 구축됩니다. 팀 사이트에 Defender를 Office 365 팀 사이트 및 문서 라이브러리에서 악성으로 식별된 파일을 차단하고 검색하는 데 도움이 됩니다. 작동 방식에 대한 자세한 내용은 을(를) 읽어 [볼 수 있습니다.](mdo-for-spo-odb-and-teams.md)

> [!IMPORTANT]
> **이 절차를 시작하기** 전에 사용자 환경 에 대해 감사 로깅이 Microsoft 365 합니다. 이 작업은 일반적으로 감사 로그 역할이 할당된 사용자가 Exchange Online. 자세한 내용은 감사 로그 검색 켜기 또는 [끄기!를 참조하세요.](../../compliance/turn-audit-log-search-on-or-off.md)

1. 보안 및 [& 센터에서](https://protection.office.com)위협  관리 정책 ATP Safe 첨부 파일을 선택한 다음 \>  \> **전역** 설정을 **클릭합니다.**

2. Office 365, SharePoint, OneDrive 및 Microsoft Teams 토글에 대한 **Defender** 켜기 설정이 오른쪽에 있는지 확인: ![ 을 토글하고 ](../../media/scc-toggle-on.png) 저장을 **클릭합니다.**

3. 조직의 첨부 파일 정책 및 Safe 정책 [](set-up-safe-attachments-policies.md) 및 링크 정책을 Safe [검토합니다(적절한 경우 편집).](set-up-safe-links-policies.md)

4. (권장) 전역 관리자 또는 SharePoint Online 관리자로서 _DisallowInfectedFileDownload_ 매개 변수를 로 설정하여 **[Set-SPOTenant](/powershell/module/sharepoint-online/Set-SPOTenant)** cmdlet을 실행합니다. `$true`

   - `$true` 검색된 파일에 대한 모든 작업(삭제 제외)을 차단합니다. 검색된 파일을 열거나 이동, 복사 또는 공유할 수 없습니다.
   - `$false` 삭제 및 다운로드를 제외한 모든 작업을 차단합니다. 사람들은 위험을 수락하고 검색된 파일을 다운로드할 수 있습니다.

   > [!TIP]
   > PowerShell과 함께 PowerShell을 사용하는 Microsoft 365 자세한 내용은 [PowerShell을 사용하여 Microsoft 365 관리를 참조합니다.](../../enterprise/manage-microsoft-365-with-microsoft-365-powershell.md)

5. 모든 데이터 센터에 변경 내용을 분산하는 데 최대 30분 Microsoft 365 수 있습니다.

### <a name="now-set-up-alerts-for-detected-files"></a>이제 검색된 파일에 대한 경고 설정

SharePoint Online, 비즈니스용 OneDrive 또는 Microsoft Teams 파일이 악성으로 식별된 경우 알림을 받으면 경고를 설정할 수 있습니다.

1. 보안 및 [& 센터에서](https://protection.office.com) **경고** 관리 \> **를 선택 합니다.**

2. 새 **경고 정책 을 선택 합니다.**

3. 경고의 이름을 지정합니다. 예를 들어 라이브러리에 악성 파일을 입력할 수 있습니다.

4. 경고에 대한 설명을 입력합니다. 예를 들어 online, SharePoint 또는 OneDrive 파일에서 악성 파일이 검색되면 관리자에게 OneDrive 수 Microsoft Teams.

5. 다음의 **경우 이 경고 보내기... 섹션에서** 다음을 설정하세요.

   a. 활동 **목록에서** **파일에서 검색된 맬웨어를 선택합니다.**

   b. 사용자 **필드는 비워** 두면 됩니다.

6. 이 **알림 보내기...** 섹션에서 악의적인 파일이 감지될 때 알림을 수신해야 하는 전역 관리자, 보안 관리자 또는 보안 독자를 하나 이상 선택합니다.

7. **를 저장합니다.**

경고에 대한 자세한 내용은 보안 및 준수 센터에서 활동 [& 참조합니다.](../../compliance/create-activity-alerts.md)

> [!NOTE]
> 구성이 완료되면 다음 링크를 사용하여 작업 조사를 시작하세요.
>
>- [위협 방지 상태 보고서](view-email-security-reports.md#threat-protection-status-report)
>- [Microsoft 365 Defender 포털을 사용하여 Defender for Office 365](manage-quarantined-messages-and-files.md#use-the-microsoft-365-defender-portal-to-manage-quarantined-files-in-defender-for-office-365)
>- [SharePoint Online, OneDrive 또는 Microsoft Teams](https://support.microsoft.com/office/01e902ad-a903-4e0f-b093-1e1ac0c37ad2)
>- [2016년 8월에 관리자로 quarantined messages and files Microsoft 365](manage-quarantined-messages-and-files.md)

## <a name="part-6---additional-settings-to-configure"></a>6부 - 구성할 추가 설정

맬웨어, 악의적인 URL 및 파일, 피싱 및 스팸으로부터 보호를 구성하는 것과 함께 제로 아워 자동 제거를 구성하는 것이 좋습니다.

### <a name="zero-hour-auto-purge-for-email-in-eop"></a>EOP에서 전자 메일에 대한 제로 아워 자동 제거

[ZAP(제로](zero-hour-auto-purge.md) 아워 자동 제거)는 EOP를 포함 하는 [구독에서 사용할 수 있습니다.](/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description) 이 보호는 기본적으로 켜져 있습니다. 그러나 보호를 적용하려면 다음 조건을 충족해야 합니다.

- 스팸 작업은 스팸 방지 정책에서 메시지를 **정크** 메일 폴더로 [이동으로 설정됩니다.](anti-spam-protection.md)

- 사용자는 기본 정크 메일 설정을 유지하며 정크 메일 보호를 해제하지 않습니다. [](configure-junk-email-settings-on-exo-mailboxes.md)

자세한 내용은 제로 아워 자동 제거 - 스팸 및 맬웨어로부터 [보호를 참조합니다.](zero-hour-auto-purge.md)

## <a name="post-setup-tasks-and-next-steps"></a>설치 후 작업 및 다음 단계

위협 방지 기능을 구성한 후 해당 기능이 작동되는 방법을 모니터링해야 합니다. 필요한 작업을 할 수 있도록 정책을 검토하고 변경합니다. 또한 가치를 추가할 수 있는 새로운 기능 및 서비스 업데이트를 확인합니다.

****

|수행할 작업|자세한 정보를 알아볼 수 있는 리소스|
|---|---|
|보고서를 확인하여 위협 방지 기능이 조직에 어떻게 작동하고 있는지 확인|[보안 대시보드](security-dashboard.md) <p> [전자 메일 보안 보고서](view-email-security-reports.md) <p> [Microsoft Defender for Office 365](view-reports-for-mdo.md) <p> [위협 탐색기](threat-explorer.md)|
|필요한 경우 위협 방지 정책을 주기적으로 검토하고 변경합니다.|[Secure Score](../defender/microsoft-secure-score.md) <p> [스마트 보고서 및 인사이트](reports-and-insights-in-security-and-compliance.md) <p> [Microsoft 365 조사 및 대응 기능](./office-365-ti.md)|
|새로운 기능 및 서비스 업데이트 감시|[표준 및 대상 지정 릴리스 옵션](../../admin/manage/release-options-in-office-365.md) <p> [메시지 센터](../../admin/manage/message-center.md) <p> [Microsoft 365 로드맵](https://www.microsoft.com/microsoft-365/roadmap?filters=&searchterms=advanced%2Cthreat%2Cprotection) <p> [서비스 설명](/office365/servicedescriptions/office-365-service-descriptions-technet-library)|
|EOP 및 Defender for Office 365|[EOP 및 Microsoft Defender 보안에 대한 Office 365 설정](recommended-settings-for-eop-and-office365.md)|

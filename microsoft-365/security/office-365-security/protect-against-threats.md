---
title: 위협으로부터 보호
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
ms.openlocfilehash: 438200f3f8a6a846d49bc397d6a4b0a0a33cad40
ms.sourcegitcommit: 686f192e1a650ec805fe8e908b46ca51771ed41f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/24/2021
ms.locfileid: "52624624"
---
# <a name="protect-against-threats"></a>위협으로부터 보호

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

****

|보호 유형|구독 요구 사항|
|---|---|
|감사 로깅(보고 목적으로)|[Exchange Online](/office365/servicedescriptions/exchange-online-service-description/exchange-online-service-description)|
|맬웨어 방지 보호 기능|[](/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description) **Exchange Online Protection(EOP)**|
|피싱 방지 보호 기능|[EOP](/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)|
|스팸 방지 보호 기능|[EOP](/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)|
|제로 아워 자동 제거(전자 메일용)|[EOP](/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)|
|전자 메일 및 전자 메일의 악의적인 URL 및 Office 보호(안전한 링크 및 안전한 첨부 파일)|[Office 365용 Microsoft Defender](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)|
|작업 부하, SharePoint, OneDrive 및 Microsoft Teams 설정|[Office 365용 Microsoft Defender](turn-on-mdo-for-spo-odb-and-teams.md)|
|지능형 피싱 방지 보호|[Office 365용 Microsoft Defender](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)|

### <a name="roles-and-permissions"></a>역할 및 사용 권한

정책에 대해 Defender를 Office 365 보안 및 준수 센터에서 [적절한 역할을 & 합니다.](/office365/servicedescriptions/office-365-platform-service-description/office-365-securitycompliance-center) 아래 표에서 이러한 작업을 수행할 수 있는 역할을 확인하세요.

****

|역할 또는 역할 그룹|자세한 내용을 알아보는 위치|
|---|---|
|전역 관리자|[Microsoft 365 관리자 역할 정보](../../admin/add-users/about-admin-roles.md)|
|보안 관리자|[Azure Active Directory의 관리자 역할 권한](/azure/active-directory/users-groups-roles/directory-assign-admin-roles)|
|Exchange Online 조직 관리|[Exchange Online의 사용 권한](/exchange/permissions-exo/permissions-exo) <p> 및 <p> [Exchange Online PowerShell](/powershell/exchange/exchange-online-powershell)|
|

자세한 내용은 [Security & Compliance Center의 사용 권한을 참조합니다.](permissions-in-the-security-and-compliance-center.md)

## <a name="before-you-begin-turn-on-audit-logging-for-reporting-and-investigation"></a>시작하기 전에 보고 및 조사에 대한 감사 로깅 켜기

감사 로깅을 조기 시작합니다. 다음과 같은 특정 단계에 대한 감사를 **ON으로** 해야 합니다. 감사 로깅은 을(를) 포함 하는 [구독에서 사용할 Exchange Online.](/office365/servicedescriptions/exchange-online-service-description/exchange-online-service-description) 보안 대시보드, 전자 메일 보안 보고서 [](security-dashboard.md)및 탐색기 등의 위협 [](threat-explorer.md)방지 보고서에서 데이터를 확인하려면 감사 로깅이 에 있어야 *합니다.* [](view-email-security-reports.md) 자세한 내용은 감사 로그 검색 켜기 또는 [끄기 를 참조합니다.](../../compliance/turn-audit-log-search-on-or-off.md)

## <a name="part-1---anti-malware-protection"></a>1부 - 맬웨어 방지 보호

[맬웨어 방지 보호는](anti-malware-protection.md) EOP를 포함 하는 [구독에서 사용할 수 있습니다.](/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)

1. 보안 및 [& 센터에서](https://protection.office.com)위협 관리 정책 맬웨어 방지  \>  \> **를 선택 합니다.**

2. 기본 정책을 **두 번** 클릭한 다음 설정을 **선택합니다.**

3. 다음 설정을 지정합니다.

    - **맬웨어 검색 응답 섹션에서** 기본 설정을 **아니요로 지정합니다.**

    - 일반 **첨부 파일 형식 필터 섹션에서** 을 **선택 합니다.**

4. **저장** 을 클릭합니다.

맬웨어 방지 정책 옵션에 대한 자세한 내용은 맬웨어 방지 정책 [구성을 참조하세요.](configure-anti-malware-policies.md)

## <a name="part-2---anti-phishing-protection"></a>2부 - 피싱 방지 보호 기능

[피싱 방지 보호는](anti-phishing-protection.md) EOP를 포함 하는 [구독에서 사용할 수 있습니다.](/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description) 고급 피싱 방지 보호는 에 대한 [Defender에서](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)사용할 수 Office 365.

다음 절차에서는 Microsoft Defender에서 피싱 방지 정책을 구성하는 방법을 Office 365. 단계는 EOP에서 피싱 방지 정책을 구성하는 경우와 비슷합니다.

1. 보안 및 [& 센터에서](https://protection.office.com)위협 **관리** 정책 피싱 방지 \>  \> **를 선택 합니다.**

2. 기본 **정책을 클릭합니다.**

3. 가장 **섹션에서** 편집을 **클릭하고** 다음 설정을 지정합니다.

   - 보호할 **사용자 추가 탭에서** 보호 *켜기를* 니다. 그런 다음 조직의 보드 구성원, CEO, CFO 및 기타 고위 리더와 같은 사용자를 추가합니다. 개별 전자 메일 주소를 입력하거나 클릭하여 목록을 표시할 수 있습니다.

   - 보호할 **도메인 추가 탭에서** 소유한 도메인이 자동으로 **포함을 으로 니다.** 사용자 지정 도메인이 있는 경우 지금 추가합니다.

   - 작업 **탭에서** 가장된 사용자 및 가장된 도메인 옵션 둘 다에 대한 메시지  **검역을** 선택합니다.  또한 가장 보안 팁을 켜세요.

   - 사서함 **인텔리전스 탭에서** 사서함 인텔리전스가 켜져 있는지 확인한 다음 사서함 인텔리전스 기반 가장 보호를 켜야 합니다. 가장된  사용자가 전자 메일을 보낸 경우 목록에서 메시지 **검역을 선택합니다.**

   - 신뢰할 **수 있는 보낸** 사람 및 도메인 추가 탭에서 추가할 신뢰할 수 있는 보낸 사람 또는 도메인을 지정합니다.

   - **설정을** **검토한** 후 설정 검토 탭에 저장합니다.

4. **스푸핑 섹션에서** 편집을 **클릭하고** 다음 설정을 지정합니다.

   - 스푸핑 필터 **설정 탭에서** 스푸핑 방지 보호가 켜져 있는지 확인합니다.

   - 작업 **탭에서** 메시지 **를 Quarantine (을) 선택합니다.**

   - **변경** 내용을  검토한 후 설정 검토 탭에 저장합니다. (변경하지 않은 경우 **취소**.)

5. 기본 정책 설정 페이지를 닫습니다.

피싱 방지 정책 옵션에 대한 자세한 내용은 Microsoft [Defender에서](configure-atp-anti-phishing-policies.md)피싱 방지 정책 구성을 Office 365.

## <a name="part-3---anti-spam-protection"></a>3부 - 스팸 방지 보호

[스팸 방지 보호는](anti-spam-protection.md) EOP를 포함 하는 [구독에서 사용할 수 있습니다.](/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)

1. 보안 및 [& 센터에서](https://protection.office.com)위협 **관리** 정책 스팸 방지 \>  \> **를 선택 합니다.**

2. 사용자 지정 **탭에서** 사용자 지정 설정을 니다.

3. 기본 **스팸 필터 정책을 확장하고** 정책 **편집을** 클릭한 후 다음 설정을 지정합니다.

   - 스팸 **및 대량 작업** 섹션에서 임계값을 5 또는 6으로 설정합니다.

   - 허용 **목록 섹션에서** 허용된 보낸 사람 및 도메인을 검토(및/또는 편집)합니다.

4. **저장** 을 클릭합니다.

스팸 방지 정책 옵션에 대한 자세한 내용은 [EOP에서 스팸 방지 정책 구성을 참조하세요.](configure-your-spam-filter-policies.md)

## <a name="part-4---protection-from-malicious-urls-and-files-safe-links-and-safe-attachments-in-defender-for-office-365"></a>4부 - 악의적인 URL 및 파일로부터 보호(안전한 링크 및 안전한 첨부 파일 for Office 365)

악성 URL 및 파일로부터 클릭 시간 보호는 Microsoft [Defender for](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)Office 365. 안전한 첨부 파일 및 [안전한](safe-attachments.md) 링크 [정책을 통해 설정됩니다.](safe-links.md)

### <a name="safe-attachments-policies-in-microsoft-defender-for-office-365"></a>Microsoft Defender for Office 365

안전한 첨부 파일을 [설정하기 위해](safe-attachments.md)하나 이상의 안전한 링크 정책을 만드시다.

1. 보안 및 [& 센터에서](https://protection.office.com) **위협** 관리 정책 ATP 안전한 첨부 파일을 선택한 \>  \> 다음 만들기를 **클릭합니다.**

2. 나타나는 **새 안전** 첨부 파일 정책 마법사에서 다음 설정을 구성합니다.

   - 이름 **상자에** `Block malware` 를 입력하고 다음 을 **클릭합니다.**

   - 설정 **페이지에서** 다음 설정을 구성합니다.
     - 안전한 첨부 **파일 알 수 없는 맬웨어 응답 섹션에서** 차단 을 선택 **합니다.**
     - 첨부 파일 **리디렉션 섹션에서** 리디렉션 사용 **옵션을 선택합니다.** 검색된 파일을 검토할 조직의 보안 관리자 또는 운영자의 전자 메일 주소를 지정합니다.

     **다음** 을 클릭합니다.

3. 적용 **대상** 페이지에서 조건 추가를 클릭하고 적용 대상인 경우 적용을 **선택합니다.** 받는 사람 도메인이 입니다. **추가를** 클릭하고 도메인 또는 도메인을 선택하고 **추가,** 완료를 클릭한 후 다음을 **클릭합니다.**

4. 설정을 검토하고 마친 을 **클릭합니다.**

### <a name="safe-links-policies-in-microsoft-defender-for-office-365"></a>Microsoft Defender for Office 365

안전한 링크를 [설정하려면](safe-links.md)안전한 링크에 대한 전역 설정을 검토 및 편집하고 안전한 링크 정책을 하나 이상 만들 수 있습니다.

1. 보안 및 [&](https://protection.office.com)센터에서 **위협** 관리 정책 ATP 안전한 링크를 선택하고 전역 설정을 클릭한 후 다음 설정을 \>  \> 구성합니다. 

   - 다음에서 안전한 링크 사용 **확인: Office 365** 응용 프로그램이 켜져 있는지 확인: ![ 을 토글합니다. ](../../media/scc-toggle-on.png)
   - 사용자가 안전한 링크를 **클릭하는** 경우 추적하지 않습니다. 사용자 클릭을 추적하려면 이 설정을 해제합니다. ![ 토글 끄기. ](../../media/scc-toggle-off.png)
   - **사용자가 원래 URL에 대한 안전한** 링크를 클릭할 수 없습니다. 이 설정이 켜져 있는지 확인합니다. ![ 토글합니다. ](../../media/scc-toggle-on.png)

   작업을 마쳤으면 **저장** 을 클릭합니다.

2. 기본 안전한 링크 페이지에서 만들기를 **클릭합니다.**

3. 나타나는 **안전한** 링크 만들기 정책 마법사에서 다음 설정을 구성합니다.

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

## <a name="part-5---verify-safe-attachments-for-sharepoint-onedrive-and-microsoft-teams-is-turned-on"></a>5부 - 설정되어 있는 SharePoint, OneDrive 및 Microsoft Teams 첨부 파일 확인

SharePoint, OneDrive 및 Teams 작업은 공동 작업을 위해 구축됩니다. 팀 사이트에 Defender를 Office 365 팀 사이트 및 문서 라이브러리에서 악성으로 식별된 파일을 차단하고 검색하는 데 도움이 됩니다. 작동 방식에 대한 자세한 내용은 을(를) 읽어 [볼 수 있습니다.](mdo-for-spo-odb-and-teams.md)

> [!IMPORTANT]
> **이 절차를 시작하기** 전에 사용자 환경 에 대해 감사 로깅이 Microsoft 365 합니다. 이 작업은 일반적으로 감사 로그 역할이 할당된 사용자가 Exchange Online. 자세한 내용은 감사 로그 검색 켜기 또는 [끄기!를 참조하세요.](../../compliance/turn-audit-log-search-on-or-off.md)

1. 보안 및 [& 센터에서](https://protection.office.com) **위협** 관리 정책 \>  \> **ATP 안전한** 첨부 파일을 선택한 다음 전역 설정을 **클릭합니다.**

2. Office 365, SharePoint, OneDrive 및 Microsoft Teams 토글에 대한 **Defender** 켜기 설정이 오른쪽에 있는지 확인: ![ 을 토글하고 ](../../media/scc-toggle-on.png) 저장을 **클릭합니다.**

3. 조직의 안전 첨부 파일 정책 및 안전한 [](set-up-safe-attachments-policies.md) 링크 정책을 검토하고 적절하게 [편집합니다.](set-up-safe-links-policies.md)

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
>- [보안 및 & 센터를 사용하여 분리된 파일 관리](manage-quarantined-messages-and-files.md#microsoft-defender-for-office-365-only-use-the-security--compliance-center-to-manage-quarantined-files)
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

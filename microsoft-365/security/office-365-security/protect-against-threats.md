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
description: 관리자는 Microsoft 365의 위협 방지에 대해 알아보고 조직에 위협 보호를 사용하는 방법을 구성할 수 있습니다.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: cb2866fd3e60c021ae89ffabe7149f4b415d63bc
ms.sourcegitcommit: e920e68c8d0eac8b152039b52cfc139d478a67b3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/09/2021
ms.locfileid: "50150715"
---
# <a name="protect-against-threats"></a>위협으로부터 보호

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**적용 대상**
- [Exchange Online Protection](https://go.microsoft.com/fwlink/?linkid=2148611)
- [Microsoft Defender for Office 365 요금제 1 및 계획 2](https://go.microsoft.com/fwlink/?linkid=2148715)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

다음은 Office 365용 Defender의 구성을 청크로 끊는 빠른 시작 가이드입니다. Office 365의 위협 방지 기능을 새로 사용하는 경우 어디서부터 시작해야 할지, 아니면 가장 잘 알 수 있는 경우 이 지침을 검사 목록 및 시작점으로 사용하세요. 

> [!IMPORTANT]
> **각 정책 종류에** 대한 초기 권장 설정이 포함되어 있습니다. 그러나 많은 옵션을 사용할 수 있으며 특정 조직의 요구에 맞게 설정을 조정할 수 있습니다. 정책 또는 변경 내용이 데이터 센터를 통해 작동하도록 약 30분 동안 허용합니다.

## <a name="requirements"></a>요구 사항

### <a name="subscriptions"></a>구독

위협 방지 기능은 모든 *Microsoft* 또는 Office 365 구독에 포함되어 있습니다. 그러나 일부 구독에는 고급 기능이 있습니다. 아래 표에는 최소 구독 요구 사항과 함께 이 문서에 포함된 보호 기능이 나열됩니다.

> [!TIP]
> 감사를 켜는 방법 이외에 Office 365 **EOP(Exchange** Online Protection)의 일부로 표시된 맬웨어 방지, 피싱 방지 및 스팸 방지를 시작하는 단계가 있습니다.  이는 기억할 때까지 Office 365용 Defender 문서에서 이상한 것처럼 보일 수 **있습니다(Office 365용 Defender)에** EOP가 포함되어 빌드될 때까지.

****

|보호 유형|구독 요구 사항|
|---|---|
|감사 로깅(보고용)|[Exchange Online](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-service-description)|
|맬웨어 방지 보호 기능|[EOP(Exchange Online Protection)](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description) |
|피싱 방지 보호 기능|[EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)|
|스팸 방지 보호 기능|[EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)|
|제로 아워 자동 비우기(전자 메일의 경우)|[EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)|
|전자 메일 및 Office 문서의 악의적인 URL 및 파일 보호(안전한 링크 및 안전한 첨부 파일)|[Office 365용 Microsoft Defender](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)|
|SharePoint, OneDrive 및 Microsoft Teams 워크로드에 대한 안전한 첨부 파일 켜기|[Office 365용 Defender ](atp-for-spo-odb-and-teams.md)|
|고급 피싱 방지 보호 기능|[Office 365용 Defender](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)|

### <a name="roles-and-permissions"></a>역할 및 사용 권한

Office 365 정책에 대한 Defender를 구성하려면 보안 및 준수 센터에서 적절한 [역할을 & 합니다.](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-securitycompliance-center) 아래 표에서 이러한 작업을 수행할 수 있는 역할을 살펴보세요.

****

|역할 또는 역할 그룹|자세한 내용을 알아보는 위치|
|---|---|
|전역 관리자|[Microsoft 365 관리자 역할 정보](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles)|
|보안 관리자|[Azure Active Directory의 관리자 역할 권한](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)|
|Exchange Online 조직 관리|[Exchange Online의 사용 권한](https://docs.microsoft.com/exchange/permissions-exo/permissions-exo) <p> 및 <p> [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell)|
|

자세한 내용은 보안 및 준수 [센터의 & 참조합니다.](permissions-in-the-security-and-compliance-center.md)

## <a name="before-you-begin-turn-on-audit-logging-for-reporting-and-investigation"></a>시작하기 전에 보고 및 조사에 대한 감사 로깅 켜기

감사 로깅을 조기 시작해야 합니다. 다음과 같은 특정 단계에 대한 감사를 **ON으로** 해야 합니다. 감사 로깅은 Exchange Online이 포함된 [구독에서 사용할 수 있습니다.](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-service-description) 보안 대시보드, 전자 메일 보안 보고서, 탐색기 [](view-email-security-reports.md)등의 위협 [](threat-explorer.md)방지 보고서에서 데이터를 확인하려면 감사 로깅이 설정되어 있어야 *합니다.* [](security-dashboard.md) 자세한 내용은 감사 로그 검색 설정 [또는 해제를 참조합니다.](../../compliance/turn-audit-log-search-on-or-off.md)

## <a name="part-1---anti-malware-protection"></a>1부 - 맬웨어 방지 보호

[맬웨어 방지 보호는](anti-malware-protection.md) EOP를 포함 하는 [구독에서 사용할 수 있습니다.](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)

1. 보안 및 [& 센터에서](https://protection.office.com)위협 관리 정책 맬웨어  \>  \> **방지를 선택하십시오.**

2. 기본 정책을 두 **번** 클릭한 다음 설정을 **선택합니다.**

3. 다음 설정을 지정합니다.

    - **맬웨어 검색 응답 섹션에서** 기본 설정을 **No로 유지하십시오.**

    - 일반 첨부 **파일 형식 필터** 섹션에서 **을(를) 선택하십시오.**

4. **저장** 을 클릭합니다.

맬웨어 방지 정책 옵션에 대한 자세한 내용은 맬웨어 방지 정책 [구성을 참조하세요.](configure-anti-malware-policies.md)

## <a name="part-2---anti-phishing-protection"></a>2부 - 피싱 방지 보호 기능

[피싱](anti-phishing-protection.md) 방지 보호는 EOP를 포함 하는 [구독에서 사용할 수 있습니다.](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description) Office [365용 Defender에서](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)고급 피싱 방지 보호 기능을 사용할 수 있습니다.

다음 절차에서는 Office 365용 Microsoft Defender에서 피싱 방지 정책을 구성하는 방법을 설명합니다. 이 단계는 EOP에서 피싱 방지 정책을 구성하는 경우와 비슷합니다.

1. 보안 및 [& 센터에서](https://protection.office.com)위협 **관리** 정책 ATP 피싱 \>  \> **방지를 선택 합니다.**

2. 기본 **정책을 클릭합니다.**

3. 가장 **섹션에서** 편집을 클릭한 다음 다음 설정을 지정합니다. 

   - 탭을 **보호할 사용자 추가에서** *보호를 니다.* 그런 다음 조직의 보드 구성원, CEO, CFO 및 기타 고위 리더와 같은 사용자를 추가합니다. 개별 전자 메일 주소를 입력하거나 클릭하여 목록을 표시할 수 있습니다.

   - 보호할 **도메인** 추가 탭에서 내 소유의 도메인을 자동으로 **포함합니다.** 사용자 지정 도메인이 있는 경우 지금 추가합니다.

   - 작업 **탭에서** 가장된 사용자 및 가장된  도메인 옵션 둘 다에 대한 메시지의 **검역을** 선택합니다.  또한 가장 보안 팁을 켜세요.

   - 사서함 **인텔리전스** 탭에서 사서함 인텔리전스가 켜져 있는지 확인한 다음 사서함 인텔리전스 기반 가장 보호를 니다. In the **If email is sent by an impersonated user** list, choose **Quarantine the message.**

   - 신뢰할 수 **있는 보낸** 사람 및 도메인 추가 탭에서 추가할 신뢰할 수 있는 보낸 사람 또는 도메인을 지정합니다.

   - **설정을** **검토한** 후 설정 검토 탭에 저장합니다.

4. **스푸핑 섹션에서** 편집을 클릭한 다음 다음 설정을 지정합니다. 

   - **스푸핑** 필터 설정 탭에서 스푸핑 방지 보호가 켜져 있는지 확인합니다.

   - 작업 **탭에서** 메시지를 **Quarantine (1)로 선택합니다.**

   - **변경** 내용을 **검토한** 후 설정 검토 탭에 저장합니다. 변경하지 않은 경우 취소 **.)**

5. 기본 정책 설정 페이지를 닫습니다.

피싱 방지 정책 옵션에 대한 자세한 내용은 [Microsoft Defender for Office 365에서](configure-atp-anti-phishing-policies.md)피싱 방지 정책 구성을 참조하세요.

## <a name="part-3---anti-spam-protection"></a>3부 - 스팸 방지 보호 기능

[스팸 방지 보호는](anti-spam-protection.md) EOP를 포함 하는 [구독에서 사용할 수 있습니다.](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)

1. 보안 및 [& 센터에서](https://protection.office.com) **위협 관리** 정책 스팸 \>  \> **방지를 선택 합니다.**

2. 사용자 지정 **탭에서** 사용자 지정 설정을 니다.

3. 기본 **스팸 필터 정책을 확장하고** 정책 **편집을** 클릭한 다음 다음 설정을 지정합니다.

   - 스팸 및 **대량 작업** 섹션에서 임계값을 5 또는 6으로 설정합니다.

   - 허용 **목록 섹션에서** 허용된 보낸 사람 및 도메인을 검토 및/또는 편집합니다.

4. **저장** 을 클릭합니다.

스팸 방지 정책 옵션에 대한 자세한 내용은 EOP에서 스팸 방지 정책 [구성을 참조하세요.](configure-your-spam-filter-policies.md)

## <a name="part-4---protection-from-malicious-urls-and-files-safe-links-and-safe-attachments-in-defender-for-office-365"></a>4부 - 악의적인 URL 및 파일로부터 보호(Office 365용 Defender의 안전한 링크 및 안전한 첨부 파일)

악의적인 URL 및 파일로부터 클릭 시간 보호는 Microsoft [Defender for Office 365를](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)포함 하는 구독에서 사용할 수 있습니다. 안전한 첨부 파일 및 [안전한](atp-safe-attachments.md) 링크 [정책을 통해 설정됩니다.](atp-safe-links.md)

### <a name="safe-attachments-policies-in-microsoft-defender-for-office-365"></a>Office 365용 Microsoft Defender의 안전 첨부 파일 정책

안전한 첨부 파일을 [설정하기](atp-safe-attachments.md)위해 하나 이상의 안전 링크 정책을 만드시다.

1. 보안 [&](https://protection.office.com)준수 센터에서 위협 **관리** \>  \> **정책 ATP 안전한** 첨부 파일을 선택한 다음 만들기를 **클릭합니다.**

2. 나타나는 **새 안전** 첨부 파일 정책 마법사에서 다음 설정을 구성합니다.

   - 이름 **상자에** `Block malware` 입력하고 다음을 **클릭합니다.**

   - 설정 **페이지에서** 다음 설정을 구성합니다.
     - 안전한 첨부 **파일 알 수 없는 맬웨어 응답 섹션에서** 차단을 선택 **합니다.**
     - 첨부 파일 **리디렉션 섹션에서** 리디렉션 사용 **옵션을 선택합니다.** 검색된 파일을 검토할 조직의 보안 관리자 또는 운영자의 전자 메일 주소를 지정합니다.

     **다음** 을 클릭합니다.

3. 적용  대상 페이지에서 조건 **추가를** 클릭하고 적용 대상을 선택합니다. 받는 사람 도메인이 있는 경우 적용을 **클릭합니다.** **추가,** 도메인 선택, **추가,** 완료, 다음을 **클릭합니다.** 

4. 설정을 검토하고 **마쳤습니다.**

### <a name="safe-links-policies-in-microsoft-defender-for-office-365"></a>Office 365용 Microsoft Defender의 안전한 링크 정책

안전한 링크를 [설정하려면](atp-safe-links.md)안전한 링크에 대한 전역 설정을 검토 및 편집하고 안전한 링크 정책을 하나 이상 만드시다.

1. 보안 & 준수 [센터에서](https://protection.office.com) **위협** 관리 정책 ATP 안전한 링크를 선택하고 전역 설정을 클릭한 다음 다음 설정을 \>  \>  구성합니다.

   - 안전한 링크 사용 **확인: Office 365** 응용 프로그램이 켜져 있습니다. ![ ](../../media/scc-toggle-on.png) 토글합니다.
   - 사용자가 안전한 링크를 **클릭하는** 경우 추적하지 않습니다. 사용자 클릭을 추적하려면 이 설정을 해제합니다. ![ 토글 끄기. ](../../media/scc-toggle-off.png)
   - **사용자가 원래 URL에 대한** 안전한 링크를 클릭할 수 없습니다. 이 설정이 켜져 있는지 확인합니다. ![ 토글합니다. ](../../media/scc-toggle-on.png)

   작업을 마쳤으면 **저장** 을 클릭합니다.

2. 기본 안전한 링크 페이지에서 만들기를 **클릭합니다.**

3. 나타나는 **안전** 링크 정책 만들기 마법사에서 다음 설정을 구성합니다.

   - 이름 **상자에** 이름(예: )을 입력하고 `Safe Links` 다음을 **클릭합니다.**

   - 설정 **페이지에서** 다음 설정을 구성합니다.
     - **메시지에서 알 수** 없는 악의적인 URL에 대한 작업을 선택합니다. 을 **선택합니다.**
     - **Microsoft Teams 내에서** 알 수 없는 URL 또는 악의적인 URL에 대한 작업을 **선택합니다.**
     - **조직 내에서 보낸 전자 메일 메시지에 안전한 링크 적용**
     - **URL 검색이 완료될 때까지 기다렸다가 메시지를 배달합니다.**
     - **조직 내에서 보낸 전자 메일 메시지에 안전한 링크 적용**
     - **사용자가 원래 URL을 클릭할 수 있도록 허용 안 하세요.**

     **다음** 을 클릭합니다.

4. 적용  대상 페이지에서 조건 **추가를** 클릭하고 적용 대상을 선택합니다. 받는 사람 도메인이 있는 경우 적용을 **클릭합니다.** **추가,** 도메인 선택, **추가,** 완료, 다음을 **클릭합니다.** 

5. 설정을 검토하고 **마쳤습니다.**

자세한 내용은 [안전한 링크 정책 설정](set-up-atp-safe-links-policies.md)을 참조하세요.

## <a name="part-5---verify-safe-attachments-for-sharepoint-onedrive-and-microsoft-teams-is-turned-on"></a>5부 - SharePoint, OneDrive 및 Microsoft Teams의 안전한 첨부 파일이 켜져 있는지 확인

SharePoint, OneDrive 및 Teams와 같은 워크로드는 공동 작업을 위해 구축됩니다. Office 365용 Defender를 사용하면 팀 사이트 및 문서 라이브러리에서 악성으로 식별된 파일을 차단하고 검색하는 데 도움이 됩니다. 여기에서 작동 방식에 대해 자세히 읽을 수 [있습니다.](atp-for-spo-odb-and-teams.md)

> [!IMPORTANT]
> 이 절차를 시작하기 전에 **Microsoft 365** 환경에 대해 감사 로깅이 이미 설정되어 있는지 확인하십시오. 이 작업은 일반적으로 Exchange Online에 할당된 감사 로그 역할이 있는 사용자가 수행합니다. 자세한 내용은 감사 로그 검색 설정 [또는 해제를 참조하세요!](../../compliance/turn-audit-log-search-on-or-off.md)

1. 보안 & 준수 [센터에서](https://protection.office.com)위협 **관리** \>  \> **정책 ATP 안전한** 첨부 파일을 선택한 다음 전역 설정을 **클릭합니다.**

2. **SharePoint, OneDrive 및 Microsoft Teams용 Office 365용 Defender** 켜기 토글이 오른쪽에 있는지 확인: 토글 켜기, 저장을 ![ ](../../media/scc-toggle-on.png) **차례로 클릭합니다.**

3. 조직의 안전 첨부 파일 정책 및 안전한 [](set-up-atp-safe-attachments-policies.md) 링크 정책을 검토하고 적절하게 [편집합니다.](set-up-atp-safe-links-policies.md)

4. (권장) 전역 관리자 또는 SharePoint Online 관리자는 _DisallowInfectedFileDownload_ 매개 변수가 으로 설정된 **[Set-SPOTenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant)** cmdlet을 실행합니다. `$true`

   - `$true` 검색된 파일에 대한 모든 작업(삭제 제외)을 차단합니다. 검색된 파일을 열거나, 이동하거나, 복사하거나, 공유할 수 없습니다.
   - `$false` 삭제 및 다운로드를 제외한 모든 작업을 차단합니다. 사람들은 위험을 수락하고 검색된 파일을 다운로드할 수 있습니다.

   > [!TIP]
   > Microsoft 365에서 PowerShell을 사용하는 자세한 내용은 [PowerShell을 사용하여 Microsoft 365 관리를 참조합니다.](https://docs.microsoft.com/microsoft-365/enterprise/manage-microsoft-365-with-microsoft-365-powershell)

5. 변경 내용을 모든 Microsoft 365 데이터 센터에 분산하는 데 최대 30분을 허용합니다.

### <a name="now-set-up-alerts-for-detected-files"></a>이제 검색된 파일에 대한 경고 설정

SharePoint Online, 비즈니스용 OneDrive 또는 Microsoft Teams의 파일이 악성으로 식별된 경우 알림을 받으기 위해 경고를 설정할 수 있습니다.

1. 보안 및 [& 센터에서](https://protection.office.com)경고  관리 \> **경고를 선택 합니다.**

2. 새 **경고 정책을 선택 합니다.**

3. 경고의 이름을 지정합니다. 예를 들어 라이브러리에 악성 파일을 입력할 수 있습니다.

4. 경고에 대한 설명을 입력합니다. 예를 들어 SharePoint Online, OneDrive 또는 Microsoft Teams에서 악성 파일이 감지되면 관리자에게 고지할 수 있습니다.

5. 다음을 **설정하여 이 경고 보내기...** 섹션에서 다음을 설정하세요.

   a. 활동 **목록에서** **파일에서 검색된 맬웨어를 선택합니다.**

   b. Users **필드는 비워** 두면 됩니다.

6. 다음에 이 알림 보내기 **섹션에서** 악성 파일이 감지될 때 알림을 수신해야 하는 전역 관리자, 보안 관리자 또는 보안 독자를 하나 이상 선택합니다.

7. **저장합니다.**

경고에 대한 자세한 내용은 보안 및 준수 센터에서 활동 [& 참조합니다.](../../compliance/create-activity-alerts.md)

> [!NOTE]
> 구성이 완료되면 다음 링크를 사용하여 작업 조사를 시작하세요.
>
>- [위협 방지 상태 보고서](view-email-security-reports.md#threat-protection-status-report)
>- [보안 및 & 센터를 사용하여 고지된 파일 관리](manage-quarantined-messages-and-files.md#microsoft-defender-for-office-365-only-use-the-security--compliance-center-to-manage-quarantined-files)
>- [SharePoint Online, OneDrive 또는 Microsoft Teams에서 악성 파일이 발견될 때 할 일](https://support.microsoft.com/office/01e902ad-a903-4e0f-b093-1e1ac0c37ad2)
>- [Microsoft 365에서 관리자로 에지된 메시지 및 파일 관리](manage-quarantined-messages-and-files.md)

## <a name="part-6---additional-settings-to-configure"></a>6부 - 구성할 추가 설정

맬웨어, 악의적인 URL 및 파일, 피싱 및 스팸으로부터 보호를 구성하는 것과 함께 제로 아워 자동 삭제를 구성하는 것이 좋습니다.

### <a name="zero-hour-auto-purge-for-email-in-eop"></a>EOP에서 전자 메일에 대한 제로 아워 자동 제거

[ZAP(제로](zero-hour-auto-purge.md) 아워 자동 비우기)는 EOP를 포함 하는 [구독에서 사용할 수 있습니다.](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description) 이 보호는 기본적으로 켜져 있습니다. 그러나 보호를 적용하려면 다음 조건을 충족해야 합니다.

- 스팸 작업은 스팸 방지 **정책에서** 메시지를 정크 메일 폴더로 [이동으로 설정됩니다.](anti-spam-protection.md)

- 사용자는 기본 정크 메일 설정을 유지하며 [정크](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md)메일 보호를 해제하지 않은 경우

자세한 내용은 제로 아워 자동 비우기 - 스팸 및 맬웨어로부터 [보호를 참조합니다.](zero-hour-auto-purge.md)

## <a name="post-setup-tasks-and-next-steps"></a>설치 후 작업 및 다음 단계

위협 방지 기능을 구성한 후 해당 기능이 작동되는 방법을 모니터링해야 합니다. 정책이 필요한 작업을 할 수 있도록 정책을 검토하고 변경합니다. 또한 가치를 추가할 수 있는 새로운 기능 및 서비스 업데이트를 확인합니다.

****

|수행할 작업|자세한 정보를 알아볼 수 있는 리소스|
|---|---|
|보고서를 확인하여 위협 방지 기능이 조직에 대해 어떻게 작동하고 있는지 확인|[보안 대시보드](security-dashboard.md) <p> [전자 메일 보안 보고서](view-email-security-reports.md) <p> [Office 365용 Microsoft Defender에 대한 보고서](view-reports-for-atp.md) <p> [위협 탐색기](threat-explorer.md)|
|필요한 경우 위협 방지 정책을 주기적으로 검토하고 변경|[Secure Score](../mtp/microsoft-secure-score.md) <p> [스마트 보고서 및 인사이트](reports-and-insights-in-security-and-compliance.md) <p> [Microsoft 365 위협 조사 및 응답 기능](keep-users-safe-with-office-365-ti.md)|
|새로운 기능 및 서비스 업데이트 감시|[표준 및 대상 지정 릴리스 옵션](https://docs.microsoft.com/microsoft-365/admin/manage/release-options-in-office-365) <p> [메시지 센터](https://docs.microsoft.com/microsoft-365/admin/manage/message-center) <p> [Microsoft 365 로드맵](https://www.microsoft.com/microsoft-365/roadmap?filters=&searchterms=advanced%2Cthreat%2Cprotection) <p> [서비스 설명](https://docs.microsoft.com/office365/servicedescriptions/office-365-service-descriptions-technet-library)|
|Office 365용 EOP 및 Defender에 대한 권장 표준 및 엄격한 보안 구성에 대한 자세한 정보|[EOP 및 Office 365용 Microsoft Defender 보안에 대한 권장 설정](recommended-settings-for-eop-and-office365-atp.md)|

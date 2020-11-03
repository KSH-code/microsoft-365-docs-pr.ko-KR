---
title: 위협으로부터 보호
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: Admin
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
ms.date: 09/08/2020
search.appverid:
- MOE150
- MET150
ms.assetid: b10023f6-f30f-45d3-b3ad-b71aa4aa0d58
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
description: 관리자는 Microsoft 365의 위협 보호에 대해 알아보고 조직에서이를 사용 하는 방법을 구성할 수 있습니다.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: f6ac5b67d589db57d449ba61f07668b10b32706d
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/03/2020
ms.locfileid: "48845723"
---
# <a name="protect-against-threats"></a>위협으로부터 보호

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


다음은 Office 365 용 Defender의 구성을 청크로 나누는 빠른 시작 가이드입니다. Office 365의 위협 방지 기능을 처음 사용 하는 경우 시작할 위치를 잘 모르는 경우에는이 *지침을 검사* 목록 및 출발점으로 사용해 보세요.

> [!IMPORTANT]
> **초기 권장 설정은 각 정책 유형에 대해 포함 되지만 대부분의 옵션을 사용할 수 있으며, 특정 조직의 요구에 맞게 설정을 조정할 수** 있습니다. 정책이 나 변경 내용이 데이터 센터를 통해 작동 하는 데 약 30 분 정도 걸릴 수 있습니다.

## <a name="requirements"></a>요구 사항

### <a name="subscriptions"></a>구독

위협 보호 기능은 *모든* Microsoft 또는 Office 365 구독에 포함 되어 있습니다. 그러나 일부 구독은 고급 기능을 제공 합니다. 아래 표에는이 문서에 포함 된 보호 기능과 최소 구독 요구 사항이 함께 나와 있습니다.

> [!TIP]
> 감사를 설정 하는 지침 보다는 Office 365 Exchange Online Protection ( **EOP** )의 일부로 표시 되는 맬웨어 방지, 피싱 방지 및 스팸 방지에 대 한 *단계가* 진행 되 고 있음을 확인할 수 있습니다. 이는 office 365 용 defender ( **defender 365** )에 들어 있고, EOP를 사용할 수 있을 때까지이 문서에 대 한 정보

****

|보호 유형|구독 요구 사항|
|---|---|
|감사 로깅 (보고 목적)|[Exchange Online](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-service-description)|
|맬웨어 방지 보호 기능|**EOP** ( [Exchange Online Protection](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description) )|
|피싱 방지 보호 기능|[EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)|
|스팸 방지 보호 기능|[EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)|
|0 시간 자동 삭제 (전자 메일의 경우)|[EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)|
|전자 메일 및 Office 문서 (안전한 링크 및 안전한 첨부 파일)의 악성 Url 및 파일과의 보호|[Microsoft Defender for Office 365](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)|
|SharePoint, OneDrive 및 Microsoft 팀 작업에 대 한 ATP 켜기|[Defender for Office 365 ](atp-for-spo-odb-and-teams.md)|
|고급 피싱 방지 보호|[Office 365용 Microsoft Defender](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)|

### <a name="roles-and-permissions"></a>역할 및 사용 권한

Office 365 정책에 대해 Defender를 구성 하려면 [보안 & 준수 센터](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-securitycompliance-center)에 적절 한 역할이 할당 되어 있어야 합니다. 이러한 작업을 수행할 수 있는 역할은 아래 표를 참조 하세요.

****

|역할 또는 역할 그룹|자세한 정보|
|---|---|
|전역 관리자|[Microsoft 365 관리자 역할 정보](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles)|
|보안 관리자|[Azure Active Directory의 관리자 역할 권한](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)|
|Exchange Online 조직 관리|[Exchange Online의 사용 권한](https://docs.microsoft.com/exchange/permissions-exo/permissions-exo) <br>및<br> [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell)|
|

자세한 내용은 [보안 및 &amp; 준수 센터의 사용 권한을](permissions-in-the-security-and-compliance-center.md)참조 하세요.

## <a name="before-you-begin-turn-on-audit-logging-for-reporting-and-investigation"></a>시작 하기 전에 보고 및 조사에 대 한 감사 로깅 설정

감사 로깅을 일찍 시작 합니다. 다음과 같은 특정 단계에 대해서는 감사를 **설정** 해야 합니다. 감사 로깅은 [Exchange Online](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-service-description)이 포함 된 구독에서 사용할 수 있습니다. [보안 대시보드](security-dashboard.md), [전자 메일 보안 보고서](view-email-security-reports.md)및 [탐색기](threat-explorer.md)와 같은 위협 보호 보고서의 데이터를 보려면 감사 로깅이 *설정* 되어 있어야 합니다. 자세한 내용은 [Turn audit log search on or off](../../compliance/turn-audit-log-search-on-or-off.md)를 참조 하십시오.

## <a name="part-1---anti-malware-protection"></a>1 부-맬웨어 방지 보호 기능

[맬웨어 방지 보호](anti-malware-protection.md) 는 [EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)을 포함 하는 구독에서 사용할 수 있습니다.

1. [보안 & 준수 센터](https://protection.office.com)에서 **위협 관리**  >  **정책**  >  **맬웨어 방지** 를 선택 합니다.

2. **기본** 정책을 두 번 클릭 한 다음 **설정을** 선택 합니다.

3. 다음 설정을 지정 합니다.

    - **맬웨어 검색 응답** 섹션에서 기본 설정인 **아니요** 를 그대로 둡니다.

    - **일반 첨부 파일 형식 필터** 섹션에서 **설정** 를 선택 합니다.

4. **저장** 을 클릭합니다.

맬웨어 방지 정책 옵션에 대 한 자세한 내용은 [맬웨어 방지 정책 구성을](configure-anti-malware-policies.md)참조 하십시오.

## <a name="part-2---anti-phishing-protection"></a>2 부-피싱 방지 보호 기능

[피싱 방지 보호](anti-phishing-protection.md) 기능은 [EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)을 포함 하는 구독에서 사용할 수 있습니다. 고급 피싱 방지 보호는 [Defender For Office 365](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)에서 사용할 수 있습니다.

다음 절차에서는 Office 365 용 Microsoft Defender에서 피싱 방지 정책을 구성 하는 방법을 설명 합니다. 이 단계는 EOP에서 피싱 방지 정책을 구성 하는 경우에도 비슷합니다.

1. [보안 & 준수 센터](https://protection.office.com)에서 **위협 관리**  >  **정책**  >  **ATP 피싱 방지** 를 선택 합니다.

2. **기본 정책을** 클릭 합니다.

3. **가장** 섹션에서 **편집** 을 클릭 하 고 다음 설정을 지정 합니다.

   - **보호할 사용자 추가** 탭 *에서 보호를* 설정 합니다. 그런 다음 조직의 보드 구성원, CEO, CFO 및 기타 선임 리더와 같은 사용자를 추가 합니다. (개별 전자 메일 주소를 입력 하거나를 클릭 하 여 목록을 표시할 수 있습니다.)

   - **보호할 도메인 추가** 탭에서 **자신이 소유한 도메인을 자동으로 포함** 을 설정 합니다. 사용자 지정 도메인이 있는 경우 지금 추가 합니다.

   - **작업** 탭에서 **가장 된 사용자** 및 **가장 도메인** 옵션 둘 다에 대해 **메시지 격리** 를 선택 합니다. 또한 가장 안전한 팁을 설정 합니다.

   - **사서함** 인텔리전스 탭에서 사서함 인텔리전스가 설정 되어 있고 사서함 인텔리전스 기반 가장을 사용 하도록 설정 되어 있는지 확인 합니다. 가장 된 **사용자 목록이 전자 메일을 보낸 경우** 에는 **메시지 격리** 를 선택 합니다.

   - **신뢰할 수 있는 보낸 사람 및 도메인 추가** 탭에서 추가 하려는 신뢰할 수 있는 보낸 사람 또는 도메인을 지정 합니다.

   - 설정을 검토 한 후에 **설정 검토** 탭에서 **저장** 합니다.

4. **스푸핑** 섹션에서 **편집** 을 클릭 하 고 다음 설정을 지정 합니다.

   - **스푸핑 필터 설정** 탭에서 스푸핑 방지 보호가 설정 되어 있는지 확인 합니다.

   - **작업** 탭에서 **메시지 격리** 를 선택 합니다.

   - 변경 내용을 검토 한 후에는 **설정 검토** 탭에서 **저장** 합니다. 변경 하지 않은 경우 **취소** 를 수행 합니다.

5. 기본 정책 설정 페이지를 닫습니다.

피싱 방지 정책 옵션에 대 한 자세한 내용은 [Microsoft Defender For Office 365에서 피싱 방지 정책 구성을](configure-atp-anti-phishing-policies.md)참조 하세요.

## <a name="part-3---anti-spam-protection"></a>3 부-스팸 방지 보호 기능

[스팸 방지 보호](anti-spam-protection.md) 기능은 [EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)을 포함 하는 구독에서 사용할 수 있습니다.

1. [보안 & 준수 센터](https://protection.office.com)에서 **위협 관리**  >  **정책**  >  **스팸 방지** 를 선택 합니다.

2. **사용자 지정** 탭에서 사용자 지정 설정을 켭니다.

3. **기본 스팸 필터 정책을** 확장 하 고 **정책 편집** 을 클릭 한 후 다음 설정을 지정 합니다.

   - **스팸 및 대량 작업** 섹션에서 임계값을 5 또는 6으로 설정 합니다.

   - **허용 목록** 섹션에서 허용 되는 보낸 사람 및 도메인을 검토 (및/또는 편집) 합니다.

4. **저장** 을 클릭합니다.

스팸 방지 정책 옵션에 대 한 자세한 내용은 [EOP에서 스팸 방지 정책 구성을](configure-your-spam-filter-policies.md)참조 하십시오.

## <a name="part-4---protection-from-malicious-urls-and-files-safe-links-and-safe-attachments-in-defender-for-office-365"></a>제 4 부-악성 Url 및 파일의 보호 (Defender for Office 365의 안전한 링크 및 안전한 첨부 파일)

악성 Url 및 파일 로부터의 클릭 시간 보호는 [Office 365 용 Microsoft Defender](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)를 포함 하는 구독에서 사용할 수 있습니다. [안전한 첨부 파일](atp-safe-attachments.md) 및 [안전한 링크](atp-safe-links.md) 정책을 통해 설정 됩니다.

### <a name="safe-attachments-policies-in-microsoft-defender-for-office-365"></a>Microsoft Defender for Office 365의 안전 첨부 파일 정책

[안전한 첨부 파일](atp-safe-attachments.md)을 설정 하려면 하나 이상의 안전한 링크 정책을 만듭니다.

1. [보안 & 준수 센터](https://protection.office.com)에서 **위협 관리**  >  **정책**  >  **ATP 안전한 첨부 파일** 을 선택한 다음 **만들기** 를 클릭 합니다.

2. **새 안전 첨부 파일 정책** 마법사가 나타나면 다음 설정을 구성 합니다.

   - **이름** 상자에을 입력 하 `Block malware` 고 **다음** 을 클릭 합니다.

   - **설정** 페이지에서 다음 설정을 구성 합니다.
     - **안전한 첨부 파일 알 수 없는 맬웨어 응답** 섹션에서 **차단을** 선택 합니다.
     - **첨부 파일 리디렉션** 섹션에서 **리디렉션 사용** 옵션을 선택 합니다. 검색 된 파일을 검토할 사용자 조직의 보안 관리자 또는 운영자의 전자 메일 주소를 지정 합니다.

     **다음** 을 클릭합니다.

3. **적용 대상** 페이지에서 **조건 추가** 를 클릭 하 고, **받는 사람 도메인이 있는 경우 적용** 을 선택한 다음, **추가,** 도메인 또는 도메인을 차례로 선택 하 고 **추가** , **완료** 를 차례로 클릭 한 후 **다음** 을 클릭 합니다.

4. 설정을 검토 하 고 **마침을** 클릭 합니다.

### <a name="safe-links-policies-in-microsoft-defender-for-office-365"></a>Microsoft Defender for Office 365의 안전한 링크 정책

[안전한 링크](atp-safe-links.md)를 설정 하려면 안전한 링크에 대 한 전역 설정을 검토 및 편집 하 고 하나 이상의 안전한 링크 정책을 만듭니다.

1. [보안 & 준수 센터](https://protection.office.com)에서 **위협 관리**  >  **정책**  >  **ATP 안전한 링크** 를 선택 하 고 **전역 설정을** 클릭 한 후에 다음 설정을 구성 합니다.

   - **에서 안전한 링크 사용 확인: Office 365 응용 프로그램** 은 켜져 있음: ![ 설정/해제 ](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png) 합니다.
   - **사용자가 안전 링크를 클릭 하는 경우 추적 안 함** :이 설정을 해제 하 여 사용자 클릭: 토글을 추적 ![ ](../../media/scc-toggle-off.png) 합니다.
   - **사용자가 원본 URL에 대 한 안전한 링크를 클릭 하는 것을 허용 하지** 않습니다 .이 설정이 설정 되어 있는지 확인 합니다: 켜기를 선택 ![ ](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png) 합니다.

   작업을 마쳤으면 **저장** 을 클릭합니다.

2. 기본 안전한 링크 페이지에서 다시 **만들기** 를 클릭 합니다.

3. **안전 링크 정책 만들기** 마법사가 나타나면 다음 설정을 구성 합니다.

   - **이름** 상자에 이름 (예:)을 입력 `Safe Links` 하 고 **다음** 을 클릭 합니다.

   - **설정** 페이지에서 다음 설정을 구성 합니다.
     - **메시지에서 알 수 없는 잠재적 악성 url에 대 한 작업을 선택** **합니다.**
     - **Microsoft 팀 내에서 알 수 없거나 잠재적 악성 url에 대 한 작업을 선택** **합니다.**
     - **조직 내에서 전송 된 전자 메일 메시지에 안전한 링크 적용**
     - **메시지를 배달 하기 전에 URL 검색이 완료 될 때까지 기다립니다.**
     - **조직 내에서 전송 된 전자 메일 메시지에 안전한 링크 적용**
     - **사용자가 원래 URL로 클릭 하도록 허용 안 함**

     **다음** 을 클릭합니다.

4. **적용 대상** 페이지에서 **조건 추가** 를 클릭 하 고, **받는 사람 도메인이 있는 경우 적용** 을 선택한 다음, **추가,** 도메인 또는 도메인을 차례로 선택 하 고 **추가** , **완료** 를 차례로 클릭 한 후 **다음** 을 클릭 합니다.

5. 설정을 검토 하 고 **마침을** 클릭 합니다.

자세한 내용은 [안전한 링크 정책 설정](set-up-atp-safe-links-policies.md)을 참조하세요.

## <a name="part-5---verify-atp-for-sharepoint-onedrive-and-microsoft-teams-is-turned-on"></a>5 부-SharePoint, OneDrive 및 Microsoft 팀에 대 한 ATP가 설정 되어 있는지 확인

SharePoint, OneDrive 및 팀과 같은 워크 로드는 공동 작업을 위해 빌드됩니다. Office 365 용 Defender를 사용 하면 팀 사이트 및 문서 라이브러리에서 악의적으로 식별 된 파일을 차단 하 고 검색할 수 있습니다. 여기서 작동 하는 방법에 대 한 자세한 내용은 [여기](https://docs.microsoft.com/microsoft-365/security/office-365-security/atp-for-spo-odb-and-teams)에서 확인할 수 있습니다.

> [!IMPORTANT]
> **이 절차를 시작 하기 전에 Microsoft 365 환경에 대해 감사 로깅이 이미 설정 되어 있는지 확인** 합니다. 이 작업은 일반적으로 Exchange Online에서 감사 로그 역할이 할당 된 사용자가 수행 합니다. 자세한 내용은 [Turn 감사 로그 검색 켜기 또는 끄기를](../../compliance/turn-audit-log-search-on-or-off.md)참조 하세요.

1. [보안 & 준수 센터](https://protection.office.com)에서 **위협 관리**  >  **정책**  >  **ATP 안전한 첨부 파일** 을 선택한 다음 **전역 설정을** 클릭 합니다.

2. **SharePoint, OneDrive 및 Microsoft 팀에서 ATP 설정 켜기** 가 오른쪽으로 설정 되어 있는지 확인 하 ![ ](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png) 고 **저장** 을 클릭 합니다.

3. 조직의 [안전한 첨부 파일 정책](set-up-atp-safe-attachments-policies.md) 및 [안전한 링크 정책을](set-up-atp-safe-links-policies.md)검토 하 고 적절 하 게 편집 합니다.

4. 는 전역 관리자 또는 SharePoint Online 관리자는 _DisallowInfectedFileDownload_ 매개 변수를로 설정 하 여 **[set-spotenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant)** cmdlet을 실행 합니다 `$true` .

   - `$true` 검색 된 파일에 대 한 모든 작업 (삭제 제외)을 차단 합니다. 사용자가 검색 된 파일을 열거나, 이동 하거나, 복사 하거나, 공유할 수 없습니다.
   - `$false` 삭제 및 다운로드를 제외한 모든 작업을 차단 합니다. 사용자는 위험을 수락 하 고 검색 된 파일을 다운로드할 수 있습니다.

   > [!TIP]
   > Microsoft 365에서 PowerShell을 사용 하는 방법에 대 한 자세한 내용은 PowerShell을 사용 하 여 [microsoft 365 관리](https://docs.microsoft.com/microsoft-365/enterprise/manage-microsoft-365-with-microsoft-365-powershell)를 참조 하세요.

5. 변경 내용이 모든 Microsoft 365 데이터 센터에 전파 되는 데 최대 30 분 정도 걸릴 수 있습니다.

### <a name="now-set-up-alerts-for-detected-files"></a>이제 검색 된 파일에 대 한 알림을 설정 합니다.

SharePoint Online의 파일 (비즈니스용 OneDrive 또는 Microsoft 팀)이 악성으로 식별 된 경우 알림을 받으려면 알림을 설정 하면 됩니다.

1. [보안 & 준수 센터](https://protection.office.com) **에서 경고를** \> **관리** 합니다 .를 선택 합니다.

2. **새 경고 정책을** 선택 합니다.

3. 알림의 이름을 지정 합니다. 예를 들어 라이브러리에 유해한 파일을 입력할 수 있습니다.

4. 경고에 대 한 설명을 입력 합니다. 예를 들어 SharePoint Online, OneDrive 또는 Microsoft 팀에서 악성 파일이 검색 되 면 관리자에 게 알림 메시지를 입력할 수 있습니다.

5. 다음 **경우에이 알림 보내기** 섹션에서 다음을 설정 합니다.

   a. **작업** 목록에서 **검색 된 맬웨어를 파일에서** 선택 합니다.

   b. **Users** 필드는 비워 둡니다.

6. **이 알림 보내기** ... 섹션에서 악의적인 파일이 검색 되 면 알림을 받을 전역 관리자, 보안 관리자 또는 보안 판독기를 하나 이상 선택 합니다.

7. **저장** 을 합니다.

경고에 대 한 자세한 내용은 [보안 & 준수 센터에서 활동 경고 만들기](../../compliance/create-activity-alerts.md)를 참조 하십시오.

> [!NOTE]
> 구성을 마친 후에는 다음 링크를 사용 하 여 작업 조사를 시작 합니다.
>
>- [위협 방지 상태 보고서](view-email-security-reports.md#threat-protection-status-report)
>- [보안 & 준수 센터를 사용 하 여 격리 된 파일 관리](manage-quarantined-messages-and-files.md#microsoft-defender-for-office-365-only-use-the-security--compliance-center-to-manage-quarantined-files)
>- [SharePoint Online, OneDrive 또는 Microsoft 팀에서 악의적인 파일을 찾을 때 수행할 작업](https://support.microsoft.com/office/01e902ad-a903-4e0f-b093-1e1ac0c37ad2)
>- [Microsoft 365에서 격리 된 메시지 및 파일을 관리자 권한으로 관리](manage-quarantined-messages-and-files.md)

## <a name="part-6---additional-settings-to-configure"></a>6 부-구성할 추가 설정

맬웨어, 악성 Url, 파일, 피싱 및 스팸 으로부터 보호를 구성 하는 것과 함께 0 시간 자동 삭제를 구성 하는 것이 좋습니다.

### <a name="zero-hour-auto-purge-for-email-in-eop"></a>EOP의 전자 메일에 대 한 제로 시간 자동 삭제

[EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)을 포함 하는 구독에서 [0 시간 자동 삭제](zero-hour-auto-purge.md) (ZAP)를 사용할 수 있습니다. 이 보호 기능은 기본적으로 설정 되어 있습니다. 그러나 보호 기능을 적용 하려면 다음 조건을 충족 해야 합니다.

- 스팸 [방지 정책](anti-spam-protection.md)에서 **정크 메일 폴더로 메시지를 이동** 하도록 스팸 작업을 설정 합니다.

- 사용자가 기본 [정크 메일 설정을](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md)유지 하 고 정크 메일 보호 기능을 해제 하지 않은 경우

자세한 내용은 스팸 및 맬웨어를 방지 하는 [0 시간 자동 삭제](zero-hour-auto-purge.md)를 참조 하세요.

## <a name="post-setup-tasks-and-next-steps"></a>설치 후 작업 및 다음 단계

위협 방지 기능을 구성한 후에는 이러한 기능이 작동 하는 방식을 모니터링 해야 합니다. 필요한 작업을 수행 하도록 정책을 검토 하 고 수정 합니다. 또한 값을 추가할 수 있는 새로운 기능 및 서비스 업데이트도 시청 하세요.

****

|수행할 작업|자세한 정보를 알아볼 수 있는 리소스|
|---|---|
|보고서를 확인 하 여 조직에서 위협 방지 기능을 사용 하는 방법 보기|[보안 대시보드](security-dashboard.md)<br/>[전자 메일 보안 보고서](view-email-security-reports.md)<br/>[Microsoft Defender for Office 365에 대 한 보고서](view-reports-for-atp.md)<br/>[위협 탐색기](threat-explorer.md)|
|필요에 따라 위협 보호 정책 주기적으로 검토 및 수정|[Secure Score](../mtp/microsoft-secure-score.md)<br/>[스마트 보고서 및 통찰력](reports-and-insights-in-security-and-compliance.md)<br/>[Microsoft 365 위협 조사 및 응답 기능](keep-users-safe-with-office-365-ti.md)|
|새로운 기능 및 서비스 업데이트 조사|[표준 및 대상 지정 된 릴리스 옵션](https://docs.microsoft.com/microsoft-365/admin/manage/release-options-in-office-365)<br/>[메시지 센터](https://docs.microsoft.com/microsoft-365/admin/manage/message-center)<br/>[Microsoft 365 로드맵](https://www.microsoft.com/microsoft-365/roadmap?filters=&searchterms=advanced%2Cthreat%2Cprotection)<br/>[서비스 설명](https://docs.microsoft.com/office365/servicedescriptions/office-365-service-descriptions-technet-library)|
|EOP 및 Office 용 Defender에 대 한 권장 표준 및 엄격한 보안 구성에 대 한 자세한 정보를 알아봅니다. 365|[EOP 및 Office 용 Microsoft Defender 365 보안에 대 한 권장 설정](recommended-settings-for-eop-and-office365-atp.md)|

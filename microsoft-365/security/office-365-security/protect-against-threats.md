---
title: Microsoft Defender의 위협으로부터 보호Office 365, 맬웨어 방지, 피싱 방지, 스팸 방지, 금고 링크, 금고 첨부 파일, ZAP(제로 아워 자동 제거), MDO 보안 구성
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: Admin
ms.topic: overview
ms.localizationpriority: medium
ms.date: 06/22/2021
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
ms.openlocfilehash: 86bfbc2f25d6c03acd9f95a3c4b475240532d153
ms.sourcegitcommit: 7b83e2605895fee5c73cd1d01f4cd16e1457a69f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/11/2021
ms.locfileid: "60907972"
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
>
> Defender for Office 365 대부분의 정책의 수동 구성을 건너뛰기 위해 표준 또는 엄격한 수준에서 미리 설정한 보안 정책을 사용할 수 있습니다. 자세한 내용은 EOP에서 보안 정책 미리 설정 및 Microsoft [Defender for Office 365.](preset-security-policies.md)

## <a name="requirements"></a>요구 사항

### <a name="subscriptions"></a>구독

위협 방지 기능은 모든 *Microsoft* 또는 Office 365 포함되어 있습니다. 그러나 일부 구독에는 고급 기능이 있습니다. 아래 표에는 이 문서에 포함된 보호 기능과 최소 구독 요구 사항이 나열됩니다.

> [!TIP]
> 감사를 켜는 지시 이상의 단계는  EOP(맬웨어 방지) 의 일부로 표시된 맬웨어 방지, 피싱방지 및 스팸 방지를 Office 365 Exchange Online Protection 있습니다. (에 대한 **Defender** for Office 365) EOP를 포함하고 빌드할 때까지 이 문서에서 이 Office 365 이상한 것처럼 보일 수 있습니다.

<br>

****

|보호 유형|구독 요구 사항|
|---|---|
|감사 로깅(보고 목적으로)|[Exchange Online](/office365/servicedescriptions/exchange-online-service-description/exchange-online-service-description)|
|맬웨어 방지 보호 기능|[](/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description) **Exchange Online Protection(EOP)**|
|피싱 방지 보호 기능|[EOP](/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)|
|스팸 방지 보호 기능|[EOP](/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)|
|전자 메일 및 전자 메일 문서의 악의적인 URL 및 파일 보호(Office 금고 링크 및 금고 첨부 파일)|[Office 365용 Microsoft Defender](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)|

### <a name="roles-and-permissions"></a>역할 및 사용 권한

정책에 대해 Defender를 Office 365 적절한 역할을 할당해야 합니다. 아래 표에서 이러한 작업을 수행할 수 있는 역할을 확인하세요.

<br>

****

|역할 또는 역할 그룹|자세한 내용을 알아보는 위치|
|---|---|
|전역 관리자|[Microsoft 365 관리자 역할 정보](../../admin/add-users/about-admin-roles.md)|
|보안 관리자|[Azure AD 기본 제공 역할](/azure/active-directory/roles/permissions-reference#security-administrator)
|Exchange Online 조직 관리|[Exchange Online의 사용 권한](/exchange/permissions-exo/permissions-exo)|
|

자세한 내용은 Microsoft 365 Defender [포털의 사용 권한을 참조합니다.](permissions-microsoft-365-security-center.md)

### <a name="turn-on-audit-logging-for-reporting-and-investigation"></a>보고 및 조사에 대한 감사 로깅 켜기

- 감사 로깅을 조기 시작합니다. 다음 단계 중 일부에 대해 **감사를 ON으로** 해야 합니다. 감사 로깅은 을(를) 포함 하는 [구독에서 사용할 Exchange Online.](/office365/servicedescriptions/exchange-online-service-description/exchange-online-service-description) 위협 방지 [보고서,](view-email-security-reports.md)전자 메일 보안 보고서 [](threat-explorer.md)및 탐색기에서 데이터를 확인하려면 감사 로깅이 에 있어야 *합니다.* 자세한 내용은 감사 로그 검색 켜기 또는 [끄기 를 참조합니다.](../../compliance/turn-audit-log-search-on-or-off.md)

## <a name="part-1---anti-malware-protection-in-eop"></a>1부 - EOP의 맬웨어 방지 보호

맬웨어 방지에 대한 권장 설정에 대한 자세한 내용은 EOP 맬웨어 방지 정책 [설정 을 참조하세요.](recommended-settings-for-eop-and-office365.md#eop-anti-malware-policy-settings)

1. 의  Microsoft 365 Defender 포털에서 맬웨어 방지 페이지를 열 수 <https://security.microsoft.com/antimalwarev2> 있습니다.

2. **맬웨어 방지 페이지에서** 이름을 클릭하여 **Default(기본값)라는** 정책을 선택합니다.

3. 정책 세부 정보 플라이아웃이 열리면 보호 설정 편집을 **클릭하고** 다음 설정을 구성합니다.
   - **보호 설정** 섹션:
     - **공통 첨부 파일 필터 사용:** 선택(켜기)을 선택합니다. 파일 **형식 사용자 지정을 클릭하여** 파일 형식을 더 추가합니다.
     - **맬웨어에 대해 0시간 자동 제거** 사용: 이 설정이 선택되어 있는지 확인 맬웨어에 대한 ZAP에 대한 자세한 내용은 맬웨어에 대한 [ZAP(제로 아워 자동 제거)를 참조하세요.](zero-hour-auto-purge.md#zero-hour-auto-purge-zap-for-malware)
   - **Quarantine policy:** Leave the default value AdminOnlyAccessPolicy selected. Quarantine policies define what users are able to do to quarantined messages, and whether users receive quarantine notifications. 자세한 내용은 [격리 정책](quarantine-policies.md)을 참조하세요.
   - **알림** 섹션: 알림 설정이 선택되어 있는지 확인합니다.

   작업을 마쳤으면 **저장** 을 클릭합니다.

4. 정책 세부 정보 플라이아웃으로 돌아와 **닫기** 를 클릭합니다.

맬웨어 방지 정책을 구성하는 방법에 대한 자세한 내용은 EOP에서 맬웨어 방지 [정책 구성을 참조하세요.](configure-anti-malware-policies.md)

## <a name="part-2---anti-phishing-protection-in-eop-and-defender-for-office-365"></a>2부 - EOP의 피싱 방지 보호 기능 및 EOP용 Defender Office 365

[피싱 방지 보호는](anti-phishing-protection.md) EOP를 포함 하는 [구독에서 사용할 수 있습니다.](/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description) 고급 피싱 방지 보호는 에 대한 [Defender에서](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)사용할 수 Office 365.

피싱 방지 정책에 대한 권장 설정에 대한 자세한 내용은 [EOP](recommended-settings-for-eop-and-office365.md#eop-anti-phishing-policy-settings) 피싱 방지 정책 설정 및 Microsoft Defender for [Office 365.](recommended-settings-for-eop-and-office365.md#anti-phishing-policy-settings-in-microsoft-defender-for-office-365)

다음 절차에서는 기본 피싱 방지 정책을 구성하는 방법을 설명합니다. 설정 Defender에서만 사용할 수 있는 Office 365 명확하게 표시됩니다.

1. 의  Microsoft 365 Defender 포털에서 피싱 방지 페이지를 열 수 <https://security.microsoft.com/antiphishing> 있습니다.

2. 피싱 **방지 페이지에서** 이름을 클릭하여 **Office365 AntiPhish Default(기본값)라는** 정책을 선택합니다.

3. 나타나는 정책 세부 정보 플라이아웃에서 다음 설정을 구성합니다.
   - **피싱 임계값 & 보호** 섹션: 보호 설정 편집을 **클릭하고** 플라이아웃에서 열리도록 다음 설정을 구성합니다.
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

   - **작업** 섹션: 작업 **편집을** 클릭하고 플라이아웃에서 열리도록 다음 설정을 구성합니다.
     - **메시지 작업** 섹션: 다음 설정을 구성합니다.
       - **가장된** 사용자로 메시지가 검색된 경우 : 메시지 을 선택하여 을 <sup>\*</sup> **선택합니다.** 사용자  가장 보호에 의해 검역된 메시지에 적용되는 검역 정책을 선택하는 경우 검역 정책 적용 상자가 나타납니다. [](quarantine-policies.md)
       - **가장된** 도메인으로 메시지가 검색된 경우 : 메시지 을 선택하여 을 <sup>\*</sup> **선택합니다.** 도메인  가장 보호에 의해 검역된 메시지에 적용되는 검역 정책을 선택하는 경우 검역 정책 적용 상자가 나타납니다. [](quarantine-policies.md)
       - **사서함 인텔리전스에서** 가장된 사용자를 검색하는 경우 : 받는 사람의 정크 메일 폴더로 메시지 이동(표준) 또는 메시지 검역(엄격)을 <sup>\*</sup> 선택합니다.   메시지의 검역을 선택하면 사서함  인텔리전스 보호에 의해 검역된 [](quarantine-policies.md) 메시지에 적용되는 검역 정책을 선택할 수 있는 정책 적용 상자가 나타납니다. 
       - **메시지가 스푸핑으로** 검색된 경우  : 받는 사람의 정크 메일 폴더로 메시지  이동(표준) 또는 메시지 검량(엄격)을 선택합니다.  메시지 **검역을** 선택하면 스푸핑  인텔리전스 보호를 통해 검역된 메시지에 적용되는 검역 정책을 선택하는 검역 정책 적용 상자가 나타납니다. [](quarantine-policies.md)
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

1. 에서 스팸 **방지 정책** 페이지를 Microsoft 365 Defender 를 <https://security.microsoft.com/antispam> 니다.

2. 스팸 **방지 정책** 페이지에서 이름을 클릭하여 목록에서 스팸 방지 인바운드 정책(기본값)이라는 정책을 선택합니다. 

3. 나타나는 정책 세부 정보 플라이아웃에서 다음 설정을 구성합니다.
   - **스팸 속성 & 대량** 전자 메일 임계값: 스팸 임계값 및 속성 **편집을 클릭합니다.** 플라이아웃이 나타나면 다음 설정을 구성합니다.
     - **대량 전자 메일 임계값:** 이 값을 5(엄격) 또는 6(표준)으로 설정합니다.
     - 다른 설정은 기본값(해제 또는 없음)으로 **떠 .**

     작업을 마쳤으면 **저장** 을 클릭합니다.

   - **작업** 섹션: 작업 **편집을 클릭합니다.** 플라이아웃이 나타나면 다음 설정을 구성합니다.
     - **메시지 작업** 섹션:
       - **스팸:** **정크** 메일 폴더로 메시지 이동이 선택되어 있는지 확인(표준)을 선택하거나 **Quarantine message** (Strict)를 선택합니다.
       - **높은 지수 스팸**: 메시지 **검란을 선택합니다.**
       - **피싱**: **메시지 검란을 선택합니다.**
       - **높은 신뢰도 피싱:** **메시지의 검지가 선택되어 있는지** 확인
       - **대량:** **정크** 메일 폴더로 메시지 이동이 선택되어 있는지 확인(표준) 또는 메시지 검지(엄격)를 선택합니다. 

       메시지 차단을 선택하는 각 작업의 경우  스팸 방지 보호를 통해 검역된 [](quarantine-policies.md) 메시지에 적용되는 검역 정책을 선택하는 정책 선택 상자가 나타납니다. 

     - **이 며칠 동안** 스팸을 검지에서 보존 : **30일** 값을 확인 합니다.
     - **스팸 보안 팁 사용:** 이 설정이 선택되어 있는지 확인(켜져 있습니다.)
     - **ZAP(제로 아워 자동 제거)** 사용: 이 설정이 선택되어 있는지 확인(켜져 있습니다.)
       - **피싱 메시지 사용:** 이 설정이 선택되어 있는지 확인(켜져 있습니다.) 자세한 내용은 피싱에 대한 [ZAP(제로 아워 자동 제거)를 참조하세요.](zero-hour-auto-purge.md#zero-hour-auto-purge-zap-for-phishing)
       - **스팸 메시지 사용:** 이 설정이 선택되어 있는지 확인(켜져 있습니다.) 자세한 내용은 스팸에 대한 [ZAP(제로 아워 자동 제거)를 참조하세요.](zero-hour-auto-purge.md#zero-hour-auto-purge-zap-for-spam)

     작업을 마쳤으면 **저장** 을 클릭합니다.

   - **허용 및** 차단된 보낸 사람 및 도메인 섹션: [EOP에서](create-block-sender-lists-in-office-365.md) 차단된 보낸 사람 목록 만들기 또는 [EOP에서](create-safe-sender-lists-in-office-365.md)수신 허용 - 보낸 사람 목록 만들기에 설명된 바와 같이 허용된 보낸 사람 및 허용된 도메인을 검토하거나 편집합니다.

     작업을 마쳤으면 **저장** 을 클릭합니다.

4. 작업을 마쳤으면 **닫기** 를 클릭합니다.

스팸 방지 정책을 구성하는 방법에 대한 자세한 내용은 [EOP에서 스팸 방지 정책 구성을 참조하세요.](configure-your-spam-filter-policies.md)

## <a name="part-4---protection-from-malicious-urls-and-files-safe-links-and-safe-attachments-in-defender-for-office-365"></a>4부 - 악의적인 URL 및 파일로부터 보호(금고 Defender의 링크 및 금고 첨부 Office 365 파일)

악성 URL 및 파일로부터 클릭 시간 보호는 Microsoft [Defender for](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)Office 365. 첨부 파일 및 링크 금고 [정책을](safe-attachments.md) [통해 금고](safe-links.md) 설정됩니다.

### <a name="safe-attachments-policies-in-microsoft-defender-for-office-365"></a>금고 Microsoft Defender for Office 365

첨부 파일에 대한 권장 설정에 금고 자세한 내용은 을 참조하세요. [금고 설정 을 선택합니다.](recommended-settings-for-eop-and-office365.md#safe-attachments-settings)

1. 의 **금고 포털에서** Microsoft 365 Defender 첨부 파일 페이지를 열 수 <https://security.microsoft.com/safeattachmentv2> 있습니다.

2. 첨부 **금고** 페이지에서 전역 설정을 클릭한 다음 나타나는 플라이아웃에서 다음 설정을 구성합니다. 
   - **에** 대한 Office 365, SharePoint OneDrive 및 Microsoft Teams : 이 설정 켜기( ![ 토글합니다. ](../../media/scc-toggle-on.png) ).

     > [!IMPORTANT]
     > **금고,** OneDrive 및 SharePoint, OneDrive 및 Microsoft Teams 첨부 파일을 설정하기 전에 조직에서 감사 로깅이 설정되어 있는지 확인해야 합니다. 이 작업은 일반적으로 감사 로그 역할이 할당된 사용자가 Exchange Online. 자세한 내용은 감사 로그 검색 켜기 또는 [끄기!를 참조하세요.](../../compliance/turn-audit-log-search-on-or-off.md)

   - **금고 클라이언트에** 대한 Office 켜기 : 이 설정( ![ 토글합니다. ](../../media/scc-toggle-on.png) ). 이 기능은 필수 라이선스 유형에서만 사용할 수 있으며 의미가 있습니다. 자세한 내용은 금고 [문서의 Microsoft 365 E5.](safe-docs.md)
   - **파일을 악성으로** 식별한 문서가 금고 경우에도 사용자가 보호된 보기를 클릭할 수 있도록 허용 : 이 설정이 꺼져 있는지 ![ 확인( 토글 해제). ](../../media/scc-toggle-off.png)

   완료되면 **저장을 클릭합니다.**

3. 첨부 파일 **금고 다시** 만들기 ![ 아이콘을 ](../../media/m365-cc-sc-create-icon.png) 클릭합니다.

4. 열 **수 있는** 금고 첨부 파일 만들기 정책 마법사에서 다음 설정을 구성합니다.
   - **정책 페이지의 이름을 지정합니다.**
     - **이름:** 고유한 설명을 입력합니다.
     - **설명:** 선택적 설명을 입력합니다.
   - **사용자 및 도메인** 페이지: 첫 번째 정책이기 때문에 적용 범위를 [](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains) 최대화하려는 경우 도메인 상자에 허용 도메인을 입력하는 **것이** 좋습니다. 그렇지 않으면 사용자  및  그룹 상자를 사용하여 보다 세부적인 제어를 할 수 있습니다. 이러한 사용자, 그룹 및 도메인 제외를 선택하고 값을 입력하여 **예외를 지정할** 수 있습니다.
   - **설정** 페이지:
     - **금고 알 수 없는 맬웨어 응답**: 차단을 **선택합니다.**
     - **Quarantine policy**: The default value is blank, which means the AdminOnlyAccessPolicy policy is used. Quarantine policies define what users are able to do to quarantined messages, and whether users receive quarantine notifications. 자세한 내용은 [격리 정책](quarantine-policies.md)을 참조하세요.
     - **검색된 첨부 파일이 있는** 첨부 파일 **리디렉션:** 리디렉션 사용: 이 설정을 켜고(선택) 검색된 메시지를 받을 전자 메일 주소를 입력합니다.
     - **검색을 금고** 수 없는 경우 첨부 파일 검색 응답을 적용합니다(시간 제한 또는 오류). 이 설정이 선택되어 있는지 확인

5. 완료되면 제출을 **클릭하고** 완료를 **클릭합니다.**

6. (권장) 전역 관리자 또는 SharePoint Online 관리자로서 _DisallowInfectedFileDownload_ 매개 변수를 SharePoint **[Set-SPOTenant](/powershell/module/sharepoint-online/Set-SPOTenant)** cmdlet을 `$true` 실행합니다.
   - `$true` 검색된 파일에 대한 모든 작업(삭제 제외)을 차단합니다. 검색된 파일을 열거나, 이동하거나, 복사하거나, 공유할 수 없습니다.
   - `$false` 삭제 및 다운로드를 제외한 모든 작업을 차단합니다. 사람들은 위험을 수락하고 검색된 파일을 다운로드할 수 있습니다.

7. 모든 데이터 센터에 변경 내용을 분산하는 데 최대 30분 Microsoft 365 수 있습니다.

첨부 파일에 대한 금고 정책 및 전역 설정을 구성하는 금고 자세한 내용은 다음 항목을 참조하십시오.

- [Microsoft Defender에서 금고 첨부 파일 정책 설정 Office 365](set-up-safe-attachments-policies.md)
- [SharePoint, OneDrive 및 Microsoft Teams에 대해 안전한 첨부 파일 설정](turn-on-mdo-for-spo-odb-and-teams.md)
- [Microsoft 365 E5에서 안전한 문서](safe-docs.md)

### <a name="safe-links-policies-in-microsoft-defender-for-office-365"></a>금고 Microsoft Defender for Office 365

링크의 권장 설정에 대한 자세한 금고 링크 금고 [참조하세요.](recommended-settings-for-eop-and-office365.md#safe-links-settings)

1. 의 **금고** 포털에서 Microsoft 365 Defender 링크 페이지를 열 수 <https://security.microsoft.com/safelinksv2> 있습니다.

2. 링크 **금고** 페이지에서 전역 설정을 클릭한 다음 나타나는 플라이아웃에서 다음 설정을 구성합니다.
   - **설정 앱 섹션의** 콘텐츠에 Office 365 적용되는 앱:
     - 금고 앱에서 Office 365 **링크 사용:** 이 설정이 켜져 있는지 확인( ![ 토글합니다. ](../../media/scc-toggle-on.png) ).
     - **사용자가 앱의** 보호된 링크를 클릭하는 Office 365 추적하지 않습니다. 이 설정을 끄려면( ![ 토글 끄기). ](../../media/scc-toggle-off.png)
     - **사용자가 앱의** 원래 URL을 클릭할 수 Office 365: 이 설정이 켜져 있는지 확인합니다( ![ 토글합니다. ](../../media/scc-toggle-on.png) ).

   완료되면 **저장을 클릭합니다.**

3. 다시 금고 **페이지에서** 만들기 ![ 아이콘을 ](../../media/m365-cc-sc-create-icon.png) 클릭합니다.

4. 열 **수 있는** 금고 정책 만들기 마법사에서 다음 설정을 구성합니다.
   - **정책 페이지의 이름을 지정합니다.**
     - **이름:** 고유한 설명을 입력합니다.
     - **설명:** 선택적 설명을 입력합니다.
   - **사용자 및 도메인** 페이지: 첫 번째 정책이기 때문에 적용 범위를 [](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains) 최대화하려는 경우 도메인 상자에 허용 도메인을 입력하는 **것이** 좋습니다. 그렇지 않으면 사용자  및  그룹 상자를 사용하여 보다 세부적인 제어를 할 수 있습니다. 이러한 사용자, 그룹 및 도메인 제외를 선택하고 값을 입력하여 **예외를 지정할** 수 있습니다.
   - **보호 설정** 페이지:
     - **메시지에서 알 수** 없는 악의적인 URL에 대한 작업 선택: 이 설정을 **켜기 를 선택합니다.**
     - **에서 알 수 없는 URL** 또는 잠재적으로 악의적인 URL에 대한 작업을 Microsoft Teams : 이 설정을 **켜기 를 선택합니다.** 2020년 3월 현재 이 설정은 Preview에 있으며 TAP(Microsoft Teams Technology Adoption Program)의 구성원에게만 제공되거나 작동합니다.
     - **파일을 지정하는** 의심스러운 링크 및 링크에 대한 실시간 URL 검색 적용: 이 설정을 선택합니다(켜기).
       - **메시지를 배달하기** 전에 URL 검색이 완료될 때까지 기다렸다가 : 이 설정을 선택합니다(켜기).
     - **조직 금고 보낸** 전자 메일 메시지에 대한 링크 적용: 이 설정을 선택합니다(켜기).
     - **사용자 클릭 추적 안 하세요.** 이 설정이 선택되어 있지 않은지 확인(꺼져 있습니다.)
     - **사용자가 원래 URL을 클릭할** 수 없습니다. 이 설정이 켜져 있는지 확인합니다(선택).
     - 알림 **및** 경고 페이지에 조직 브랜드 표시: 조직에서 회사 로고를 업로드할 수 있도록 조직에 대한 Microsoft 365 테마 사용자 지정의 지침을 따라야만 이 설정을 선택(켜기)할 수 있습니다. [](../../admin/setup/customize-your-organization-theme.md)
     - **다음 URL을 다시 덮어치지 않습니다.** 이 설정에는 특정 권장이 없습니다. 자세한 내용은 링크 정책의 "다음 URL을 다시 [금고 않습니다." 목록을 참조하세요.](safe-links.md#do-not-rewrite-the-following-urls-lists-in-safe-links-policies)
   - **알림** 페이지:
     - **사용자에게 어떻게 알리시겠습니까?** 섹션: 선택적으로 사용자  지정 알림 텍스트 사용을 선택하여 사용할 사용자 지정 알림 텍스트를 입력할 수 있습니다. 자동 **지역화에** Microsoft 번역기 사용자 지정 알림 텍스트를 사용자 언어로 번역할 수도 있습니다. 그렇지 않은 경우 기본 알림 텍스트 사용을 **선택된 그대로** 떠날 수 있습니다.

5. 완료되면 제출을 **클릭하고** 완료를 **클릭합니다.**

금고 링크 정책 및 전역 설정을 구성하는 금고 지침은 다음 항목을 참조하십시오.

- [Microsoft Defender에서 금고 링크 정책 Office 365](set-up-safe-links-policies.md)
- [Microsoft Defender에서 금고 링크에 대한 전역 설정 Office 365](configure-global-settings-for-safe-links.md)

### <a name="now-set-up-alerts-for-detected-files-in-sharepoint-online-or-onedrive-for-business"></a>이제 검색된 파일에 대한 알림을 SharePoint Online 또는 비즈니스용 OneDrive

SharePoint Online 또는 비즈니스용 OneDrive 파일이 악성으로 식별된 경우 알림을 받으기 위해 이 섹션에 설명된 바와 같이 경고를 설정할 수 있습니다.

1. 의 Microsoft 365 Defender 포털에서 전자 메일 & 공동 작업 정책 & <https://security.microsoft.com>  \> **정책** \> **으로 이동하세요.**

2. 경고 **정책 페이지에서** 새 경고 **정책 을 클릭합니다.**

3. 새 **경고 정책 마법사가** 열립니다. 이름 **페이지에서** 다음 설정을 구성합니다.
   - **이름:** 고유하고 설명적인 이름을 입력합니다. 예를 들어 라이브러리에 악성 파일을 입력할 수 있습니다.
   - **설명:** 선택적 설명을 입력합니다.
   - **심각도**: **낮음,** 중간 또는 **높음** **을 선택합니다.**
   - **범주:** **위협 관리 를 선택합니다.**

   완료되면 다음을 **클릭합니다.**

4. 경고 **설정 만들기 페이지에서** 다음 설정을 구성합니다.
   - **어떤 것을 경고하고 싶나요?** 섹션: **활동이** \> **파일에서 맬웨어가 검색되었습니다.**
   - **경고를 트리거할** 방법 섹션: 활동이 규칙과 일치할 때마다 **확인이** 선택됩니다.

   완료되면 다음을 **클릭합니다.**

5. 받는 **사람 설정 페이지에서** 다음 설정을 구성합니다.
   - **전자 메일 알림 보내기:** 이 설정이 선택되어 있는지 확인
   - **전자 메일 받는 사람:** 악의적인 파일이 감지될 때 알림을 수신해야 하는 전역 관리자, 보안 관리자 또는 보안 독자를 하나 이상 선택합니다.
   - **일별 알림 제한:** **제한 없음이 선택되어** 있는지 확인

   완료되면 다음을 **클릭합니다.**

6. 설정 **검토 페이지에서** 설정을 검토하고 **예,** 바로 켜기 선택되어 있는지 확인한 다음 마친을 **클릭합니다.**

경고 정책에 대한 자세한 내용은 에서 [경고 정책을 Microsoft 365 규정 준수 센터.](../../compliance/alert-policies.md)

> [!NOTE]
> 구성이 완료되면 다음 링크를 사용하여 작업 조사를 시작하세요.
>
> - [위협 방지 상태 보고서](view-email-security-reports.md#threat-protection-status-report)
> - [Microsoft 365 Defender 포털을 사용하여 Defender for Office 365](manage-quarantined-messages-and-files.md#use-the-microsoft-365-defender-portal-to-manage-quarantined-files-in-defender-for-office-365)
> - [SharePoint Online, OneDrive 또는 Microsoft Teams](https://support.microsoft.com/office/01e902ad-a903-4e0f-b093-1e1ac0c37ad2)
> - [2016년 8월에 관리자로 quarantined messages and files Microsoft 365](manage-quarantined-messages-and-files.md)

## <a name="post-setup-tasks-and-next-steps"></a>설치 후 작업 및 다음 단계

위협 방지 기능을 구성한 후 해당 기능이 작동되는 방법을 모니터링해야 합니다. 필요한 작업을 할 수 있도록 정책을 검토하고 변경합니다. 또한 가치를 추가할 수 있는 새로운 기능 및 서비스 업데이트를 확인합니다.

<br>

****

|수행할 작업|자세한 정보를 알아볼 수 있는 리소스|
|---|---|
|보고서를 확인하여 위협 방지 기능이 조직에 어떻게 작동하고 있는지 확인|[전자 메일 보안 보고서](view-email-security-reports.md) <p> [Microsoft Defender for Office 365](view-reports-for-mdo.md) <p> [위협 탐색기](threat-explorer.md)|
|필요한 경우 위협 방지 정책을 주기적으로 검토하고 변경합니다.|[Secure Score](../defender/microsoft-secure-score.md) <p> [Microsoft 365 조사 및 대응 기능](./office-365-ti.md)|
|새로운 기능 및 서비스 업데이트 감시|[표준 및 대상 지정 릴리스 옵션](../../admin/manage/release-options-in-office-365.md) <p> [메시지 센터](../../admin/manage/message-center.md) <p> [Microsoft 365 로드맵](https://www.microsoft.com/microsoft-365/roadmap?filters=&searchterms=advanced%2Cthreat%2Cprotection) <p> [서비스 설명](/office365/servicedescriptions/office-365-service-descriptions-technet-library)|
|

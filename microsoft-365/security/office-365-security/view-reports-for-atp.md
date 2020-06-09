---
title: Advanced Threat Protection에 대 한 보고서 보기
f1.keywords:
- CSH
ms.author: tracyp
author: msfttracyp
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: e47e838c-d99e-4c0b-b9aa-e66c4fae902f
ms.collection:
- M365-security-compliance
description: 보안 및 준수 센터에서 Office 365 Advanced Threat Protection에 대 한 보고서를 찾아서 사용 &amp; 합니다.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 3e6f6e3f2fd5820f280ab47f3ffdde11bd9da72e
ms.sourcegitcommit: 73b2426001dc5a3f4b857366ef51e877db549098
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/09/2020
ms.locfileid: "44613363"
---
# <a name="view-reports-for-office-365-advanced-threat-protection"></a>Office 365 Advanced Threat Protection에 대 한 보고서 보기

조직에 [Office 365 ATP (Advanced Threat Protection](office-365-atp.md) )가 있고 [필요한 사용 권한이](#what-permissions-are-needed-to-view-the-atp-reports)있는 경우 보안 및 준수 센터에서 여러 ATP 보고서를 사용할 수 있습니다 &amp; . ( **보고서** \> 로 이동 **대시보드**.)

![보안&amp; 규정 준수 센터 대시보드는 Advanced Threat Protection이 작업 중인 위치를 확인할 수 있도록 도와줍니다](../../media/6b213d34-adbb-44af-8549-be9a7e2db087.png)

ATP 보고서에는 다음이 포함 됩니다.

- [위협 방지 상태 보고서](#threat-protection-status-report)
- [ATP 파일 형식 보고서](#atp-file-types-report)
- [ATP 메시지 폐기 보고서](#atp-message-disposition-report)
- [실시간 검색 또는 탐색기](threat-explorer.md) (OFFICE 365 ATP 계획 1 또는 2 중 어떤 것이 있는지에 따라 다름)
- ... [등](#additional-reports-to-view)이 있습니다.

이 문서를 읽으면 ATP 보고서에 대 한 개요를 확인 하 고 사용 하는 방법을 확인할 수 있습니다.

## <a name="threat-protection-status-report"></a>위협 방지 상태 보고서

**위협 방지 상태** 보고서는 EOP ( [Exchange Online Protection](exchange-online-protection-overview.md) ) 및 [Office 365 ATP](office-365-atp.md)에 의해 감지 되어 차단 된 악의적인 콘텐츠와 악성 전자 메일에 대 한 정보를 함께 가져오는 단일 보기입니다. 이 보고서는 시간에 따른 검색 (최대 90 일)을 확인 하는 데 유용 하며, 보안 관리자는 경향을 식별 하거나 정책 조정이 필요한 지 여부를 결정할 수 있습니다.

이 보고서는 맬웨어 방지 엔진에 의해 차단 된 파일 또는 웹 사이트 주소 (Url)와 같은 악성 콘텐츠가 포함 된 고유한 전자 메일 메시지의 집계 된 개수를 제공 합니다 [(0 시간 자동 제거 (ZAP)](zero-hour-auto-purge.md)및 Atp [safe Links](atp-safe-links.md), [Atp 안전한 첨부 파일](atp-safe-attachments.md)및 [atp](set-up-anti-phishing-policies.md)기능).

이러한 정보를 필터링 하 고 breakdowns이 보고서의 정보를 보다 세부적으로 분류 하는 데 사용할 수 있습니다. 특히 **전자 메일** \> **피싱** 및 **전자 메일** \> **맬웨어 보기**에 대 한 ' 중단 기준 ' 메뉴가 포함 되어 있습니다. 그러면 다음과 같이 데이터를 분류 합니다.

|||
|---|---|
|검색 유형별|이러한 위협을 파악 하는 데 도움이 되는 정책은 무엇입니까?|
|검색 기술|어떤 기본 Microsoft 기술이 위협을 포착 했습니까?|
|배달 상태별|위협으로 검색 된 전자 메일 메시지는 어떻게 되었습니까?|
|

> [!TIP]
> 전자 메일 > 피싱 | 맬웨어 보기에는 *ATP에서 생성 된 파일 신뢰도*, *파일 샌드 박싱*, *URL 샌드 박싱*, *스푸핑 방지: DMARC 실패*등의 범주를 포함 하 여 표시 되는 검색 기술에 대 한 자세한 breakdowns 있으며,이를 통해 조직에서 위협을 찾아낼 기능을 정확히 알 수 있습니다.

![' 나누기 기준 '이 표시 되는 위협 보호 상태 보고서 드롭다운](../../media/tp-threatProtectStatRpt-BreakDownBy.png)

이러한 보기는 단추 클릭 ( **전자 메일** \> **피싱**, **전자 메일** \> **맬웨어**및 **콘텐츠** \> **맬웨어** 보기)을 통해 내보낼 수 있는 옵션을 제공 합니다. 컴퓨터로 내보낸 집계 된 데이터를 Excel에서 열 수 있습니다.

![이 그래픽은 맬웨어 보기 메뉴의 옵션으로 내보내기, 만들기 일정 및 요청 보고서 간의 오른쪽을 보여 줍니다.](../../media/tp-threatProtectStatRpt-BreakDownByExport.png)

**참고**: **피싱** 및 **맬웨어에** 대해 내보낼 수 있는 최대 항목 수는 1만에 불과합니다. 보기를 내보낼 경우 가장 최근 1만 항목만 내보내집니다.

개요 및 전자 메일 보기에는 24 시간 (요청 다시)이 아닌 처리 시간 내에 정보가 표시 됩니다. 여기에서 속도 향상은 명확한 신호입니다.

> [!NOTE]
> [Office 365 ATP](office-365-atp.md) 또는 [Exchange Online Protection](exchange-online-protection-overview.md)(EOP)이 있는 고객은 위협 보호 상태 보고서를 사용할 수 있습니다. 그러나 ATP 고객에 대 한 위협 방지 상태 보고서에 표시 되는 정보에는 고객에 게 표시 될 수 있는 것과 다른 데이터가 포함 될 가능성이 EOP. 예를 들어 ATP 고객에 대 한 위협 방지 상태 보고서에는 [SharePoint Online, OneDrive 또는 Microsoft 팀에서 검색 된 악성 파일](atp-for-spo-odb-and-teams.md)에 대 한 정보가 포함 됩니다. 이러한 정보는 ATP와 관련 된 것 이므로, EOP가 아닌 고객은 위협 보호 상태 보고서에 해당 세부 정보를 볼 수 없습니다.

위협 방지 상태 보고서를 보려면 [보안 및 &amp; 준수 센터](https://protection.office.com)에서 **보고서** \> **대시보드** \> **위협 보호 상태로**이동 합니다.

![ATP 위협 방지 상태 보고서](../../media/6bdd41eb-62e0-423b-9fd4-d1d5baf0cbd5.png)

하루 동안 자세한 상태를 보려면 그래프를 가리킵니다.

![ATP 위협 방지 상태 데이터 (일)](../../media/d5c2c6ad-c002-4985-a032-c866e46fdea8.png)

기본적으로 위협 방지 상태 보고서에는 최근 7 일간의 데이터가 표시 됩니다. 그러나 **필터** 를 선택 하 고 날짜 범위를 변경 하 여 데이터를 최대 90 일까 지 확인할 수 있습니다. 평가판 구독을 사용 하는 경우에는 30 일간의 데이터를 제한할 수 있습니다.

![ATP 위협 방지 상태 필터](../../media/4f703369-642b-402b-9758-b9c828283410.png)

**데이터 보기 기준** 메뉴를 사용 하 여 보고서에 표시 되는 정보를 변경할 수도 있습니다.

![ATP 위협 방지 상태 보고서에 대 한 옵션 보기](../../media/4959bf8c-d192-4542-b00b-184e101e7513.png)

## <a name="url-protection-status-report"></a>URL 보호 상태 보고서

이 보고서는 수집 된 데이터를 기반으로 하며, 클릭 당 검색 되는 위협, 즉 대부분의 다른 전자 메일 위협 관련 보고서는 메시지 데이터에 따라 결정 됩니다. 이 보고서는 전자 메일 메시지 및 문서의 하이퍼링크에서 제공 되는 위협 (클릭 당)을 보여 주도록 디자인 되었습니다. 다음과 같은 두 가지 보기가 있습니다.

|||
|---|---|
|URL 보호 작업 클릭|차단 되었지만 차단 되었지만 사용자가 간편 하 게 클릭 하 여 재정의 되 고 허용 되는 Url 수를 확인 합니다.|
|URL 클릭 응용 프로그램|URL이 클릭 된 응용 프로그램을 확인 합니다.|
|

정보 테이블에서는 클릭 시간 및 사용자 정보에 대 한 자세한 정보를 볼 수 있습니다. 마지막으로, URL 보호 상태 보고서에는 ATP 안전한 링크 기능의 보호 기능이 표시 되므로 ATP 안전한 링크를 사용 하도록 설정한 고객만이 보고서에 반영 된 데이터를 볼 수 있습니다.

> [!NOTE]
> 이는 *보호 추세 보고서*로, 데이터가 더 큰 데이터 집합의 추세를 나타냅니다. 따라서 집계 보기의 데이터는 실시간으로 사용할 수 없지만 세부 정보 표 보기의 데이터는 두 보기 간에 약간의 차이가 있을 수 있습니다.

## <a name="atp-file-types-report"></a>ATP 파일 형식 보고서

**Atp 파일 형식** 보고서에는 [Atp 안전한 첨부 파일](atp-safe-attachments.md)에 의해 악의적으로 검색 된 파일 유형이 표시 됩니다.

이 보고서를 보려면 [보안 및 &amp; 준수 센터](https://protection.office.com)에서 **보고서** \> **대시보드** \> **ATP 파일 형식**으로 이동 합니다.

![ATP 파일 형식 보고서](../../media/6e3f5d33-79aa-4b2d-938c-6ef135d9e54c.png)
  
특정 날짜를 가리키면 [ATP 안전한 첨부 파일](atp-safe-attachments.md) 및 [스팸 방지 맬웨어 방지 &amp; 보호](anti-spam-and-anti-malware-protection.md)에서 검색 된 악의적인 파일의 유형을 확인할 수 있습니다.
  
![ATP 파일 형식 하루에 대 한 보고서 데이터](../../media/10d18428-699a-41d2-a73e-be3a8214ada1.png)

## <a name="atp-message-disposition-report"></a>ATP 메시지 폐기 보고서

**ATP 메시지 처리** 보고서에는 악성 콘텐츠가 있는 것으로 검색 된 전자 메일 메시지에 대해 수행 된 작업이 표시 됩니다.

이 보고서를 보려면 [보안 및 &amp; 준수 센터](https://protection.office.com)에서 **보고서** \> **대시보드** \> **ATP 메시지 처리**로 이동 합니다.

![ATP 메시지 처리 보고서](../../media/b0ff65c4-53d3-496d-bafa-8937a5eb69e5.png)

차트의 막대 위에 마우스를 올리면 해당 요일의 검색 된 전자 메일에 대해 수행한 작업을 확인할 수 있습니다.

![ATP 메시지 처리 보고서 데이터 (일)](../../media/68d2beb8-4b30-48c4-8ba6-5e8ab88ae456.png)

## <a name="additional-reports-to-view"></a>볼 수 있는 추가 보고서

이 문서에서 설명 하는 ATP 보고서 외에도 다음 표에 설명 된 것 처럼 다른 몇 가지 보고서를 사용할 수 있습니다.

|||
|---|---|
|**보고서**|**세부 정보**|
|**탐색기** 또는 **실시간**검색: (Office 365 ATP 계획 2 고객에 게 탐색기가 있습니다. Office 365 ATP 계획 1 고객은 실시간 검색을 합니다.|[위협 탐색기 (실시간 검출)](threat-explorer.md)|
|상위 보낸 사람 및 받는 사람 보고서, 스푸핑 메일 보고서, 스팸 감지 보고서 등의 **전자 메일 보안 보고서**|[보안 및 준수 센터의 전자 메일 보안 보고서 보기 &amp;](view-email-security-reports.md)|
|**ATP 안전한 링크 URL 추적**: (PowerShell을 사용 하 여 생성 하는 보고서) 이 보고서는 지난 7 일 동안 ATP 안전한 링크 작업의 결과를 보여 줍니다.|[Get-UrlTrace cmdlet 참조](https://docs.microsoft.com/powershell/module/exchange/get-urltrace)|
|**EOP 및 ATP 결과**: (PowerShell을 사용 하 여 생성 하는 사용자 지정 보고서) 이 보고서에는 도메인, 날짜, 이벤트 유형, 방향, 동작 및 메시지 수와 같은 정보가 포함 됩니다.|[MailTrafficATPReport cmdlet 참조](https://docs.microsoft.com/powershell/module/exchange/get-mailtrafficatpreport)|
|**EOP 및 ATP**검색: (PowerShell을 사용 하 여 생성 하는 사용자 지정 보고서) 이 보고서에는 악성 파일 또는 Url, 피싱 시도, 가장 및 기타 잠재적 위협 (전자 메일 또는 파일)에 대 한 자세한 정보가 포함 되어 있습니다.|[MailDetailATPReport cmdlet 참조](https://docs.microsoft.com/powershell/module/exchange/get-maildetailatpreport)|
|

## <a name="what-permissions-are-needed-to-view-the-atp-reports"></a>ATP 보고서를 표시 하는 데 필요한 사용 권한은 무엇입니까?

이 문서에서 설명 하는 보고서를 보고 사용 하려면 보안 및 ** &amp; 준수 센터와 Exchange 관리 센터 둘 다에 대해 적절 한 역할이 할당 되어 있어야 합니다**.

- 보안 &amp; 및 준수 센터에는 다음 역할 중 하나가 할당 되어 있어야 합니다.

  - 조직 관리
  - 보안 관리자 (Azure Active Directory 관리 센터에서 할당할 수 [https://aad.portal.azure.com](https://aad.portal.azure.com) 있음)
  - 보안 운영자 (Azure Active Directory 관리 센터에서 할당할 수 [https://aad.portal.azure.com](https://aad.portal.azure.com) 있음)
  - 보안 읽기 권한자

- Exchange Online의 경우 Exchange 관리 센터 ( [https://outlook.office365.com/ecp](https://outlook.office365.com/ecp) ) 또는 PowerShell cmdlet ( [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell)참조)에서 다음 역할 중 하나를 할당 받아야 합니다.

  - 조직 관리
  - 보기 전용 조직 관리
  - 보기 권한만 있는 받는 사람 역할
  - 준수 관리

자세한 내용은 다음 리소스를 참조하세요.

- [보안 및 준수 센터의 사용 권한 &amp;](permissions-in-the-security-and-compliance-center.md)

- [Exchange Online의 기능 사용 권한](https://docs.microsoft.com/exchange/permissions-exo/feature-permissions)

## <a name="what-if-the-reports-arent-showing-data"></a>보고서에 데이터가 표시 되지 않으면 어떻게 하나요?

ATP 보고서에 데이터가 표시 되지 않는 경우 정책이 올바르게 설정 되어 있는지 다시 확인 합니다. 조직에 atp 보호 기능을 적용 하려면 atp [안전한 링크 정책](set-up-atp-safe-links-policies.md) 및 [Atp 안전 첨부 파일 정책이](set-up-atp-safe-attachments-policies.md) 정의 되어 있어야 합니다. 또한 [Office 365에서 스팸 방지 및 맬웨어 방지 보호 기능을](anti-spam-and-anti-malware-protection.md)참조 하세요.

## <a name="related-topics"></a>관련 항목

[보안 및 준수 센터의 보고서 및 정보 &amp;](reports-and-insights-in-security-and-compliance.md)
  
[역할 권한 (Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#role-permissions)

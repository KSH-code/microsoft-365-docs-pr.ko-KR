---
title: SharePoint 2010에서 업그레이드
ms.author: tracyp
author: MSFTTracyP
manager: laurawi
ms.date: 04/13/2020
audience: ITPro
ms.topic: conceptual
ms.prod: office-online-server
localization_priority: Normal
ms.collection:
- Ent_O365
- SPO_Content
search.appverid:
- MET150
- WSU140
- OSU140
ms.assetid: 985a357f-6db7-401f-bf7a-1bafdf1f312c
f1.keywords:
- NOCSH
description: SharePoint 2010 및 Sharepoint Server 2010에서 업그레이드할 정보 및 리소스를 찾아 하세요. 두 가지 모두 지원은 2021년 4월 13일까지입니다.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 4fa82fb0e382a244cdc126609ac62d17280b9702
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50925335"
---
# <a name="upgrading-from-sharepoint-2010"></a>SharePoint 2010에서 업그레이드

*이 문서는 Microsoft 365 Enterprise와 Office 365 Enterprise에 모두 적용됩니다.*

Microsoft SharePoint 2010 및 SharePoint Server 2010은 **2021년 4월 13일부터** 지원이 종료됩니다. 이 문서에서는 기존 SharePoint Server 2010 데이터를 Microsoft 365의 SharePoint Online으로 마이그레이션하거나, 사내 SharePoint Server 2010 환경을 업그레이드하는 데 도움이 되는 리소스를 제공합니다.

## <a name="what-is-end-of-support"></a>지원이 *종료된 것은 무엇입니까?*

대부분의 Microsoft 제품에는 새로운 기능, 버그 수정, 보안 수정 등 지원 수명 주기가 있습니다. 지원 종료 날짜가 지난 후 제품 작동이 중지되지 않지만 Microsoft는 더 이상 다음을 제공하지 않습니다.

- 발생할 수 있는 문제에 대한 기술 지원

- 서버의 안정성과 사용 가능성에 영향을 줄 수 있는 문제에 대한 버그 수정

- 서버가 보안 위반에 취약해질 수 있는 취약점에 대한 보안 수정

- 표준 시간대 업데이트.

즉, 제품에 대한 추가 업데이트, 패치 또는 수정이 없습니다(보안 패치/수정 포함). Microsoft 지원은 지원 노력을 최신 버전으로 완전히 전환할 것입니다.

SharePoint Server 2010 지원이 종료되면 제품을 업그레이드하고 중요한 데이터를 마이그레이션하기 전에 더 이상 필요하지 않는 데이터를 삭제합니다.

> [!NOTE]
> 소프트웨어 수명 주기는 일반적으로 초기 릴리스부터 10년 동안 지속됩니다. [Microsoft 솔루션 공급자는](https://go.microsoft.com/fwlink/?linkid=841249) 다음 버전의 소프트웨어로 업그레이드하거나 Microsoft 365 마이그레이션(또는 둘 다)으로 마이그레이션하는 데 도움이 될 수 있습니다. 중요한 기술, 특히 SharePoint에서 사용하는 Microsoft SQL Server 기술에 대한 지원 종료 날짜를 알고 있어야 합니다. 자세한 내용은 [고정 수명 주기 정책을 참조하세요.](https://support.microsoft.com/help/14085)

## <a name="plan-ahead"></a>미리 계획

제품 수명 주기 사이트에서 종료 날짜를 [확인 합니다.](https://support.microsoft.com/lifecycle/search?alpha=SharePoint%20Server%202010) 이러한 날짜를 염두에 두어 업그레이드 또는 마이그레이션을 계획합니다. 제품이 나열된 날짜에 *작동을* 중지하지 않습니다. 그러나 해당 날짜 이후에는 설치가 더 이상 패치되지 않습니다. 따라서 제품의 다음 버전으로의 매끄러운 전환을 계획할 수 있습니다.

이 행렬은 마이그레이션 옵션 간 과정을 그리면 도움이 됩니다.

|지원 제품 종료|좋음 |가장 적합한|
|---|---|---|
|SharePoint Server 2010|SharePoint Server 2013(사내)|SharePoint Online|
||SharePoint Online을 통해 SharePoint Server 2013 하이브리드|SharePoint Server 2016(사내)|
|||SharePoint 클라우드 하이브리드 검색|

낮은 규모의 옵션(양호)을 선택하는 경우 SharePoint Server 2010에서 마이그레이션한 후 곧 다른 업그레이드에 대한 계획을 세우는 것이 좋습니다.

다음은 SharePoint Server 2010에 대한 지원이 종료되지 않도록 방지하기 위해 취할 수 있는 세 가지 경로입니다.

![SharePoint Server 2010 업그레이드 경로](../media/upgrade-from-sharepoint-2010/upgrade-from-sharepoint-2010-paths.png)

> [!NOTE]
> SharePoint Server 2010 및 SharePoint Foundation 2010에 대한 지원 종료는 현재 2021년 4월 13일로 예정됩니다. 그러나 제품 수명 [주기](https://support.microsoft.com/lifecycle) 사이트에서 최신 날짜를 확인해야 합니다.

## <a name="whats-next"></a>다음 작업

SharePoint Server 2013 및 SharePoint Foundation 2013은 자체 서버에 사내에 설치할 수 있습니다. 또는 Microsoft 365의 일부인 온라인 서비스인 SharePoint Online을 사용할 수 있습니다. 다음을 선택할 수 있습니다.

- SharePoint Online으로 마이그레이션합니다.

- SharePoint Server 또는 SharePoint Foundation을 사내에서 업그레이드합니다.

- 위의 두 가지 작업을 모두 합니다.

- [SharePoint 하이브리드 솔루션을 구현합니다.](/sharepoint/hybrid/hybrid)

사용자 지정을 유지 관리하거나 마이그레이션하고 하드웨어를 업그레이드하는 등 서버 팜을 유지 관리하는 데 들이는 숨겨진 비용을 고려합니다. 이러한 요소를 고려한 경우, 보다 쉽게 On-premises를 업그레이드할 수 있습니다. 사용자 지정을 많이 수행하지 않고 레거시 SharePoint Server에서 팜을 실행하면 SharePoint Online으로의 계획된 마이그레이션을 통해 이점을 사용할 수 있습니다. 또한 사내 SharePoint Server 환경의 경우 SharePoint Online에서 일부 데이터를 이동하여 하드웨어 관리 오버헤드를 줄일 수 있습니다.

> [!NOTE]
> SharePoint 관리자는 Microsoft 365 구독을 만들고, 새 SharePoint Online 사이트를 설정한 다음 SharePoint Server 2010에서 정리하여 필수 문서만 새 사이트로 만들 수 있습니다. 그런 다음 SharePoint Server 2010 사이트에서 모든 남은 데이터를 사내 보관함으로 드레인할 수 있습니다.

|SharePoint Online|SharePoint Server 사내|
|---|---|
|높은 시간(계획/실행/확인)|높은 시간(계획/실행/확인)|
|자금 비용 절감(하드웨어 구매 없음)|자금 비용이 더 높음(하드웨어 구매)|
|마이그레이션의 일회성 비용|향후 마이그레이션당 일회성 비용 반복|
|총 소유/유지 관리 비용 절감|총 소유/유지 관리 비용 높음|

Microsoft 365로 일회성 이동하면 데이터를 구성하고 클라우드로 이동할 데이터 및 남길 데이터를 결정하는 동안 비용이 더 많이 드는 것입니다. 그러나 데이터가 마이그레이션된 후 향후 업그레이드는 자동으로 수행됩니다. 따라서 하드웨어 및 소프트웨어 업데이트를 더 이상 관리할 필요가 없습니다. 팜의 사용 시간은 Microsoft SLA(서비스 수준 [계약)에 의해 지원됩니다.](/office365/servicedescriptions/office-365-platform-service-description/service-level-agreement)

### <a name="migrate-to-sharepoint-online"></a>SharePoint Online으로 마이그레이션

SharePoint Online에서 필요한 모든 기능을 제공하는지 확인 [SharePoint 서비스 설명을 참조하세요.](/office365/servicedescriptions/sharepoint-online-service-description/sharepoint-online-service-description)

SharePoint Server 2010(또는 SharePoint Foundation 2010)에서 SharePoint Online으로 직접 마이그레이션할 수 없습니다. 마이그레이션 작업의 많은 수작업이 수동입니다. 그러나 이 단계에서는 이동하기 전에 더 이상 필요하지 않습니다. 다른 데이터를 저장소에 보관할 수 있습니다. 

SharePoint Server 2010 및 SharePoint Foundation 2010은 지원 종료 시 작동하지 않습니다. 따라서 관리자는 고객이 일부 데이터를 이동하는 것을 잊어버려도 SharePoint가 계속 실행되는 기간을 사용할 수 있습니다.

SharePoint Server 2013 또는 SharePoint Server 2016으로 업그레이드하고 데이터를 SharePoint Online에 저장하려는 경우 SharePoint 마이그레이션 [API를](https://support.office.com/article/Upload-on-premises-content-to-SharePoint-Online-using-PowerShell-cmdlets-555049c6-15ef-45a6-9a1f-a1ef673b867c?ui=en-US&amp;rs=en-US&amp;ad=US) 사용하여 정보를 비즈니스용 OneDrive로 마이그레이션할 수 있습니다.

|SharePoint Online 이점|SharePoint Online 단점|
|---|---|
|Microsoft는 SPO 하드웨어 및 모든 하드웨어 관리 기능을 제공합니다.|사용 가능한 기능은 SharePoint Server의 사내 및 SPO 간에 다를 수 있습니다.|
|구독의 전역 관리자로서 SPO 사이트에 관리자를 할당할 수 있습니다.|SharePoint Server의 팜 관리자가 사용할 수 있는 일부 작업은 Microsoft 365의 SharePoint 관리자 역할에 존재하지 않습니다(또는 필요하지 않은 경우). 그러나 SharePoint 관리, 사이트 모음 관리 및 사이트 소유권은 사용자조그에 로컬입니다.|
|Microsoft는 SharePoint Online이 실행되는 SQL 하드웨어 및 소프트웨어에 패치, 수정 및 업데이트를 적용합니다.|서비스에서 현재 파일 시스템에 액세스할 수 없는 경우 사용자 지정이 제한됩니다.|
|Microsoft는 서비스 수준 [계약을 게시하고](/office365/servicedescriptions/office-365-platform-service-description/service-level-agreement) 서비스 수준 인시던트 해결을 위해 신속하게 움직입니다.|백업 및 복원 및 기타 복구 옵션은 SharePoint Online의 서비스에서 자동화됩니다. 사용되지 않는 경우 백업을 덮어 쓰게 됩니다.|
|보안 테스트 및 서버 성능 조정은 Microsoft에서 서비스에서 지속적으로 수행됩니다.|사용자 인터페이스 및 기타 SharePoint 기능에 대한 변경 내용은 서비스에서 설치하며 설정 또는 해제해야 할 수 있습니다.|
|Microsoft 365는 Microsoft 규정 준수 제품인 다양한 산업 [표준을 충족합니다.](/compliance/regulatory/offering-home)|[마이그레이션에 대한 FastTrack](https://go.microsoft.com/fwlink/?linkid=518597) 지원은 제한됩니다.  <br/> 업그레이드의 많은 내용은 수동 또는 SharePoint Online 및 [OneDrive](/sharepointmigration/upload-on-premises-content-to-sharepoint-online-using-powershell-cmdlets)마이그레이션 콘텐츠 로드맵에 설명된 SPO 마이그레이션 API를 통해 수행됩니다.|
|Microsoft 지원 엔지니어 및 데이터 센터 직원은 구독에 대한 무제한 관리자 액세스 권한이 없습니다.|최신 버전의 SharePoint를 지원하기 위해 하드웨어 인프라를 업그레이드해야 하는 경우 또는 업그레이드를 위해 보조 팜이 필요한 경우 추가 비용이 있을 수 있습니다.|
|솔루션 공급자는 데이터를 SharePoint Online으로 마이그레이션하는 일회성 작업을 지원할 수 있습니다.|SharePoint Online에 대한 모든 변경 내용이 제어 내에 있는 것은 아니며, 마이그레이션 후 메뉴, 라이브러리 및 기타 기능의 디자인 차이로 일시적으로 사용 가능성에 영향을 줄 수 있습니다.|
|온라인 제품은 서비스 전체에서 자동으로 업데이트됩니다. 기능은 더 이상 사용하지 않을 수 있지만 지원 수명 주기가 실제 종료된 기능은 없습니다.|기본 서버와 SharePoint Server 또는 SharePoint Foundation에 대한 지원 종료 SQL 있습니다.|

새 Microsoft 365 사이트를 만들기로 결정하고 필요한 경우 데이터를 수동으로 해당 사이트로 마이그레이션하려면 [Microsoft 365](https://www.microsoft.com/microsoft-365/)옵션을 선택합니다.

### <a name="upgrade-sharepoint-server-on-premises"></a>SharePoint Server 사내 업그레이드

SharePoint Server 2019의 경우 업그레이드가 *직렬로 진행되어야 합니다.* SharePoint Server 2010에서 SharePoint Server 2016 또는 SharePoint 2019로 직접 업그레이드할 수 있는 방법은 없습니다. 직렬 업그레이드 경로:

- SharePoint Server 2010 \> SharePoint Server 2013 \> SharePoint Server 2016

SharePoint 2010에서 SharePoint Server 2016으로의 전체 경로를 따르는 데는 시간이 걸릴 수 있습니다. 업그레이드에는 하드웨어 비용(SQL 서버도 업그레이드해야 합니다), 소프트웨어 및 관리 비용이 수반됩니다. 또한 사용자 지정을 업그레이드하거나 중단해야 할 수도 있습니다. SharePoint Server 팜을 업그레이드하기 전에 중요한 사용자 지정을 문서화해야 합니다.

> [!NOTE]
> 지원 종료 SharePoint 2010 팜을 유지 관리하고, 새 하드웨어에 SharePoint Server 2016 팜을 설치한 다음(별도의 팜을 나란히 실행) 콘텐츠의 수동 마이그레이션(예: 콘텐츠 다운로드 및 다시 업로드용)을 계획하고 실행할 수 있습니다. 그러나 수동 이동을 하는 계정의 별칭이 있는 현재 마지막으로 수정된 계정이 2010년의 문서와 같이 이러한 수동 이동에 대한 잠재적 문제가 있습니다. 또한 사이트, 하위 사이트, 사용 권한 및 목록 구조를 다시 설정하는 등의 작업을 미리 수행해야 합니다. 업그레이드 전에 환경을 정리해야 합니다. 저장소로 이동할 수 있는 데이터를 고려하거나 더 이상 필요하지 않습니다. 이렇게 하면 마이그레이션의 영향을 줄일 수 있습니다. 업그레이드하기 전에 그리고 해제하기 전에(확실하게) 기존 팜이 작동해야 합니다.

지원되는 업그레이드 경로와 지원되지 않는 업그레이드 경로를 *검토해야 합니다.*

- [SharePoint Server 2010](/previous-versions/office/sharepoint-2007-products-and-technologies/cc262747(v=office.12))

- [SharePoint Server 2013](/SharePoint/upgrade-and-update/review-supported-editions-and-products-for-upgrading-to-sharepoint-2013)

사용자 *지정이* 있는 경우 마이그레이션 경로의 각 단계를 계획하는 것이 중요합니다.

- [SharePoint Server 2010](/previous-versions/office/sharepoint-server-2010/cc263203(v=office.14))

- [SharePoint Server 2013](/SharePoint/upgrade-and-update/create-a-communication-plan-for-the-upgrade-to-sharepoint-2013)

|On-premises advantage|사내 불이행|
|---|---|
|서버 하드웨어에서 SharePoint 팜(및 해당 SQL)의 모든 측면을 완전하게 제어할 수 있습니다.|모든 중단 및 수정은 회사의 책임입니다. 그러나 제품이 지원 종료되지 않은 경우 유료 Microsoft 지원에 참여할 수 있습니다.|
|하이브리드를 통해 SharePoint Online 구독에 사내 팜을 연결하는 옵션이 있는 SharePoint Server의 전체 기능 집합|SharePoint Server 및 해당 SQL 팜의 업그레이드, 패치, 보안 픽스, 하드웨어 업그레이드 및 모든 유지 관리는 사내에서 관리됩니다.|
|SharePoint Online보다 더 많은 사용자 지정 옵션을 위한 모든 액세스|[Microsoft 규정 준수 제품은](/compliance/regulatory/offering-home) 수동으로 구성해야 합니다.|
|보안 테스트 및 서버 성능 조정은 제어 하에 프레미스에서 수행됩니다.|Microsoft 365는 SharePoint Server의 사내와 상호 연결되지 않는 기능을 SharePoint Online에서 사용할 수 있도록 할 수 있습니다.|
|솔루션 공급자는 데이터를 다음 버전의 SharePoint Server 이상으로 마이그레이션하는 데 도움이 될 수 있습니다.|SharePoint Server 사이트는 SharePoint Online에 표시되어 있는 [SSL/TLS](/SharePoint/security-for-sharepoint-server/enable-tls-1-1-and-tls-1-2-support-in-sharepoint-server-2016) 인증서를 자동으로 사용하지 않습니다.|
|SharePoint Server의 이름 지정 규칙 및 백업 및 복원 및 기타 복구 옵션에 대한 모든 제어|SharePoint Server의 사내는 제품 수명 주기에 민감합니다.|

### <a name="upgrade-resources"></a>리소스 업그레이드

먼저 하드웨어 및 소프트웨어 요구 사항을 비교합니다. 현재 환경이 기본 요구 사항을 충족하지 않는 경우 팜 또는 서버의 하드웨어를 먼저 업그레이드해야 SQL 있습니다. 

일부 사이트를 SharePoint Online의 "evergreen" 하드웨어로 이동할 수 있습니다. 평가를 수행한 후 지원되는 업그레이드 경로 및 방법을 따르면 됩니다.

- *하드웨어/소프트웨어 요구 사항:*

    [SharePoint Server 2010](/previous-versions/office/sharepoint-server-2010/cc262485(v=office.14))  |  [SharePoint Server 2013](/SharePoint/install/hardware-and-software-requirements-0)  |  [SharePoint Server 2016](/SharePoint/install/hardware-and-software-requirements)

- *소프트웨어 경계 및 제한:*

    [SharePoint Server 2010](/previous-versions/office/sharepoint-server-2010/cc262787(v=office.14))  |  [SharePoint Server 2013](/SharePoint/install/software-boundaries-and-limits)  |  [SharePoint Server 2016](/SharePoint/install/software-boundaries-and-limits-0)

- *업그레이드 프로세스 개요:*

    [SharePoint Server 2010](/previous-versions/office/sharepoint-server-2010/cc303420(v=office.14))  |  [SharePoint Server 2013](/SharePoint/upgrade-and-update/upgrade-to-sharepoint-server-2016)  |  [SharePoint Server 2016](/SharePoint/upgrade-and-update/upgrade-to-sharepoint-server-2016)

### <a name="create-a-hybrid-solution-with-sharepoint-online-and-sharepoint-server-on-premises"></a>SharePoint Online 및 SharePoint Server의 하이브리드 솔루션 만들기

하이브리드 설정은 일부 마이그레이션 요구에 대해 사내 및 온라인 둘 다의 최상의 기능을 제공합니다. SharePoint Server 2013, 2016 또는 2019 팜을 SharePoint Online에 연결하여 SharePoint 하이브리드를 만들 수 있습니다. SharePoint 하이브리드 솔루션에 대해 [자세히 알아보십시오.](https://support.office.com/article/4c89a95a-a58c-4fc1-974a-389d4f195383.aspx)

하이브리드 SharePoint Server 팜이 마이그레이션 목표인 경우 온라인에서 이동할 사이트 및 사용자와 온라인 상태로 유지해야 하는 사이트를 알아 넣습니다. SharePoint Server 팜 콘텐츠의 순위를 높음, 중간 또는 낮음으로 설정하면 이 결정에 도움이 될 수 있습니다. 로그인용 사용자 계정과 SharePoint Server 검색 인덱스를 SharePoint Online과만 공유하면 됩니다. 그러나 사이트 사용 방법을 살펴보기 전까지는 이 요소가 명확하지 않을 수 있습니다. 회사에서 나중에 모든 콘텐츠를 SharePoint Online으로 마이그레이션하기로 결정한 경우 남은 모든 계정과 데이터를 온라인으로 이동하고, 사내 팜을 해제할 수 있습니다. SharePoint 팜의 관리/관리는 이 시점부터 Microsoft 365 콘솔을 통해 수행됩니다.

기존 유형의 하이브리드 및 사내 SharePoint 팜과 Microsoft 365 구독 간의 연결을 구성하는 방법을 익히세요.

|옵션|설명|
|---|---|
|[Microsoft 규정 준수 제품.](/compliance/regulatory/offering-home)|[마이그레이션에 대한 FastTrack](https://www.microsoft.com/fasttrack/microsoft-365) 지원은 제한됩니다.<br/><br/> 업그레이드의 많은 내용은 수동 또는 SharePoint Online 및 [OneDrive](/sharepointmigration/upload-on-premises-content-to-sharepoint-online-using-powershell-cmdlets)마이그레이션 콘텐츠 로드맵에 설명된 SPO 마이그레이션 API를 통해 수행됩니다.|
|Microsoft 지원 엔지니어 및 데이터 센터 직원은 구독에 대한 무제한 관리자 액세스 권한이 없습니다.|최신 버전의 SharePoint를 지원하기 위해 하드웨어 인프라를 업그레이드해야 하는 경우 또는 보조 팜이 필요한 경우 추가 비용이 있을 수 있습니다.|
|파트너는 데이터를 SharePoint Online으로 마이그레이션하는 일회성 작업을 지원할 수 있습니다.||
|온라인 제품은 서비스 전체에서 자동으로 업데이트됩니다. 기능은 더 이상 사용이 불가능할 수 있지만 지원이 종료된 사실은 없습니다.||

새 Microsoft 365 사이트를 만들고 필요한 경우 데이터를 수동으로 마이그레이션하기로 결정한 경우 [Microsoft 365](https://www.microsoft.com/microsoft-365/)옵션을 선택합니다.

### <a name="upgrade-sharepoint-server-on-premises"></a>SharePoint Server 사내 업그레이드

SharePoint 업그레이드에서는 버전을 건너뛸 수 없습니다. 즉, 업그레이드가 직렬로 진행됩니다.

- SharePoint 2007 \> SharePoint Server 2010 \> SharePoint Server 2013 \> SharePoint Server 2016

SharePoint 2007에서 SharePoint Server 2016으로의 전체 경로를 사용하려면 상당한 시간을 투자하고 하드웨어(SQL 서버도 업그레이드해야 합니까), 소프트웨어 및 관리 비용이 수반됩니다. 기능의 중요도에 따라 사용자 지정을 업그레이드하거나 중단해야 합니다.

> [!NOTE]
> 수명 종료 SharePoint 2007 팜을 유지 관리하고, 새 하드웨어에 SharePoint Server 2016 팜을 설치한 다음(별도의 팜을 나란히 실행) 콘텐츠의 수동 마이그레이션(예: 콘텐츠 다운로드 및 다시 업로드용)을 계획하고 실행할 수 있습니다. 그러나 이러한 수동 이동에는 마지막으로 수정된 계정을 수동으로 이동하는 계정의 별칭으로 바꾸는 문서 이동과 같은 몇 가지 단점이 있습니다. 또한 사이트, 하위 사이트, 사용 권한 및 목록 구조를 다시 설정하는 등의 작업을 미리 수행해야 합니다. 어떤 경우든 저장소로 이동할 수 있는 데이터를 고려하거나 더 이상 마이그레이션의 영향을 줄일 필요가 없습니다.

업그레이드 전에 환경을 정리해야 합니다. 업그레이드하기 전에 그리고 해제하기 전에 기존 팜이 작동해야 합니다.

지원되는 업그레이드 경로와 지원되지 않는 업그레이드 경로를 *검토해야 합니다.*

- [SharePoint Server 2007](/previous-versions/office/sharepoint-2007-products-and-technologies/cc262747(v=office.12))

- [SharePoint Server 2010](/previous-versions/office/sharepoint-2007-products-and-technologies/cc262747(v=office.12))

- [SharePoint Server 2013](/SharePoint/upgrade-and-update/review-supported-editions-and-products-for-upgrading-to-sharepoint-2013)

사용자 지정이 *있는* 경우 마이그레이션 경로의 각 단계에 대한 업그레이드를 계획하는 것이 중요합니다.

- [SharePoint 2007](/previous-versions/office/sharepoint-2007-products-and-technologies/cc263203(v=office.12))

- [SharePoint Server 2010](/previous-versions/office/sharepoint-server-2010/cc263203(v=office.14))

- [SharePoint Server 2013](/SharePoint/upgrade-and-update/create-a-communication-plan-for-the-upgrade-to-sharepoint-2013)

|On-premises pro|On-premises con|
|---|---|
|서버 하드웨어에서 SharePoint 팜의 모든 측면을 완전하게 제어할 수 있습니다.|모든 중단 및 수정은 회사의 책임입니다. 그러나 제품이 지원 종료되지 않은 경우 유료 Microsoft 지원에 참여할 수 있습니다.|
|하이브리드를 통해 SharePoint Online 구독에 사내 팜을 연결하는 옵션이 있는 SharePoint Server의 전체 기능 집합|업그레이드, 패치, 보안 픽스 및 SharePoint Server의 모든 유지 관리는 사내에서 관리됩니다.|
|보다 많은 사용자 지정을 위한 모든 권한이 있습니다.|[Microsoft 규정 준수 제품은](/compliance/regulatory/offering-home) 수동으로 구성해야 합니다.|
|보안 테스트 및 서버 성능 조정은 제어 하에 프레미스에서 수행됩니다.|Microsoft 365는 SharePoint Server온-프레미스와 상호 연결되지 않는 기능을 SharePoint Online에서 사용할 수 있도록 할 수 있습니다.|
|파트너는 데이터를 다음 SharePoint Server 버전 이상으로 마이그레이션하는 데 도움을 줄 수 있습니다.|SharePoint Server 사이트는 SharePoint Online에 표시되어 있는 [SSL/TLS](/SharePoint/security-for-sharepoint-server/enable-tls-1-1-and-tls-1-2-support-in-sharepoint-server-2016) 인증서를 자동으로 사용하지 않습니다.|
|SharePoint Server의 이름 지정 규칙 및 백업 및 복원 및 기타 복구 옵션에 대한 모든 제어|SharePoint Server의 사내는 제품 수명 주기에 민감합니다.|

### <a name="upgrade-resources"></a>리소스 업그레이드

먼저 하드웨어 및 소프트웨어 요구 사항을 충족하는지 알고 지원되는 업그레이드 방법을 따르세요.

- *에 대한 하드웨어/소프트웨어 요구 사항*

    [SharePoint Server 2010](/previous-versions/office/sharepoint-server-2010/cc262485(v=office.14))  |  [SharePoint Server 2010](/previous-versions/office/sharepoint-server-2010/cc262485(v=office.14))  |  [SharePoint Server 2013](/SharePoint/install/hardware-and-software-requirements-0)  |  [SharePoint Server 2016](/SharePoint/install/hardware-and-software-requirements)

- *에 대한 소프트웨어 경계 및 제한* 사항

    [SharePoint Server 2007](/previous-versions/office/sharepoint-2007-products-and-technologies/cc262787(v=office.12))  |  [SharePoint Server 2010](/previous-versions/office/sharepoint-server-2010/cc262787(v=office.14))  |  [SharePoint Server 2013](/SharePoint/install/software-boundaries-and-limits)  |  [SharePoint Server 2016](/SharePoint/install/software-boundaries-and-limits-0)

- *에 대한 업그레이드 프로세스 개요*

    [SharePoint Server 2007](/previous-versions/office/sharepoint-2007-products-and-technologies/cc303420(v=office.12))  |  [SharePoint Server 2010](/previous-versions/office/sharepoint-server-2010/cc303420(v=office.14))  |  [SharePoint Server 2013](/SharePoint/upgrade-and-update/upgrade-to-sharepoint-server-2016)  |  [SharePoint Server 2016](/SharePoint/upgrade-and-update/upgrade-to-sharepoint-server-2016)

### <a name="create-a-sharepoint-hybrid-solution-between-sharepoint-online-and-on-premises"></a>SharePoint Online과 사내 간에 SharePoint 하이브리드 솔루션 만들기

마이그레이션 요구에 대한 대답이 사내에서 제공하는 컨트롤과 SharePoint Online에서 제공하는 낮은 소유권 비용 사이에 있는 경우 하이브리드를 통해 SharePoint Server 2013 또는 2016 팜을 SharePoint Online에 연결할 수 있습니다. [SharePoint 하이브리드 솔루션에 대해 자세히 알아보십시오.](https://support.office.com/article/4c89a95a-a58c-4fc1-974a-389d4f195383.aspx)

하이브리드 SharePoint Server 팜이 비즈니스에 도움이 된다고 결정한 경우 기존 유형의 하이브리드 및 사내 SharePoint 팜과 Microsoft 365 구독 간의 연결을 구성하는 방법을 익히세요.

테스트 랩 가이드로 설정할 수 있는 Microsoft 365 개발/테스트 환경을 만들 [수 있습니다.](m365-enterprise-test-lab-guides.md) 평가판을 얻거나 Microsoft 365 구독을 구매한 후 데이터를 마이그레이션할 수 있는 SharePoint Online에서 사이트 모음, 웹 및 문서 라이브러리를 만들 수 있습니다. 마이그레이션 API를 사용하여 수동으로 마이그레이션하거나 하이브리드 마법사를 통해 내 사이트 콘텐츠를 비즈니스용 OneDrive로 마이그레이션하려는 경우 마이그레이션할 수 있습니다.

> [!NOTE]
> 하이브리드 옵션을 사용하려면 먼저 SharePoint Server 2010 팜을 SharePoint Server 2013 또는 2016으로 업그레이드해야 합니다. SharePoint Foundation 2010 및 SharePoint Foundation 2013은 SharePoint Online과의 하이브리드 연결을 지원하지 않습니다.

## <a name="summary-of-options-for-office-2010-client-and-servers-and-windows-7"></a>Office 2010 클라이언트 및 서버 및 Windows 7에 대한 옵션 요약

Office 2010 클라이언트 및 서버와 Windows 7에 대한 업그레이드, 마이그레이션 및 클라우드 옵션으로 이동에 대한 시각적 요약은 [지원 종료 포스터](../downloads/Office2010Windows7EndOfSupport.pdf)를 참조하세요.

[![Office 2010 클라이언트 및 서버에 대한 지원 종료 및 Windows 7 포스터](../media/upgrade-from-office-2010-servers-and-products/office2010-windows7-end-of-support.png)](../downloads/Office2010Windows7EndOfSupport.pdf)

이 포스터는 Office 2010 클라이언트 및 서버 제품 및 Windows 7 지원 종료를 방지하기 위해 취할 수 있는 다양한 경로를 보여 주며, Microsoft 365 Enterprise에서 기본 경로 및 옵션 지원이 강조 표시되어 있습니다.

이 [포스터를](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/Office2010Windows7EndOfSupport.pdf) 다운로드하여 편지형, 법률형 또는 타블로이드(11 x 17) 형식으로 인쇄할 수도 있습니다.

## <a name="related-articles"></a>관련 문서

[Office 2007 또는 2010 서버 및 클라이언트에서 업그레이드하는 데 도움이 되는 리소스](upgrade-from-office-2010-servers-and-products.md)

[Overview of the upgrade process from SharePoint 2010 to SharePoint 2013](/SharePoint/upgrade-and-update/overview-of-the-upgrade-process-from-sharepoint-2010-to-sharepoint-2013)

[SharePoint 2010에서 SharePoint 2013으로의 업그레이드 모범 사례](/SharePoint/upgrade-and-update/best-practices-for-upgrading-from-sharepoint-2010-to-sharepoint-2013)

[SharePoint 2013에서 데이터베이스 업그레이드 문제 해결](/SharePoint/upgrade-and-update/troubleshoot-database-upgrade-issues-in-sharepoint-2013)

[업그레이드에 도움이 되는 Microsoft 솔루션 공급자 검색](https://go.microsoft.com/fwlink/?linkid=841249)

[SharePoint Server 2013에 대해 업데이트된 제품 서비스 정책](/SharePoint/product-servicing-policy/updated-product-servicing-policy-for-sharepoint-2013)

[SharePoint Server 2016에 대해 업데이트된 제품 서비스 정책](/SharePoint/product-servicing-policy/updated-product-servicing-policy-for-sharepoint-server-2016)
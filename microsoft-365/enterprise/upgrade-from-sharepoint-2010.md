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
description: SharePoint 2010 및 Sharepoint Server 2010에서 업그레이드할 정보 및 리소스를 찾을 수 있습니다. 둘 다에 대 한 지원은 2021 년 4 월 13 일입니다.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: fba095a15164f8a09ce1e0a1cbd5ee9cd298aa74
ms.sourcegitcommit: d3ca8021f7da00a474ac14aac5f1358204a848f2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/01/2020
ms.locfileid: "49519766"
---
# <a name="upgrading-from-sharepoint-2010"></a>SharePoint 2010에서 업그레이드

*이 문서는 Microsoft 365 Enterprise와 Office 365 Enterprise에 모두 적용됩니다.*

Microsoft SharePoint 2010 및 SharePoint Server 2010는 기술 지원 종료 **(2021 년 4 월 13 일**)에 도달 합니다. 이 문서에서는 Microsoft 365에서 기존 SharePoint Server 2010 데이터를 SharePoint Online으로 마이그레이션하거나 온-프레미스 SharePoint Server 2010 환경을 업그레이드 하는 데 도움이 되는 리소스를 제공 합니다.

## <a name="what-is-end-of-support"></a>*지원이 종료* 되는 이유는 무엇 인가요?

대부분의 Microsoft 제품에는 지원 수명 주기가 있으며, 이러한 기능은 새로운 기능, 버그 수정, 보안 픽스 등을 받게 됩니다. 지원 종료 날짜 후에도 제품의 작동이 중지 되지는 않지만 Microsoft는 더 이상 다음을 제공 하지 않습니다.

- 발생할 수 있는 문제에 대 한 기술 지원

- 서버의 안정성 및 유용성에 영향을 줄 수 있는 문제에 대 한 버그 수정

- 보안 침해에 취약 한 서버를 만들 수 있는 취약성에 대 한 보안 수정

- 표준 시간대 업데이트

즉, 보안 패치/픽스를 포함 하 여 제품에 대 한 업데이트, 패치 또는 수정 사항이 더 이상 없는 것입니다. Microsoft Support는 지원 노력을 보다 최신 버전으로 완전히 전환 했을 것입니다.

SharePoint Server 2010에 대 한 지원이 끝나면 더 이상 필요 없는 데이터를 삭제 하 고, 제품을 업그레이드 하 고 중요 한 데이터를 마이그레이션해야 합니다.

> [!NOTE]
> 일반적으로 소프트웨어 수명 주기는 초기 릴리스에서 10 년 동안 지속 됩니다. [Microsoft 솔루션 공급자](https://go.microsoft.com/fwlink/?linkid=841249) 는 다음 버전의 소프트웨어로 업그레이드 하거나 microsoft 365 마이그레이션 (또는 둘 다)로 마이그레이션하는 데 도움을 받을 수 있습니다. 특히 SharePoint에서 사용 하는 Microsoft SQL Server 버전의 경우 중요 한 기본 기술에 대 한 지원 종료 날짜를 잘 알고 있어야 합니다. 자세한 내용은 [고정 수명 주기 정책을](https://support.microsoft.com/help/14085)참조 하세요.

## <a name="plan-ahead"></a>사전 계획

[제품 수명 주기 사이트](https://support.microsoft.com/lifecycle/search?alpha=SharePoint%20Server%202010)에서 지원이 완료 되는 날짜를 확인 합니다. 이러한 날짜를 염두에 두고 업그레이드 또는 마이그레이션을 계획 합니다. 제품의 작업은 나열 된 날짜에 *중지 되지 않습니다* . 그러나 해당 날짜 이후에는 설치에 더 이상 패치가 적용 되지 않으므로 다음 제품 버전으로의 원활한 전환을 계획 해야 합니다.

이 매트릭스는 마이그레이션 옵션 간의 과정을 그리는 데 도움이 됩니다.

|지원 종료 제품|좋습니다 |방법은|
|---|---|---|
|SharePoint Server 2010|SharePoint Server 2013 (온-프레미스)|SharePoint Online|
||Sharepoint Server 2013 hybrid with SharePoint Online|SharePoint Server 2016 (온-프레미스)|
|||SharePoint 클라우드 하이브리드 검색|

확장의 낮은 끝에 있는 옵션을 선택 하는 경우 SharePoint Server 2010에서 마이그레이션 후 곧바로 다른 업그레이드 계획을 시작 해야 합니다.

다음은 SharePoint Server 2010에 대 한 지원 종료를 방지 하기 위해 수행할 수 있는 세 가지 경로입니다.

![SharePoint Server 2010 업그레이드 경로](../media/upgrade-from-sharepoint-2010/upgrade-from-sharepoint-2010-paths.png)

> [!NOTE]
> SharePoint Server 2010 및 SharePoint Foundation 2010에 대 한 지원 종료는 현재 년 4 월 13 2021 일에 예정 되어 있습니다. 하지만 [제품 수명 주기 사이트](https://support.microsoft.com/lifecycle) 에서 최신 날짜를 확인 해야 합니다.

## <a name="whats-next"></a>다음 작업

SharePoint Server 2013 및 SharePoint Foundation 2013은 자체 서버에 온-프레미스로 설치할 수 있습니다. 또는 Microsoft 365의 일부인 온라인 서비스인 SharePoint Online을 사용할 수 있습니다. 다음을 선택할 수 있습니다.

- SharePoint Online으로 마이그레이션합니다.

- SharePoint Server 또는 SharePoint Foundation 온-프레미스를 업그레이드 합니다.

- 위의 두 가지 작업을 모두 수행 합니다.

- [SharePoint 하이브리드](https://docs.microsoft.com/sharepoint/hybrid/hybrid) 솔루션을 구현 합니다.

사용자 지정 유지 관리 또는 마이그레이션 하드웨어 업그레이드를 포함 하 여 서버 팜 유지 관리에 대 한 숨겨진 비용을 고려해 야 합니다. 이러한 요인을 고려 했다면 온-프레미스에서 업그레이드 하는 것이 더 쉽습니다. 고급 사용자 지정을 수행 하지 않고 레거시 SharePoint 서버에서 팜을 실행 하는 경우 계획 된 마이그레이션에서 SharePoint Online으로의 혜택을 누릴 수 있습니다. 온-프레미스 SharePoint Server 환경의 경우 SharePoint Online에서 일부 데이터를 이동 하 여 하드웨어 관리 오버 헤드를 줄일 수도 있습니다.

> [!NOTE]
> SharePoint 관리자는 Microsoft 365 구독을 만들고, 새 SharePoint Online 사이트를 설정 하 고, SharePoint Server 2010를 완전히 잘라내어 새로운 사이트에 필수 문서만을 가져올 수 있습니다. 그런 다음 SharePoint Server 2010 사이트에서 온-프레미스 보관 사서함으로 나머지 데이터를 모두 제거할 수 있습니다.

|SharePoint Online|SharePoint Server 온-프레미스|
|---|---|
|높은 비용 (계획/실행/확인)|높은 비용 (계획/실행/확인)|
|저렴 한 비용 (하드웨어 구입 없음)|자금 비용 (하드웨어 구입)|
|마이그레이션 1 회 비용|향후 마이그레이션 당 1 회 비용 반복|
|낮은 총 소유 비용/유지 관리|높은 총 소유 비용/유지 관리|

Microsoft 365로의 일회성 이동은 데이터를 구성 하는 동안 비용이 더 높고 클라우드로 수행할 작업 및 뒤에 남길 작업을 결정 합니다. 그러나 데이터를 마이그레이션한 후에는 하드웨어 및 소프트웨어 업데이트를 더 이상 관리할 필요가 없으므로 향후 업그레이드가 자동으로 수행 됩니다. 그리고 팜의 작동 시간은 [MICROSOFT SLA (서비스 수준 계약)](https://go.microsoft.com/fwlink/?linkid=843153)를 통해 지원 됩니다.

### <a name="migrate-to-sharepoint-online"></a>SharePoint Online으로 마이그레이션

SharePoint Online에서 필요한 모든 기능을 제공 하는지 확인 합니다. [SharePoint 서비스 설명을](https://docs.microsoft.com/office365/servicedescriptions/sharepoint-online-service-description/sharepoint-online-service-description)참조 하세요.

SharePoint Server 2010 (또는 SharePoint Foundation 2010)에서 SharePoint Online으로 직접 마이그레이션할 수는 없습니다. 따라서 마이그레이션 작업의 대부분이 수동으로 진행 됩니다. 그러나이 단계에서는 이동 하기 전에 더 이상 필요 하지 않은 데이터 및 사이트를 정리할 수 있습니다. 다른 데이터를 저장소에 보관할 수 있습니다. 

SharePoint Server 2010 및 SharePoint Foundation 2010은 지원 종료로 인해 작동 하지 않습니다. 따라서 고객이 일부 데이터를 이동 하는 것을 잊은 경우에는 SharePoint가 여전히 실행 되 고 있는 기간을 사용할 수 있습니다.

Sharepoint Server 2013 또는 SharePoint Server 2016로 업그레이드 하 고 데이터를 SharePoint Online에 추가 하기로 결정 하는 경우 [Sharepoint 마이그레이션 API](https://support.office.com/article/Upload-on-premises-content-to-SharePoint-Online-using-PowerShell-cmdlets-555049c6-15ef-45a6-9a1f-a1ef673b867c?ui=en-US&amp;rs=en-US&amp;ad=US) 를 사용 하 여 비즈니스용 OneDrive로 정보를 마이그레이션할 수 있습니다.

|SharePoint Online 혜택|SharePoint Online 단점|
|---|---|
|Microsoft는 SPO 하드웨어 및 모든 하드웨어 관리를 제공 합니다.|사용 가능한 기능은 SharePoint Server 온-프레미스와 SPO에서 서로 다를 수 있습니다.|
|구독에 대 한 전역 관리자 이며 관리자를 SPO 사이트에 할당할 수 있습니다.|SharePoint Server 온-프레미스의 팜 관리자가 사용할 수 있는 일부 작업은 Microsoft 365의 SharePoint 관리자 역할에 존재 하지 않거나 필요 하지 않습니다. 그러나 SharePoint 관리, 사이트 모음 관리 및 사이트 소유권은 조직에 대해 로컬입니다.|
|Microsoft는 SharePoint Online이 실행 되는 SQL server를 포함 하 여 기본 하드웨어 및 소프트웨어에 대 한 패치, 수정 사항 및 업데이트를 적용 합니다.|서비스의 기본 파일 시스템에 대 한 액세스 권한이 없기 때문에 사용자 지정이 제한 됩니다.|
|Microsoft는 서비스 수준 [계약](https://go.microsoft.com/fwlink/?linkid=843153) 을 게시 하 고 신속 하 게 이동 하 여 서비스 수준 인시던트를 해결 합니다.|백업 및 복원 및 기타 복구 옵션은 SharePoint Online의 서비스에 의해 자동화 됩니다. 사용 하지 않는 경우 백업을 덮어씁니다.|
|보안 테스트 및 서버 성능 조정은 Microsoft의 서비스에서 지속적으로 수행 됩니다.|사용자 인터페이스 및 기타 SharePoint 기능의 변경 내용은 서비스에 의해 설치 되며 설정 또는 해제 해야 할 수 있습니다.|
|Microsoft 365는 다양 한 업계 표준을 [충족 합니다.](https://go.microsoft.com/fwlink/?linkid=843165)|마이그레이션에 대 한 [Fasttrack](https://go.microsoft.com/fwlink/?linkid=518597) 지원은 제한 됩니다.  <br/> 업그레이드의 대부분은 수동 또는 [SharePoint Online 및 OneDrive 마이그레이션 콘텐츠 로드맵](https://go.microsoft.com/fwlink/?linkid=843184)에 설명 된 SPO 마이그레이션 API를 통해 진행 됩니다.|
|Microsoft 지원 엔지니어 및 데이터 센터 직원은 구독에 대 한 무제한 관리자 액세스 권한이 없습니다.|최신 버전의 SharePoint를 지원 하도록 하드웨어 인프라를 업그레이드 해야 하거나 업그레이드에 보조 팜이 필요한 경우에는 추가 비용이 있을 수 있습니다.|
|솔루션 공급자는 데이터를 SharePoint Online으로 마이그레이션하는 일회성 작업에 도움이 될 수 있습니다.|일부 SharePoint Online 변경 내용은 사용자의 컨트롤 내에 포함 되지 않습니다. 마이그레이션 후 메뉴, 라이브러리 및 기타 기능의 디자인 차이점은 사용 편리성에 일시적으로 영향을 줄 수 있습니다.|
|온라인 제품은 서비스 간에 자동으로 업데이트 됩니다. 기능은 사용 중지 수 있지만 실제 지원 기간 말은 아닙니다.|기본 SQL server 뿐만 아니라 SharePoint Server 또는 SharePoint Foundation에 대 한 지원 주기가 종료 되었습니다.|

새 Microsoft 365 사이트를 만들고 필요에 따라 데이터를 수동으로 마이그레이션하려는 경우 [microsoft 365 옵션](https://www.microsoft.com/microsoft-365/)을 확인 합니다.

### <a name="upgrade-sharepoint-server-on-premises"></a>SharePoint Server 온-프레미스 업그레이드

SharePoint Server 2019에서 업그레이드는  *순차적* 으로 진행 되어야 합니다. SharePoint Server 2010에서 SharePoint Server 2016로 또는 SharePoint 2019로 직접 업그레이드할 수 있는 방법은 없습니다. Serial 업그레이드 경로:

- SharePoint Server 2010 \> Sharepoint server 2013 \> sharepoint server 2016

SharePoint 2010부터 SharePoint Server 2016까지 전체 경로를 따르도록 하기 위해 시간과 계획을 받습니다. 업그레이드에는 하드웨어 비용 (SQL server도 업그레이드 해야 함), 소프트웨어 및 관리가 포함 됩니다. 또한 사용자 지정 내용을 업그레이드 하거나 중단 해야 할 수도 있습니다. SharePoint Server 팜을 업그레이드 하기 전에 중요 한 사용자 지정 내용을 문서화 해야 합니다.

> [!NOTE]
> 지원 종료 SharePoint 2010 팜을 유지 관리 하 고, 새 하드웨어에 SharePoint Server 2016 팜을 설치한 다음, 별도의 팜을 함께 실행 하 고 콘텐츠를 수동으로 마이그레이션 (예: 콘텐츠 다운로드 및 다시 업로드) 할 수 있습니다. 그러나 2010에서 제공 하는 문서와 같이 수동 이동을 수행 하는 계정의 별칭을 사용 하 여 현재 마지막으로 수정한 계정으로 인해 이러한 수동 이동에 대 한 잠재적인 주의 사항이 있습니다. 사이트, 하위 사이트, 사용 권한 및 목록 구조를 다시 만드는 등의 작업을 수행 해야 합니다. 업그레이드 전에 환경을 정리 해야 합니다. 저장소로 이동할 수 있거나 더 이상 필요 하지 않은 데이터를 고려 합니다. 이렇게 하면 마이그레이션의 영향을 줄일 수 있습니다. 업그레이드를 수행 하기 전에 기존 팜이 제대로 작동 하 고 있어야 합니다.

*지원 및 지원 되지 않는 업그레이드 경로* 를 검토 해야 합니다.

- [SharePoint Server 2010](https://go.microsoft.com/fwlink/?linkid=843156)

- [SharePoint Server 2013](https://go.microsoft.com/fwlink/?linkid=843157)

*사용자 지정* 내용이 있는 경우 마이그레이션 경로의 각 단계를 계획 하는 것이 중요 합니다.

- [SharePoint Server 2010](https://go.microsoft.com/fwlink/?linkid=843160)

- [SharePoint Server 2013](https://go.microsoft.com/fwlink/?linkid=843162)

|온-프레미스 혜택|온-프레미스 단점|
|---|---|
|서버 하드웨어에서 SharePoint 팜의 모든 측면, 즉 SQL에 대 한 모든 권한을 가집니다.|모든 휴식 및 수정 사항은 회사의 책임입니다. 그러나 제품이 더 이상 지원 되지 않는 경우에는 Microsoft 지원 서비스에 문의 하는 것이 좋습니다.|
|하이브리드를 통해 온-프레미스 팜을 SharePoint Online 구독에 연결 하는 옵션을 사용 하는 SharePoint Server 온-프레미스의 전체 기능 집합입니다.|업그레이드, 패치, 보안 픽스, 하드웨어 업그레이드 및 모든 SharePoint Server 및 해당 SQL 팜의 유지 관리는 온-프레미스에서 관리 됩니다.|
|SharePoint Online 보다 더 강력한 사용자 지정 옵션에 대 한 모든 권한|[Microsoft 규정 준수 제품은](https://go.microsoft.com/fwlink/?linkid=843165) 온-프레미스에서 수동으로 구성 해야 합니다.|
|보안 테스트 및 서버 성능 조정은 사용자의 제어에 따라 온-프레미스에서 수행 됩니다.|Microsoft 365은 sharepoint Online에서 SharePoint Server 온-프레미스와 상호 작용 하지 않는 기능을 사용할 수 있도록 합니다.|
|솔루션 공급자는 다음 버전의 SharePoint Server (및 이후)로 데이터를 마이그레이션하는 데 도움이 될 수 있습니다.|Sharepoint Server 사이트에서는 SharePoint Online에 표시 되는 대로 [SSL/TLS](https://go.microsoft.com/fwlink/?linkid=843167) 인증서를 자동으로 사용 하지 않습니다.|
|SharePoint Server 온-프레미스의 명명 규칙 및 백업 및 복원 및 기타 복구 옵션에 대 한 모든 권한|SharePoint Server 온-프레미스는 제품 수명 주기에 중요 합니다.|

### <a name="upgrade-resources"></a>리소스 업그레이드

먼저 하드웨어 및 소프트웨어 요구 사항을 비교 합니다. 현재 환경이 기본 요구 사항을 충족 하지 않는 경우에는 팜 또는 SQL server의 하드웨어를 먼저 업그레이드 해야 할 수 있습니다. 

일부 사이트를 SharePoint Online의 "" * "하드웨어로 이동 하도록 결정할 수 있습니다. 평가를 마친 후에는 지원 되는 업그레이드 경로와 방법을 따릅니다.

- *다음에 대 한 하드웨어/소프트웨어 요구 사항:*

    [SharePoint Server 2010](https://go.microsoft.com/fwlink/?linkid=843204)  |  [SharePoint Server 2013](https://go.microsoft.com/fwlink/?linkid=843206)  |  [SharePoint Server 2016](https://go.microsoft.com/fwlink/?linkid=843207)

- *다음에 대 한 소프트웨어 경계 및 제한 사항:*

    [SharePoint Server 2010](https://go.microsoft.com/fwlink/?linkid=843247)  |  [SharePoint Server 2013](https://go.microsoft.com/fwlink/?linkid=843248)  |  [SharePoint Server 2016](https://go.microsoft.com/fwlink/?linkid=843249)

- *업그레이드 프로세스 개요:*

    [SharePoint Server 2010](https://go.microsoft.com/fwlink/?linkid=843251)  |  [SharePoint Server 2013](https://go.microsoft.com/fwlink/?linkid=843252)  |  [SharePoint Server 2016](https://go.microsoft.com/fwlink/?linkid=843359)

### <a name="create-a-hybrid-solution-with-sharepoint-online-and-sharepoint-server-on-premises"></a>SharePoint Online 및 SharePoint Server 온-프레미스를 사용 하 여 하이브리드 솔루션 만들기

하이브리드 설치는 일부 마이그레이션 요구에 대해 온-프레미스 및 온라인을 모두 제공 합니다. Sharepoint Server 2013, 2016 또는 2019 팜을 SharePoint Online에 연결 하 여 sharepoint 하이브리드를 만들 수 있습니다. [sharepoint 하이브리드 솔루션에 대해 알아봅니다](https://support.office.com/article/4c89a95a-a58c-4fc1-974a-389d4f195383.aspx).

하이브리드 SharePoint Server 팜이 마이그레이션 목표 인 경우 온라인으로 이동 하 고 온-프레미스에 유지 해야 하는 사이트 및 사용자를 파악 합니다. SharePoint Server 팜 콘텐츠를 회사에 대 한 높음, 중간 또는 낮은 영향으로 순위를 지정 하면 이러한 결정에 도움이 됩니다. SharePoint Online을 사용 하 여 로그인 및 SharePoint Server 검색 인덱스에 대해 사용자 계정만 공유 해야 할 수 있습니다. 그러나 사이트가 사용 되는 방식을 확인 해야이 요소가 명확 해질 수 있습니다. 나중에 회사에서 모든 콘텐츠를 SharePoint Online으로 마이그레이션하는 경우 나머지 모든 계정 및 데이터를 온라인으로 이동 하 고 온-프레미스 팜을 해제할 수 있습니다. SharePoint 팜의 관리/관리는 해당 시점부터 Microsoft 365 콘솔을 통해 수행 됩니다.

기존 유형의 하이브리드을 숙지 하 고 온-프레미스 SharePoint 팜 및 Microsoft 365 구독 간의 연결을 구성 하는 방법에 대해 잘 알고 있어야 합니다.

|옵션|설명|
|---|---|
|[Microsoft 준수 제품](https://go.microsoft.com/fwlink/?linkid=843165)|마이그레이션에 대 한 [Fasttrack](https://www.microsoft.com/fasttrack/microsoft-365) 지원은 제한 됩니다.<br/><br/> 업그레이드의 대부분은 수동 또는 [SharePoint Online 및 OneDrive 마이그레이션 콘텐츠 로드맵](https://go.microsoft.com/fwlink/?linkid=843184)에 설명 된 SPO 마이그레이션 API를 통해 진행 됩니다.|
|Microsoft 지원 엔지니어 및 데이터 센터 직원은 구독에 대 한 무제한 관리자 액세스 권한이 없습니다.|최신 버전의 SharePoint를 지원 하도록 하드웨어 인프라를 업그레이드 해야 하는 경우 또는 보조 팜이 필요한 경우에는 추가 비용이 생길 수 있습니다.|
|파트너는 데이터를 SharePoint Online으로 마이그레이션하는 일회성 작업을 지원할 수 있습니다.||
|온라인 제품은 서비스 간에 자동으로 업데이트 됩니다. 기능은 사용 중지 수 있지만 실제로 지원 되는 말은 아닙니다.||

새 Microsoft 365 사이트를 만들어 필요에 따라 수동으로 데이터를 마이그레이션하는 경우 [microsoft 365 옵션](https://www.microsoft.com/microsoft-365/)을 확인 합니다.

### <a name="upgrade-sharepoint-server-on-premises"></a>SharePoint Server 온-프레미스 업그레이드

SharePoint 업그레이드에서 버전을 건너뛰는 방법은 없습니다. 즉, 업그레이드가 순차적으로 진행 됨을 의미 합니다.

- Sharepoint 2007 \> sharepoint server 2010 sharepoint server \> 2013 \> sharepoint server 2016

SharePoint 2007에서 SharePoint Server 2016로 전체 경로를 사용 하려면 하드웨어 (SQL server도 업그레이드 해야 함), 소프트웨어 및 관리 비용을 고려 하 여 상당한 시간이 투자 되는 것을 의미 합니다. 기능의 중요도에 따라 사용자 지정 내용이 업그레이드 되거나 중단 되어야 합니다.

> [!NOTE]
> 수명 종료 SharePoint 2007 팜을 유지 관리 하 고, 새 하드웨어에 SharePoint Server 2016 팜을 설치한 다음, 별도의 팜을 함께 실행 하 고 콘텐츠를 수동으로 마이그레이션을 계획 하 고 실행 하 여 콘텐츠를 다운로드 하 고 다시 업로드 하는 것이 가능 합니다. 그러나 이러한 수동 이동에는 이전에 수정한 계정을 수동으로 이동 하는 계정의 별칭으로 교체 하는 등의 몇 가지 단점이 있습니다. 사이트, 하위 사이트, 사용 권한 및 목록 구조를 다시 만드는 등의 작업을 미리 수행 해야 합니다. 어떤 경우 든 저장소로 이동할 수 있는 데이터를 고려 하거나 더 이상 마이그레이션의 영향을 줄일 필요가 없습니다.

업그레이드 전에 환경을 정리 해야 합니다. 업그레이드 하기 전에 기존 팜이 제대로 작동 하 고 있어야 합니다.

*지원 및 지원 되지 않는 업그레이드 경로* 를 검토 해야 합니다.

- [SharePoint Server 2007](https://go.microsoft.com/fwlink/?linkid=843156)

- [SharePoint Server 2010](https://go.microsoft.com/fwlink/?linkid=843156)

- [SharePoint Server 2013](https://go.microsoft.com/fwlink/?linkid=843157)

*사용자 지정* 내용이 있는 경우 마이그레이션 경로의 각 단계에 대 한 업그레이드를 계획 하는 것이 중요 합니다.

- [SharePoint 2007](https://go.microsoft.com/fwlink/?linkid=843158)

- [SharePoint Server 2010](https://go.microsoft.com/fwlink/?linkid=843160)

- [SharePoint Server 2013](https://go.microsoft.com/fwlink/?linkid=843162)

|온-프레미스 pro|온-프레미스 con|
|---|---|
|서버 하드웨어에서 SharePoint 팜의 모든 측면에 대 한 모든 권한|모든 휴식 및 수정 사항은 회사의 책임입니다. 하지만 제품이 더 이상 지원 되지 않는 경우에도 유료 Microsoft 지원을 받을 수 있습니다.|
|하이브리드를 통해 온-프레미스 팜을 SharePoint Online 구독에 연결 하는 옵션을 사용 하는 SharePoint Server 온-프레미스의 전체 기능 집합입니다.|업그레이드, 패치, 보안 픽스 및 모든 SharePoint Server의 온-프레미스 유지 관리|
|보다 강력한 사용자 지정을 위한 모든 권한|[Microsoft 규정 준수 제품은](https://go.microsoft.com/fwlink/?linkid=843165) 온-프레미스에서 수동으로 구성 해야 합니다.|
|보안 테스트 및 서버 성능 조정은 사용자의 제어 아래에서 온-프레미스에 수행 됩니다.|Microsoft 365은 sharepoint Online에서 SharePoint Server 온-프레미스와 상호 작용 하지 않는 기능을 사용할 수 있도록 합니다.|
|파트너는 다음 버전의 SharePoint Server (및 이외)로 데이터를 마이그레이션하는 데 도움이 될 수 있습니다.|Sharepoint Server 사이트에서는 SharePoint Online에 표시 되는 대로 [SSL/TLS](https://go.microsoft.com/fwlink/?linkid=843167) 인증서를 자동으로 사용 하지 않습니다.|
|SharePoint Server 온-프레미스의 명명 규칙 및 백업 및 복원 및 기타 복구 옵션에 대 한 모든 권한|SharePoint Server 온-프레미스는 제품 수명 주기에 중요 합니다.|

### <a name="upgrade-resources"></a>리소스 업그레이드

먼저 하드웨어 및 소프트웨어 요구 사항을 충족 하는지 파악 한 다음 지원 되는 업그레이드 방법을 따릅니다.

- 다음 *에 대 한 하드웨어/소프트웨어 요구 사항*:

    [SharePoint Server 2010](https://go.microsoft.com/fwlink/?linkid=843204)  |  [SharePoint Server 2010](https://go.microsoft.com/fwlink/?linkid=843204)  |  [SharePoint Server 2013](https://go.microsoft.com/fwlink/?linkid=843206)  |  [SharePoint Server 2016](https://go.microsoft.com/fwlink/?linkid=843207)

- 다음 *에 대 한 소프트웨어 경계 및 제한* 사항:

    [SharePoint Server 2007](https://go.microsoft.com/fwlink/?linkid=843245)  |  [SharePoint Server 2010](https://go.microsoft.com/fwlink/?linkid=843247)  |  [SharePoint Server 2013](https://go.microsoft.com/fwlink/?linkid=843248)  |  [SharePoint Server 2016](https://go.microsoft.com/fwlink/?linkid=843249)

- *업그레이드 프로세스 개요*:

    [SharePoint Server 2007](https://go.microsoft.com/fwlink/?linkid=843250)  |  [SharePoint Server 2010](https://go.microsoft.com/fwlink/?linkid=843251)  |  [SharePoint Server 2013](https://go.microsoft.com/fwlink/?linkid=843252)  |  [SharePoint Server 2016](https://go.microsoft.com/fwlink/?linkid=843359)

### <a name="create-a-sharepoint-hybrid-solution-between-sharepoint-online-and-on-premises"></a>SharePoint Online과 온-프레미스 간에 SharePoint 하이브리드 솔루션 만들기

마이그레이션 요구 사항에 대 한 대답이 온-프레미스에서 제공 되는 컨트롤 사이의 위치에 있고 SharePoint Online에서 제공 하는 소유 지분 비용이 더 많은 경우 sharepoint Server 2013 또는 2016 팜을 하이브리드를 통해 SharePoint Online에 연결할 수 있습니다. [SharePoint 하이브리드 솔루션에 대 한 자세한 정보](https://support.office.com/article/4c89a95a-a58c-4fc1-974a-389d4f195383.aspx)

하이브리드 SharePoint Server 팜이 비즈니스에 이익이 되는 경우 기존 유형의 하이브리드을 숙지 하 고 온-프레미스 SharePoint 팜과 Microsoft 365 구독 간에 연결을 구성 하는 방법에 대해 알아봅니다.

[테스트 랩 가이드](m365-enterprise-test-lab-guides.md)를 사용 하 여 설정할 수 있는 Microsoft 365 개발/테스트 환경을 만들 수 있습니다. 평가판을 받거나 Microsoft 365 구독을 구매한 후에는 SharePoint Online에서 데이터를 마이그레이션할 수 있는 사이트 모음, 웹 및 문서 라이브러리를 만들 수 있습니다. 마이그레이션 API를 사용 하 여 수동으로 마이그레이션하거나, 하이브리드 마법사를 통해 내 사이트 콘텐츠를 비즈니스용 OneDrive로 마이그레이션할 수 있습니다.

> [!NOTE]
> 하이브리드 옵션을 사용 하려면 먼저 SharePoint Server 2010 팜을 온-프레미스에서 SharePoint Server 2013 또는 2016로 업그레이드 해야 합니다. Sharepoint Foundation 2010 및 SharePoint Foundation 2013은 SharePoint Online과의 하이브리드 연결을 지원 하지 않습니다.

## <a name="summary-of-options-for-office-2010-client-and-servers-and-windows-7"></a>Office 2010 클라이언트 및 서버 및 Windows 7의 옵션 요약

Office 2010 클라이언트 및 서버와 Windows 7에 대한 업그레이드, 마이그레이션 및 클라우드 옵션으로 이동에 대한 시각적 요약은 [지원 종료 포스터](../downloads/Office2010Windows7EndOfSupport.pdf)를 참조하세요.

[![Office 2010 클라이언트 및 서버 및 Windows 7 포스터에 대 한 지원 종료](../media/upgrade-from-office-2010-servers-and-products/office2010-windows7-end-of-support.png)](../downloads/Office2010Windows7EndOfSupport.pdf)

이 포스터에서는 Office 2010 클라이언트 및 서버 제품 및 Windows 7 지원 종료를 방지 하기 위해 수행할 수 있는 다양 한 경로를 설명 하며, Microsoft 365 Enterprise의 기본 설정 경로 및 옵션을 지원 합니다.

또한이 포스터를 [다운로드](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/Office2010Windows7EndOfSupport.pdf) 하 여 letter, legal 또는 tabloid (11 x 17) 형식으로 인쇄할 수 있습니다.

## <a name="related-articles"></a>관련 문서

[Office 2007 또는 2010 서버 및 클라이언트에서 업그레이드 하는 데 도움이 되는 리소스](upgrade-from-office-2010-servers-and-products.md)

[Overview of the upgrade process from SharePoint 2010 to SharePoint 2013](https://technet.microsoft.com/library/mt493301%28v=office.16%29.aspx)

[SharePoint 2010에서 SharePoint 2013으로의 업그레이드 모범 사례](https://technet.microsoft.com/library/mt493305%28v=office.16%29.aspx)

[SharePoint 2013에서 데이터베이스 업그레이드 문제 해결](https://go.microsoft.com/fwlink/?linkid=843195)

[업그레이드에 도움이 되는 Microsoft 솔루션 공급자 검색](https://go.microsoft.com/fwlink/?linkid=841249)

[SharePoint Server 2013에 대해 업데이트된 제품 서비스 정책](https://technet.microsoft.com/library/mt493253%28v=office.16%29.aspx)

[SharePoint Server 2016에 대해 업데이트된 제품 서비스 정책](https://technet.microsoft.com/library/mt782882%28v=office.16%29.aspx)

---
title: 중요 eDiscovery 사례에서 eDiscovery 보류 만들기
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
description: 핵심 eDiscovery 사례와 연결 된 보류를 만들어 조사와 관련이 있을 수 있는 콘텐츠를 보존할 수 있습니다.
ms.openlocfilehash: d2c9c02f7530c58975ddf99289a3a0872788146a
ms.sourcegitcommit: d7975c391e03eeb96e29c1d02e77d2a1433ea67c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/05/2020
ms.locfileid: "48920332"
---
# <a name="create-an-ediscovery-hold"></a>eDiscovery 보존 만들기

핵심 eDiscovery 사례를 사용 하 여 사례와 관련이 있을 수 있는 콘텐츠를 보존 하는 보류를 만들 수 있습니다. 서비스 케이스에서 조사 중인 사용자의 Exchange 사서함과 비즈니스용 OneDrive 계정을 배치할 수 있습니다. Microsoft 팀, Office 365 그룹 및 Yammer 그룹과 연결 된 사서함 및 사이트에 보류를 적용할 수도 있습니다. 콘텐츠 위치를 보존 상태로 설정 하는 경우 콘텐츠 위치에서 보류를 제거 하거나 보류를 삭제할 때까지 콘텐츠가 보존 됩니다.

EDiscovery 보류를 만든 후에는 보류를 적용 하는 데 최대 24 시간이 걸릴 수 있습니다. 

보류를 만들 때 지정한 콘텐츠 위치에 보존 되는 콘텐츠의 범위를 지정 하려면 다음 옵션을 사용할 수 있습니다.
  
- 지정 된 위치에 있는 모든 콘텐츠가 보존 되는 무한 보류를 만듭니다. 또는 검색 쿼리와 일치 하는 지정 된 위치에 있는 콘텐츠만 보존 되도록 쿼리 기반 보류를 만들 수 있습니다.

- 해당 날짜 범위 내에서 전송, 수신 또는 만든 콘텐츠만 보존 하는 날짜 범위를 지정할 수 있습니다. 또는 보낸 날짜, 수신 또는 만든 시기에 관계 없이 지정 된 위치에 있는 모든 콘텐츠를 보유할 수 있습니다.
  
## <a name="how-to-create-an-ediscovery-hold"></a>EDiscovery 보존을 만드는 방법

코어 eDiscovery 사례와 연결 된 eDiscovery 보존을 만들려면:
  
1. 적절 한 [https://compliance.microsoft.com](https://compliance.microsoft.com) eDiscovery 권한이 할당 된 사용자 계정에 대 한 자격 증명을 사용 하 여으로 이동 하 여 로그인 합니다.

2. Microsoft 365 준수 센터의 왼쪽 탐색 창에서 **모두 표시** 를 클릭 한 다음 **eDiscovery > 코어** 를 클릭 합니다.

3. **핵심 eDiscovery** 페이지에서 보류를 만들 사례를 선택 하 고 **열기 사례** 를 클릭 합니다.

4. 사례에 대 한 **홈** 페이지에서 **보류** 탭을 클릭 합니다.
  
5. **보류** 페이지에서 **만들기** 를 클릭 합니다.

6. **보류 이름** 지정 마법사 페이지에서 이름을 입력 하 고 선택적으로 설명을 추가한 후 **다음** 을 클릭 합니다. 보류 이름은 조직에서 고유해야 합니다.

7. **콘텐츠 위치** 페이지에서 보류 하도록 설정할 콘텐츠 위치를 선택 합니다. 사서함, 사이트 및 공용 폴더를 보류에 배치할 수 있습니다.

    ![보류 시킬 콘텐츠 위치 선택](../media/a59e4265-9151-4dbf-913f-6a4ab8db06b4.png)
  
   1. **사서함 위치** - **사용자, 그룹 또는 팀 선택을** 클릭 한 다음 **사용자, 그룹 또는 팀 선택** 을 클릭 하 여 보류할 사서함을 지정 합니다. 검색 상자를 사용 하 여 사용자 사서함과 메일 그룹 (그룹 구성원의 사서함을 보류)을 보류 상태로 설정 합니다. 또한 Microsoft Team, Office 365 그룹 또는 Yammer 그룹에 대 한 연결 된 사서함을 보류할 수 있습니다. 사용자, 그룹, 팀 확인란을 선택 하 고 **선택을** 클릭 한 후 **완료** 를 클릭 합니다.

   1. **사이트 위치** - **사이트 선택을** 클릭 한 다음 **사이트 선택을** 클릭 하 여 SharePoint 및 OneDrive 계정을 보류 하도록 지정 합니다. 보류 하도록 설정할 각 사이트의 URL을 입력 합니다. Microsoft Team, Office 365 그룹 또는 Yammer 그룹에 대 한 SharePoint 사이트의 URL을 추가할 수도 있습니다. **선택을** 클릭 하 고 **완료** 를 클릭 합니다.
  
   1. **Exchange 공용 폴더** ![ ](../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png) Exchange Online 조직의 모든 공용 폴더를 보류 상태로 설정 하려면 toggle switch toggle Control을 **all** 위치로 이동 합니다. 특정 공용 폴더를 선택 하 여 보류 상태로 설정할 수는 없습니다. 공용 폴더를 보존 하지 않으려면 toggle 스위치를 **"없음"** 으로 설정 된 상태로 둡니다.

   > [!NOTE]
   > 하나 이상의 콘텐츠 위치를 보류에 추가 해야 합니다. 그렇지 않으면 eDiscovery 보류 정적 할당은 보류 중인 항목이 없음을 나타냅니다.

8. 보류에 콘텐츠 위치를 모두 추가한 후에 **다음** 을 클릭 합니다.

9. 조건을 사용 하 여 쿼리 기반 보존을 만들려면 다음을 완료 합니다. 그렇지 않고 지정 된 콘텐츠 위치의 모든 콘텐츠를 유지 하려면 **다음** 을 클릭 합니다.

    ![조건을 사용 하 여 쿼리 기반 보류 만들기](../media/d587b58e-d05c-4ac0-b0fe-09019e4f1063.png)
  
    1. **키워드** 아래의 상자에 검색 조건을 충족 하는 콘텐츠만 보존 되도록 검색 쿼리를 입력 합니다. 키워드, 전자 메일 메시지 속성 또는 문서 속성 (예: 파일 이름)을 지정할 수 있습니다. **AND** , **OR** , **NOT** 등의 부울 연산자를 사용 하 여 보다 복잡 한 쿼리를 사용할 수도 있습니다.

    1. **조건 추가** 를 클릭 하 여 보류에 대 한 검색 쿼리 범위를 좁히는 조건을 하나 이상 추가 합니다. 각 조건은 보류를 만들 때 만들어지고 실행 되는 KQL 검색 쿼리에 절을 추가 합니다. 예를 들어 날짜 범위를 지정 하 여 원거리 시간 내에 만들어진 전자 메일 또는 사이트 문서를 보류할 수 있습니다. 조건은 **AND** 연산자에 의해 **키워드** 상자에 지정 된 키워드 쿼리에 논리적으로 연결 됩니다. 즉, 항목은 유지 될 키워드 쿼리와 조건을 모두 충족 해야 합니다.

    검색 쿼리를 만들고 조건을 사용 하는 방법에 대 한 자세한 내용은 [키워드 쿼리 및 검색 조건을](keyword-queries-and-search-conditions.md)참조 하십시오.

10. 쿼리 기반 보존을 구성한 후 **다음** 을 클릭 합니다.

11. 설정을 검토 하 고 필요한 경우 편집 한 후 **이 보류 만들기** 를 클릭 합니다.

## <a name="query-based-holds-placed-on-site-documents"></a>쿼리 기반 보류를 사이트 문서에 저장

SharePoint 사이트에 있는 문서에 대해 쿼리 기반 eDiscovery 보류를 수행할 때는 다음 사항을 염두에 두어야 합니다.

- 쿼리 기반 보존은 삭제 후 잠시 동안 사이트의 모든 문서를 보존 합니다. 즉, 문서가 삭제 되 면 해당 문서는 쿼리 기반 보존의 기준과 일치 하지 않는 경우에도 보존 보류 라이브러리로 이동 됩니다. 그러나 쿼리 기반 유지와 일치 하지 않는 삭제 된 문서는 보존 보류 라이브러리를 처리 하는 타이머 작업에 의해 제거 됩니다. 타이머 작업은 주기적으로 실행 되며 보존 보류 라이브러리의 모든 문서를 쿼리 기반 eDiscovery 보류 (및 다른 유형의 보류 및 보존 정책)로 비교 합니다. 타이머 작업은 쿼리 기반 유지와 일치 하지 않는 문서를 삭제 하 고 그에 해당 하는 문서를 보존 합니다.

- 쿼리 기반 보존은 특정 폴더 또는 사이트에서 문서를 보존 하거나 다른 위치 기반 보존 조건을 사용 하는 것과 같은 대상 유지를 수행 하는 데 사용해 서는 안 됩니다. 이렇게 하면 의도 하지 않은 결과가 발생할 수 있습니다. 키워드, 날짜 범위 또는 기타 문서 속성과 같은 위치에 기반 하지 않는 저장 기준을 사용 하 여 사이트 문서를 보존 하는 것이 좋습니다.

## <a name="ediscovery-hold-statistics"></a>eDiscovery 보존 통계

EDiscovery 보류를 만든 후에는 선택한 보류에 대 한 플라이 아웃 페이지에 새로 보존에 대 한 정보가 표시 됩니다. 이 정보에는 보류 중인 사서함 및 사이트의 수와 보류 중인 항목의 총 수와 크기, 보류 통계가 계산 된 마지막 시간 등이 포함 됩니다. 이러한 보존 통계는 사례와 관련 된 콘텐츠를 보존할 것인지 식별 하는 데 도움이 됩니다.
  
![보류 통계](../media/575cfe0a-9210-4ae4-8df8-65665d66712e.png)
  
EDiscovery 보존 통계에 대해 다음 사항을 염두에 두어야 합니다.
  
- 보류 중인 총 항목 수는 보류 된 모든 콘텐츠 원본의 항목 수를 나타냅니다. 쿼리 기반 보존을 만든 경우이 통계는 쿼리와 일치 하는 항목의 수를 나타냅니다.

- 보류 중인 항목 수에는 콘텐츠 위치에 있는 인덱싱되지 않은 항목도 포함 됩니다. 쿼리 기반 보존을 만드는 경우에는 콘텐츠 위치에 있는 모든 인덱싱되지 않은 항목이 보존 됩니다. 여기에는 날짜 범위 조건 외부에 있을 수 있는 쿼리 기반 보류 및 인덱싱되지 않은 항목의 검색 조건과 일치 하지 않는 인덱싱되지 않은 항목이 포함 됩니다. 검색 쿼리와 일치 하지 않거나 날짜 범위에 의해 제외 된 인덱싱되지 않은 항목이 검색 결과에 포함 되지 않는 경우에는이 작업이 실행 되는 것과는 다릅니다. 인덱싱되지 않은 항목에 대 한 자세한 내용은 [부분적으로 인덱싱된 항목](partially-indexed-items-in-content-search.md)을 참조 하십시오.

- **통계 업데이트** 를 클릭 하 여 보류 중인 항목 수를 계산 하는 검색 예측을 다시 실행 하 여 최신 보존 통계를 가져올 수 있습니다.

- 사서함 이나 사이트가 보류 중인 사용자가 SharePoint 및 OneDrive에서 새 전자 메일 메시지를 보내거나 받고 새 문서를 만들기 때문에 보류 중인 항목 수는 시간이 지남에 따라 증가 합니다.

- Exchange 사서함, SharePoint 사이트 또는 OneDrive 계정을 다중 지리적 환경에서 다른 지역으로 이동 하는 경우 해당 사이트에 대 한 통계가 보존 통계에 포함 되지 않습니다. 하지만 해당 위치의 콘텐츠는 계속 유지 됩니다. 또한 사서함 이나 사이트가 다른 지역으로 이동 되 면 보류에 표시 되는 SMTP 주소 또는 URL이 자동으로 업데이트 되지 않습니다. 콘텐츠 위치가 보존 통계에 다시 포함 되도록 보류를 편집 하 고 URL 또는 SMTP 주소를 업데이트 해야 합니다.

## <a name="search-locations-on-ediscovery-hold"></a>EDiscovery 보류의 검색 위치

핵심 eDiscovery 사례에서 [콘텐츠를 검색할](search-for-content-in-core-ediscovery.md) 때 사례와 연결 된 보류에 적용 된 콘텐츠 위치만 검색 하도록 검색을 빠르게 구성할 수 있습니다.

![위치, 보류 중인 위치](../media/d56398aa-0b20-4500-8e26-494eab92a99f.png)

보류 중인 **위치** 옵션을 선택 하 여 유지 된 모든 콘텐츠 위치를 검색 합니다. 사례에 eDiscovery 보류를 여러 개 포함 하는 경우이 옵션을 선택 하면 모든 보류의 콘텐츠 위치가 검색 됩니다. 또한 콘텐츠 위치가 쿼리 기반 유지로 설정 된 경우에는 검색을 실행할 때 보류 쿼리와 일치 하는 항목만 검색 됩니다. 즉, 보류 기준과 검색 조건과 일치 하는 콘텐츠만 검색 결과와 함께 반환 됩니다. 예를 들어 특정 날짜 이전에 보내거나 만든 항목을 유지 하는 사용자가 쿼리 기반 케이스 보류에 저장 된 경우 해당 항목만 검색 됩니다. 이 작업은 사례 보류 쿼리와 검색 쿼리를 **and** 연산자로 연결 하 여 수행 됩니다.

EDiscovery 보류에서 위치를 검색할 때 주의 해야 할 몇 가지 사항은 다음과 같습니다.

- 콘텐츠 위치가 같은 경우에 여러 보류의 일부인 경우에는 보류 쿼리가 모든 사례 콘텐츠 옵션을 사용 하 여 해당 콘텐츠 위치를 검색할 때 **OR** 연산자로 결합 됩니다. 마찬가지로 콘텐츠 위치가 서로 다른 두 보류의 일부인 반면, 하나는 쿼리를 기반으로 하며 나머지는 무기한 유지 되는 경우 (모든 콘텐츠를 보류 하는 경우)에는 무제한 유지로 인해 모든 콘텐츠가 검색 됩니다.

- 검색에서 보류 중인 위치를 검색 하도록 구성한 후 위치를 추가 또는 제거 하거나 보류 쿼리를 변경 하 여 eDiscovery 보류를 변경 하면 검색 구성이 해당 변경 내용으로 업데이트 됩니다. 그러나 검색 결과를 업데이트 하려면 보류가 변경 된 후에 검색을 다시 실행 해야 합니다.

- EDiscovery 사례의 단일 위치에 eDiscovery를 여러 개 저장 한 경우 보류 중인 위치를 검색 하도록 선택 하면 해당 검색 쿼리에 대 한 최대 키워드 수가 500이 됩니다. 이는 검색에서 **OR** 연산자를 사용 하 여 쿼리 기반 보류를 모두 결합 하기 때문입니다. 결합 된 보류 쿼리와 검색 쿼리에 500 개 보다 많은 키워드가 있으면 쿼리 기반 사례와 일치 하는 콘텐츠 뿐 아니라 사서함의 모든 콘텐츠가 검색 됩니다.

- EDiscovery 보류가 켜 **지거나 설정 된** 경우에도 보류 중인 위치를 계속 검색할 수 있습니다.

## <a name="preserve-content-in-microsoft-teams"></a>Microsoft 팀의 콘텐츠 보존

Microsoft 팀 채널의 일부인 대화는 Microsoft 팀과 연결 된 사서함에 저장 됩니다. 마찬가지로 팀 구성원이 채널에서 공유하는 파일은 팀의 SharePoint 사이트에 저장됩니다. 따라서 팀 사서함 및 SharePoint 사이트를 eDiscovery 보류에 배치 하 여 대화 및 파일을 채널에 보존 해야 합니다.

또는 팀의 채팅 목록에 속하는 대화 ( *1:1 채팅* 또는 *1: N 그룹 채팅* 이라고 함)는 채팅에 참가 하는 사용자의 사서함에 저장 됩니다. 그리고 채팅 대화에서 사용자가 공유 하는 파일은 해당 파일을 공유 하는 사용자의 OneDrive 계정에 저장 됩니다. 따라서 채팅 목록에 대화와 파일을 보존 하기 위해 개별 사용자 사서함과 OneDrive 계정을 eDiscovery 보류에 추가 해야 합니다. 팀 사서함과 사이트를 보류 하는 것 외에도 Microsoft 팀 구성원의 사서함을 유지 하는 것이 좋습니다.

2020 년 2 월 부터는 개인 채널의 콘텐츠를 보존 하는 기능이 설정 되었습니다. 개인 채널 채팅은 채팅 참가자의 사서함에 저장 되므로 사용자 사서함을 eDiscovery 보류에 두면 개인 채널 채팅이 보존 됩니다. 또한 사용자 사서함이 2 월 2020 이전에 eDiscovery 보존 상태로 설정 된 경우에는 해당 사서함에 저장 된 개인 채널 메시지에 보류가 자동으로 적용 됩니다. 개인 채널에서 공유 되는 파일 보존도 지원 됩니다.

팀 콘텐츠를 보존 하는 방법에 대 한 자세한 내용은 [법적 보유에 Microsoft 팀 사용자 또는 팀](https://docs.microsoft.com/MicrosoftTeams/legal-hold)소개를 참조 하세요.
    
> [!IMPORTANT]
> 클라우드 기반 조직에서 팀의 채팅 목록에 속하는 대화에 참가 하는 사용자에 게는 사서함을 eDiscovery 보류에 넣을 때 채팅 대화를 유지 하기 위해 Exchange Online 사서함이 있어야 합니다. 채팅 목록의 일부인 대화는 채팅 참가자의 클라우드 기반 사서함에 저장 되기 때문입니다. 채팅 참가자에 게 Exchange Online 사서함이 없으면 해당 채팅 대화를 보존할 수 없습니다. 예를 들어 Exchange 하이브리드 배포에서 온-프레미스 사서함이 있는 사용자는 팀의 채팅 목록에 속하는 대화에 참가할 수 있습니다. 그러나이 경우 이러한 사용자는 보류할 수 있는 클라우드 기반 사서함이 없기 때문에 이러한 대화의 콘텐츠를 보존할 수 없습니다.
  
모든 팀 또는 팀 채널에는 메모 작성 및 공동 작업을 위한 Wiki도 포함 되어 있습니다. Wiki 콘텐츠는 자동으로 .mht 형식의 파일에 저장됩니다. 이 파일은 팀의 SharePoint 사이트에 있는 Teams Wiki Data 문서 라이브러리에 저장됩니다. 팀의 SharePoint 사이트를 eDiscovery 보류에 추가 하 여 wiki 콘텐츠를 보존할 수 있습니다.

> [!NOTE]
> 팀 또는 팀 채널에 대 한 Wiki 콘텐츠를 보존 하는 기능 (팀의 SharePoint 사이트를 보류할 때)은 2017 년 6 월 22 일에 릴리스 되었습니다. 팀 사이트를 보류 중인 경우에는 해당 날짜에 대해 Wiki 콘텐츠가 유지 됩니다. 그러나 팀 사이트가 유지 되 고 Wiki 콘텐츠가 6 월 22 2017 일 이전에 삭제 된 경우에는 Wiki 콘텐츠가 보존 되지 않습니다.

### <a name="office-365-groups"></a>Office 365 그룹

팀은 Office 365 그룹을 기반으로 작성 됩니다. 따라서 Office 365 그룹을 eDiscovery 보존에 배치 하는 것은 팀 콘텐츠를 보류 하는 것과 비슷합니다.

EDiscovery 보존에 팀 및 Office 365 그룹을 둘 다 배치할 때는 다음 사항을 염두에 두어야 합니다.

- 앞에서 설명한 것 처럼 팀 및 Office 365 그룹에 있는 콘텐츠를 보류 상태로 설정 하려면 그룹 또는 팀과 연결 된 사서함 및 SharePoint 사이트를 지정 해야 합니다.

- [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell) 에서 **remove-unifiedgroup** cmdlet을 실행 하 여 팀 및 Office 365 그룹의 속성을 볼 수 있습니다. 이 방법을 사용 하면 팀 또는 Office 365 그룹과 연결 된 사이트의 URL을 가져올 수 있습니다. 예를 들어 다음 명령을 실행하면 Senior Leadership Team이라는 Office 365 그룹의 선택된 속성이 표시됩니다.

    ```text
    Get-UnifiedGroup "Senior Leadership Team" | FL DisplayName,Alias,PrimarySmtpAddress,SharePointSiteUrl

    DisplayName            : Senior Leadership Team
    Alias                  : seniorleadershipteam
    PrimarySmtpAddress     : seniorleadershipteam@contoso.onmicrosoft.com
    SharePointSiteUrl      : https://contoso.sharepoint.com/sites/seniorleadershipteam
    ```

    > [!NOTE]
    > **Get-UnifiedGroup** cmdlet를 실행하려면 Exchange Online에서 보기 전용 받는 사람 역할을 할당받았거나 보기 전용 받는 사람 역할이 할당된 역할 그룹의 구성원이어야 합니다. 
  
- 사용자의 사서함을 검색할 때 사용자가 구성원으로 속해 있는 팀 또는 Office 365 그룹은 검색 되지 않습니다. 마찬가지로, 팀 또는 Office 365 그룹을 eDiscovery 보류에 배치 하면 그룹 사서함과 그룹 사이트만 보존 됩니다. 그룹 구성원의 사서함 및 비즈니스용 OneDrive 사이트는 eDiscovery 보류에 명시적으로 추가 하지 않으면 보류 되지 않습니다. 따라서 법적 이유로 팀 또는 Office 365 그룹을 보류 상태로 설정 해야 하는 경우에는 팀 또는 그룹 구성원의 사서함과 OneDrive 계정을 동일한 보류에 추가 하는 것이 좋습니다.

- 팀 또는 Office 365 그룹의 구성원 목록을 가져오려면 Microsoft 365 관리 센터의 **그룹** 페이지에서 해당 속성을 볼 수 있습니다. 또는 Exchange Online PowerShell에서 다음 명령을 실행할 수 있습니다.

    ```powershell
    Get-UnifiedGroupLinks <group or team name> -LinkType Members | FL DisplayName,PrimarySmtpAddress
    ```

    > [!NOTE]
    > **Get-UnifiedGroupLinks** cmdlet를 실행하려면 Exchange Online에서 보기 전용 받는 사람 역할을 할당받았거나 보기 전용 받는 사람 역할이 할당된 역할 그룹의 구성원이어야 합니다.

## <a name="onedrive-accounts"></a>OneDrive 계정

EDiscovery 사례와 연결 된 보류 또는 검색에 추가할 수 있도록 조직의 비즈니스용 OneDrive 사이트에 대 한 Url 목록을 수집 하려면 [조직의 모든 OneDrive 위치 목록 만들기](https://docs.microsoft.com/onedrive/list-onedrive-urls)를 참조 하십시오. 이 문서의 스크립트는 조직의 모든 OneDrive 사이트 목록을 포함 하는 텍스트 파일을 만듭니다. 이 스크립트를 실행하려면 SharePoint Online 관리 셸을 설치하고 사용해야 합니다. 조직의 MySite 도메인에 대한 URL을 검색하려는 각 OneDrive 사이트 앞에 붙입니다. 이것은 모든 OneDrive 도메인을 포함하는 도메인입니다(예: `https://contoso-my.sharepoint.com`). 사용자의 OneDrive 사이트에 대한 URL의 예는 다음과 같습니다.  `https://contoso-my.sharepoint.com/personal/sarad_contoso_onmicrosoft.com`.

> [!IMPORTANT]
> 사용자의 OneDrive 계정에 대 한 URL에는 UPN (사용자 계정 이름)이 포함 됩니다 (예: `https://alpinehouse-my.sharepoint.com/personal/sarad_alpinehouse_onmicrosoft_com` ). 드물지만 사용자의 UPN이 변경 되는 경우에는 해당 OneDrive URL도 새 UPN을 통합 하도록 변경 됩니다. 사용자의 OneDrive 계정이 eDiscovery 보류의 일부인 경우 이전 및 해당 UPN이 변경 되 면 보류를 업데이트 해야 하며 보류를 업데이트 하 고 사용자의 새 OneDrive URL을 추가 하 고 이전 항목을 제거해 야 합니다. 자세한 내용은 [UPN 변경 내용이 OneDrive URL에 미치는 영향](https://docs.microsoft.com/onedrive/upn-changes)을 참조하세요.

## <a name="removing-content-locations-from-an-ediscovery-hold"></a>EDiscovery 보류에서 콘텐츠 위치 제거

사서함, SharePoint 사이트 또는 OneDrive 계정이 eDiscovery 보류에서 제거 된 후 *지연 보류가* 적용 됩니다. 즉, 콘텐츠 위치에서 데이터가 영구적으로 삭제 (제거) 되는 것을 방지 하기 위해 보류의 실제 제거가 30 일 동안 지연 됩니다. 이를 통해 관리자는 eDiscovery 보류가 제거 된 후에 제거 될 콘텐츠를 검색 하거나 복구할 수 있습니다. 사서함 및 사이트에 대 한 지연 대기 작동 방식에 대 한 자세한 정보는 서로 다릅니다.

- **사서함:** 다음 번에 관리 되는 폴더 도우미가 사서함을 처리 하 고 eDiscovery 보류가 제거 되었음을 감지할 때 대기 시간이 사서함에 저장 됩니다. 특히 관리 되는 폴더 도우미가 다음 사서함 속성 중 하나를 **True** 로 설정 하면 사서함에 지연 보류가 적용 됩니다.

   - **DelayHoldApplied:** 이 속성은 사용자의 사서함에 저장 된 전자 메일 관련 콘텐츠 (Outlook 및 웹에서 Outlook을 사용 하는 사용자가 생성)에 적용 됩니다.

   - **DelayReleaseHoldApplied:** 이 속성은 사용자의 사서함에 저장 되어 있는 Microsoft 팀, Microsoft Forms 및 Microsoft Yammer와 같은 Outlook 이외의 앱에 의해 생성 된 클라우드 기반 콘텐츠에 적용 됩니다. Microsoft 앱에서 생성 되는 클라우드 데이터는 일반적으로 사용자 사서함의 숨겨진 폴더에 저장 됩니다.

   이전 속성을 True로 설정 하는 경우 사서함에 지연 보류가 **적용** 되 면 사서함이 소송 보존 상태에 있는 것 처럼 보류 시간에 무제한 유지 되는 것으로 간주 됩니다. 30 일 후에 지연 보류가 만료 되 고 Microsoft 365에서 자동으로 지연 보존 (DelayHoldApplied 또는 DelayReleaseHoldApplied 속성을 **False** 로 설정)을 제거 하 여 보류가 제거 되도록 시도 합니다. 이러한 속성 중 하나를 **False** 로 설정 하면 다음에 관리 되는 폴더 도우미가 사서함을 처리할 때 제거 하도록 표시 된 해당 항목을 제거 합니다.

   자세한 내용은 [지연되는 사서함 관리](identify-a-hold-on-an-exchange-online-mailbox.md#managing-mailboxes-on-delay-hold)를 참조하세요.

- **SharePoint 및 OneDrive 사이트:** 사이트가 eDiscovery 보류에서 제거 된 후 30 일 지연 보존 기간 중에 보존 되는 모든 SharePoint 또는 OneDrive 콘텐츠는 삭제 되지 않습니다. 이는 사이트를 보존 정책에서 해제할 때 발생 하는 결과와 비슷합니다. 또한 30 일 지연 보존 기간 동안에는 보존 보류 라이브러리에서이 콘텐츠를 수동으로 삭제할 수 없습니다. 

   자세한 내용은 [보존 정책 릴리스](retention.md#releasing-a-policy-for-retention)를 참조 하세요.

서비스 케이스가 닫힐 때 보류가 해제 되었기 때문에 핵심 eDiscovery 사례를 닫을 때 보류 중인 콘텐츠 위치에도 지연 보류가 적용 됩니다. 사례를 닫는 방법에 대 한 자세한 내용은 [닫기, 다시 열기 및 삭제 a Core eDiscovery 사례](close-reopen-delete-core-ediscovery-cases.md)를 참조 하세요.

## <a name="ediscovery-hold-limits"></a>eDiscovery 보존 제한

다음 표에는 eDiscovery 사례 및 사례 보존에 대 한 한계가 나와 있습니다.

  | 제한 설명 | Limit |
  |:-----|:-----|
  |조직의 최대 사례 수  <br/> |제한 없음  <br/> |
  |조직에 대 한 eDiscovery 보류의 최대 수  <br/> |10,000  <br/> |
  |단일 eDiscovery 보류의 최대 사서함 수  <br/> |1,000  <br/> |
  |단일 eDiscovery 보류의 최대 SharePoint 및 비즈니스용 OneDrive 사이트 수  <br/> |100  <br/> |
  |EDiscovery 홈 페이지에 표시 되는 최대 사례 수 및 사례 내의 보류, 검색 및 내보내기 탭에 표시 되는 최대 항목 수입니다. <sup>1</sup> |1,000|
  |||

   > [!NOTE]
   > <sup>1</sup> 1000 개 보다 많은 사례, 보류 중, 검색 또는 내보내기의 목록을 보려면 해당 Office 365 Security & 준수 PowerShell cmdlet을 사용할 수 있습니다.
   >
   > - [Remove-compliancecase](https://docs.microsoft.com/powershell/module/exchange/get-compliancecase)
   > - [New-caseholdpolicy](https://docs.microsoft.com/powershell/module/exchange/get-caseholdpolicy)
   > - [Get-ComplianceSearch](https://docs.microsoft.com/powershell/module/exchange/get-compliancesearch)
   > - [New-compliancesearchaction](https://docs.microsoft.com/powershell/module/exchange/get-compliancesearchaction)

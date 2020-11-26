---
title: 콘텐츠의 처리
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: 처리 검토를 사용하든 콘텐츠가 구성한 설정에 따라 자동으로 삭제되는지, 콘텐츠의 처리를 모니터링하고 관리합니다.
ms.openlocfilehash: 9900bbc58818a98ad41f4f796184ccf21041bbfe
ms.sourcegitcommit: a9486f9dc51f0908393000ec3c211e3430c26abd
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/25/2020
ms.locfileid: "49409215"
---
# <a name="disposition-of-content"></a>콘텐츠의 처리

>*[보안 및 규정 준수를 위한 Microsoft 365 라이선싱 지침](https://aka.ms/ComplianceSD).*

Microsoft 365 준수 센터의 **레코드 관리** 에서 **처리** 탭을 사용하여 처리 검토를 관리하고 보존 기간이 끝날 때 자동으로 삭제된 [레코드](records-management.md#records)를 봅니다. 

## <a name="prerequisites-for-viewing-content-dispositions"></a>콘텐츠 처리를 보기 위한 필수 구성 요소

처리 검토를 관리하고 레코드가 삭제되었는지 확인하려면 충분한 권한이 필요하고 감사를 사용하도록 설정해야 합니다.

### <a name="permissions-for-disposition"></a>처리 권한

Microsoft 365 준수 센터의 **처리** 탭에 액세스하려면 사용자에게 **처리 관리** 관리자 역할이 있어야 합니다. 이 역할은 기본 관리자 역할 그룹, **준수 관리자** 및 **준수 데이터 관리자** 에 포함되어 있습니다.

사용자에게 이 필수 처리 관리 역할을 부여하려면 이러한 기본 역할 그룹 중 하나에 추가하거나 혹은 사용자 지정 역할 그룹을 만들고(예: 명명된 "처리 검토자") 이 그룹에 처리 관리 역할을 부여합니다.  

> [!NOTE]
> 전역 관리자 조차도 **처리 관리** 역할이 부여되어야 합니다. 

또한 처리 프로세스 중에 항목의 내용을 보려면 **콘텐츠 탐색기 콘텐츠 뷰어** 와 **콘텐츠 탐색기 목록 뷰어** 의 두 역할 그룹에 사용자를 추가합니다. 사용자가 이 역할 그룹의 사용 권한이 없는 경우, 처리 검토 완료를 위해 처리 검토 작업을 여전히 선택할 수 있지만, 준수 센터에서 항목의 내용을 보지 않고 이를 수행해야 합니다.

지침은 [사용자에게 Office 365 보안 및 준수 센터의 액세스 권한 부여하기](../security/office-365-security/grant-access-to-the-security-and-compliance-center.md)를 참조하세요.

### <a name="enable-auditing"></a>감사 사용

첫 처리 작업 최소 하루 이전에 감사를 사용하도록 설정합니다. 자세한 내용은 [Office 365 보안 &amp; 준수 센터에서 감사 로그 검색](search-the-audit-log-in-security-and-compliance.md)을 참조하세요. 

## <a name="disposition-reviews"></a>처리 검토

콘텐츠가 보존 기간 끝에 도달하면 해당 콘텐츠를 검토하여 안전하게 삭제할 수 있는지 여부를 결정하는 몇 가지 이유가 있습니다("처분"). 예를 들어 다음을 수행해야 할 수 있습니다.
  
- 소송 또는 감사의 경우에 관련 콘텐츠의 삭제를 일시 중단합니다.
    
- 해당 콘텐츠에 연구 또는 기록적 가치가 있는 경우 처리 목록에서 콘텐츠를 제거하여 보관함에 저장합니다.
    
- 원래 보존 설정이 임시 혹은 잠정적 솔루션이어서 콘텐츠에 다른 보존 기간을 할당합니다.
    
- 콘텐츠를 클라이언트에게 반환하거나 다른 조직으로 이전합니다.

보존 기간이 끝날 때 처리 검토가 트리거되는 경우:
  
- 선택하는 사용자는 검토할 콘텐츠가 있다는 전자 메일 알림을 받습니다. 이러한 검토자는 개별 사용자 또는 메일 사용이 가능한 보안 그룹이 될 수 있습니다. 알림은 주 단위로 전송됩니다.
    
- 검토자는 Microsoft 365 준수 센터의 **처리** 탭으로 이동하여 콘텐츠를 검토하고 영구적으로 삭제하거나, 보존 기간을 연장하거나, 다른 보존 레이블을 적용할 것인지 결정합니다.

처리 검토에는 Exchange 사서함, SharePoint 사이트, OneDrive 계정 및 Microsoft 365 그룹의 콘텐츠가 포함될 수 있습니다. 해당 위치에서 처리 검토를 기다리는 콘텐츠는 검토자가 콘텐츠를 영구적으로 삭제하도록 선택한 후에만 삭제됩니다.

> [!NOTE]
> 처리 검토를 지원하려면 사서함에 10MB 이상의 데이터가 있어야 합니다.

**개요** 탭에서 보류 중인 모든 처리의 개요를 볼 수 있습니다. 예를 들면:

![레코드 관리에서 보류 중인 처리 개요](../media/dispositions-overview.png)

**보류 중인 모든 처리 보기** 를 선택하면 **처리** 페이지로 이동됩니다. 예를 들면 다음과 같습니다.

![Microsoft 365 규정 준수 센터의 처리 페이지](../media/disposition-tab.png)


### <a name="workflow-for-a-disposition-review"></a>처리 검토를 위한 워크플로

다음 다이어그램에서는 보존 레이블을 게시한 다음 사용자가 수동으로 적용하는 경우 처리 검토에 대한 기본 워크플로를 보여줍니다. 또는 처리 검토를 위해 구성한 보존 레이블을 콘텐츠에 자동으로 적용할 수 있습니다.
  
![처리 작업 진행 방식의 흐름을 보여 주는 차트](../media/5fb3f33a-cb53-468c-becc-6dda0ec52778.png)
  
보존 기간이 끝날 때 처리 검토를 트리거하는 것은 보존 레이블과만 함께 제공되는 구성 옵션입니다. 보존 정책에는 이 옵션을 사용할 수 없습니다. 이 두 가지 보존 솔루션에 대한 자세한 내용은 [보존 정책과 보존 레이블에 대해 알아보기](retention.md)를 참조하세요.

보존 레이블을 위한 **보존 설정 정의** 페이지에서:

![레이블에 대한 보존 설정](../media/disposition-review-option.png)
 
이 **처리 검토 트리거** 옵션을 선택한 후, 마법사의 다음 페이지에서 처리 검토자를 지정합니다.

![처리 검토자 지정](../media/disposition-reviewers.png)

검토자의 경우 사용자 또는 메일 사용이 가능한 보안 그룹을 지정합니다. 이 옵션에 대해 Microsoft 365 그룹([이전 Office 365 그룹](https://techcommunity.microsoft.com/t5/microsoft-365-blog/office-365-groups-will-become-microsoft-365-groups/ba-p/1303601))은 지원되지 않습니다.

### <a name="viewing-and-disposing-of-content"></a>콘텐츠 보기 및 처리

콘텐츠를 검토할 준비가 되었음을 검토자가 전자 메일로 알림을 받는 경우, Microsoft 365 준수 센터의 **레코드 관리** 에서 **처리** 탭으로 이동합니다. 검토자는 각 보존 레이블에 대해 얼마나 많은 항목이 처리를 대기 중인지 확인할 수 있고, 보존 레이블을 선택하여 해당 레이블이 있는 모든 콘텐츠를 볼 수 있습니다.

보존 레이블을 선택한 후, **보류 중인 처리** 탭에서 해당 레이블에 대해 보류 중인 모든 처리를 보게됩니다. 한 개 이상의 항목을 선택하여 작업을 선택하고 사유 메모를 입력합니다.

![처리 옵션](../media/retention-disposition-options.png)

그림에서 볼 수 있듯이 지원되는 작업은 다음과 같습니다. 
  
- 항목을 영구적으로 삭제
- 보존 기간 연장
- 다른 보존 레이블 적용

위치와 콘텐츠에 대한 사용 권한을 보유하면 **위치** 열에 있는 링크를 사용하여 원래 위치에 있는 문서를 볼 수 있습니다. 처리 검토를 진행하는 동안 콘텐츠는 원래 위치에서 이동할 수 없으며, 검토자가 그렇게 하도록 선택하기 전에는 삭제되지 않습니다.

전자 메일 알림은 주 단위로 자동으로 검토자에게 전송됩니다. 이 예약된 프로세스는 콘텐츠가 보존 기간의 끝에 도달하는 경우, 검토자자 콘텐츠가 처리를 기다리고 있다는 전자 메일 알림을 받는 데 최대 7일이 걸릴 수 있습니다.
  
모든 처리 작업은 감사되고 검토자가 입력한 사유 텍스트는 저장되어 **처리된 항목** 페이지의 **메모** 열에 표시됩니다.
  
### <a name="how-long-until-disposed-content-is-permanently-deleted"></a>처리된 콘텐츠가 영구적으로 삭제될 때까지 걸리는 시간

처리 검토를 기다리는 콘텐츠는 검토자가 콘텐츠를 영구적으로 삭제하도록 선택한 후에만 삭제됩니다. 검토자가 이 옵션을 선택하는 경우, SharePoint 사이트 또는 OneDrive 계정의 콘텐츠가 [보존 설정이 적소에 있는 콘텐츠와 작동하는 방법](retention.md#how-retention-settings-work-with-content-in-place)에 설명된 표준 정리 프로세스를 사용할 수 있게 됩니다.

## <a name="disposition-of-records"></a>레코드 처리

**레코드 관리** 페이지의 **처리** 탭을 사용하여 자동으로 또는 처리 검토 후에 현재 삭제된 레코드를 식별합니다. 이러한 항목에는 **유형** 열에 **처리된 레코드** 를 표시합니다. 예를 들면 다음과 같습니다.

![처리 검토가 없이 처리된 항목](../media/records-disposed2.png)

레코드 레이블을 위해 **처리된 항목** 탭에 표시되는 항목은 항목이 처리된 후 최대 7년간 유지되고, 해당 기간에 대한 레코드 당 100만 항목의 제한을 둡니다. **계산** 수가 이 100만의 제한에 근접하고 레코드에 대한 처리 증거가 필요한 경우, [Microsoft 지원](https://docs.microsoft.com/office365/admin/contact-support-for-business-products)에 문의하세요.

> [!NOTE]
> 이 기능은 [통합 감사 로그](search-the-audit-log-in-security-and-compliance.md)의 정보를 기초로 하며, 따라서 해당 이벤트를 캡처할 수 있도록 감사를 [사용 설정하고 검색 가능하도록](turn-audit-log-search-on-or-off.md) 해야 합니다.

감사를 위해 **파일 및 페이지 활동** 범주에서 **레코드로 표시된 삭제된 파일** 을 검색합니다. 이 감사 이벤트는 문서 및 이일에 적용됩니다.

## <a name="filter-and-export-the-views"></a>보기 필터링 및 내보내기

**처리** 페이지에서 보존 레이블을 선택하는 경우, **보류 중인 처리** 탭(해당 하는 경우)과 **처리된 항목** 탭을 사용하여 보기를 필터링하여 항목을 보다 쉽게 찾을 수 있도록 합니다. 

보류 중인 처리의 경우에는 시간 범위가 만료 날짜를 기준으로 합니다. 처리된 항목의 경우에는 시간 범위가 삭제 날짜를 기준으로 합니다.
  
아래의 항목에 대한 정보를 .csv 파일로 내보낼 수 있습니다. 그런 다음 Excel을 사용하여 정렬을 하고 관리할 수 있습니다.

![처리에 대한 내보내기 옵션](../media/retention-export-option.png)


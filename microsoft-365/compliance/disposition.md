---
title: 콘텐츠 처리
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: 처리 검토를 사용 하 든, 구성 된 설정에 따라 콘텐츠를 자동으로 삭제할지 여부에 관계 없이 콘텐츠 삭제를 모니터링 하 고 관리 합니다.
ms.openlocfilehash: 47cb8f023f378796f206e436aa33e74b2993ac97
ms.sourcegitcommit: 9d8816ddc3a97676ff947db80265e47b734f5462
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/30/2020
ms.locfileid: "43952621"
---
# <a name="disposition-of-content"></a>콘텐츠 처리

>*[보안 및 규정 준수를 위한 Microsoft 365 라이선싱 지침](https://aka.ms/ComplianceSD).*

Microsoft 365 준수 센터의 **레코드 관리** 에서 **처리** 탭을 사용 하 여 처리 검토를 관리 하 고 보존 기간이 끝나면 자동으로 삭제 된 [레코드](records.md) 를 확인 합니다. 

## <a name="prerequisites-for-viewing-content-dispositions"></a>콘텐츠 dispositions를 보기 위한 필수 구성 요소

처리 검토를 관리 하 고 레코드가 삭제 되었는지 확인 하려면 충분 한 사용 권한이 있어야 하 고 감사를 사용 하도록 설정 해야 합니다.

### <a name="permissions-for-disposition"></a>처리 권한

Microsoft 365 준수 센터의 **처리** 탭에 액세스 하려면 **처리 관리** 역할 및 **보기 전용 감사 로그** 역할의 구성원 이어야 합니다. **처리 검토자**라는 새 역할 그룹을 만들고이 두 역할을 해당 역할 그룹에 추가 하는 것이 좋습니다. 

**보기 전용 감사 로그** 역할에 한정 됩니다.

- 감사 로그를 검색 하는 데 사용 되는 기본 cmdlet은 Exchange Online cmdlet 이므로 보안 & 준수 센터의 **사용 권한** 페이지를 사용 하는 대신 [Exchange online의 exchange 관리 센터](https://docs.microsoft.com/Exchange/exchange-admin-center)를 사용 하 여 사용자에 게이 역할을 할당 해야 합니다. 자세한 내용은 [Exchange Online에서 역할 그룹 관리](https://docs.microsoft.com/Exchange/permissions-exo/role-groups)를 참조 하십시오.

- Microsoft 365 그룹 ([이전의 Office 365 그룹](https://techcommunity.microsoft.com/t5/microsoft-365-blog/office-365-groups-will-become-microsoft-365-groups/ba-p/1303601))은이 역할에 대해 지원 되지 않습니다. 대신 사용자 사서함, 메일 사용자 또는 메일 사용이 가능한 보안 그룹을 할당 합니다.

사용자에 게 **처리 관리** 역할을 부여 하 고 새 **처리 검토자** 역할을 만드는 방법에 대 한 지침은 [사용자에 게 Office 365 &amp; 보안 및 준수 센터에](../security/office-365-security/grant-access-to-the-security-and-compliance-center.md)대 한 액세스 권한을 부여를 참조 하세요.

### <a name="enable-auditing"></a>감사 사용

감사 기능이 사용 하도록 설정 되어 있는지 확인 하 고 첫 번째 처리 작업 보다 하루 이상입니다. 자세한 내용은 [Office 365 보안 &amp; 및 준수 센터에서 감사 로그 검색](search-the-audit-log-in-security-and-compliance.md)을 참조 하세요. 

## <a name="disposition-reviews"></a>처리 검토

콘텐츠가 보존 기간의 끝에 도달 하면 해당 콘텐츠를 검토 하 여 안전 하 게 삭제할 수 있는지 여부 ("삭제 된")를 결정 해야 하는 몇 가지 이유가 있습니다. 예를 들어 다음을 수행 해야 할 수 있습니다.
  
- 소송 또는 감사의 경우 관련 콘텐츠 삭제를 일시 중단 합니다.
    
- 처리 목록에서 콘텐츠를 제거 하 여 해당 콘텐츠에 조사 또는 기록 값이 있는 경우 보관 사서함에 저장 합니다.
    
- 원래 보존 설정이 임시 또는 provisional 솔루션 이기 때문에 콘텐츠에 다른 보존 기간을 할당 합니다.
    
- 콘텐츠를 클라이언트에 반환 하거나 다른 조직으로 전송 합니다.

처리 검토가 보존 기간이 끝날 때 트리거되는 경우:
  
- 선택한 사용자는 검토할 콘텐츠가 있는 전자 메일 알림을 받습니다. 이러한 검토자는 개별 사용자, 메일 그룹 또는 Office 365 그룹이 될 수 있습니다. 알림은 주 단위로 전송 됩니다.
    
- 검토자가 Microsoft 365 준수 센터의 **처리** 탭으로 이동 하 여 콘텐츠를 검토 하 고이를 영구적으로 삭제할지, 보존 기간을 연장할 지 아니면 다른 보존 레이블을 적용할지를 결정 합니다.

처리 검토에는 Exchange 사서함, SharePoint 사이트, OneDrive 계정 및 Microsoft 365 그룹의 콘텐츠가 포함 될 수 있습니다. 해당 위치에서 처리 검토를 대기 중인 콘텐츠는 검토자가 콘텐츠를 영구적으로 삭제 하도록 선택한 후에만 삭제 됩니다.

**개요** 탭에서 모든 보류 중인 dispositions의 개요를 확인할 수 있습니다. 예를 들어:

![레코드 관리 개요에서 보류 중인 dispositions](../media/dispositions-overview.png)

**보류 중인 모든 Dispositions 보기**를 선택 하면 **처리** 페이지로 이동 됩니다. 예시:

![Microsoft 365 준수 센터의 Dispositions 페이지](../media/disposition-tab.png)


### <a name="workflow-for-a-disposition-review"></a>처리 검토를 위한 워크플로

보존 레이블을 게시 한 다음 사용자가 수동으로 적용 하는 경우의 처리 검토에 대 한 기본 워크플로입니다. 또한 처리 검토를 위해 구성 된 보존 레이블을 콘텐츠에 자동으로 적용할 수 있습니다.
  
![처리가 작동 하는 방식 흐름을 보여 주는 차트](../media/5fb3f33a-cb53-468c-becc-6dda0ec52778.png)
  
보존 기간이 끝날 때 처리 검토를 트리거하는 것은 [보존 레이블과](labels.md)함께 사용할 수 있는 구성 옵션입니다. 보존 정책에서는이 옵션을 사용할 수 없습니다.
  
![레이블에 대 한 보존 설정](../media/a16dd202-8862-40ac-80ff-6fee974de5da.png)
 
> [!NOTE]
> **검토할 준비가 된 항목이 있을 때 이러한 사용자에 게 알림**옵션을 선택 하면 사용자 또는 메일 사용이 가능한 보안 그룹을 지정 합니다. Microsoft 365 그룹 ([이전의 Office 365 그룹](https://techcommunity.microsoft.com/t5/microsoft-365-blog/office-365-groups-will-become-microsoft-365-groups/ba-p/1303601))은이 옵션에 대해 지원 되지 않습니다.

### <a name="viewing-and-disposing-of-content"></a>콘텐츠 보기 및 삭제

콘텐츠를 검토할 준비가 된 전자 메일로 검토자에 게 알림을 받으면 Microsoft 365 준수 센터의 **레코드 관리** 에서 **처리** 탭으로 이동 합니다. 검토자는 처리를 위해 대기 중인 각 보존 레이블의 수를 확인 한 다음 보존 레이블을 선택 하 여 해당 레이블이 있는 모든 콘텐츠를 볼 수 있습니다.

보존 레이블을 선택한 후에는 **보류 중인 처리** 탭에서 해당 레이블에 대해 보류 중인 dispositions를 모두 확인 합니다. 그런 다음 작업을 선택 하 고 사유 설명을 입력할 수 있는 항목을 하나 이상 선택 합니다.

![처리 옵션](../media/retention-disposition-options.png)

그림에서 볼 수 있듯이 지원 되는 동작은 다음과 같습니다. 
  
- 항목을 영구적으로 삭제
- 보존 기간 확장
- 다른 보존 레이블 적용

위치 및 콘텐츠에 대 한 사용 권한을 부여 하면 **위치** 열의 링크를 사용 하 여 문서를 원래 위치에서 볼 수 있습니다. 처리 검토 중에는 콘텐츠가 원래 위치에서 이동 하지 않으며, 검토자가이를 선택 하기 전 까지는 삭제 되지 않습니다.
  
전자 메일 알림은 매주 검토자에 게 자동으로 전송 됩니다. 이 일정 상의 프로세스는 콘텐츠가 보존 기간의 끝에 도달 하는 경우 검토자가 콘텐츠 처리를 기다리는 전자 메일 알림을 받는 데 최대 7 일이 걸릴 수 있음을 의미 합니다.
  
모든 처리 작업을 감사할 수 있습니다.
  
### <a name="how-long-until-disposed-content-is-permanently-deleted"></a>삭제 된 콘텐츠가 영구적으로 삭제 될 때 까지의 기간

처리 검토를 기다리는 콘텐츠는 검토자가 콘텐츠를 영구적으로 삭제 하도록 선택한 후에만 삭제 됩니다. 검토자가이 옵션을 선택 하면 SharePoint 사이트 또는 OneDrive 계정의 콘텐츠가 [보존 정책이 현재 위치에 있는 콘텐츠에 작동 하는 방식](retention-policies.md#how-a-retention-policy-works-with-content-in-place)에 설명 된 표준 정리 프로세스를 수행할 수 있게 됩니다.

## <a name="disposition-of-records"></a>레코드 처리

> [!NOTE]
> 처리 검토 없이 자동으로 삭제 된 레코드를 확인 하는 기능은 4 2020 월 중에 테 넌 트로 서서히 롤아웃 되므로이 환경이 즉시 표시 되지 않을 수 있습니다.

**레코드 관리** 페이지의 **처리** 탭을 사용 하 여 자동으로 삭제 되는 레코드를 식별 합니다. 이러한 항목은 **형식** 열에서 **삭제 된 레코드** 를 표시 합니다. 예시:

![처리 검토 없이 삭제 된 항목](../media/records-disposed2.png)

레코드 레이블에 대 한 삭제 된 **항목** 탭에 표시 되는 항목은 항목을 삭제 한 후 최대 7 년 동안 유지 되며 해당 기간에 대 한 레코드 당 항목 제한은 100만 개입니다. 이 100만에 도달 **하 고 레코드** 에 대 한 처리 증거를 요구 하는 경우에는 [Microsoft 지원](https://docs.microsoft.com/office365/admin/contact-support-for-business-products)서비스에 문의 하십시오.

> [!NOTE]
> 이 기능은 [통합 된 감사 로그](search-the-audit-log-in-security-and-compliance.md) 의 정보를 기반으로 하므로 해당 이벤트가 캡처될 수 있도록 감사를 [사용 하도록 설정 하 고 검색](turn-audit-log-search-on-or-off.md) 해야 합니다.
    
## <a name="filter-and-export-the-views"></a>보기 필터링 및 내보내기

**처리** 페이지에서 보존 레이블을 선택 하면 **보류 중인 처리** 탭 (해당 되는 경우) 및 **삭제 된 항목** 탭을 사용 하 여 보기를 필터링 하 여 항목을 보다 쉽게 찾을 수 있도록 합니다. 

보류 중인 dispositions의 경우 시간 범위는 만료 날짜를 기준으로 합니다. 삭제 된 항목의 경우에는 시간 범위가 삭제 날짜를 기준으로 합니다.
  
다음과 같이 보기의 항목에 대 한 정보를 .csv 파일로 내보낸 다음 Excel을 사용 하 여 정렬 하 고 관리할 수 있습니다.

![폐기 옵션 내보내기](../media/retention-export-option.png)
  
![Excel에서 내보낸 처리 데이터](../media/08e3bc09-b132-47b4-a051-a590b697e725.png)



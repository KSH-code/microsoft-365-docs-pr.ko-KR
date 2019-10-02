---
title: Microsoft 365 준수 센터의 새로운 기능
ms.author: brendonb
author: brendonb
manager: laurawi
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- SPO160
- MOE150
- MET150
ms.assetid: e3c6df61-8513-499d-ad8e-8a91770bff63
ms.collection:
- M365-security-compliance
description: Microsoft 365 준수 센터에 지속적으로 새로운 기능을 추가 하 고, 문제를 해결 하 고, 사용자 의견에 따라 변경 사항을 적용 하 고 있습니다. 이번 달에 제공 된 내용을 확인 합니다.
ms.openlocfilehash: b80edfb0425904b03426ef0ff3cdd1d251e638ea
ms.sourcegitcommit: c6eab4a9f1b70e7ff0db6b2a1128a4db2591cbaf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/02/2019
ms.locfileid: "37369639"
---
# <a name="whats-new-in-the-microsoft-365-compliance-center"></a>Microsoft 365 준수 센터의 새로운 기능

[Microsoft 365 준수 센터](microsoft-365-compliance-center.md)에 지속적으로 새로운 기능을 추가 하 고, 문제를 해결 하 고, 사용자 의견에 따라 변경 사항을 적용 하 고 있습니다. 현재 사용 가능한 기능을 확인 하려면 아래를 확인 하세요. 일부 기능은 고객에 게 다양 한 속도로 롤아웃 됩니다. 아직 기능을 볼 수 없는 경우 대상 지정 된 [릴리스에](https://docs.microsoft.com/office365/admin/manage/release-options-in-office-365)자신을 추가 해 보세요.

> [!TIP]
> 다른 관리 센터에서 어떤 작업을 진행 하 고 싶으십니까? 다음 문서를 확인 하세요.<br>[Microsoft 365 관리 센터의 새로운 기능](https://docs.microsoft.com/office365/admin/whats-new-in-preview?view=o365-worldwide)<br>[SharePoint 관리 센터의 새로운 기능](https://docs.microsoft.com/sharepoint/what-s-new-in-admin-center)

## <a name="september-2019"></a>2019년 9월

이번 달에 출시 된 릴리스가 어떻게 조용한 지 궁금 하십니까? [Microsoft Ignite](https://www.microsoft.com/ignite) 의 11 월에 unveiled 되는 혁신적인 새 규정 준수 솔루션을 구축 하 고 있습니다. 계속 조정

### <a name="new-encryption-options-for-sensitivity-labels"></a>민감도 레이블의 새 암호화 옵션 

민감도 레이블에 대 한 암호화를 구성할 때 사용자가 전자 메일 및 문서에 레이블을 수동으로 적용할 때 사용 권한을 할당할 수 있는 두 가지 옵션이 있습니다.<br>
- **Outlook 전자 메일**에 레이블을 적용할 때 사용자는 전달 금지 옵션에 해당 하는 제한을 적용할 수 있습니다. 받는 사람이 메시지를 읽을 수는 있지만 콘텐츠를 전달, 인쇄 또는 복사 하지는 못합니다.
- **Word, PowerPoint 및 Excel 파일**에 레이블을 적용 하는 경우 사용자에 게 특정 사용자 및 그룹에 대 한 액세스 권한을 지정 하 라는 메시지가 표시 됩니다.

[자세한 정보](encryption-sensitivity-labels.md#let-users-assign-permissions)

## <a name="august-2019"></a>8 월 2019

### <a name="update-to-data-investigations"></a>데이터 조사에 대 한 업데이트

데이터 조사를 수행할 때 이제 원래 위치에서 항목을 삭제할 수 있습니다. 즉, 조직 전체에서 Exchange 사서함, SharePoint 사이트 및 OneDrive 계정에서 항목을 삭제할 수 있습니다. 항목을 증거로 수집 했기 때문에 세부 정보 집합에 보관 된 복사본을 추가 하거나 참조로 유지 하는 것을 조사할 수 있습니다. [자세한 정보](manage-data-spillage-incidents.md#step-4-delete-the-spilled-data) 

## <a name="july-2019"></a>7 월 2019 일

### <a name="new-admin-roles"></a>새 관리자 역할

조직의 보안 및 규정 준수를 관리 하는 데 도움이 되는 새로운 관리자 역할이 두 개 릴리스 되었습니다. 모든 친구에 게 알리기.

- **준수 데이터 관리자** 이 역할을 가진 사용자에 게는 Microsoft 365 준수 센터, Microsoft 365 관리 센터 및 Azure에서 데이터를 보호 하 고 추적할 수 있는 권한이 있습니다. 또한 Exchange 관리 센터, 준수 관리자, 팀 & 비즈니스용 Skype 관리 센터에 대 한 모든 항목을 관리 하 고 Azure 및 Microsoft 365에 대 한 지원 티켓을 만들 수 있습니다.
- **보안 운영자**입니다. 이 역할을 가진 사용자는 경고를 관리 하 고 Microsoft 365 보안 센터, Azure Active Directory, Id 보호, 권한이 부여 된 Id 관리 및 Office 365의 모든 항목을 포함 하 여 보안 관련 기능에 대 한 전역 읽기 전용 액세스 권한을 가질 수 있습니다. 보안 & 준수 센터

[이러한 역할에 대해 자세히 알아보기](https://docs.microsoft.com/microsoft-365/security//office-365-security/permissions-microsoft-365-compliance-security)

### <a name="search-and-filtering-for-reports"></a>보고서 검색 및 필터링

보고서의 해상로 스크롤하여 원하는 것을 찾을 수 없습니다. 이제 제목에 따라 보고서를 검색 하 고 ' 레이블 ' 및 ' 준수 ', ' Office 365 ' 및 ' Microsoft Cloud App Security '와 같은 원본 범주에 대 한 필터링을 수행할 수 있습니다.

![필터가 적용 된 보고서의 검색 및 필터 단추 화면 캡처](media/mcc_report_filtering.png)

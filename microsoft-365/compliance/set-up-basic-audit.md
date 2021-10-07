---
title: 2013에서 기본 감사 Microsoft 365
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.localizationpriority: medium
ms.collection:
- M365-security-compliance
- m365solution-audit
- m365initiative-compliance
- m365solution-scenario
search.appverid:
- MOE150
- MET150
description: 이 문서에서는 조직의 사용자 및 관리자가 수행한 감사 활동을 검색할 수 있도록 기본 감사를 설정하는 방법에 대해 설명합니다.
ms.openlocfilehash: 9190383fdfab8e4207186ca93895ec9ce23ec6d4
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60200320"
---
# <a name="set-up-basic-audit-in-microsoft-365"></a>2013에서 기본 감사 Microsoft 365

기본 감사 Microsoft 365 사용하여 사용자 및 관리자가 다양한 Microsoft 365 수행한 활동에 대한 감사 레코드를 검색할 수 있습니다. 기본 감사는 대부분의 Microsoft 365 Office 365 조직에서 기본적으로 사용하도록 설정되기 때문에 사용자 및 조직의 다른 사람이 감사 로그를 검색하기 전에 몇 가지만 해야 합니다.

이 문서에서는 기본 감사를 설정하는 데 필요한 다음 단계에 대해 논의합니다.

![기본 감사를 설정하는 단계입니다.](../media/BasicAuditingWorkflow.png)

이러한 단계에는 감사 레코드를 생성하고 보존하는 데 필요한 적절한 조직 구독 및 사용자 라이선스를 보장하고 감사 로그를 검색할 수 있도록 보안 운영, IT, 규정 준수 및 법률 팀의 팀 구성원에게 사용 권한을 할당하는 작업이 포함됩니다.

자세한 내용은 에서 [기본 감사를 Microsoft 365.](auditing-solutions-overview.md#basic-audit)

## <a name="step-1-verify-organization-subscription-and-user-licensing"></a>1단계: 조직 구독 및 사용자 라이선스 확인

기본 감사에 대한 라이선스를 사용하려면 감사 로그 검색 도구 및 감사 레코드를 기록하고 보존하는 데 필요한 사용자당 라이선스에 대한 액세스를 제공하는 적절한 조직 구독이 필요합니다.

사용자 또는 관리자가 감사되는 활동을 수행하면 감사 레코드가 생성되어 조직의 감사 로그에 저장됩니다. 기본 감사에서 감사 레코드는 90일 동안 감사 로그에 보존되고 검색할 수 있습니다.

기본 감사에 대한 구독 및 라이선스 요구 사항 목록은 에서 감사 [솔루션을 Microsoft 365.](auditing-solutions-overview.md#licensing-requirements)

## <a name="step-2-assign-permissions-to-search-the-audit-log"></a>2단계: 감사 로그 검색에 대한 사용 권한 할당

감사 로그를 검색하려면 조사 팀의 관리자와 구성원에게 View-Only 감사 로그 또는 감사 Exchange Online 역할이 할당되어야 합니다. 기본적으로 이러한 역할은 Exchange 관리 센터의 **사용 권한** 페이지에서 규정 준수 관리 및 조직 관리 역할 그룹에 할당됩니다. Office 365 및 Microsoft 365의 전역 관리자는 자동으로 Exchange Online 서비스에서 조직 관리 역할 그룹의 구성원이 됩니다. 최소 권한 수준을 사용하여 감사 로그를 검색할 수 있는 권한을 사용자에게 제공하려면 Exchange Online에서 사용자 지정 역할 그룹을 만들고, 보기 전용 감사 로그 또는 감사 로그 역할을 추가한 다음, 새 역할 그룹의 구성원으로 사용자를 추가할 수 있습니다. 자세한 내용은 [Exchange Online에서 역할 그룹 관리](/Exchange/permissions-exo/role-groups)를 참조하세요.

다음 스크린샷은 조직 관리 센터의 조직 관리 역할 그룹에 할당된 두 가지 감사 관련 역할을 Exchange 보여줍니다.

![역할 그룹의 역할 그룹에 할당된 역할을 Exchange Online.](../media/EACAuditRoles.png)

## <a name="step-3-search-the-audit-log"></a>3단계: 감사 로그 검색

이제 감사 로그에서 감사 로그를 검색할 준비가 Microsoft 365 규정 준수 센터.

1. 으로 이동한 후 적절한 감사 권한이 할당된 계정을 사용하여 <https://compliance.microsoft.com> 로그인합니다.

2. 창의 왼쪽 탐색 창에서 Microsoft 365 규정 준수 센터 표시를 **클릭한** 다음 감사를 **클릭합니다.**

3. 감사 **페이지에서** 검색 탭의 다음 조건을 사용하여 검색을 **구성합니다.** 

   ![감사 로그 검색에 대한 구성 설정입니다.](../media/AuditLogSearchToolMCCCallouts.png)

   1. **날짜 및 시간 범위입니다.** 날짜 및 시간 범위를 선택하여 해당 기간 내에 발생한 이벤트를 표시합니다. 날짜 및 시간은 현지 시간으로 표시됩니다. 기본적으로 지난 7일이 선택됩니다.
  
   2. **활동**. 검색할 활동을 선택합니다. 검색 상자를 사용하여 목록에 추가할 활동을 검색합니다. 감사된 활동의 일부 목록은 감사된 활동을 [참조하세요.](search-the-audit-log-in-security-and-compliance.md#audited-activities) 감사된 모든 활동에 대한 항목을 반환하기 위해 이 상자를 비워 두십시오.
  
   3. **사용자**.  이 상자를 클릭하고 검색 결과를 표시할 사용자 이름을 입력합니다. 이 상자에서 선택한 사용자가 수행한 선택한 활동에 대한 감사 로그 항목이 결과 목록에 표시됩니다. 조직의 모든 사용자(및 서비스 계정)에 대한 항목을 반환하려면 이 상자를 비워 둡니다.
  
   4. **파일, 폴더 또는 사이트**. 파일 또는 폴더 이름을 일부 또는 모두 입력하여 지정된 키워드가 포함된 폴더 파일과 관련된 활동을 검색합니다. 파일 또는 폴더의 URL을 지정할 수도 있습니다. 파일 또는 폴더의 URL을 사용하는 경우 전체 URL 경로를 입력해야 합니다. 또는 URL의 일부를 입력하는 경우 특수 문자나 공백을 포함하지 않습니다. 조직의 모든 파일 및 폴더에 대한 항목을 반환하려면 이 상자를 비워 둡니다.

4. 검색을 **클릭하여** 검색을 실행합니다.

감사 로그 검색이 실행되고 있는 새 페이지가 표시됩니다. 검색이 완료되면 감사 레코드가 페이지에 표시됩니다. 레코드를 클릭하여 자세한 속성이 있는 플라이아웃 페이지를 표시합니다.

자세한 지침은 준수 센터에서 감사 로그 [검색을 참조하세요.](search-the-audit-log-in-security-and-compliance.md)

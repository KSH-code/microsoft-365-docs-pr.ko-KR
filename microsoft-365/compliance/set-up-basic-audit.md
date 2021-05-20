---
title: Microsoft 365 기본 감사 설정
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365solution-audit
- m365initiative-compliance
- m365solution-scenario
search.appverid:
- MOE150
- MET150
description: 이 문서에서는 조직의 사용자와 관리자가 수행하는 감사 활동을 검색할 수 있도록 기본 감사를 설정하는 방법에 대해 설명합니다.
ms.openlocfilehash: 59b5c85003ef0e19f7d3dd7417f764f446244652
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/19/2021
ms.locfileid: "52564832"
---
# <a name="set-up-basic-audit-in-microsoft-365"></a>Microsoft 365 기본 감사 설정

Microsoft 365 기본 감사를 사용하면 사용자와 관리자가 다른 Microsoft 365 서비스에서 수행되는 활동에 대한 감사 기록을 검색할 수 있습니다. 기본 감사는 대부분의 Microsoft 365 및 Office 365 조직에 대해 기본적으로 활성화되므로 조직의 다른 사용자가 감사 로그를 검색하기 전에 수행해야 하는 일은 몇 가지일 뿐입니다.

이 문서에서는 기본 감사를 설정하는 데 필요한 다음 단계에 대해 설명합니다.

![기본 감사를 설정하는 단계](../media/BasicAuditingWorkflow.png)

이러한 단계에는 감사 기록을 생성 및 보존하는 데 필요한 적절한 조직 구독 및 사용자 라이선스를 보장하고 감사 로그를 검색할 수 있도록 보안 운영, IT, 규정 준수 및 법률 팀의 팀 구성원에게 권한을 할당하는 것이 포함됩니다.

자세한 내용은 [Microsoft 365 기본 감사를](auditing-solutions-overview.md#basic-audit)참조하십시오.

## <a name="step-1-verify-organization-subscription-and-user-licensing"></a>1단계: 조직 구독 및 사용자 라이선스 확인

기본 감사에 대한 라이선스에는 감사 기록 및 유지에 필요한 감사 로그 검색 도구 및 사용자별 라이선스에 대한 액세스를 제공하는 적절한 조직 구독이 필요합니다.

사용자 또는 관리자가 감사되는 활동을 수행하면 감사 레코드가 생성되어 조직의 감사 로그에 저장됩니다. 기본 감사에서는 감사 기록이 90일 동안 감사 로그에서 보관되고 검색할 수 있습니다.

기본 감사에 대한 구독 및 라이선스 요구 사항 목록은 [Microsoft 365 감사 솔루션을](auditing-solutions-overview.md#licensing-requirements)참조하십시오.

## <a name="step-2-assign-permissions-to-search-the-audit-log"></a>2단계: 감사 로그를 검색할 수 있는 권한을 할당합니다.

관리자와 조사 팀의 구성원은 감사 로그를 검색하기 위해 Exchange Online View-Only 감사 로그 또는 감사 로그 역할을 할당해야 합니다. 기본적으로 이러한 역할은 Exchange 관리 센터의 **사용 권한** 페이지에서 규정 준수 관리 및 조직 관리 역할 그룹에 할당됩니다. Office 365 및 Microsoft 365 글로벌 관리자는 Exchange Online 조직 관리 역할 그룹의 구성원으로 자동으로 추가됩니다. 최소 권한 수준을 사용하여 감사 로그를 검색할 수 있는 권한을 사용자에게 제공하려면 Exchange Online에서 사용자 지정 역할 그룹을 만들고, 보기 전용 감사 로그 또는 감사 로그 역할을 추가한 다음, 새 역할 그룹의 구성원으로 사용자를 추가할 수 있습니다. 자세한 내용은 [Exchange Online에서 역할 그룹 관리](/Exchange/permissions-exo/role-groups)를 참조하세요.

다음 스크린샷에는 Exchange 관리 센터의 조직 관리 역할 그룹에 할당된 두 개의 감사 관련 역할이 표시됩니다.

![Exchange Online 역할 그룹에 할당된 감사 역할](../media/EACAuditRoles.png)

## <a name="step-3-search-the-audit-log"></a>3단계: 감사 기록 검색

이제 Microsoft 365 규정 준수 센터에서 감사 로그를 검색할 준비가 되었습니다.

1. 적절한 <https://compliance.microsoft.com> 감사 권한이 할당된 계정을 사용하여 로그인합니다.

2. Microsoft 365 규정 준수 센터의 왼쪽 탐색 창에서 **모든 표시를** 클릭한 다음 **감사를 클릭합니다.**

3. **감사** 페이지에서 **검색** 탭에서 다음 조건을 사용하여 검색을 구성합니다. 

   ![감사 로그 검색을 위한 구성 설정](../media/AuditLogSearchToolMCCCallouts.png)

   1. **날짜 및 시간 범위**. 날짜 및 시간 범위를 선택하여 해당 기간 내에 발생한 이벤트를 표시합니다. 날짜 및 시간은 현지 시간으로 표시됩니다. 마지막 7일은 기본적으로 선택됩니다.
  
   2. **활동**. 검색할 활동을 선택합니다. 검색 상자를 사용하여 목록에 추가할 활동을 검색합니다. 감사된 활동의 일부 목록은 [감사된 활동을](search-the-audit-log-in-security-and-compliance.md#audited-activities)참조하십시오. 이 상자를 비워 모든 감사된 활동에 대한 항목을 반환합니다.
  
   3. **사용자**.  이 상자를 클릭하고 사용자 이름을 입력하여 검색 결과를 표시합니다. 이 상자에서 선택한 사용자가 수행하는 선택한 활동에 대한 감사 로그 항목이 결과 목록에 표시됩니다. 조직의 모든 사용자(및 서비스 계정)에 대한 항목을 반환하려면 이 상자를 비워 둡니다.
  
   4. **파일, 폴더 또는 사이트**. 지정된 키워드가 포함된 폴더 파일과 관련된 활동을 검색하려면 파일 또는 폴더 이름의 일부 또는 전부를 입력합니다. 파일 또는 폴더의 URL을 지정할 수도 있습니다. 파일 이나 폴더의 URL을 사용 하는 경우, 전체 URL 경로 형식 또는 URL의 일부를 입력 하는 경우 특별 한 문자 또는 공백을 포함 하지 마십시오. 조직의 모든 파일 및 폴더에 대한 항목을 반환하려면 이 상자를 비워 둡니다.

4. **검색을** 클릭하여 검색을 실행합니다.

감사 로그 검색이 실행 중임을 보여주는 새 페이지가 표시됩니다. 검색이 완료되면 감사 레코드가 페이지에 표시됩니다. 레코드를 클릭하여 자세한 속성이 있는 플라이아웃 페이지를 표시합니다.

자세한 지침은 규정 [준수 센터에서 감사 로그 검색을](search-the-audit-log-in-security-and-compliance.md)참조하십시오.

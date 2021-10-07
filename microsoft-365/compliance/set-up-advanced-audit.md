---
title: 2013에서 고급 감사 Microsoft 365
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
ms.custom: admindeeplinkMAC
search.appverid:
- MOE150
- MET150
description: 이 문서에서는 사용자 계정이 손상된 경우 포렌식 조사를 수행하거나 기타 보안 관련 인시던트에 대한 조사를 수행할 수 있도록 고급 감사를 설정하는 방법을 설명합니다.
ms.openlocfilehash: 34ae98eaafcc3eeb3d6a25a457f017999b8c6078
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60192070"
---
# <a name="set-up-advanced-audit-in-microsoft-365"></a>2013에서 고급 감사 Microsoft 365

조직에 고급 감사를 지원하는 구독 및 최종 사용자 라이선스가 있는 경우 다음 단계를 수행하여 고급 감사의 추가 기능을 설정하고 사용하세요.

![고급 감사 설정 워크플로.](../media/AdvancedAuditWorkflow.png)

## <a name="step-1-set-up-advanced-audit-for-users"></a>1단계: 사용자에 대한 고급 감사 설정

MailItemsAccessed 및 전송과 같은 중요한 이벤트를 기록하는 기능과 같은 고급 감사 기능을 사용하려면 적절한 E5 라이선스가 사용자에게 할당되어야 합니다. 또한 이러한 사용자에 대해 고급 감사 앱/서비스 계획을 실행해야 합니다. 고급 감사 앱이 사용자에게 할당되었는지 확인하려면 각 사용자에 대해 다음 단계를 수행하세요.

1. 이 Microsoft 365 관리 센터 사용자 활성 사용자로  >  이동하여 사용자를 선택합니다.<a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank"></a>

2. 사용자 속성 플라이아웃 페이지에서 **라이선스 및 앱** 을 클릭합니다.

3. 라이선스 **섹션에서** 사용자에게 E5 라이선스가 할당되어 있는지 또는 적절한 추가 기능 라이선스가 할당되어 있는지를 확인해야 합니다. 고급 감사를 지원하는 라이선스 목록은 고급 감사 라이선스 요구 [사항을 참조하세요.](auditing-solutions-overview.md#advanced-audit-1)

4. **앱** 구역을 확장하고 **Microsoft 365 고급 감사** 확인란이 선택되어 있는지 확인합니다.

5. 확인란을 선택하지 않은 경우 해당 확인란을 선택한 다음 변경 내용 **저장을 클릭합니다.**

   MailItemsAccessed 및 Send에 대한 감사 레코드 로깅은 24시간 이내에 시작됩니다. 다른 두 고급 감사 이벤트 SearchQueryInitiatedExchange 및 SearchQueryInitiatedSharePoint의 로깅을 시작하기 위해 3단계를 수행해야 합니다.

그룹 기반 라이선스를 사용하여 사용자 그룹에 라이선스를 할당하는 조직의 경우 그룹의 Microsoft 365 고급 감사에 대한 라이선스 할당을 해제해야 합니다. 변경 내용을 저장한 후에는 그룹에 대해 Microsoft 365 고급 감사를 해제했는지 확인합니다. 그런 다음, 그룹에 대한 라이선스 할당을 다시 설정합니다. 그룹 기반 라이선싱에 대한 자세한 내용은 [Azure Active Directory에서 그룹 구성원으로 사용자에게 라이선스 할당](/azure/active-directory/users-groups-roles/licensing-groups-assign)을 참조하세요.

또한 사용자 사서함 또는 공유 사서함에 기록되는 사서함 작업을 사용자 지정한 경우 Microsoft에서 릴리스한 새 고급 감사 이벤트는 해당 사서함에 대해 자동으로 감사되지 않습니다. 각 로그온 유형에 대해 감사되는 사서함 작업을 변경하는 방법에 대한 자세한 내용은 [사서함 감사 관리](enable-mailbox-auditing.md#change-or-restore-mailbox-actions-logged-by-default)의 "기본적으로 로그되는 사서함 작업 변경 또는 복원" 섹션을 참조하세요.

## <a name="step-2-enable-advanced-audit-events"></a>2단계: 고급 감사 이벤트 사용

사용자가 Exchange Online 및 SharePoint Online에서 검색을 수행할 때 두 개의 고급 감사 이벤트(SearchQueryInitiatedExchange 및 SearchQueryInitiatedSharePoint)를 로깅하도록 설정해야 합니다. 사용자에 대해 이러한 두 이벤트를 감사할 수 있도록 설정하려면 [PowerShell에서](/powershell/exchange/connect-to-exchange-online-powershell)각 사용자에 대해 Exchange Online 실행합니다.

```powershell
Set-Mailbox <user> -AuditOwner @{Add="SearchQueryInitiated"}
```

다중 위치 환경에서는 사용자의 사서함이 있는 포리스트에서 이전 **Set-Mailbox** 명령을 실행해야 합니다. 사용자의 사서함 위치를 식별하기 위해 다음 명령을 실행합니다. 

```powershell
Get-Mailbox <user identity> | FL MailboxLocations
```

검색 쿼리 감사를 사용하도록 설정하는 명령을 이전에 사용자 사서함이 있는 포리스트와 다른 포리스트에서 실행한 경우 실행하여 사용자 사서함에서 SearchQueryInitiated 값을 제거한 다음 사용자의 사서함이 있는 포리스트의 사용자 사서함에 추가해야 `Set-Mailbox -AuditOwner @{Remove="SearchQueryInitiated"}` 합니다.

## <a name="step-3-set-up-audit-retention-policies"></a>3단계: 감사 보존 정책 설정

Exchange, SharePoint 및 Azure AD 감사 레코드를 1년 동안 유지하는 기본 정책에 더해 조직의 보안 작업, IT 및 규정 준수 팀의 요구 사항을 충족하는 추가 감사 로그 보존 정책을 만들 수 있습니다. 자세한 내용은 [감사 로그 보존 정책 관리](audit-log-retention-policies.md)를 참조하십시오.

## <a name="step-4-search-for-advanced-audit-events"></a>4단계: 고급 감사 이벤트 검색

이제 조직에 대해 고급 감사를 설정한 후, 포렌식 조사를 수행 할 때 중요한 고급 감사 이벤트 및 기타 활동을 검색할 수 있습니다. 1단계 및 2단계를 완료한 후 손상된 계정 및 기타 유형의 보안 또는 규정 준수 조사에 대한 법정 조사 중에 고급 감사 이벤트 및 기타 활동을 검색할 수 있습니다. MailItemsAccessed 고급 감사 이벤트를 사용하여 손상된 사용자 계정에 대한 포렌식 조사를 수행하는 데 대한 자세한 내용은 고급 감사를 사용하여 손상된 계정 조사를 [참조하세요.](mailitemsaccessed-forensics-investigations.md)

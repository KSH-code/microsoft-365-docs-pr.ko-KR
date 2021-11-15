---
title: 도이클란드 Microsoft 클라우드에서 마이그레이션하는 동안의 eDiscovery 경험에 대한 정보
ms.author: andyber
author: andybergen
manager: laurawi
ms.date: 12/01/2020
audience: ITPro
ms.topic: article
ms.service: o365-solutions
ms.localizationpriority: medium
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
f1.keywords:
- CSH
ms.custom:
- Ent_TLGs
- admindeeplinkDEFENDER
description: '요약: 도이치란드 Microsoft 클라우드에서 마이그레이션하기 위한 eDiscovery 마이그레이션 단계입니다.'
ms.openlocfilehash: 08c44374b834796bce5f624008dd2f7493e7c3f7
ms.sourcegitcommit: 542e6b5d12a8d400c3b9be44d849676845609c5f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/15/2021
ms.locfileid: "60963074"
---
# <a name="information-about-the-ediscovery-experience-during-the-migration-from-microsoft-cloud-deutschland"></a>도이클란드 Microsoft 클라우드에서 마이그레이션하는 동안의 eDiscovery 경험에 대한 정보
다음 섹션에서는 독일 Microsoft 클라우드(도이치란드 Microsoft 클라우드)에서 새 독일 데이터 센터 지역의 Office 365 서비스로 이동하는 경우의 eDiscovery 경험에 대한 추가 정보를 제공합니다.

## <a name="ediscovery-administration-until-phase-4"></a>4단계까지의 eDiscovery 관리
4단계까지는 보안 및 준수 센터를 완전히 사용할 수 있습니다. 모든 콘텐츠는 여전히 Microsoft 클라우드 독일에 남아 있으며 Microsoft 클라우드 독일 보안 및 규정 준수 센터( 에서 관리할 수 https://protection.office.de/) 있습니다.

## <a name="ediscovery-experience-between-phase-4-until-the-the-end-of-phase-9"></a>4단계에서 9단계가 끝날 때까지의 eDiscovery 환경
4단계의 시작부터 9단계까지 eDiscovery 검색은 실패하거나 마이그레이션된 SharePoint Online, 비즈니스용 OneDrive 및 Exchange Online 위치에 대해 0 결과를 반환합니다.

> [!NOTE]
> 마이그레이션 중에 고객은 콘텐츠 검색을 포함하여 보안 및 준수 센터에서 사례, 보류& 검색 [및 내보내기 &](/microsoft-365/compliance/manage-legal-investigations)수 [있습니다.](/microsoft-365/compliance/search-for-content) 그러나 마이그레이션된 SharePoint Online, 비즈니스용 OneDrive Exchange Online 검색하면 0개 결과가 반환되거나 오류가 발생합니다.

검색에서 마이그레이션 중에 결과가 0개 또는 오류를 반환하는 경우 SharePoint Online에 대해 다음 작업을 수행하세요.

- SharePoint 또는 비즈니스용 OneDrive 파일 및 폴더 다운로드의 지침에 따라 OneDrive Online 또는 [SharePoint.](https://support.office.com/article/download-files-and-folders-from-onedrive-or-sharepoint-5c7397b7-19c7-4893-84fe-d02e8fa5df05) 이 방법을 사용하려면 SharePoint 온라인 관리자 권한 또는 읽기 전용 권한이 필요합니다.
- OneDrive 또는 SharePoint에서 파일 및 [](https://support.office.com/article/download-files-and-folders-from-onedrive-or-sharepoint-5c7397b7-19c7-4893-84fe-d02e8fa5df05)폴더 다운로드에 설명된 제한이 초과되는 경우 고객은 Sync SharePoint and [Teams files with your computer의](https://support.office.com/article/sync-sharepoint-files-with-the-new-onedrive-sync-app-6de9ede8-5b6e-4503-80b2-6190f3354a88)지침에 따라 비즈니스용 OneDrive 동기화 클라이언트를 사용할 수 있습니다.

- 자세한 내용은 에서 [In-Place eDiscovery in Exchange Server.](/Exchange/policy-and-compliance/ediscovery/ediscovery)


## <a name="ediscovery-administration-after-phase-9"></a>9단계 이후의 eDiscovery 관리

**다음에 적용됩니다.** eDiscovery를 사용하는 모든 고객

9단계에서 새 독일 데이터 센터 지역으로 이동하는 최종 단계가 완료됩니다. 이 단계에서는 나머지 모든 서비스 구성 요소가 마이그레이션됩니다.
9단계 이후에는 Microsoft 클라우드 독일(protection.office.de)의 보안 및 준수 센터 사용이 더 이상 지원되지 않습니다. 새 보안 <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">Microsoft 365 보안</a> 센터 또는 Microsoft 365 규정 준수 센터 사용합니다. <a href="https://go.microsoft.com/fwlink/p/?linkid=2077149" target="_blank"></a> 모든 데이터가 새 관리 포털로 마이그레이션됩니다.

| Step(s) | 설명 | 영향 |
|:-------|:-------|:-------|
|  모든 SharePoint, 비즈니스용 OneDrive 및 Exchange Online 위치가 SCC(보안 및 준수 센터)와 함께 마이그레이션됩니다. | 모든 eDiscovery 활동은 전 세계 테넌트에서 실행해야 합니다. 이제 검색이 100% 성공합니다. 오류 또는 오류는 정상적인 지원 채널을 따라야 합니다. | 없음 |
||||

### <a name="ediscovery-retention-policy"></a>eDiscovery 보존 정책
**다음에 적용됩니다.**  마이그레이션 전 단계의 일부로 보존 정책을 적용한 모든 고객

| Step(s) | 설명 | 영향 |
|:-------|:-------|:-------|
| 마이그레이션 전 단계 중에 만들어진 조직 전체 보존 정책 제거 | 고객은 마이그레이션 전 작업 중에 만들어진 조직 전체 보존 정책을 제거할 수 있습니다. | 없음 |
||||

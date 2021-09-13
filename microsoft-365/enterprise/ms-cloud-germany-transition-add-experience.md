---
title: 도이클란드 Microsoft 클라우드에서 마이그레이션을 위한 마이그레이션 후 활동
ms.author: andyber
author: andybergen
manager: laurawi
ms.date: 12/11/2020
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
f1.keywords:
- CSH
ms.custom:
- Ent_TLGs
description: '요약: 독일 Microsoft 클라우드(도이치란드 Microsoft 클라우드)에서 새 독일 데이터 센터 지역의 Office 365 서비스로 이동한 후의 마이그레이션 후 활동'
ms.openlocfilehash: 3659ce8ffa3424c3521c8f8954be88c7d53d0a51
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2021
ms.locfileid: "59191252"
---
# <a name="post-migration-activities-for-the-migration-from-microsoft-cloud-deutschland"></a>도이클란드 Microsoft 클라우드에서 마이그레이션을 위한 마이그레이션 후 활동

다음 섹션에서는 독일 Microsoft 클라우드(도이치란드 Microsoft 클라우드)에서 새 독일 데이터 센터 지역의 Office 365 서비스를 이동한 후 여러 서비스에 대한 마이그레이션 후 활동을 제공합니다.

## <a name="azure-ad"></a>Azure AD
<!-- This AAD Endpoints comparison table could be added to the documentation, not finally decided.
### Azure AD Endpoints
**Applies to:** All customers

After the cut over to Azure AD is complete, the organization is fully using Office 365 services and is no longer connected to Microsoft Cloud Deutschland and the endpoints cannot be used anymore. At this point, the customer needs to ensure that all applications are using the endpoints for the new German datacenter region.
The following table provides an overview about which endpoints will replace the previously used endpoints in Microsoft Cloud Germany (Microsoft Cloud Deutschland). 

|Endpoint in Microsoft Cloud Germany  |Endpoint in the new German datacenter region  |
|:---------|:---------|
|becws.microsoftonline.de<br>provisioningapi.microsoftonline.de |becws.microsoftonline.com<br>provisioningapi.microsoftonline.com |
|adminwebservice.microsoftonline.de |adminwebservice.microsoftonline.com |
|login.microsoftonline.de<br>logincert.microsoftonline.de<br>sts.microsoftonline.de |login.microsoftonline.com<br>login.windows.net<br>logincert.microsoftonline.com<br>accounts.accesscontrol.windows.net |
|enterpriseregistration.microsoftonline.de |enterpriseregistration.windows.net |
|graph.cloudapi.de |graph.windows.net |
|graph.microsoft.de |graph.microsoft.com |
|||
-->

### <a name="azure-ad-federated-authentication-with-ad-fs"></a>AD FS를 사용하는 Azure AD 페더전 인증
**다음에 적용됩니다.** AD FS와의 페더러드 인증을 사용하는 모든 고객

| Step(s) | 설명 | 영향 |
|:-------|:-------|:-------|
| 도이치클라드 MICROSOFT 클라우드 AD FS에서 신뢰 파티 트러스트 제거 | Azure AD에 대한 컷오버가 완료되면 조직은 Office 365 서비스를 완전히 사용하고 있으며 더 이상 도이클란드 Microsoft 클라우드에 연결되지 않습니다. 이 시점에서 고객은 도이치클라드 Microsoft 클라우드 끝점에 대한 신뢰 파티 트러스트는 제거해야 합니다. Azure AD가 IdP(ID 공급자)로 활용될 때 고객의 응용 프로그램이 도이치클라드 Microsoft 클라우드 끝점을 지점하지만 이행할 수 있습니다. | 페더리드 인증 조직 | 
||||

<!--
    Question from ckinder
    The following paragraph is not clear
-->
### <a name="group-approvals"></a>그룹 승인
**다음에 적용됩니다.** 마이그레이션 전 지난 30일 동안 Azure AD 그룹 승인 요청이 승인되지 않은 최종 사용자 

| Step(s) | 설명 | 영향 |
|:-------|:-------|:-------|
| 원래 요청이 승인되지 않은 경우 마이그레이션 전에 지난 30일 동안 Azure AD 그룹에 가입하기 위한 요청을 다시 요청해야 합니다. | 최종 사용자 고객은 마이그레이션 전 지난 30일 동안 해당 요청이 승인되지 않은 경우 액세스 패널을 사용하여 Azure AD 그룹에 가입하기 위한 요청을 다시 제출해야 합니다. |  최종 사용자: <ol><li>액세스 [패널로 이동합니다.](https://account.activedirectory.windowsazure.com/r#/joinGroups)</li><li>마이그레이션 30일 전에 구성원 승인이 보류된 Azure AD 그룹을 찾아야 합니다.</li><li>Azure AD 그룹에 다시 참가를 요청합니다.</li></ol> 마이그레이션 후 다시 요청되지 않는 한 마이그레이션을 승인할 수 없습니다. |
||||

## <a name="custom-dns-updates"></a>사용자 지정 DNS 업데이트
**다음에 적용됩니다.**  자체 DNS 영역 관리

| Step(s) | 설명 | 영향 |
|:------|:-------|:-------|
| 서비스 끝점에 대한 Office 365 DNS 서비스를 업데이트합니다. | 도이치클라드 Microsoft 클라우드를 지점으로 하는 고객 관리 DNS 항목을 업데이트하여 글로벌 서비스 끝점을 Office 365 합니다. DNS [구성의](https://admin.microsoft.com/Adminportal/Home#/Domains) Microsoft 365 관리 센터 도메인을 참조하고 변경 내용을 적용합니다. | 이렇게 하지 못하면 서비스 또는 소프트웨어 클라이언트가 실패할 수 있습니다. |
||||

## <a name="third-party-services"></a>타사 서비스
**다음에 적용됩니다.** Office 365 서비스 끝점에 타사 서비스를 사용하는 고객

| Step(s) | 설명 | 영향 |
|:-------|:-------|:-------|
| Office 365 끝점에 대한 파트너 및 타사 서비스를 업데이트합니다. | <ul><li>독일을 지점으로 하는 타사 서비스 및 Office 365 서비스 끝점을 Office 365 업데이트해야 합니다. 예: 공급업체 및 파트너에 따라 응용 프로그램의 갤러리 앱 버전(사용 가능한 경우)을 다시 등록합니다. </li><li>에서 으로 Graph 사용자 지정 응용 프로그램을 `graph.microsoft.de` `graph.microsoft.com` 지정합니다. 변경된 끝점이 있는 다른 API도 활용하는 경우 업데이트해야 합니다. </li><li>모든 비제한 엔터프라이즈 응용 프로그램을 변경하여 전 세계 끝점으로 리디렉션합니다. </li></ul>| 필수 작업입니다. 이렇게 하지 못하면 서비스 또는 소프트웨어 클라이언트가 실패할 수 있습니다. |
||||
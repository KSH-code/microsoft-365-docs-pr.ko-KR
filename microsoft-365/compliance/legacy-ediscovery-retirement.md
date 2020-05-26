---
title: eDiscovery 도구의 사용 중지
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection: M365-security-compliance
description: Exchange Online의 원본 위치 eDiscovery 및 원본 위치 유지 및 해당 PowerShell cmdlet은 2020의 처음 절반에서 만료 됩니다. 또한 검색 사서함 cmdlet 및 Advanced eDiscovery v 1.0은 동일한 기간 내에 폐기 됩니다.
ms.openlocfilehash: 547b58bebf4ade04bc9c1992ed7f0f518924341f
ms.sourcegitcommit: 40ec697e27b6c9a78f2b679c6f5a8875dacde943
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/23/2020
ms.locfileid: "44351919"
---
# <a name="retirement-of-legacy-ediscovery-tools"></a>eDiscovery 도구의 사용 중지

> [!IMPORTANT]
> Microsoft는 공개 상태 상황을 평가 했으며이로 인해 고객에 게 미치는 영향을 이해 하 고 있습니다. 강력 하 게 파트너와 협력 하 고 글로벌 시민을 맡고 싶습니다. 이 문서에 설명 된 레거시 eDiscovery 도구에 대 한 예약 된 만료는 3 개월까지 지연 하 게 됩니다. **업데이트 된 만료 날짜는 아래에 반영 됩니다.**

Microsoft는 지난 몇 년 동안 Exchange Online에서 전자 메일 콘텐츠를 검색, 미리 보기 및 내보내는 데 사용할 수 있는 eDiscovery 도구를 제공 하 고 있습니다. 그러나 이러한 도구는 더 이상 SharePoint Online 및 Microsoft 365 그룹과 같은 다른 Microsoft 365 서비스에서 비 Exchange 콘텐츠를 검색 하는 효율적인 방법을 제공 하지 않습니다. 이 문제를 해결 하기 위해 Microsoft는 다양 한 Microsoft 365 콘텐츠를 검색 하는 데 도움이 되는 기타 eDiscovery 도구를 제공 합니다. 그리고 [Microsoft 365 준수 센터](https://compliance.microsoft.com)의 최신 eDiscovery 기능을 최신 및 강력 하 게 통합 하는 것이 어려운 작업입니다. 이를 통해 조직은 Exchange Online을 비롯 한 다양 한 Microsoft 365 서비스에서 콘텐츠에 대 한 법적, 내부 및 기타 문서 요청에 응답할 수 있습니다.

Microsoft 365 준수 센터에서 새롭게 향상 된 eDiscovery 기능을 사용 하는 경우 Exchange Online 및 Microsoft 365에서 전자 메일 콘텐츠를 검색 하는 데 관련 된 다음과 같은 eDiscovery 관련 기능과 기능이 더 이상 제공 되지 않습니다.

- Exchange 관리 센터의 원본 [위치 eDiscovery](https://docs.microsoft.com/exchange/security-and-compliance/in-place-ediscovery/in-place-ediscovery) 및 [현재 위치 유지](https://docs.microsoft.com/exchange/security-and-compliance/create-or-remove-in-place-holds)

- 원본 위치 eDiscovery 및 원본 위치 유지를 지 원하는 Exchange Online PowerShell cmdlet (이러한 cmdlet은*new-mailboxsearch* cmdlet으로 집합적으로 식별 됨) 여기에는 다음 cmdlet이 포함 됩니다.

  - [New-mailboxsearch](https://docs.microsoft.com/powershell/module/exchange/new-mailboxsearch)

  - [시작-New-mailboxsearch](https://docs.microsoft.com/powershell/module/exchange/start-mailboxsearch)

  - [New-mailboxsearch](https://docs.microsoft.com/powershell/module/exchange/stop-mailboxsearch)

  - [New-mailboxsearch](https://docs.microsoft.com/powershell/module/exchange/set-mailboxsearch)

   > [!NOTE]
   > [New-mailboxsearch](https://docs.microsoft.com/powershell/module/exchange/get-mailboxsearch) 및 [new-mailboxsearch](https://docs.microsoft.com/powershell/module/exchange/remove-mailboxsearch) cmdlet은 기타 * * * *-new-mailboxsearch * * * cmdlet이 사용 중지 된 후에 사용할 수 있으므로 다른 eDiscovery 및 유지 도구로 전환할 때 사용할 수 있습니다. 그러나 아래에 언급 된 특정 날짜 이후에는 Microsoft 지원에서 이러한 두 cmdlet을 더 이상 지원 하지 않습니다.

- Exchange Online PowerShell의 [검색 사서함](https://docs.microsoft.com/powershell/module/exchange/search-mailbox?view=exchange-ps) cmdlet

- Exchange 웹 서비스 API에서 다음 작업을 수행 합니다.

   - [GetSearchableMailboxes](https://docs.microsoft.com/exchange/client-developer/web-service-reference/getsearchablemailboxes-operation)

   - [SearchMailboxes](https://docs.microsoft.com/exchange/client-developer/web-service-reference/searchmailboxes-operation)
   
   - [SetHoldOnMailboxes](https://docs.microsoft.com/exchange/client-developer/web-service-reference/setholdonmailboxes-operation)

   - [GetHoldOnMailboxes](https://docs.microsoft.com/exchange/client-developer/web-service-reference/getholdonmailboxes-operation)

- Office [365 Advanced ediscovery v 1.0](office-365-advanced-ediscovery.md)-Office 365 보안 & 준수 센터의 핵심 ediscovery 사례를 통해 액세스 되는 고급 ediscovery의 첫 번째 버전입니다. Advanced eDiscovery v 1.0의 만료는 핵심 eDiscovery 사례를 만들고 관리 하는 기능에는 영향을 주지 않습니다.

> [!NOTE]
> 폐기 중인 eDiscovery 기능은 클라우드 기반 버전의 Microsoft 365 및 Office 365에만 적용 됩니다. 온-프레미스 버전의 Exchange 및 SharePoint에서 eDiscovery 기능은 계속 해 서 지원 됩니다.

이 문서의 다음 섹션에서는 폐기 되는 각 기능에 대 한 지침을 제공 합니다. 이 정보는 만료 된 도구 대신 사용할 수 있는 timeline 및 대체 도구를 포함 합니다.

## <a name="in-place-ediscovery-and-in-place-holds-in-the-exchange-admin-center"></a>Exchange 관리 센터의 원본 위치 eDiscovery 및 현재 위치 유지 

원래 알림 2017 년 7 월 1 일에는 EAC (Exchange 관리 센터)의 원본 위치 eDiscovery & 보류 기능이 폐기 됩니다. EAC의 원본 위치 eDiscovery & 보류 페이지를 사용 하 여 Exchange Online에서 콘텐츠를 검색 하 고, 유지 하 고, 내보낼 수 있습니다. 또한 원본 위치 eDiscovery를 사용 하면 검색 결과를 검색 사서함으로 복사 하 여 사용자 또는 다른 eDiscovery 관리자가 콘텐츠를 검토 하 고 법적, 규정 및 공개 요청에 사용할 수 있도록 할 수 있습니다.

이러한 모든 기능 (검색 결과를 검색 사서함으로 복사 하는 것을 제외)은 이제 [microsoft 365 준수 센터](https://docs.microsoft.com/microsoft-365/compliance/microsoft-365-compliance-center) 의 콘텐츠 검색, EDiscovery 및 고급 eDiscovery 도구 (microsoft 365 서비스에 대 한 향상 된 기능, 안정성 및 지원)에서 제공 되므로 가능한 한 빨리 이러한 도구를 사용 하는 것이 좋습니다. 아래 표에는 이러한 다른 eDiscovery 도구로 전환할 때 사용할 수 있는 도구와 원본 위치 eDiscovery 및 원본 위치 유지를 사용 하지 않는 도구가 나와 있습니다.

### <a name="scope-of-affected-organizations"></a>영향을 받는 조직의 범위

- Office 365 및 Microsoft 365 Enterprise 조직

- Office 365 및 Microsoft 365 교육 기관

- Office 365 및 Microsoft 365 정부 기관 여기에는 GCC, GCC High 및 DoD가 포함 됩니다.

- Office 365 Germany

### <a name="timeline-for-retirement"></a>만료에 대 한 시간 표시 막대

- 2020 년 7 월 1 일: 새 검색 및 보류를 만들 수는 없지만 기존 검색을 계속 실행 하 고 편집 하 고 삭제할 수 있습니다. Microsoft Support는 EAC에서 더 이상 원본 위치 eDiscovery & 보존 되지 않습니다.

- 2020: EAC의 원본 위치 eDiscovery & 보존 기능은 읽기 전용 모드에 저장 됩니다. 즉, 기존 검색 및 보류만 제거할 수 있습니다.

### <a name="alternative-tools"></a>대체 도구

다음 표에서는 폐기 중인 기존 기능을 대체 하는 데 사용할 수 있는 기타 도구에 대해 설명 합니다.

<table>
<thead>
<tr class="header">
<th><strong>기능</strong></th>
<th><strong>대체 도구</strong></th>
<th><strong>Comments</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>법적 목적을 위한 검색, 내보내기 및 보관</td>
<td>Microsoft 365 준수 센터의 핵심 eDiscovery 사례 </td>
<td><p>핵심 eDiscovery 사례의 기능을 사용 하면 원본 위치 eDiscovery 및 원본 위치 유지에 대 한 기능 패리티가 제공 됩니다. 여기에는 다음이 포함됩니다.</p>
<ul>
<li>
<p>수백만 위치로 검색 확장</p>
</li>
<li>
<p>콘텐츠 검색, 내보내기 및 보류를 위한 더 높은 안정성</p>
</li>
<li>
<p>Office 365 응용 프로그램에 저장 된 Exchange Online, SharePoint Online, 비즈니스용 OneDrive, 비즈니스용 Skype, Microsoft 팀, Yammer 그룹, Microsoft 365 그룹 및 기타 콘텐츠에 대 한 콘텐츠 검색</p></li></ul>
<p>자세한 내용은 <a href="https://docs.microsoft.com/microsoft-365/compliance/manage-legal-investigations">Office 365에서 법적 조사 관리</a>를 참조 하세요.</td>
</tr>
<tr class="even">
<td>보존을 위해 보류</td>
<td>Microsoft 365 준수 센터의 보존 정책</td>
<td><p>보존 정책을 사용 하 여 콘텐츠를 보존 하 고 원할 경우 보존 기간이 만료 된 후에 삭제할 수 있습니다. 기타 기능은 다음과 같습니다.</p>
<ul>
<li>
<p>전체 조직에 정책 적용 </p>
</li><li>
<p>Exchange Online, SharePoint Online, 비즈니스용 OneDrive, 비즈니스용 Skype, Microsoft 팀 및 Office 365 그룹 등의 특정 콘텐츠 위치에 정책 적용</p></li>
<li>
<p>특정 사용자에 게 정책 적용</p></li></ul>
<p>자세한 내용은 <a href="https://docs.microsoft.com/microsoft-365/compliance/retention-policies">보존 정책 개요</a>를 참조 하세요.</td>
</tr>
<tr class="odd">
<td>검토를 위해 전자 메일 검색 결과를 검색 사서함으로 복사</td><td>Advanced eDiscovery v 2.0에서 집합 검토</td>
<td><p>Microsoft 365의 콘텐츠를 검토 하는 것이 훨씬 쉬워졌습니다. 검토 집합에는 다음을 비롯 하 여 검토에 필요한 시간 및 데이터를 줄이는 데 도움이 되는 다양 한 기능이 있습니다.</p>
<ul>
<li><p>빠른 검색 쿼리를 수행 하 고 검토 집합의 콘텐츠 필터링</p></li>
<li><p>검토 집합의 콘텐츠를 분석 합니다. 여기에는 전자 메일 스레딩, 거의 중복 검색, 테마 분석 및 예측 코딩이 포함 됩니다.</p></li>
<li><p>검토 집합에서 문서 태그 지정</p></li>
<li><p>변호사 클라이언트 권한 콘텐츠를 식별 하는 데 도움이 되는 태그 지정 제안</p></li></ul>
<p>자세한 내용은 M<a href="https://docs.microsoft.com/microsoft-365/compliance/overview-ediscovery-20">icrosoft 365의 고급 eDiscovery 솔루션 개요</a>를 참조하세요.</p>
<p>
<p>또는 검색 결과를 PST 파일로 내보낸 다음 Microsoft 365 가져오기 서비스를 사용 하 여 Pst를 검색 사서함으로 가져올 수 있습니다. 단계별 지침은 <a href="https://docs.microsoft.com/microsoft-365/compliance/use-network-upload-to-import-pst-files">네트워크 업로드를 사용 하 여 PST 파일을 Office 365에 가져오기</a>를 참조 하세요.
</tr>
<tr class=even>
  <td>한 사서함에서 다른 사서함으로 메시지 복사</td>
  <td><a href="https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-permissions-for-recipients">사서함에 사용 권한 할당</a></td>
  <td>사용자에 게 다른 사용자의 전자 메일에 대 한 액세스 권한을 부여 하려면 (예: 직원이 조직을 떠나는 경우 다른 사용자에 게 이전 직원의 전자 메일에 액세스할 수 있는 경우) 해당 사용자에 게 이전 직원의 사서함에 대 한 액세스 권한을 할당 하는 것이 좋습니다. 따라서 사서함 항목을 다른 사용자 사서함 또는 공유 사서함으로 복사 하는 대신 사용자에 게 원본 사서함에 액세스 하기 위한 권한을 할당 하기만 하면 됩니다.</td>
  
  </tr>
<tr class="odd">
<td>복구 가능한 항목 폴더에서 항목 복원</td>
  <td><a href="https://docs.microsoft.com/powershell/module/exchange/Restore-RecoverableItems">복원-RecoverableItems</td>
  <td>항목에 대해 삭제 된 항목 보존 기간이 만료 되지 않은 경우 사서함에서 영구적으로 삭제 된 항목 ( <i>일시 삭제</i> 된 항목으로도 알려짐)을 복원할 수 있습니다. 자세한 내용은 <a href="https://docs.microsoft.com/Exchange/security-and-compliance/recoverable-items-folder/recoverable-items-folder">Exchange Online의 복구 가능한 항목 폴더</a>를 참조 하세요.</td>
</tr>
</tbody>
</table>

### <a name="faqs-about-in-place-ediscovery-and-in-place-holds"></a>원본 위치 eDiscovery 및 현재 위치 유지 관련 Faq

**EAC의 원본 위치 eDiscovery & 보존 기능을 사용 하 여 변호사가 검토를 위해 검색 사서함에 검색할 검색 결과를 복사 합니다. 현재 어떤 옵션을 사용할 수 있나요?**

이 기능은 오늘 두 가지 방법으로 복제할 수 있습니다. 첫 번째는 [Advanced eDiscovery v 2.0에서 검토 집합](https://docs.microsoft.com/microsoft-365/compliance/view-documents-in-review-set)을 사용 하는 것입니다. 검토 집합에는 문서, 태그 지정, 전자 메일 스레딩, 중복 그룹화, 테마 분석 및 예측 코딩 같은 전통적인 검토 도구에 표시 되는 것과 동일한 기능이 많이 있습니다. 검토를 위해 검색 사서함을 계속 사용 하려는 경우 두 번째 옵션은 검색 결과를 PST 파일로 내보낸 다음 Microsoft 준수 센터의 [pst 가져오기 기능](use-network-upload-to-import-pst-files.md) 을 사용 하 여 해당 pst 파일을 검색 사서함으로 가져오는 것입니다.

**EDiscovery 관리자가 새 도구를 사용 하 여 검색할 수 있는 콘텐츠 위치 (예: 사서함 또는 사이트)를 제어 하려면 어떻게 해야 합니까?**

Microsoft 365 준수 센터에서는 또한 [준수 경계](set-up-compliance-boundaries.md) 를 사용 하 여 eDiscovery 관리자가 검색할 수 있는 콘텐츠 위치를 제어 합니다. 규정 준수 경계는 지리적 boarders을 준수 하기 위해 필요한 기관 경계 또는 국내 기업에 머물러 있어야 하는 정부 기관에서 유용 합니다.

**현재 검색 및 보류를 Microsoft 365 준수 센터로 어떻게 이동할 수 있나요?**

PowerShell을 사용 하 여 원본 위치 eDiscovery 검색을 마이그레이션하고 EAC에서 보류 상태로 유지할 수 있습니다. 자세한 내용은 [EAC에서 검색 및 보류에서 Microsoft 365 준수 센터로 마이그레이션을](https://go.microsoft.com/fwlink/?linkid=2114224)참조 하십시오.

## <a name="-mailboxsearch-cmdlets"></a>\*-New-mailboxsearch cmdlet

Exchange 관리 센터에서 2017 년 7 월 1 일에 발표 된 원래 공지와 마찬가지로, 원본 위치 eDiscovery & 보류 기능 및 해당 하는 New-mailboxsearch cmdlet을 ** \* 사용** 중지 합니다. 이러한 cmdlet은 사용자에 게 법적, 규정 및 공개 요청에 대 한 사서함 콘텐츠를 검색, 유지 및 내보낼 수 있는 기능을 제공 합니다.

이제 이러한 기능을 [<span class="underline">Microsoft 365 준수 센터</span>](https://docs.microsoft.com/microsoft-365/compliance/microsoft-365-compliance-center) 및 Office 365 Security & 준수 센터 PowerShell에서 향상 된 성능 및 확장성으로 사용할 수 있기 때문에 이러한 향상 된 cmdlet을 사용 해야 합니다. 이러한 cmdlet에는 [<span class="underline"> \* -remove-compliancecase</span>](https://docs.microsoft.com/powershell/module/exchange/get-compliancecase), [<span class="underline"> \* -ComplianceSearch</span>](https://docs.microsoft.com/powershell/module/exchange/get-compliancesearch), [<span class="underline"> \* -new-caseholdpolicy</span>](https://docs.microsoft.com/powershell/module/exchange/get-caseholdpolicy), [<span class="underline"> \* -new-caseholdrule</span>](https://docs.microsoft.com/powershell/module/exchange/get-caseholdrule)및 [<span class="underline"> \* -new-compliancesearchaction</span>](https://docs.microsoft.com/powershell/module/exchange/get-compliancesearchaction)가 포함 됩니다.

### <a name="scope-of-affected-organizations"></a>영향을 받는 조직의 범위

- Office 365 및 Microsoft 365 Enterprise 조직

- Office 365 및 Microsoft 365 교육 기관

- Office 365 및 Microsoft 365 정부 기관 여기에는 GCC, GCC High 및 DoD가 포함 됩니다.

- Office 365 Germany

### <a name="timeline"></a>타임라인

- 7 월 1 일, 2020 **: 새 원본** 위치 eDiscovery 검색 및 원본 위치 유지를 만들 수는 없지만, cmdlet을 사용 하 여 기존 검색을 실행, 편집 및 삭제 하 고 사용자의 위험에도 영향을 받을 수 있습니다. Microsoft Support는 이러한 유형의 검색 및 보존에 대 한 지원을 더 이상 제공 하지 않습니다.

- 2020 년 10 월 1 일: 앞에서 설명한 것 처럼 EAC의 원본 위치 eDiscovery &는 읽기 전용 모드에 저장 됩니다. 이는 또한 **new-mailboxsearch**, **new-mailboxsearch**또는 **new-mailboxsearch** cmdlet을 사용할 수 없음을 의미 합니다. 기존 검색 및 보류만 가져오고 제거할 수 있습니다.

### <a name="alternative-tools"></a>대체 도구

다음 표에서는 폐기 중인 기존 기능을 대체 하는 데 사용할 수 있는 기타 도구에 대해 설명 합니다.

<table>
<thead>
<tr class="header">
<th><strong>기능</strong></th>
<th><strong>대체 도구</strong></th>
<th><strong>Comments</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>검색 및 내보내기</td>
<td><p><a href="https://docs.microsoft.com/powershell/module/exchange/get-compliancesearch"><span class="underline">*-ComplianceSearch</span></a></p>
<p><a href="https://docs.microsoft.com/powershell/module/exchange/get-compliancesearchaction"><span class="underline">*-New-compliancesearchaction</span></a></p>
<p><a href="https://docs.microsoft.com/powershell/module/exchange/get-compliancecase"><span class="underline">*-Remove-compliancecase</span></a></p>
<p> </p></td>
<td><p>ComplianceSearch 및 New-compliancesearchaction cmdlet은 공동 작업을 통해 콘텐츠를 검색 하 고 내보내는 데 도움이 됩니다. <strong>새 검색</strong>을 만들고 <strong>ComplianceSearch</strong> <strong>cmdlet을 사용</strong>하 여 검색 예측을 볼 수 있습니다. 그런 다음 <strong>new-compliancesearchaction</strong> cmdlet을 사용 하 여 검색 결과를 내보낼 수 있습니다. 이러한 검색 결과를 로컬 컴퓨터에 다운로드 하려면 Microsoft 365 준수 센터에서 코어 eDiscovery 도구를 사용 해야 합니다.</p>
<p>
<p><strong>참고:</strong> 이러한 cmdlet을 사용 하 여 코어 eDiscovery 사례와 관련 되지 않은 검색을 만드는 경우 이러한 검색은 Microsoft 365 준수 센터의 <strong>콘텐츠 검색</strong> 페이지에 있습니다.</p></td>
</tr>
<tr class="even">
<td>사서함의 콘텐츠를 보관 합니다.</td>
<td><p><a href="https://docs.microsoft.com/powershell/module/exchange/get-caseholdpolicy"><span class="underline">*-New-caseholdpolicy</span></a></p>
<p><a href="https://docs.microsoft.com/powershell/module/exchange/get-caseholdrule"><span class="underline">*-New-caseholdrule</span></a></p>
<p><a href="https://docs.microsoft.com/powershell/module/exchange/get-compliancecase"><span class="underline">*-Remove-compliancecase</span></a></p>
<p> </p></td>
<td><p>Microsoft 365 준수 센터의 보류는 Remove-compliancecase와 연결 되어 있어야 합니다. 먼저 준수 사례를 만든 다음 New-caseholdpolicy 및 New-caseholdrule를 만듭니다.</p>
<p><strong>참고:</strong> 만들기 New-caseholdrule 없이 New-caseholdpolicy를 만들면 New-caseholdrule가 만들어지고 New-caseholdpolicy에 연결 될 때까지 보류가 작동 하지 않습니다. 자세한 내용은 cmdlet 설명서를 참조 하세요.</p></td>
</tr>
<tr class="odd">
<td>검색 결과를 검색 사서함으로 복사</td>
<td>없음</td>
<td>이 기능은 모든 Microsoft 365 서비스에 대 한 액세스를 제공 하지 않으므로 직접 대체할 수 없습니다. 다른 해결 방법에 대 한 다음 FAQ를 참조 하세요.</td>
</tr>
  <tr class=even>
  <td>한 사서함에서 다른 사서함으로 메시지 복사</td>
  <td><a href="https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-permissions-for-recipients">사서함에 사용 권한 할당</a></td>
  <td>사용자에 게 다른 사용자의 전자 메일에 대 한 액세스 권한을 부여 하려면 (예: 직원이 조직을 떠나는 경우 다른 사용자에 게 이전 직원의 전자 메일에 액세스할 수 있는 경우) 해당 사용자에 게 이전 직원의 사서함에 대 한 액세스 권한을 할당 하는 것이 좋습니다. 따라서 사서함 항목을 다른 사용자 사서함 또는 공유 사서함으로 복사 하는 대신 사용자에 게 원본 사서함에 액세스 하기 위한 권한을 할당 하기만 하면 됩니다.</td>
  
  </tr>

</tbody>
</table>

### <a name="faqs-about--mailboxsearch-cmdlets"></a>Faq ***-new-mailboxsearch** cmdlet

**복사 검색을 사용 하 여 다른 eDiscovery 및 법적 조사를 위해 전자 메일 메시지 또는 인스턴트 메시지를 내보냅니다. 이러한 cmdlet이 만료 된 후에는 어떤 다른 옵션을 사용할 수 있나요?**

[<span class="underline">Microsoft Graph api</span>](https://developer.microsoft.com/en-us/graph) 는 분석을 위해 데이터를 추출 하는 여러 가지 방법과 ** \* new-mailboxsearch** cmdlet 보다 탄력적이 고 확장성이 뛰어난 기타 목적을 제공 합니다.

**내 검색 및 보류를 Microsoft 365 준수 센터로 마이그레이션하려면 어떻게 해야 합니까?**

PowerShell 스크립트를 사용 하 여 원본 위치 eDiscovery 검색 및 보류를 Exchange 관리 센터에서 마이그레이션할 수 있습니다. 자세한 내용은 [마이그레이션 레거시 eDiscovery 검색 및 보류를 Microsoft 365 준수 센터로 마이그레이션을](migrate-legacy-eDiscovery-searches-and-holds.md)참조 하세요.

**Cmdlet이 만료 된 후에도 검색을 계속 해 서 제거 하거나 검색할 수 있습니까?**

예, 검색을 만들고 수정 하는 기능을 제거 하는 경우에도 **new-mailboxsearch** 및 **new-mailboxsearch** 를 계속 사용할 수 있습니다. 그러나 만료 날짜가 되 고 Microsoft 지원에서 더 이상 지원을 제공할 수 없는 경우 이러한 cmdlet의 사용은 사용자의 책임을 받습니다.

## <a name="search-mailbox-cmdlet"></a>검색-사서함 cmdlet

Exchange Online PowerShell의 **검색 사서함** cmdlet은 처음에 2018에서 시작 하는 cmdlet 출력에 경고를 발표 했을 때까지 중지 됩니다. **검색 사서함** cmdlet은 원래 사용자의 사서함을 검색 하 고 악성 콘텐츠를 제거 하는 데 사용 되었습니다. Office 365 Security & 준수 센터 PowerShell에서 **ComplianceSearch** 및 **new-compliancesearchaction** cmdlet을 사용 하 여 콘텐츠를 검색 하 고 제거 하는 것이 좋습니다. 기본 제공 되는 보안 환경에서 [<span class="underline">microsoft 365 보안 기능은</span>](https://docs.microsoft.com/microsoft-365/security/) 전자 메일 및 기타 다양 한 Microsoft 서비스에 대 한 강력한 위협 방지 기능을 제공 합니다.

### <a name="scope-of-affected-organizations"></a>영향을 받는 조직의 범위

- Office 365 및 Microsoft 365 Enterprise 조직

- Office 365 및 Microsoft 365 교육 기관

- Office 365 및 Microsoft 365 정부 기관 여기에는 GCC, GCC High 및 DoD가 포함 됩니다.

- Office 365 Germany

### <a name="timeline"></a>타임라인

-  2020 년 7 월 1 일: **검색 사서함** cmdlet을 더 이상 사용할 수 없으며 Microsoft Support에서 더 이상 지원을 제공 하지 않습니다.

### <a name="alternative-tools"></a>대체 도구

다음 표에서는 폐기 중인 기존 기능을 대체 하는 데 사용할 수 있는 기타 도구에 대해 설명 합니다.

<table>
<thead>
<tr class="header">
<th><strong>기능</strong></th>
<th><strong>대체 도구</strong></th>
<th><strong>Comments</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>사서함 검색</td>
<td><p><a href="https://docs.microsoft.com/powershell/module/exchange/get-compliancesearch?view=exchange-ps"><span class="underline">*-ComplianceSearch</span></a></p>
<p><a href="https://docs.microsoft.com/powershell/module/exchange/get-compliancesearchaction?view=exchange-ps"><span class="underline">*-New-compliancesearchaction</span></a></p>
<p></a></p></td>
<td><p>ComplianceSearch 및 New-compliancesearchaction cmdlet은 공동 작업을 통해 콘텐츠를 검색 하 고 내보내는 데 도움이 됩니다. <strong>새 검색</strong>을 만들고 <strong>ComplianceSearch</strong> <strong>cmdlet을 사용</strong>하 여 검색 예측을 볼 수 있습니다. 그런 다음 <strong>new-compliancesearchaction-Export</strong> 명령을 사용 하 여 검색 결과를 내보낼 수 있습니다. 이러한 검색 결과를 로컬 컴퓨터에 다운로드 하려면 Microsoft 365 준수 센터에서 코어 eDiscovery 도구를 사용 해야 합니다.</p></p>
</td>
</tr>
<tr class="even">
<td>사서함에서 메시지 제거</td>
<td><p><a href="https://docs.microsoft.com/powershell/module/exchange/get-compliancesearch?view=exchange-ps"><span class="underline">*-ComplianceSearch</span></a></p>
<p><a href="https://docs.microsoft.com/powershell/module/exchange/get-compliancesearchaction?view=exchange-ps"><span class="underline">*-New-compliancesearchaction</span></a></p>
<p></p></td>
<td><p>ComplianceSearch 및 New-compliancesearchaction cmdlet은 상호 작용 하 여 콘텐츠를 검색 하 고 제거 하는 데 도움이 됩니다. <strong>ComplianceSearch</strong> 및 <strong>ComplianceSearch</strong> cmdlet을 사용 하 여 검색을 만들고 실행 한 후에는 <strong>new-compliancesearchaction-PurgeType</strong> 명령을 통해 콘텐츠를 제거할 수 있습니다. 자세한 내용은 <a href="https://docs.microsoft.com/microsoft-365/compliance/search-for-and-delete-messages-in-your-organization"><span class="underline">메시지 검색 및 삭제</span></a>를 참조 하세요.</p>
</td>
</tr>
<tr class="odd">
<td>사서함에서 대량 전자 메일 삭제</td>
<td><p><a href="https://docs.microsoft.com/microsoft-365/compliance/set-up-an-archive-and-deletion-policy-for-mailboxes?view=o365-worldwide"><span class="underline">사서함에 대한 보관 및 삭제 정책 설정</span></a></p>
<p></p></td>
<td><p>관리자는 항목을 사용자의 보관 사서함으로 자동으로 이동 하 고 사서함에서 항목을 자동으로 삭제 하는 보관 및 삭제 정책을 만들 수 있습니다.</p>
</td>
</tr>
<tr class="even">
<td>검색 결과를 검색 사서함으로 복사</td>
<td> </td>
<td>이 기능은 모든 Microsoft 365 서비스에 대 한 액세스를 제공 하지 않으므로 직접 대체할 수 없습니다. 대체 해결 방법은 <strong>*-new-mailboxsearch cmdlet</strong> 섹션의 faq를 참조 하세요. </td>
</tr>
</tbody>
</table>

## <a name="exchange-web-services-api-operations"></a>Exchange 웹 서비스 API 작업

Exchange 웹 서비스 API에서 이러한 작업은 Exchange 관리 센터의 원본 위치 eDiscovery & 보류 기능 및 Exchange Online PowerShell의 해당 ** \* new-mailboxsearch** cmdlet에서 사용 됩니다. 다른 레거시 eDiscovery 도구를 중지 하는 경우에도 회수 됩니다.

### <a name="scope-of-affected-organizations"></a>영향을 받는 조직의 범위

- Office 365 및 Microsoft 365 Enterprise 조직

- Office 365 및 Microsoft 365 교육 기관

- Office 365 및 Microsoft 365 정부 기관 여기에는 GCC, GCC High 및 DoD가 포함 됩니다.

- Office 365 Germany

### <a name="timeline"></a>타임라인

- 2020 년 7 월 1 일: GetSearchableMailboxes, Search우편함, SetHoldOnMailboxes 및 GetHoldOnMailboxes 작업을 더 이상 사용할 수 없으며 Microsoft Support에서 더 이상 지원을 제공 하지 않습니다.

## <a name="advanced-ediscovery-v10"></a>Advanced eDiscovery v 1.0

Advanced ediscovery **로 전환을**클릭 하 여 코어 ediscovery 사례에서 사용할 수 있는 advanced ediscovery 버전의 advanced ediscovery v 1.0이 만료 되 고 있습니다. 해당 기능은 Microsoft 365 준수 센터의 새로운 [고급 eDiscovery 솔루션](https://aka.ms/edisco) 으로 대체 되었습니다.

조직에서 Advanced eDiscovery v 1.0을 사용 하 고 있는지 확인 하려면

1. [Office 365 Security & 준수 센터로](https://protection.office.com)이동 합니다.

2. 보안 & 준수 센터의 왼쪽 탐색 창에서 **ediscovery > ediscovery**를 클릭 하 고 코어 eDiscovery 사례를 엽니다.

3. **고급 ediscovery로 전환** 단추가 표시 되 면이 단추를 클릭 하면 사용 중지 되 고 있는 1.0 버전의 고급 ediscovery로 이동 합니다. 핵심 eDiscovery에서 사례를 만들고 관리 하는 기능은 영향을 받지 않습니다. Advanced eDiscovery v 1.0에서 사례 데이터를 추가 및 분석 하는 기능 ( **Advanced ediscovery로 전환을**클릭 하는 것)은 폐기 되 고 있습니다.

Microsoft 365 ( *Advanced eDiscovery v 2.0*이 라고도 함)의 새로운 고급 ediscovery 솔루션은 원래 솔루션의 모든 기능을 제공 하지만, 해당 콘텐츠를 수집한 다음 custodian가 fast search 쿼리, 태그 지정 및 분석 기능을 활용 하 여 관련 문서를 cull 수 있도록 하는 검토 집합에 추가 하는 365 방법에 대해 설명 합니다. 이제 고급 eDiscovery에는 Microsoft 및 Microsoft 이외의 파일 형식에 대 한 향상 된 처리 및 기본 뷰어가 포함 되어 있으므로 전체 파일 형식 목록과 지원 [되는 메타](https://docs.microsoft.com/microsoft-365/compliance/document-metadata-fields-in-advanced-ediscovery)데이터 [필드가 여기에](https://docs.microsoft.com/microsoft-365/compliance/supported-filetypes-ediscovery20) 있습니다. 또한 새로운 고급 eDiscovery 솔루션은 다른 서비스의 콘텐츠에 보류를 적용 하 고, 보류를 사용자에 게 알리고, custodian 응답을 고급 eDiscovery 사례 내에서 추적할 수 있도록 하는 강력한 custodian 유지 관리 기능을 제공 합니다.

Advanced eDiscovery v 2.0에 액세스 하려면 다음을 수행 합니다.

1. [Microsoft 365 준수 센터로](https://compliance.microsoft.com)이동 합니다.

2. Microsoft 365 준수 센터의 왼쪽 탐색 창에서 **모두 표시**를 클릭 한 다음 **eDiscovery > 고급**을 클릭 합니다.

지금은 eDiscovery 워크플로를 새 고급 eDiscovery 기능으로 전환 하기 시작 하는 것이 좋습니다. 기존 사례에서는 여전히 고급 eDiscovery v 1.0에 액세스할 수 있지만 Microsoft Support는 2020 년 10 월 1 일 이후에는 지원을 제공 하지 않습니다. 자세한 내용은 다음 시간 표시 막대를 참조 하세요.

### <a name="scope-of-affected-organizations"></a>영향을 받는 조직의 범위

- Office 365 및 Microsoft 365 Enterprise 조직

- Office 365 및 Microsoft 365 교육 기관

- Office 365 Germany

### <a name="timeline"></a>타임라인

- 2020 년 7 월 1 일: 새 고급 eDiscovery v 1.0 사례를 만들 수 없습니다.

- 2020 년 10 월 1 일: 모든 경우에 새 데이터 (고급 eDiscovery에 대 한 검색 결과 준비)를 추가할 수 없습니다. 기존 사례에서 데이터 작업을 계속 수행할 수 있습니다. Microsoft Support에서는 더 이상 지원을 제공 하지 않습니다. 

### <a name="alternative-tools"></a>대체 도구

Microsoft 365 준수 센터의 [고급 eDiscovery 솔루션](https://docs.microsoft.com/microsoft-365/compliance/overview-ediscovery-20) 입니다.
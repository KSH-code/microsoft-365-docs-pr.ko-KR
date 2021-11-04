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
ms.localizationpriority: medium
search.appverid:
- MET150
ms.collection: M365-security-compliance
ms.custom: admindeeplinkCOMPLIANCE
description: In-Place eDiscovery 및 In-Place 보류(및 해당 PowerShell cmdlet)Exchange Online 2020년 상반기에는 사용 중지됩니다. 동일한 Search-Mailbox 기간 내에 Advanced eDiscovery v1.0도 사용 중지됩니다.
ms.openlocfilehash: f778a31580bb908205c707c1f613f49bd6a576d1
ms.sourcegitcommit: ab5368888876d8796da7640553fc8426d040f470
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60786449"
---
# <a name="retirement-of-legacy-ediscovery-tools"></a>eDiscovery 도구의 사용 중지

> [!IMPORTANT]
> 이 문서에 설명된 레거시 eDiscovery 도구의 기능은 Microsoft 365 서비스에서 제거되거나 계속 사용할 수 있지만 더 이상 지원되지 않습니다. 사용 가능한 모든 기능은 예고 없이 제거될 수 있습니다. 이러한 레거시 도구를 계속 사용하는 경우 이 문서에 설명된 대안 중 하나 또는 Microsoft 365 규정 준수 센터 eDiscovery 도구로 마이그레이션하는 것이 있습니다.

수년 동안 Microsoft는 전자 메일 콘텐츠를 검색, 미리 보기 및 내보낼 수 있는 eDiscovery 도구를 Exchange Online. 그러나 이러한 도구는 더 이상 Exchange Online 및 Microsoft 365 SharePoint 그룹과 같은 다른 Microsoft 365 서비스에서 비영구 콘텐츠를 검색하는 효과적인 Microsoft 365 없습니다. 이를 해결하기 위해 Microsoft는 다양한 전자 메일 콘텐츠를 검색하는 데 도움이 되는 다른 eDiscovery Microsoft 365 제공합니다. 또한 현재 및 강력한 eDiscovery 기능을 에 통합하기 위해 노력해 <a href="https://go.microsoft.com/fwlink/p/?linkid=2077149" target="_blank">Microsoft 365 규정 준수 센터.</a> 이를 통해 조직은 조직을 비롯한 여러 Microsoft 365 서비스에서 콘텐츠에 대한 법적, 내부 및 기타 문서 요청에 대응할 Exchange Online.

Microsoft 365 규정 준수 센터 eDiscovery의 새로운 기능과 향상된 기능으로 인해 Exchange Online 및 2013에서 전자 메일 콘텐츠 검색과 관련된 다음과 같은 eDiscovery 관련 기능이 Exchange Online Microsoft 365.

- [Exchange](/exchange/security-and-compliance/in-place-ediscovery/in-place-ediscovery) 관리 센터의 Exchange. [](/exchange/security-and-compliance/create-or-remove-in-place-holds)

- Exchange Online 및 In-Place 보류를 지원하는 Exchange Online PowerShell cmd In-Place let입니다(이러한 cmdlet은 **-MailboxSearch* cmdlet으로 총체적으로 식별됩니다). 여기에는 다음 cmdlet이 포함됩니다.

  - [New-MailboxSearch](/powershell/module/exchange/new-mailboxsearch)

  - [Start-MailboxSearch](/powershell/module/exchange/start-mailboxsearch)

  - [Stop-MailboxSearch](/powershell/module/exchange/stop-mailboxsearch)

  - [Set-MailboxSearch](/powershell/module/exchange/set-mailboxsearch)

   > [!NOTE]
   > [Get-MailboxSearch](/powershell/module/exchange/get-mailboxsearch) 및 [Remove-MailboxSearch](/powershell/module/exchange/remove-mailboxsearch) cmdlet은 다른 ****-MailboxSearch*** cmdlet이 사용 중지된 후에 사용할 수 있으므로 다른 eDiscovery 및 유지 도구로의 전환에 도움이 될 수 있습니다. 그러나 특정 날짜(아래 참조)가 지난 후 Microsoft 지원에서 더 이상 이러한 두 cmdlet을 지원하지 않습니다.

- PowerShell에서 [검색-Exchange Online](/powershell/module/exchange/search-mailbox) cmdlet입니다.

- 웹 서비스 API의 Exchange 작업은 다음과 같습니다.

   - [GetSearchableMailboxes](/exchange/client-developer/web-service-reference/getsearchablemailboxes-operation)

   - [SearchMailboxes](/exchange/client-developer/web-service-reference/searchmailboxes-operation)
   
   - [SetHoldOnMailboxes](/exchange/client-developer/web-service-reference/setholdonmailboxes-operation)

   - [GetHoldOnMailboxes](/exchange/client-developer/web-service-reference/getholdonmailboxes-operation)

- [Office 365 Advanced eDiscovery v1.0은](./overview-ediscovery-20.md)Advanced eDiscovery Core eDiscovery 사례를 통해 액세스되는 Microsoft 365 규정 준수 센터. v1.Advanced eDiscovery 사용 중지는 핵심 eDiscovery 사례를 만들고 관리하는 능력에 영향을 끼치지 않습니다.

> [!NOTE]
> 사용 중지되는 eDiscovery 기능은 클라우드 기반 버전의 Microsoft 365 Office 365. Exchange 및 SharePoint 버전의 eDiscovery 기능은 추가 공지가 있을 때까지 계속 지원됩니다.

이 문서의 다음 섹션에서는 사용 중지되는 각 기능에 대한 지침을 제공합니다. 이 정보에는 사용 중지된 도구 대신 사용할 수 있는 타임라인 및 대체 도구가 있습니다.

## <a name="in-place-ediscovery-and-in-place-holds-in-the-exchange-admin-center"></a>In-Place 관리 In-Place eDiscovery 및 Exchange 보류 

2017년 7월 1일의 원래 공지에 따라 EAC(Exchange 관리 센터)의 In-Place eDiscovery & 보류 기능이 사용 중지됩니다. EAC의 In-Place eDiscovery & 보류 페이지에서 콘텐츠를 검색, 보류 및 내보낼 수 Exchange Online. In-Place eDiscovery를 사용하면 검색 결과를 검색 사서함에 복사하여 사용자 또는 다른 eDiscovery 관리자가 콘텐츠를 검토하고 법률, 규정 및 공용 요청에 사용할 수 있도록 할 수 있습니다.

검색 결과를 검색 사서함에 복사하는 기능을 제외한 이러한 모든 기능을 이제 콘텐츠 검색에서 사용할 수 있기 때문에 Microsoft 365 규정 준수 센터의 eDiscovery 및 Advanced eDiscovery 도구(향상된 기능, 안정성 및 광범위한 Microsoft 365 서비스에 대한 지원)를 사용하는 것이 좋습니다. [](./microsoft-365-compliance-center.md) 가능한 한 빨리 이러한 도구를 사용하게 됩니다. 이러한 다른 eDiscovery 도구로의 전환을 지원하기 위해 아래 표에는 eDiscovery 및 보류를 사용하는 대신 사용할 In-Place In-Place 나열되어 있습니다.

### <a name="scope-of-affected-organizations"></a>영향을 받는 조직의 범위

- Office 365 및 Microsoft 365 Enterprise 조직

- Office 365 및 Microsoft 365 Education 조직

- Office 365 Microsoft 365 조직; 여기에는 GCC, GCC High 및 DoD가 포함됩니다.

- Office 365 Germany

### <a name="timeline-for-retirement"></a>사용 중지 타임라인

- 2020년 7월 1일: 새 검색 및 보류를 만들 수 없지만 기존 검색을 실행, 편집 및 삭제할 수 있습니다. Microsoft 지원은 더 이상 eDiscovery In-Place eDiscovery & 보류를 지원하지 않습니다.

- 2020년 10월 1일: In-Place eDiscovery & EAC의 보류 기능이 읽기 전용 모드로 설정됩니다. 즉, 기존 검색 및 보류만 제거할 수 있습니다.

### <a name="alternative-tools"></a>대체 도구

다음 표에서는 사용 중지되는 기존 기능을 대체하는 데 사용할 수 있는 다른 도구에 대해 설명하고 있습니다.

<table>
<thead>
<tr class="header">
<th>기능</th>
<th>대체 도구</th>
<th>설명</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>법적 목적으로 검색, 내보내기 및 보류</td>
<td>핵심 eDiscovery 사례의 Microsoft 365 규정 준수 센터 </td>
<td><p>핵심 eDiscovery 사례의 기능을 사용하여 eDiscovery 및 보류를 In-Place 기능 패리티를 In-Place 제공합니다. 여기에는 다음이 포함됩니다.</p>
<ul>
<li>
<p>검색이 수백만 위치에 확장됩니다.</p>
</li>
<li>
<p>콘텐츠를 검색, 내보내기 및 보류하기 위한 안정성 향상</p>
</li>
<li>
<p>Exchange Online, SharePoint Online, 비즈니스용 OneDrive, 비즈니스용 Skype, Microsoft Teams, Yammer 그룹, Microsoft 365 그룹 및 저장된 기타 콘텐츠에 대한 콘텐츠 검색 Office 365 응용 프로그램</p></li></ul>
</td>
</tr>
<tr class="even">
<td>보존 목적으로 보존</td>
<td>정책의 Microsoft 365 규정 준수 센터</td>
<td><p>보존 정책을 사용하여 콘텐츠를 보존하고, 필요한 경우 보존 기간이 만료된 후 삭제할 수 있습니다. 기타 기능은 다음과 같습니다.</p>
<ul>
<li>
<p>전체 조직에 정책 적용 </p>
</li><li>
<p>Exchange Online, SharePoint Online, 비즈니스용 OneDrive, 비즈니스용 Skype, Microsoft Teams 및 Office 365 그룹과 같은 특정 콘텐츠 위치에 정책 적용</p></li>
<li>
<p>특정 사용자에게 정책 적용</p></li></ul>
<p>자세한 내용은 보존 정책 및 보존 레이블에 대해 자세히를 <a href="/microsoft-365/compliance/retention-policies">참조하세요.</a></td>
</tr>
<tr class="odd">
<td>검토를 위해 전자 메일 검색 결과를 검색 사서함에 복사</td><td>v2.Advanced eDiscovery 검토 집합</td>
<td><p>한 번 더 쉽게 Microsoft 365 콘텐츠를 검토할 수 있습니다. 검토 집합에는 다음을 포함하여 검토에 필요한 시간 및 데이터를 줄이는 데 도움이 되는 다양한 기능이 있습니다.</p>
<ul>
<li><p>빠른 검색 쿼리 수행 및 검토 집합에서 콘텐츠 필터링</p></li>
<li><p>검토 집합의 콘텐츠 분석 여기에는 전자 메일 스레딩, 중복에 가까운 검색, 테마 분석 및 예측 코딩이 포함됩니다.</p></li>
<li><p>검토 집합에서 문서 태그 지정</p></li>
<li><p>변호사 클라이언트 권한 콘텐츠를 식별하는 데 도움이 되는 태그 지정 제안</p></li></ul>
<p>자세한 내용은 M<a href="/microsoft-365/compliance/overview-ediscovery-20">icrosoft 365의 고급 eDiscovery 솔루션 개요</a>를 참조하세요.</p>
<p>
<p>또는 검색 결과를 PST 파일로 내보낼 수 있습니다. 그런 다음 가져오기 Microsoft 365 사용하여 PST를 검색 사서함으로 가져올 수 있습니다. 단계별 지침은 네트워크 업로드를 사용하여 PST 파일을 로 가져오기 <a href="/microsoft-365/compliance/use-network-upload-to-import-pst-files">Office 365.</a>
</tr>
<tr class=even>
  <td>한 사서함에서 다른 사서함으로 메시지 복사</td>
  <td><a href="/exchange/recipients-in-exchange-online/manage-permissions-for-recipients">사서함에 사용 권한 할당</a></td>
  <td>다른 사용자의 전자 메일(예: 직원이 조직을 떠나 이전 직원의 전자 메일에 대한 액세스 권한을 다른 사용자에게 제공해야 하는 경우)에 액세스 권한을 부여하려면 이전 직원의 사서함에 액세스할 수 있는 권한을 해당 사용자에게 할당하는 것이 좋습니다. 따라서 사서함 항목을 다른 사용자 사서함 또는 공유 사서함에 복사하는 대신 원본 사서함에 액세스하는 데 필요한 사용 권한을 사용자에게 할당하기만 합니다.</td>
  
  </tr>
<tr class="odd">
<td>복구 가능한 항목 폴더에서 항목 복원</td>
  <td><a href="/powershell/module/exchange/Restore-RecoverableItems">Restore-RecoverableItems</td>
  <td>항목에 대한 삭제된 항목 보존 기간이 만료되지 않은 한 사서함에서 영구적으로 삭제된 항목(소프트 삭제된 항목)을 복원할 수 있습니다. <i></i> 자세한 내용은 에서 <a href="/Exchange/security-and-compliance/recoverable-items-folder/recoverable-items-folder">복구 가능한 항목 폴더를 Exchange Online.</a></td>
</tr>
</tbody>
</table>

### <a name="faqs-about-in-place-ediscovery-and-in-place-holds"></a>eDiscovery 및 In-Place 보류에 In-Place FAQ

**I use the copy search results functionality of In-Place eDiscovery & Holds in the EAC to copy search results to a discovery mailbox for review by attorneys. 현재는 어떤 옵션이 있나요?**

현재 이 기능을 복제하는 방법에는 두 가지가 있습니다. 첫 번째는 [v2.Advanced eDiscovery 검토 집합을 사용하는 것입니다.](./view-documents-in-review-set.md) 검토 집합에는 빠른 문서 검색, 태그 지정, 전자 메일 스레딩, 중복에 가까운 그룹화, 테마 분석 및 예측 코딩과 같은 기존 검토 도구에서 볼 수 있는 여러 가지 기능이 있습니다. 검색 사서함을 계속 검토하려면 두 번째 옵션은 검색 결과를 PST 파일로 내보냈다가 Microsoft 준수 센터의 PST 가져오기 기능을 사용하여 [PST](use-network-upload-to-import-pst-files.md) 파일을 검색 사서함으로 가져오는 것입니다.

**eDiscovery 관리자가 새 도구를 사용하여 검색할 수 있는 콘텐츠 위치(예: 사서함 또는 사이트)를 제어하는 방법**

또한 Microsoft 365 규정 준수 센터 준수 경계를 사용하여 eDiscovery 관리자가 검색할 수 있는 콘텐츠 위치를 제어합니다. [](set-up-compliance-boundaries.md) 규정 준수 경계는 지리적 보드를 준수하는 데 필요한 기관 경계 또는 다국적 기업에 유지해야 하는 정부 기관에서 유용합니다.

**현재 검색 및 보류를 현재 검색으로 이동하는 Microsoft 365 규정 준수 센터?**

PowerShell을 사용하여 EAC에서 eDiscovery In-Place 및 보류를 마이그레이션할 수 있습니다. 자세한 내용은 [EAC에서](./migrate-legacy-ediscovery-searches-and-holds.md)검색 및 보류를 마이그레이션을 Microsoft 365 규정 준수 센터.

## <a name="-mailboxsearch-cmdlets"></a>\*-MailboxSearch cmdlet

Exchange 관리 센터에서 2017년 7월 1일 발표된 원래 공지에 따라 In-Place eDiscovery & 보류 기능 및 해당 **\* -MailboxSearch** cmdlet은 사용 중지됩니다. 이러한 cmdlet은 법적, 규정 및 공용 요청에 대한 사서함 콘텐츠를 검색, 보류 및 내보낼 수 있는 기능을 사용자에게 제공합니다.

이러한 기능은 이제 향상된 [<span class="underline">성능과</span>](./microsoft-365-compliance-center.md) 확장성을 통해 Microsoft 365 규정 준수 센터 및 Office 365 Security & Compliance Center PowerShell에서 사용할 수 있기 때문에 이러한 향상된 cmdlet을 사용해야 합니다. 이러한 cmdlet에는 [<span class="underline"> \* -ComplianceCase,</span>](/powershell/module/exchange/get-compliancecase) [<span class="underline"> \* -ComplianceSearch,</span>](/powershell/module/exchange/get-compliancesearch) [<span class="underline"> \* -CaseHoldPolicy,</span>](/powershell/module/exchange/get-caseholdpolicy) [<span class="underline"> \* -CaseHoldRule</span>](/powershell/module/exchange/get-caseholdrule)및 [<span class="underline"> \* -ComplianceSearchAction이 포함됩니다.</span>](/powershell/module/exchange/get-compliancesearchaction)

### <a name="scope-of-affected-organizations"></a>영향을 받는 조직의 범위

- Office 365 및 Microsoft 365 Enterprise 조직

- Office 365 및 Microsoft 365 Education 조직

- Office 365 Microsoft 365 조직; 여기에는 GCC, GCC High 및 DoD가 포함됩니다.

- Office 365 Germany

### <a name="timeline"></a>시간 표시 막대

- 2020년 7월 1일: **New-MailboxSearch를** 사용하여 새 In-Place eDiscovery 검색 및 In-Place 보류를 만들 수 없지만 cmdlet을 사용하여 기존 검색 및 보류를 실행, 편집 및 삭제할 수 있습니다. Microsoft 지원은 더 이상 이러한 유형의 검색 및 보류에 대한 지원을 제공하지 않습니다.

- 2020년 10월 1일: 앞서 설명한 In-Place eDiscovery & EAC의 보류 기능은 읽기 전용 모드로 설정됩니다. 즉, **New-MailboxSearch,** **Start-MailboxSearch** 또는 **Set-MailboxSearch** cmdlet을 사용할 수 없습니다. 기존 검색 및 보류만 검색 및 제거할 수 있습니다.

### <a name="alternative-tools"></a>대체 도구

다음 표에서는 사용 중지되는 기존 기능을 대체하는 데 사용할 수 있는 다른 도구에 대해 설명하고 있습니다.

<table>
<thead>
<tr class="header">
<th>기능</th>
<th>대체 도구</th>
<th>설명</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>검색 및 내보내기</td>
<td><p><a href="/powershell/module/exchange/get-compliancesearch"><span class="underline">*-ComplianceSearch</span></a></p>
<p><a href="/powershell/module/exchange/get-compliancesearchaction"><span class="underline">*-ComplianceSearchAction</span></a></p>
<p><a href="/powershell/module/exchange/get-compliancecase"><span class="underline">*-ComplianceCase</span></a></p>
<p> </p></td>
<td><p>ComplianceSearch 및 ComplianceSearchAction cmdlet은 함께 작동하여 콘텐츠를 검색하고 내보내는 데 도움이 됩니다. 새 검색을 만들고 <strong>New-</strong>, <strong>Get-</strong>및 <strong>Start-ComplianceSearch</strong> cmdlet을 사용하여 검색 예상 정보를 볼 수 있습니다. 그런 다음 <strong>New-ComplianceSearchAction</strong> cmdlet을 사용하여 검색 결과를 내보낼 수 있습니다. 검색 결과를 로컬 컴퓨터에 다운로드하려면 Microsoft 365 규정 준수 센터 핵심 eDiscovery 도구를 계속 사용해야 합니다.</p>
<p>
<p><strong>참고:</strong> 이러한 cmdlet을 사용하여 핵심 eDiscovery 사례와 연결되지 않은 검색을 만드는 경우 이러한 검색은 <strong></strong> 해당 cmdlet의 콘텐츠 검색 페이지에 Microsoft 365 규정 준수 센터.</p></td>
</tr>
<tr class="even">
<td>사서함에 콘텐츠 보류</td>
<td><p><a href="/powershell/module/exchange/get-caseholdpolicy"><span class="underline">*-CaseHoldPolicy</span></a></p>
<p><a href="/powershell/module/exchange/get-caseholdrule"><span class="underline">*-CaseHoldRule</span></a></p>
<p><a href="/powershell/module/exchange/get-compliancecase"><span class="underline">*-ComplianceCase</span></a></p>
<p> </p></td>
<td><p>보류 Microsoft 365 규정 준수 센터 ComplianceCase와 연결해야 합니다. 먼저 준수 사례를 만든 다음 CaseHoldPolicy 및 CaseHoldRule을 생성합니다.</p>
<p><strong>참고:</strong> CaseHoldRule을 만들지 않고 CaseHoldPolicy를 만들면 CaseHoldRule이 만들어지며 CaseHoldPolicy에 연결될 때까지 보류를 사용할 수 없습니다. 자세한 내용은 cmdlet 설명서를 참조하십시오.</p></td>
</tr>
<tr class="odd">
<td>검색 사서함에 검색 결과 복사</td>
<td>없음</td>
<td>모든 Microsoft 365 서비스에 대한 액세스 권한을 제공하지는 못하기 때문에 이 기능을 직접적으로 대체할 Microsoft 365 없습니다. 대체 솔루션에 대한 자세한 내용은 아래 FAQ를 참조하세요.</td>
</tr>
  <tr class=even>
  <td>한 사서함에서 다른 사서함으로 메시지 복사</td>
  <td><a href="/exchange/recipients-in-exchange-online/manage-permissions-for-recipients">사서함에 사용 권한 할당</a></td>
  <td>다른 사용자의 전자 메일(예: 직원이 조직을 떠나 이전 직원의 전자 메일에 대한 액세스 권한을 다른 사용자에게 제공해야 하는 경우)에 액세스 권한을 부여하려면 이전 직원의 사서함에 액세스할 수 있는 권한을 해당 사용자에게 할당하는 것이 좋습니다. 따라서 사서함 항목을 다른 사용자 사서함 또는 공유 사서함에 복사하는 대신 원본 사서함에 액세스할 수 있는 사용자 권한을 할당하기만 합니다.</td>
  
  </tr>

</tbody>
</table>

### <a name="faqs-about--mailboxsearch-cmdlets"></a>***-MailboxSearch** cmdlet에 대한 FAQ

**다른 eDiscovery 및 법적 조사를 위해 복사 검색을 사용하여 전자 메일 메시지 또는 인스턴트 메시지를 내보낼 수 있습니다. 이러한 cmdlet이 사용 중지된 후 사용할 수 있는 다른 옵션은 무엇입니까?**

[<span class="underline">Microsoft Graph</span>](https://developer.microsoft.com/en-us/graph) API는 **\* -MailboxSearch** cmdlet을 사용하는 것보다 훨씬 복원력 및 확장성이 훨씬 더 높은 분석 및 기타 목적으로 데이터를 추출하는 다양한 메서드를 제공합니다.

**검색 및 보류를 검색 및 보류 Microsoft 365 규정 준수 센터?**

PowerShell 스크립트를 사용하여 In-Place eDiscovery 검색 및 보류를 Exchange 관리 센터에서 마이그레이션할 수 있습니다. 자세한 내용은 [Migrate legacy eDiscovery searches and holds to the Microsoft 365 규정 준수 센터.](migrate-legacy-eDiscovery-searches-and-holds.md)

**cmdlet이 사용 중지된 후에도 검색을 제거하거나 검색할 수 있나요?**

예. 검색을 만들고 수정하는 기능을 제거하기는 하지만 추가 알림이 있을 때까지 **Get-MailboxSearch** 및 **Remove-MailboxSearch를** 계속 사용할 수 있습니다. 그러나 이러한 cmdlet의 사용은 퇴직일 이후에는 사용자 위험에 노출될 수 있으며 Microsoft 지원 서비스에서 더 이상 지원을 제공할 수 없습니다.

## <a name="search-mailbox-cmdlet"></a>Search-Mailbox cmdlet

Exchange Online PowerShell의 **Search-Mailbox** cmdlet은 2018년 다시 시작되는 cmdlet 출력의 경고에서 원래 발표된 그대로 사용 중지됩니다. **Search-Mailbox** cmdlet은 원래 사용자의 사서함을 검색하고 악성 콘텐츠를 삭제하는 데 사용되었다. Office 365 Security & PowerShell에서 **New-ComplianceSearch** 및 **New-ComplianceSearchAction** cmdlet을 사용하여 콘텐츠를 검색하고 삭제하는 것이 좋습니다. 기본 제공 보안 환경을 위해 [<span class="underline"></span>](../security/index.yml) Microsoft 365 보안 기능은 전자 메일 및 기타 많은 보안 기능에 강력한 위협 방지 기능을 Microsoft 서비스.

### <a name="scope-of-affected-organizations"></a>영향을 받는 조직의 범위

- Office 365 및 Microsoft 365 Enterprise 조직

- Office 365 및 Microsoft 365 Education 조직

- Office 365 Microsoft 365 조직; 여기에는 GCC, GCC High 및 DoD가 포함됩니다.

- Office 365 Germany

### <a name="timeline"></a>시간 표시 막대

-  2020년 7월 1일: **Search-Mailbox** cmdlet을 더 이상 사용할 수 없습니다. Microsoft 지원에서 더 이상 지원을 제공하지 않습니다.

### <a name="alternative-tools"></a>대체 도구

다음 표에서는 사용 중지되는 기존 기능을 대체하는 데 사용할 수 있는 다른 도구에 대해 설명하고 있습니다.

<table>
<thead>
<tr class="header">
<th>기능</th>
<th>대체 도구</th>
<th>설명</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>사서함 검색</td>
<td><p><a href="/powershell/module/exchange/get-compliancesearch"><span class="underline">*-ComplianceSearch</span></a></p>
<p><a href="/powershell/module/exchange/get-compliancesearchaction"><span class="underline">*-ComplianceSearchAction</span></a></p>
<p></a></p></td>
<td><p>ComplianceSearch 및 ComplianceSearchAction cmdlet은 함께 작동하여 콘텐츠를 검색하고 내보내는 데 도움이 됩니다. 새 검색을 만들고 <strong>New-</strong>, <strong>Get-</strong>및 <strong>Start-ComplianceSearch</strong> cmdlet을 사용하여 검색 예상 정보를 볼 수 있습니다. 그런 다음 <strong>New-ComplianceSearchAction -Export</strong> 명령을 사용하여 검색 결과를 내보낼 수 있습니다. 검색 결과를 로컬 컴퓨터에 다운로드하려면 Microsoft 365 규정 준수 센터 핵심 eDiscovery 도구를 계속 사용해야 합니다.</p></p>
</td>
</tr>
<tr class="even">
<td>사서함에서 대량 전자 메일 삭제</td>
<td><p><a href="/microsoft-365/compliance/set-up-an-archive-and-deletion-policy-for-mailboxes"><span class="underline">사서함에 대한 보관 및 삭제 정책 설정</span></a></p>
<p></p></td>
<td><p>관리자는 항목을 사용자의 보관 사서함으로 자동 이동하고 사서함에서 항목을 자동으로 삭제하는 보관 및 삭제 정책을 만들 수 있습니다.</p>
</td>
</tr>
<tr class="even">
<td>검색 사서함에 검색 결과 복사</td>
<td> </td>
<td>모든 Microsoft 365 서비스에 대한 액세스 권한을 제공하지는 못하기 때문에 이 기능을 직접적으로 대체할 Microsoft 365 없습니다. 대체 솔루션에 대한 자세한 내용은 <strong>*-MailboxSearch cmdlets</strong> 섹션의 FAQ를 참조하세요. </td>
</tr>
<tr class=odd>
  <td>한 사서함에서 다른 사서함으로 메시지 복사</td>
  <td><a href="/exchange/recipients-in-exchange-online/manage-permissions-for-recipients">사서함에 사용 권한 할당</a></td>
  <td>다른 사용자의 전자 메일(예: 직원이 조직을 떠나 이전 직원의 전자 메일에 대한 액세스 권한을 다른 사용자에게 제공해야 하는 경우)에 액세스 권한을 부여하려면 이전 직원의 사서함에 액세스할 수 있는 권한을 해당 사용자에게 할당하는 것이 좋습니다. 따라서 사서함 항목을 다른 사용자 사서함 또는 공유 사서함에 복사하는 대신 원본 사서함에 액세스할 수 있는 권한을 사용자에게 할당하기만 합니다.</td>
</tr>
<tr class=even>
  <td>사서함에서 메시지 제거</td>
<td><p><a href="/powershell/module/exchange/get-compliancesearch"><span class="underline">*-ComplianceSearch</span></a></p>
<p><a href="/powershell/module/exchange/get-compliancesearchaction"><span class="underline">*-ComplianceSearchAction</span></a></p>
<p></p></td>
<td><p>ComplianceSearch 및 ComplianceSearchAction cmdlet은 함께 작동하여 콘텐츠를 검색하고 삭제하는 데 도움이 됩니다. <strong>New-ComplianceSearch</strong> 및 <strong>New-ComplianceSearch</strong> cmdlet을 사용하여 검색을 만들고 실행한 다음 <strong>New-ComplianceSearchAction -Purge -PurgeType</strong> 명령을 사용하여 콘텐츠를 지울 수 있습니다. 자세한 내용은 메시지 검색 <a href="/microsoft-365/compliance/search-for-and-delete-messages-in-your-organization"><span class="underline">및 삭제를 참조하세요.</span></a></p>
</td>
</tr>
<tr class="odd"> 
<td>사서함에서 메시지 제거</td>
<td><a href="/exchange/recipients-in-exchange-online/manage-permissions-for-recipients">사서함에 사용 권한 할당</a></td>
<td>사서함에서 메시지를 제거하려면 직원의 사서함에 액세스할 수 있는 관리자 권한을 할당합니다. 메시지는 메시지의 기본 제공 검색 및 보기 기능을 사용하여 필요한 경우 삭제하고 재활용할 수 Outlook.</td>
</tr>
</tbody>
</table>

## <a name="exchange-web-services-api-operations"></a>Exchange 웹 서비스 API 작업

Exchange 웹 서비스 API의 이러한 작업은 Exchange 관리 센터의 In-Place eDiscovery & 보류 기능 및 Exchange Online PowerShell의 해당 **\* -MailboxSearch** cmdlet에 사용됩니다. 또한 다른 레거시 eDiscovery 도구의 사용 중지의 일부로도 사용이 중지됩니다.

### <a name="scope-of-affected-organizations"></a>영향을 받는 조직의 범위

- Office 365 및 Microsoft 365 Enterprise 조직

- Office 365 및 Microsoft 365 Education 조직

- Office 365 Microsoft 365 조직; 여기에는 GCC, GCC High 및 DoD가 포함됩니다.

- Office 365 Germany

### <a name="timeline"></a>시간 표시 막대

- 2020년 7월 1일: GetSearchableMailboxes, SearchMailboxes, SetHoldOnMailboxes 및 GetHoldOnMailboxes 작업을 더 이상 사용할 수 없습니다. Microsoft 지원은 더 이상 지원을 제공하지 않습니다.

## <a name="advanced-ediscovery-v10"></a>Advanced eDiscovery v1.0

Advanced eDiscovery v1.0(핵심 eDiscovery 사례에서 사용할 수 있는 Advanced eDiscovery 버전인 v1.0은 Advanced eDiscovery 사용 중지됩니다.  해당 기능은 새 응용 Advanced eDiscovery [](./ediscovery.md) 솔루션으로 Microsoft 365 규정 준수 센터.

조직에서 v1.0을 Advanced eDiscovery 확인:

1. **eDiscovery** Microsoft 365 규정 준수 센터 선택한 다음  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=2174007" target="_blank"></a>Core eDiscovery 사례를 여는 데 사용할 수 있습니다.

1. 다음으로 전환 **단추가 Advanced eDiscovery** 클릭하면 사용 중지되는 1.0 버전의 Advanced eDiscovery 표시됩니다. Core eDiscovery에서 사례를 만들고 관리하는 능력은 영향을 받지 않습니다. v1.0으로 전환을 클릭하여 Advanced eDiscovery v1.0에서 사례 데이터를 추가하고 분석하는 Advanced eDiscovery **기능만** 사용 중지됩니다.

Microsoft 365의 새로운 Advanced eDiscovery 솔루션(Advanced eDiscovery *v2.0)은* 원래 솔루션의 모든 기능을 제공하지만 이제는 다른 Microsoft 365 서비스에서 콘텐츠를 식별하고, 해당 콘텐츠를 수집하는 관리자 기반 접근 방식을 포함합니다. 그런 다음 검토자는 빠른 검색 쿼리, 태그 지정 및 분석 기능을 활용하여 관련 문서를 선회할 수 있는 검토 집합에 추가합니다. Advanced eDiscovery Microsoft 파일 형식과 비 Microsoft 파일 형식 모두에 대한 향상된 처리 및 기본 [](./supported-filetypes-ediscovery20.md) 뷰어가 포함되어 있습니다. 여기에 파일 형식의 전체 목록이 있으며 지원되는 메타데이터 필드는 다음과 [같습니다.](./document-metadata-fields-in-advanced-ediscovery.md) 또한 새로운 Advanced eDiscovery 솔루션에서는 다른 서비스의 콘텐츠에 보류를 적용하고, 보류를 사용자에게 알리고, 보유자 응답을 추적할 수 있는 강력한 보유 관리 기능을 Advanced eDiscovery 있습니다.

Advanced eDiscovery v2.0에 액세스하려면 다음을 수행합니다.

**eDiscovery** Microsoft 365 규정 준수 센터 선택한 다음  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=2174006" target="_blank"></a>Core eDiscovery 사례를 여는 데 사용할 수 있습니다.

이때 eDiscovery 워크플로를 새 Advanced eDiscovery 전환하는 것이 좋습니다. 필요한 경우 콘텐츠를 내보내고 Advanced eDiscovery 1.0 사례를 보관할 수 있습니다. 2020년 12월 31일까지는 기존 사례에서 Advanced eDiscovery v1.0에 계속 액세스할 수 있습니다. 그러나 Microsoft 지원은 2020년 10월 1일 이후에는 지원을 제공하지 않습니다. 자세한 내용은 다음 타임라인을 참조하세요.

### <a name="scope-of-affected-organizations"></a>영향을 받는 조직의 범위

- Office 365 및 Microsoft 365 Enterprise 조직

- Office 365 및 Microsoft 365 Education 조직

- Office 365 Microsoft 365 조직; 여기에는 GCC, GCC High 및 DoD가 포함됩니다.

- Office 365 Germany

### <a name="timeline"></a>시간 표시 막대

- 2020년 7월 1일: v1.0 사례에서 새 Advanced eDiscovery 수 없습니다.

- 2020년 10월 1일: 모든 경우에 새 데이터(검색 결과 준비)를 Advanced eDiscovery 수 없습니다. 기존 사례의 데이터를 계속 사용하여 작업을 계속할 수 있습니다. Microsoft 지원이 더 이상 지원을 제공하지 않습니다. 

- 2020년 12월 31일: v1.0 사례에 액세스할 Advanced eDiscovery 없습니다.

### <a name="alternative-tools"></a>대체 도구

Advanced eDiscovery [솔루션이](./overview-ediscovery-20.md) Microsoft 365 규정 준수 센터.
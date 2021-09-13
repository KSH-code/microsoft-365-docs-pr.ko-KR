---
title: eDiscovery 솔루션 시리즈 데이터 유출 시나리오 - 검색 및 제거
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MET150
ms.assetid: d945f7dd-f62f-4ca7-b3e7-469824cfd493
description: eDiscovery 및 검색 도구를 사용하여 조직의 데이터 유출 인시던트 관리 및 대응
ms.openlocfilehash: 340bf10dc57737c024d1ffcb3a441ba53bc917d6
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2021
ms.locfileid: "59213912"
---
# <a name="ediscovery-solution-series-data-spillage-scenario---search-and-purge"></a>eDiscovery 솔루션 시리즈: 데이터 유출 시나리오 - 검색 및 제거

 **데이터 유출이란 무엇일까요? 왜 주의해야 하나요?** 데이터 유출은 기밀 문서가 불안정한 환경에 릴리스되는 경우입니다. 데이터 유출 인시던트가 감지되면 유출의 크기와 위치를 빠르게 평가하고, 유출된 데이터를 시스템에서 영구적으로 삭제하는 것이 중요합니다. 
  
## <a name="data-spillage-scenario"></a>데이터 유출 시나리오

Contoso의 책임자 정보 보안 책임자입니다. 직원이 전자 메일을 통해 여러 사용자와 비밀 유지 문서를 알 수 없는 공유하는 데이터 유출 상황을 알 수 있습니다. 이 문서를 받은 인원을 내부 및 외부적으로 빠르게 평가하려는 경우 확인되면 다른 조사자들과 사례 결과를 공유하여 검토한 다음 해당 조사에서 데이터를 영구적으로 Office 365. 조사가 완료되면 영구적으로 제거된 증거와 이후 참조에 대한 기타 사례 세부 정보가 있는 보고서를 생성해야 합니다.
  
### <a name="scope-of-this-article"></a>이 문서의 범위

이 문서에서는 메시지에 액세스하거나 복구할 수 Microsoft 365 수 있도록 메시지에서 메시지를 영구적으로 제거하는 방법에 대한 지침을 제공합니다. 메시지를 삭제하고 삭제된 항목 보존 기간이 만료될 때까지 복구할 수 있도록 설정하려면 조직에서 전자 메일 메시지 검색 및 [삭제를 참조하세요.](search-for-and-delete-messages-in-your-organization.md)
  
## <a name="workflow-for-managing-data-spillage-incidents"></a>데이터 유출 인시던트 관리 워크플로

다음은 데이터 유출 사고를 관리하는 방법입니다.

![데이터 유출 인시던트 관리를 위한 8단계 워크플로입니다.](../media/O365-eDiscoverySolutions-DataSpillage-workflow.png)
  
[(선택 사항) 1단계: 사례에 액세스할 수 있는 사용자 관리 및 규정 준수 경계 설정](#optional-step-1-manage-who-can-access-the-case-and-set-compliance-boundaries)<br/>
[2단계: eDiscovery 사례 만들기](#step-2-create-an-ediscovery-case)<br/>
[3단계: 유출된 데이터 검색](#step-3-search-for-the-spilled-data)<br/>
[4단계: 사례 결과 검토 및 유효성 검사](#step-4-review-and-validate-case-findings)<br/>
[5단계: 메시지 추적 로그를 사용하여 유출된 데이터가 공유된 방식 확인](#step-5-use-message-trace-log-to-check-how-spilled-data-was-shared)<br/>
[6단계: 사서함 준비](#step-6-prepare-the-mailboxes)<br/>
[7단계: 유출된 데이터를 영구적으로 삭제](#step-7-permanently-delete-the-spilled-data)<br/>
[8단계: 확인, 지우기 증명 및 감사 제공](#step-8-verify-provide-a-proof-of-deletion-and-audit)<br/>

## <a name="things-to-know-before-you-start"></a>시작하기 전에 알아야 할 것

- 사서함이 보류 중이면 보존 기간이 만료되거나 보류가 릴리스될 때까지 삭제된 메시지가 복구 가능한 항목 폴더에 남아 있습니다. [6단계에서는](#step-6-prepare-the-mailboxes) 사서함에서 보류를 제거하는 방법을 설명합니다. 보류를 제거하기 전에 레코드 관리 또는 법률 부서에 확인을 합니다. 조직에 보류된 사서함 또는 데이터 유출 인시던트가 우선적으로 적용될지 여부를 정의하는 정책이 있을 수 있습니다. 
    
- 데이터 유출 조사가 사례에 액세스할 수 있는 사용자를 검색하고 관리할 수 있는 사용자 사서함을 제어하기 위해 규정 준수 경계를 설정하고 [1단계에](#optional-step-1-manage-who-can-access-the-case-and-set-compliance-boundaries)설명된 사용자 지정 역할 그룹을 만들 수 있습니다. 이 작업을 위해 Organization Management 역할 그룹의 구성원 또는 역할 관리 역할을 할당해야 합니다. 사용자 또는 조직의 관리자가 이미 규정 준수 경계를 설정한 경우 1단계를 건너뛸 수 있습니다.
    
- 사례를 만들하려면 eDiscovery 관리자 역할 그룹의 구성원 또는 사례 관리 역할이 할당된 사용자 지정 역할 그룹의 구성원이 되어야 합니다. 구성원이 아닌 경우 Microsoft 365 관리자에게 [eDiscovery](assign-ediscovery-permissions.md)관리자 역할 그룹에 추가해달고 요청합니다.
    
- 콘텐츠 검색을 만들고 실행하려면 eDiscovery 관리자 역할 그룹의 구성원이거나 준수 검색 관리 역할을 할당 받아야 합니다. 메시지를 삭제하려면 조직 관리 역할 그룹의 구성원이거나 검색 및 제거 관리 역할을 할당 받아야 합니다. 역할 그룹에 사용자를 추가하는 데 대한 자세한 내용은 [eDiscovery](./assign-ediscovery-permissions.md)사용 권한 할당을 참조하세요.
    
- 8단계에서 감사 로그 eDiscovery 활동을 검색하려면 조직에 대해 감사를 설정해야 합니다. 지난 90일 이내에 수행된 활동을 검색할 수 있습니다. 감사를 사용하도록 설정하고 사용하는 방법에 대한 자세한 내용은 8단계의 데이터 유출 조사 프로세스 [감사](#auditing-the-data-spillage-investigation-process) 섹션을 참조하세요. 
    
## <a name="optional-step-1-manage-who-can-access-the-case-and-set-compliance-boundaries"></a>(선택 사항) 1단계: 사례에 액세스할 수 있는 사용자 관리 및 규정 준수 경계 설정

조직의 관행에 따라 데이터 유출 사고를 조사하고 규정 준수 경계를 설정하는 데 사용되는 eDiscovery 사례에 액세스할 수 있는 사용자도 제어해야 합니다. 이 작업을 수행하는 가장 쉬운 방법은 조사를 기존 역할 그룹의 구성원으로 Microsoft 365 규정 준수 센터 eDiscovery 사례의 구성원으로 역할 그룹을 추가하는 것입니다. 기본 제공 eDiscovery 역할 그룹 및 eDiscovery 사례에 구성원을 추가하는 방법에 대한 자세한 내용은 [eDiscovery 권한 할당을 참조하세요.](assign-ediscovery-permissions.md)
  
조직의 요구에 맞게 새 역할 그룹을 만들 수도 있습니다. 예를 들어 조직의 데이터 유출 조사자 그룹이 모든 데이터 유출 사례에 액세스하고 공동 작업을 하도록 할 수 있습니다. 이를 위해 "데이터 유출 조사자" 역할 그룹을 만들고 적절한 역할(내보내기, RMS 암호 해독, 검토, 미리 보기, 준수 검색 및 사례 관리)을 할당하고, 데이터 유출 조사자를 역할 그룹에 추가한 다음 역할 그룹을 데이터 유출 eDiscovery 사례의 구성원으로 추가하면 됩니다. 자세한 지침은 [Set up compliance boundaries for eDiscovery investigations in Office 365(eDiscovery](set-up-compliance-boundaries.md) 조사에 대한 규정 준수 경계 설정)를 참조하세요. 
  
## <a name="step-2-create-an-ediscovery-case"></a>2단계: eDiscovery 사례 만들기

eDiscovery 사례는 데이터 유출 조사를 효율적으로 관리하는 방법을 제공합니다. 1단계에서 만든 역할 그룹에 구성원을 추가하고, 역할 그룹을 새 eDiscovery 사례의 구성원으로 추가하고, 되걸기 검색을 수행하여 유출된 데이터를 찾고, 공유할 보고서를 내보내고, 사례 상태를 추적한 다음 필요한 경우 사례의 세부 정보를 참조할 수 있습니다. 데이터 유출 인시던트에 사용되는 eDiscovery 사례에 대한 명명 규칙을 설정하는 것을 고려하고, 필요한 경우를 찾고 참조할 수 있도록 사례 이름 및 설명에서와 같은 정보를 제공할 수 있습니다.
  
새 사례를 만들 수 있도록 보안 및 규정 준수 센터에서 eDiscovery를 사용할 수 있습니다. [Core eDiscovery](get-started-core-ediscovery.md#step-3-create-a-core-ediscovery-case)시작 에서 "새 사례 만들기"를 참조합니다.
  
## <a name="step-3-search-for-the-spilled-data"></a>3단계: 유출된 데이터 검색

사례 및 관리되는 액세스를 만들었다면 사례를 거치게 검색하여 유출된 데이터를 찾고 유출된 데이터를 포함하는 사서함을 식별할 수 있습니다. 7단계에서 전자 메일 메시지를 찾는 데 사용한 검색 쿼리를 사용하여 동일한 메시지를 [삭제합니다.](#step-7-permanently-delete-the-spilled-data)
  
eDiscovery 사례와 연결된 콘텐츠 검색을 만들 내용은 [Core eDiscovery](search-for-content-in-core-ediscovery.md)사례에서 콘텐츠 검색을 참조하세요.
  
> [!IMPORTANT]
> 검색 쿼리에서 사용하는 키워드에는 검색하는 실제 유출 데이터가 포함될 수 있습니다. 예를 들어 주민 번호가 포함된 문서를 검색하고 이를 검색 키워드로 사용하는 경우 쿼리를 삭제하여 추가 유출을 방지해야 합니다. [8단계에서 검색 쿼리](#deleting-the-search-query) 삭제를 참조합니다.
  
## <a name="step-4-review-and-validate-case-findings"></a>4단계: 사례 결과 검토 및 유효성 검사

콘텐츠 검색을 만든 후 검색 결과가 삭제해야 하는 전자 메일 메시지로만 구성되는지 검토하고 유효성을 검사해야 합니다. 콘텐츠 검색에서는 추가 데이터 유출을 방지하기 위해 검색 결과를 내보내지 않고도 1,000개 전자 메일 메시지의 임의 샘플링을 미리 볼 수 있습니다. 미리 보기 제한에 대한 자세한 내용은 [Limits for Content Search을 읽어 볼 수 있습니다.](limits-for-content-search.md)
  
검토할 사서함 수가 1,000개가 넘는 경우, 검토할 사서함당 전자 메일 메시지가 100개 이상인 경우 날짜 범위 또는 보낸 사람/받는 사람과 같은 추가 키워드 또는 조건을 사용하여 초기 검색을 여러 검색으로 나누고 각 검색의 결과를 개별적으로 검토할 수 있습니다. 7단계에서 메시지를 삭제할 때 사용할 모든 검색 쿼리를 [기록해 두어야 합니다.](#step-7-permanently-delete-the-spilled-data)

취득자 또는 최종 사용자에게 Office 365 E5 라이선스가 할당된 경우 검색 라이선스를 사용하여 한 번씩 최대 10,000개 검색 결과를 Advanced eDiscovery. 검토할 전자 메일 메시지가 10,000개보다 많은 경우 검색 쿼리를 날짜 범위로 나누고 검색 결과가 날짜별로 정렬될 때 각 결과를 개별적으로 검토할 수 있습니다. 이 Advanced eDiscovery 미리 보기 패널의 **레이블** 기능을 사용하여 검색 결과에 태그를 지정하고 레이블을 지정한 태그로 검색 결과를 필터링할 수 있습니다. 보조 검토자와 공동 작업할 때 유용합니다. 광학 문자 인식, Advanced eDiscovery 스레딩 및 예측 코딩과 같은 추가 분석 도구를 사용하면 수천 개의 메시지를 빠르게 처리하고 검토하고 추가 검토를 위해 태그를 지정할 수 있습니다. 자세한 [내용은 에 대한 빠른 Advanced eDiscovery.](./get-started-with-advanced-ediscovery.md)

유출된 데이터가 포함된 전자 메일 메시지를 찾은 경우 메시지 받는 사람을 확인하여 외부에서 공유된 메시지인지를 파악합니다. 메시지를 더 추적하려면 메시지 추적 로그를 사용할 수 있도록 보낸 사람 정보 및 날짜 범위를 수집할 수 있습니다. 이 프로세스는 [5단계에 설명되어 있습니다.](#step-5-use-message-trace-log-to-check-how-spilled-data-was-shared)

검색 결과를 확인한 후 다른 사용자와 찾은 결과를 보조 검토를 위해 공유할 수 있습니다. 1단계에서 사례에 할당한 사람은 eDiscovery 및 2단계에서 사례 콘텐츠를 검토하고 사례 Advanced eDiscovery 승인할 수 있습니다. 실제 콘텐츠를 내보내지 않고도 보고서를 생성할 수 있습니다. 8단계에 설명된 동일한 보고서를 지우기 증명으로 사용할 [수도 있습니다.](#step-8-verify-provide-a-proof-of-deletion-and-audit)
  
 **통계 보고서를 생성하는 경우:**
  
1. eDiscovery 사례의 검색 페이지로 이동하여 보고서를 생성할 검색을 클릭합니다.  
    
2. 플라이아웃 페이지에서 보고서 **내보내기 > 클릭합니다.**
 
      보고서 내보내기 페이지가 표시됩니다.

    ![검색을 선택한 다음 플라이아웃 페이지에서 > 보고서 내보내기 추가를 클릭합니다.](../media/O365-eDiscoverySolutions-DataSpillage-ExportReport1.png)
    
3. 인식할 **수** 없는 형식이거나 암호화되거나 다른 이유로 인덱싱되지 않은 항목을 포함하여 모든 항목을 선택한 다음 보고서 생성 을 **클릭합니다.**

4. eDiscovery 사례에서 내보내기 **를** 클릭하여 내보내기 작업 목록을 표시합니다. 새로 고침을 **클릭하여** 만든 내보내기 작업을 표시하기 위해 목록을 업데이트해야 할 수 있습니다.

5. 내보내기 작업을 클릭한  다음 플라이아웃 페이지에서 보고서 다운로드를 클릭합니다.
 
    ![내보내기 페이지에서 내보내기, "보고서 다운로드"를 클릭합니다.](../media/O365-eDiscoverySolutions-DataSpillage-ExportReport2.png)

요약 **내보내기 보고서에는** 결과가 포함된 위치 수와 검색 결과의 크기가 포함되어 있습니다. 이 기능을 사용하여 해당 보고서를 지우고 생성된 보고서와 비교하고, 이를 지우기 증명으로 제공할 수 있습니다. 결과 **보고서에는** 각 메시지의 제목, 보낸 사람, 받는 사람, 전자 메일을 읽은 경우, 날짜 및 크기를 포함하여 검색 결과에 대한 자세한 요약이 포함되어 있습니다. 이 보고서의 세부 정보 중 하나에 실제 유출된 데이터가 포함되어 있는 경우 조사가 완료되면 Results.csv 파일을 영구적으로 삭제해야 합니다.

보고서 내보내기에 대한 자세한 내용은 [Export a Content Search report를 참조하십시오.](export-a-content-search-report.md)
    
## <a name="step-5-use-message-trace-log-to-check-how-spilled-data-was-shared"></a>5단계: 메시지 추적 로그를 사용하여 유출된 데이터가 공유된 방식 확인

유출된 데이터가 있는 전자 메일이 공유된 경우 추가로 조사하려면 필요한 경우 4단계에서 수집한 보낸 사람 정보 및 날짜 범위 정보를 메시지 추적 로그에 쿼리할 수 있습니다. 메시지 추적의 보존 기간은 실시간 데이터의 경우 30일, 기록 데이터의 경우 90일입니다.
  
보안 및 규정 준수 센터에서 메시지 추적을 사용하거나 PowerShell에서 해당 cmdlet을 Exchange Online 있습니다. 메시지 추적은 반환된 데이터의 완전성을 완전하게 보장하지 않습니다. 메시지 추적 사용에 대한 자세한 내용은 다음을 참조하세요. 
  
- [보안 및 준수 센터의 메시지 추적](../security/office-365-security/message-trace-scc.md)
    
- [보안 및 준수 센터의 & 메시지 추적](https://techcommunity.microsoft.com/t5/exchange-team-blog/new-message-trace-in-office-365-security-038-compliance-center/ba-p/607893)
    
## <a name="step-6-prepare-the-mailboxes"></a>6단계: 사서함 준비

검색 결과에 삭제해야 하는 메시지만 포함되어 있는지 검토하고 유효성을 검사한 후 유출된 데이터를 삭제할 때 7단계에서 사용할 영향을 받는 사서함의 전자 메일 주소 목록을 수집해야 합니다. 유출된 데이터를 포함하는 사서함에서 단일 항목 복구를 사용할 수 있는지 또는 보류된 사서함에 대해 단일 항목 복구를 사용할 수 있는지 여부에 따라 전자 메일 메시지를 영구적으로 삭제하기 전에 사서함을 준비해야 할 수도 있습니다.
  
### <a name="get-a-list-of-addresses-of-mailboxes-with-spilled-data"></a>유출된 데이터가 있는 사서함 주소 목록 확인

유출된 데이터가 있는 사서함의 전자 메일 주소 목록을 수집하는 방법에는 두 가지가 있습니다.

**옵션 1: 유출된 데이터가 있는 사서함 주소 목록 표시**

1. eDiscovery 사례를 열고 검색 페이지로 **이동한** 다음 적절한 콘텐츠 검색을 선택합니다. 
    
2. 플라이아웃 페이지에서 결과 보기 **를 클릭합니다.**
    
3. **개별 결과** 드롭다운 목록에서 **검색 통계** 를 클릭합니다.
    
4. 유형 **드롭다운** 목록에서 위쪽 **위치를 클릭합니다.**
    
    ![검색 통계의 최상위 위치 페이지에서 검색 결과가 포함된 사서함 목록을 얻습니다.](../media/O365-eDiscoverySolutions-DataSpillage-TopLocations.png)

    검색 결과가 포함된 사서함 목록이 표시됩니다. 검색 쿼리와 일치하는 각 사서함의 항목 수도 표시됩니다.
    
5. 목록의 정보를 복사하여 파일에 저장하거나 다운로드를 클릭하여 정보를 CSV 파일에 다운로드합니다.  
    
**옵션 2: 내보내기 보고서에서 사서함 위치 확인**

4단계에서 다운로드한 내보내기 요약 [보고서를 열 수 있습니다.](#step-4-review-and-validate-case-findings) 보고서의 첫 번째 열에서 각 사서함의 전자 메일 주소는 위치 아래에 **나열됩니다.**
  
### <a name="prepare-the-mailboxes-so-you-can-delete-the-spilled-data"></a>유출된 데이터를 삭제할 수 있도록 사서함 준비

단일 항목 복구를 사용하도록 설정하거나 사서함이 보류된 경우 영구적으로 삭제(제거) 메시지가 복구 가능한 항목 폴더에 보존됩니다. 따라서 유출된 데이터를 제거하려면 먼저 기존 사서함 구성을 확인하고 단일 항목 복구를 사용하지 않도록 설정하고 보류 또는 보존 정책을 제거해야 합니다. 한 번의 사서함을 준비한 다음 다른 사서함에서 동일한 명령을 실행하거나 PowerShell 스크립트를 만들어 여러 사서함을 동시에 준비할 수 있습니다.

- 단일 항목 복구가 사용하도록 설정되어 있는지 또는 사서함이 보류 중 상태 또는 보존 정책에 할당되어 있는지 확인하려면 보류된 클라우드 기반 사서함의 복구 가능한 항목 폴더에 있는 항목 삭제의 "1단계: 사서함에 대한 정보 수집"을 참조하세요. [](delete-items-in-the-recoverable-items-folder-of-mailboxes-on-hold.md#step-1-collect-information-about-the-mailbox) 

- 단일 항목 복구를 사용할 수 [](delete-items-in-the-recoverable-items-folder-of-mailboxes-on-hold.md#step-2-prepare-the-mailbox) 없는 방법에 대한 지침은 클라우드 기반 사서함의 복구 가능한 항목 폴더에 있는 항목 삭제의 "2단계: 사서함 준비"를 참조하세요. 

- 사서함에서 보류 또는 보존 정책을 제거하는 방법에 [](delete-items-in-the-recoverable-items-folder-of-mailboxes-on-hold.md#step-3-remove-all-holds-from-the-mailbox) 대한 지침은 클라우드 기반 사서함의 복구 가능한 항목 폴더에 있는 항목 삭제의 "3단계: 사서함에서 모든 보류 제거"를 참조하세요. 

- 모든 유형의 보류가 제거된 후 사서함에 [](delete-items-in-the-recoverable-items-folder-of-mailboxes-on-hold.md#step-4-remove-the-delay-hold-from-the-mailbox) 배치된 지연 보류를 제거하는 방법에 대한 지침은 클라우드 기반 사서함의 복구 가능한 항목 폴더에 있는 항목 삭제의 "4단계: 사서함에서 지연 보류 제거"를 참조하세요.

> [!IMPORTANT]
> 보류 또는 보존 정책을 제거하기 전에 레코드 관리 또는 법률 부서에 확인을 합니다. 조직에 보류된 사서함 또는 데이터 유출 인시던트가 우선적으로 적용될지 여부를 정의하는 정책이 있을 수 있습니다. 
  
유출된 데이터가 영구적으로 삭제된 것을 확인한 후 사서함을 이전 구성으로 되전해야 합니다. [7단계의 세부 정보를 참조합니다.](#step-7-permanently-delete-the-spilled-data)

## <a name="step-7-permanently-delete-the-spilled-data"></a>7단계: 유출된 데이터를 영구적으로 삭제

6단계에서 수집하고 준비한 사서함 위치와 3단계에서 작성 및 구체화한 검색 쿼리를 사용하여 유출된 데이터가 포함된 전자 메일 메시지를 찾으면 유출된 데이터를 영구적으로 삭제할 수 있습니다.  앞서 설명한 것 처럼 메시지를 삭제하려면 조직 관리 역할 그룹의 구성원 또는 검색 및 제거 관리 역할이 할당되어야 합니다. 역할 그룹에 사용자를 추가하는 데 대한 자세한 내용은 [eDiscovery](./assign-ediscovery-permissions.md)사용 권한 할당을 참조하세요.

유출된 메시지를 삭제하려면 전자 메일 메시지 검색 [및 삭제를 참조하세요.](search-for-and-delete-messages-in-your-organization.md)

유출된 데이터를 삭제하는 경우 다음 제한에 유의하십시오.

- 검색 및 삭제 작업을 수행하여 항목을 삭제하는 데 사용할 수 있는 검색의 최대 사서함 수는 50,000개입니다. 3단계에서 만든 검색에서 50,000개가 넘는 사서함을 검색하면 제거 작업이 실패합니다. 일반적으로 단일 검색에서 50,000개 이상의 편지함을 검색하는 작업은 조직의 모든 편지함을 포함하도록 검색을 구성할 때 발생할 수 있습니다. 이 제한은 50,000개 미만의 사서함에 검색 쿼리와 일치하는 항목이 포함된 경우에도 적용됩니다.

- 사서함마다 한번에 최대 10개의 항목을 제거할 수 있습니다. 메시지를 검색하고 제거하는 기능은 사고 대응 도구로 고안되었으므로 이러한 제한은 사서함에서 메시지가 빠르게 제거되도록 합니다. 이 기능은 사용자 사서함을 정리하기 위한 기능이 아닙니다.

> [!IMPORTANT]
> Advanced eDiscovery 사례에서 검토 집합의 전자 메일 항목은 이 문서의 절차를 사용하여 삭제할 수 없습니다. 검토 집합의 항목은 라이브 서비스에서 복사되어 해당 위치에 저장되는 항목의 Azure Storage 있기 때문에입니다. 즉, 3단계에서 만든 콘텐츠 검색에서 반환되지 않습니다. 검토 집합의 항목을 삭제하려면 검토 집합이 포함된 Advanced eDiscovery 사례를 삭제해야 합니다. 자세한 내용은 [Advanced eDiscovery 사례 닫기 또는 삭제하기](close-or-delete-case.md)를 참조하세요.
  
## <a name="step-8-verify-provide-a-proof-of-deletion-and-audit"></a>8단계: 확인, 지우기 증명 및 감사 제공

워크플로에서 데이터 유출 인시던트 관리의 마지막 단계는 eDiscovery 사례로 이동한 후 해당 데이터를 삭제하는 데 사용된 동일한 검색 쿼리를 다시 실행하여 결과가 반환되지 않는지 확인하여 유출된 데이터가 사서함에서 영구적으로 제거된지 확인하는 것입니다. 유출된 데이터가 영구적으로 제거된 후 보고서를 내보내고 원본 보고서와 함께 삭제 증명으로 포함할 수 있습니다. 그런 [다음](close-reopen-delete-core-ediscovery-cases.md) 향후 참조해야 하는 경우 다시 열 수 있는 사례를 닫을 수 있습니다. 또한 사서함을 이전 상태로 되찾고, 유출된 데이터를 찾는 데 사용되는 검색 쿼리를 삭제하고, 데이터 유출 사고를 관리할 때 수행된 작업의 감사 레코드를 검색할 수도 있습니다.
  
### <a name="reverting-the-mailboxes-to-their-previous-state"></a>사서함을 이전 상태로 되버려

6단계에서 유출된 데이터를 삭제하기 전에 사서함을 준비하기 위해 사서함 구성을 변경한 경우 이전 상태로 되걸려야 합니다. 보류된 클라우드 기반 사서함의 복구 가능한 항목 폴더에 있는 항목 삭제의 "6단계: 사서함을 이전 상태로 [되찾기"를 참조합니다.](delete-items-in-the-recoverable-items-folder-of-mailboxes-on-hold.md#step-6-revert-the-mailbox-to-its-previous-state)
  
### <a name="deleting-the-search-query"></a>검색 쿼리 삭제

3단계에서 작성하고 사용한 검색 쿼리의 키워드에 실제 유출된 데이터의 일부가 포함되어 있는 경우 추가 데이터 유출을 방지하려면 검색 쿼리를 삭제해야 합니다.
  
1. 보안 및 준수 센터에서 eDiscovery 사례를 열고 검색 페이지로 이동한 다음 적절한 콘텐츠 검색을 선택합니다. 

2. 플라이아웃 페이지에서 **삭제를 클릭합니다.**

    ![검색을 선택한 다음 플라이아웃 페이지에서 삭제를 클릭합니다.](../media/O365-eDiscoverySolutions-DataSpillage-DeleteSearch.png)

### <a name="auditing-the-data-spillage-investigation-process"></a>데이터 유출 조사 프로세스 감사

감사 로그에서 조사 중에 수행된 eDiscovery 활동을 검색할 수 있습니다. 감사 로그를 검색하여 7단계에서 실행한 **New-ComplianceSearchAction -Purge** 명령에 대한 감사 레코드를 반환하여 유출된 데이터를 삭제할 수도 있습니다. 자세한 내용은 다음을 참조하세요.

- [감사 로그 검색](search-the-audit-log-in-security-and-compliance.md)

- [감사 로그에서 eDiscovery 활동 검색](search-for-ediscovery-activities-in-the-audit-log.md)

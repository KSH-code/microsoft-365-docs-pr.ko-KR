---
title: Microsoft 365 규정 준수의 새로운 기능
f1.keywords:
- NOCSH
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
description: 준수 센터에 새로운 새 솔루션을 추가 하 고, 사용자 의견에 따라 기존 기능을 업데이트 하거나, 새로운 문서 및 업데이트 된 설명서를 롤아웃할 지 여부에 관계 없이 Microsoft 365에서는 지속적인 변경 준수 가로를 유지 하는 데 도움이 됩니다. 이번 달에 제공 된 내용을 확인 합니다.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: cf019e15b1d5b915c58325c7d7c6f160acffe03e
ms.sourcegitcommit: 82d8be71c5861a501ac62a774b306a3fc1d4e627
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/10/2020
ms.locfileid: "48988856"
---
# <a name="whats-new-in-microsoft-365-compliance"></a>Microsoft 365 규정 준수의 새로운 기능

[Microsoft 365 준수 센터](microsoft-365-compliance-center.md)에 새로운 솔루션을 추가 하거나, 사용자 의견을 기반으로 기존 기능을 업데이트 하거나, 새로운 문서 및 업데이트 된 설명서를 배포 하는 경우, Microsoft 365를 통해 지속적으로 변화 하는 준수 가로를 유지 하는 데 도움이 됩니다. 현재 Microsoft 365 준수의 새로운 기능을 확인 하려면 아래를 확인 하세요. 

> [!NOTE]
> 일부 준수 기능은 고객에 게 다양 한 속도로 롤아웃 됩니다. 아직 기능을 볼 수 없는 경우 대상 지정 된 [릴리스에](https://docs.microsoft.com/office365/admin/manage/release-options-in-office-365)자신을 추가 해 보세요.


> [!TIP]
> 다른 관리 센터에서 어떤 작업을 진행 하 고 싶으십니까? 다음 문서를 확인 하세요.<br>[Microsoft 365 관리 센터의 새로운 기능](https://docs.microsoft.com/office365/admin/whats-new-in-preview?view=o365-worldwide)<br>[SharePoint 관리 센터의 새로운 기능](https://docs.microsoft.com/sharepoint/what-s-new-in-admin-center)<br>[Microsoft 365 Defender의 새로운 기능](https://docs.microsoft.com/microsoft-365/security/mtp/whats-new)<br><br>
[Microsoft 365 로드맵을](https://www.microsoft.com/en-us/microsoft-365/roadmap) 방문 하 여 시작 되었거나, 배포 중이거나, 개발 중 이거나, 이전에 출시 된 microsoft 365 기능에 대해 알아보세요.

## <a name="august-2020"></a>2020년 8월

### <a name="spotlight-insider-risk-and-communication-compliance-updates"></a>스포트라이트: 참가자 위험 및 통신 준수 업데이트

이번 달에는 몇 가지 새로운 기능 및 향상 된 기능이 공개 미리 보기에 방문 합니다.

**내부자 위험 관리**

- 새 [정책 템플릿](insider-risk-management-policies.md#policy-templates)6 개를 확인 하세요.
    - 우선 순위 사용자 별 데이터 유출
    - 불만 사용자에의 한 데이터 유출
    - 일반 보안 정책 위반
    - Departing 사용자의 보안 정책 위반
    - 우선 순위 사용자 별 보안 정책 위반
    - 불만 사용자에의 한 보안 정책 위반

- 끝점에 [대 한 Microsoft defender](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) 와의 통합을 통해 새 보안 위반 정책 템플릿에서 만든 정책으로 검색 된 활동에 대해 microsoft Defender for endpoint alerts를 가져오고 필터링 할 수 있습니다. 끝점 경고 심사 상태에 대 한 Microsoft Defender를 기반으로 하는 위험 관리를 위해 보안 경고를 가져오도록 선택할 수 있는 관련 된 [참가자 위험 설정](insider-risk-management-settings.md#microsoft-defender-for-endpoint-preview) 도 있습니다.

    > [!NOTE]
    > Microsoft Defender for Endpoint 통합용 (새 보안 정책 위반 서식 파일 포함)을 활용 하려면 조직에 끝점을 구성 하는 Microsoft Defender가 있어야 합니다. 또한 [Microsoft defender For endpoint의 고급 기능을 구성](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-features#share-endpoint-alerts-with-microsoft-compliance-center)하 여 사용자의 참가자 위험 관리 통합을 위해 microsoft Defender for endpoint을 사용 하도록 설정 해야 합니다.
 
- [정책을 만들](insider-risk-management-policies.md#create-a-new-policy)때 표시기 임계값을 사용자 지정 합니다.
- [우선 순위 사용자 그룹](insider-risk-management-settings.md#priority-user-groups-preview) 을 설정 하 여 조직의 사용자를 정의 하 고, 해당 활동은 중요 한 정보에 대 한 액세스 수준 또는 위험 기록 등의 요소를 기반으로 하 여 더 근접 한 검사를 수행 합니다.
- Office 365 관리 활동 Api를 사용 하 여 조직에서 참가자 위험 데이터를 관리 하거나 집계 하는 데 사용할 수 있는 다른 응용 프로그램으로 [참가자 위험 알림 세부 정보를 내보냅니다](insider-risk-management-settings.md#export-alerts-preview) .
- 새 [도메인 설정은](insider-risk-management-settings.md#domains-preview) 특정 도메인의 활동에 대 한 위험 수준을 정의 하 고 제어 하는 데 도움이 됩니다.

**커뮤니케이션 규정 준수**

- [알림에서 메시지를 검토할](communication-compliance-investigate-remediate.md#step-3-decide-on-a-remediation-action)때 이제 Microsoft 팀 채널, 1:1 및 그룹 채팅에서 부적절 한 메시지를 제거할 수 있습니다. 제거 된 메시지 및 콘텐츠는 중요 한 콘텐츠로 인해 제거 되었음을 설명 하는 정책 팁으로 대체 됩니다.
- 새 [통신 역할](communication-compliance-configure.md#step-1-required-enable-permissions-for-communication-compliance) (9 월의 새 통신 준수 역할 그룹 릴리스에도 포함 됩니다.)
- [개인 정보 보호](communication-compliance-feature-reference.md#privacy-preview) 및 [알림 서식 파일](communication-compliance-feature-reference.md#notice-templates)에 대 한 설정이 포함 된 새로운 통신 준수 설정 환경
- 성인용, racy 및 gory 이미지를 검색 하는 데 도움이 되는 새로운 [분류자](communication-compliance-feature-reference.md#classifiers) 입니다.
- [경고에서 메시지를 검토할](communication-compliance-investigate-remediate.md#step-2-examine-the-message-details) 때 표시 되는 새 ' 패턴 감지 ' 알림이 사용자에 의해 동일한 동작이 발생 한 것을 알 수 있습니다.

### <a name="sensitivity-labels"></a>민감도 레이블

- 미국 정부 테넌트(GCC, GCC-H 및 DoD)의 경우 민감도 레이블은 현재 Azure Information Protection 통합 레이블 지정 클라이언트 및 스캐너에 대해서만 지원됩니다. 자세한 내용은 [Azure Information Protection Premium 정부 서비스 설명](https://docs.microsoft.com/enterprise-mobility-security/solutions/ems-aip-premium-govt-service-description)을 참조하세요.
- 이제 [보안 & 준수 센터 PowerShell을 사용](create-sensitivity-labels.md#use-powershell-for-sensitivity-labels-and-their-policies) 하 여 레이블 관리 센터에 표시 되는 모든 설정을 만들고 구성할 수 있습니다. 즉, 레이블 관리 센터에서는 사용할 수 없는 설정에 PowerShell을 사용 하는 것 외에도 민감도 레이블 및 민감도 레이블 정책의 생성 및 유지 관리를 완벽 하 게 스크립팅할 수 있습니다.

### <a name="records-management-content-overhaul"></a>레코드 관리: 콘텐츠 overhaul

배포 단계를 포함 하는 새 문서, 콘텐츠를 레코드로 표시, 레코드 버전 관리:

- [레코드 관리 시작](get-started-with-records-management.md)
- [보존 레이블을 사용하여 레코드 선언](declare-records.md)
- [레코드 버전 관리를 사용하여 SharePoint 또는 OneDrive에 저장된 레코드 업데이트](record-versioning.md)

### <a name="retention-labels--policies"></a>보존 레이블 & 정책

이제 보존 관련 관리 활동이 기록 되 고 감사 로그에서 검토할 수 있습니다. 전체 목록은 [보존 정책 및 보존 레이블 활동](search-the-audit-log-in-security-and-compliance.md#retention-policy-and-retention-label-activities)을 참조하세요.

### <a name="advanced-ediscovery"></a>Advanced eDiscovery

- [검토 집합에 모음을 추가할](add-data-to-review-set.md#define-options-to-scope-your-collection-for-review)때 최신 첨부 파일 ("클라우드 첨부 파일"이 라고도 함) 및 SharePoint 문서 버전을 포함할 수 있습니다.
- 새 [직접 다운로드 내보내기 환경을](export-documents-from-review-set.md)사용 하 여 서비스 케이스 콘텐츠를 다운로드할 수 있는 Azure Storage Explorer를 사용할 필요가 없습니다.


## <a name="july-2020"></a>2020년 7월

### <a name="spotlight-on-help-docs"></a>도움말 문서에 대 한 스포트라이트

조직의 중요 한 데이터를 보호 하 고 제어 하는 데 사용 되는 준수 솔루션을 쉽게 이해할 수 있도록 두 개의 새 랜딩 페이지를 만든 후 관련 문서 링크를 비롯 하 여 이러한 목표를 달성 하는 방법에 대해 간략하게 설명 합니다.

[Microsoft 365의 microsoft Information Protection](information-protection.md)<br>
[Microsoft 365의 microsoft 정보 거 버 넌 스](manage-Information-governance.md)

### <a name="advanced-ediscovery-add-non-custodial-data-sources-to-your-cases"></a>고급 eDiscovery: 사례에 custodial 되지 않는 데이터 원본 추가

Custodian ( [비 custodial 데이터 원본](non-custodial-data-sources.md))과 연결 하지 않고 사례에 데이터를 추가 합니다. 이 custodial 데이터를 보존 해야 하는 경우 새 고급 인덱싱 기능을 사용 하 여이 작업을 수행할 수 있습니다.

### <a name="data-connectors-hr-connector-enhancements"></a>데이터 커넥터: HR 커넥터 향상

(미리 보기) 새 버전의 [HR 커넥터](import-hr-data.md) 를 사용 하면 작업 수준 변경, 성능 검토 및 성능 향상 계획과 관련 된 데이터를 가져올 수 있습니다. 이 데이터는 여러 가지 [참가자 위험 정책](insider-risk-management-policies.md) 에서 관련 작업을 검색 하는 데 사용할 수 있습니다.

### <a name="retention-labels-new-support-for-email"></a>보존 레이블: 새 전자 메일 지원

이제 메시지의 레이블이 지정 된 시기를 기반으로 전자 메일 보존을 시작 하는 [보존 레이블을](retention.md#retention-labels) 만들 수 있습니다. 이 설정은 항목 전송 시기에 따라 보존 되는 일정 항목에는 적용 되지 않습니다.

### <a name="sensitivity-labels-new-feature-and-an-improvement"></a>민감도 레이블: 새로운 기능 및 개선

- (미리 보기) 레이블에 대 한 암호화 설정을 구성 하는 경우 [이중 키 암호화](encryption-sensitivity-labels.md#double-key-encryption) 를 사용 하 여 레이블이 지정 된 파일 및 전자 메일을 더 보호 하기 위한 새 옵션을 찾습니다.
- 민감도 레이블을 만들거나 삭제 하거나 레이블 정책을 만들거나 편집 하거나 삭제 하는 경우 변경 내용이 이제 1 시간 내에 모든 사용자, 앱 및 서비스와 동기화 됩니다.

## <a name="june-2020"></a>2020년 6월

### <a name="spotlight-new-data-connectors-hit-preview"></a>스포트라이트: 새 데이터 연결선 적중 미리 보기

고객의 약속을 기반으로 하 여 타사 소스에서 Microsoft 365로 데이터를 가져올 수 있도록 하기 위해 두 가지 추가 데이터 커넥터의 미리 보기 릴리스를 발표 했습니다.

- [Bloomberg 메시지](archive-bloomberg-message-data.md) Bloomberg 메시지 공동 작업 도구에서 금융 서비스 전자 메일 데이터를 가져오고 보관 합니다. 데이터를 사서함에 저장 한 후에는 소송 보존, 콘텐츠 검색, 원본 위치 보관, 감사, 통신 준수 및 보존 정책과 같은 규정 준수 기능의 데이터에 액세스 하 여 사용할 수 있습니다.
- [얼음 채팅](archive-icechat-data.md) ICE Chat 공동 작업 도구에서 금융 서비스 채팅 데이터를 가져오고 보관 합니다. 데이터를 사서함에 저장 한 후에는 소송 보존, eDiscovery, 보관, 감사, 통신 준수 및 보존 정책과 같은 규정 준수 기능의 데이터에 액세스 하 여 사용할 수 있습니다.

### <a name="compliance-score--compliance-manager-the-hits-keep-coming"></a>준수 점수 & 준수 관리자: 방문 횟수 유지

6 월 업데이트에는 [준수 점수](compliance-score.md)에 대 한 새로운 평가 드릴 다운 보기가 포함 되어 있습니다. 제어 진행률을 모니터링 하 고, 추가 하 고, 규정 준수 점수에서 직접 삭제 합니다.

준수 점수 및 준수 관리자에 대 한 업데이트를 최신 상태로 유지 하 고 싶으십니까? [규정 준수 점수 릴리즈 정보](compliance-score-release-notes.md) 를 책갈피로 자주 확인 합니다.

## <a name="may-2020"></a>2020년 5월

### <a name="spotlight-data-classification-is-officially-released"></a>스포트라이트: 데이터 분류가 공식적으로 릴리스 되었습니다.

데이터 분류, 즉, '[데이터 파악](data-classification-overview.md)', 기능 (분석, 콘텐츠 탐색기 및 활동 탐색기)은 미리 보기 단계에서 나눈 것 이며 모든 조직에서 사용할 수 있습니다. 강력한 통찰력 및 도구를 사용 하면 조직 전체의 콘텐츠에 중요 한 정보 및 레이블 (보존 및 민감도)을 활용 하는 방식을 검색 하 고 평가할 수 있습니다. 중요 한 정보가 포함 된 콘텐츠를 검토 하거나 레이블이 적용 되 고, Microsoft 365 위치 간 레이블 작업을 탐색 하 고, 사용자 지정 중요 한 정보 유형을 만듭니다.

비디오 둘러보기 사용 ...

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4vx8x]

### <a name="trainable-classifiers-a-fix-and-a-feature"></a>Trainable 분류자: 수정 및 기능

Trainable 분류자를 보다 향상 시킬 수 있습니다.

- 사용자 의견을 기반으로 하는 수정 프로그램: 고객 지정 분류자의 초기값을 설정 하 고 학습 하면 더 이상 SharePoint 사이트 Url 및 폴더 경로를 입력 하지 않아도 됩니다. 이제 사이트 및 폴더의 미리 채우기 목록에서 선택할 수 있습니다.
- 새 기능: 민감도 레이블을 만들고 Office 앱에 대 한 자동 레이블 설정을 구성 하는 경우 이제 trainable 분류자와 일치 하는 콘텐츠에 레이블을 자동으로 적용 하거나 사용자가 적용할 수 있도록 권장 합니다. [자세한 정보](apply-sensitivity-label-automatically.md#configuring-trainable-classifiers-for-a-label)

### <a name="communication-compliance-yammer-support-is-here"></a>통신 준수: Yammer 지원이 제공 됩니다.

개인 메시지 및 Yammer의 공용 커뮤니티 대화는 통신 준수 정책에서 지원 됩니다. Yammer는 선택적 채널 이며, 메시지 및 첨부 파일의 검색을 지원 하려면 [기본 모드](https://docs.microsoft.com/yammer/configure-your-yammer-network/overview-native-mode) 에 있어야 합니다.

### <a name="data-loss-prevention-new-sharing-restriction"></a>데이터 손실 방지: 새 공유 제한

SharePoint 또는 OneDrive의 콘텐츠를 보호 하는 DLP 정책을 설정할 때 이제 "콘텐츠에 대 한 액세스 제한" 작업을 구성 하 여 '[링크를 포함 하는 사용자](https://support.microsoft.com/office/share-files-outside-your-organization-with-anyone-links-53e91027-fb8e-4a6e-a3e4-5df4be32e38a)' 옵션을 통해 콘텐츠에 대 한 액세스 권한을 부여 받은 사용자를 차단할 수 있습니다.

### <a name="insider-risk-management-tailor-your-alert-volume"></a>참가자 위험 관리: 경고 볼륨을 조정 합니다.

참가자 위험 정책에 따라 검색 되는 사용자 활동에는 특정 위험 점수가 할당 되며이 점수에는 경고 심각도 (낮음, 중간, 높음)가 지정 됩니다. 기본적으로 Microsoft 365에서는 특정 양의 낮음, 중간 및 높음 심각도 알림을 생성 하지만 새 [경고 볼륨 설정을](insider-risk-management-settings.md#alert-volume)사용 하 여 요구 사항에 맞게 볼륨을 올리거나 낮출 수 있습니다.

### <a name="pst-import-new-region-supported"></a>PST 가져오기: 새 지역이 지원 됨

이제 미국 아랍/아랍에미리트에서 네트워크 업로드를 사용할 수 있습니다.

### <a name="sensitivity-labels-new-privacy-option"></a>민감도 레이블: 새 개인 정보 옵션

레이블에 대해 [사이트 및 그룹 설정을](sensitivity-labels-teams-groups-sites.md#how-to-configure-groups-and-site-settings) 구성 하는 경우 이제 개인 정보 옵션을 **없음-사용자가 사이트에 액세스할 수 있는 사람을 선택** 하도록 설정할 수 있습니다. 이 기능은 민감도 레이블을 사용 하 여 컨테이너의 콘텐츠를 보호 하려는 경우에 유용 하지만 사용자가 개인 정보 설정을 직접 구성할 수 있도록 합니다.

## <a name="april-2020"></a>2020년 4월

### <a name="records-management-overhauland-a-new-addition"></a>레코드 관리: Overhaul 새 추가

4 월에는 레코드 관리 솔루션에 대 한 몇 가지 주요 업데이트가 포함 되어 있습니다.

- 이제 ' 레코드 관리 ' 섹션을 준수 센터에서 모두 사용할 수 있습니다. 파일 계획, 보존 레이블 및 라벨 정책, 이벤트 및 폐기에 대 한 업데이트 된 사용자 인터페이스 및 기능을 활용 합니다.
- 처리에 대해서는 SharePoint 및 OneDrive의 레코드에 대 한 [처리 증거](disposition.md#disposition-of-records) 를 제공 하기도 합니다. 이제 자동 또는 폐기 검토 후에 해당 위치에 있는 항목의 목록을 볼 수 있습니다.

### <a name="sensitivity-labels-preview-auto-labeling-policies"></a>민감도 레이블: 자동 레이블 지정 정책 미리 보기

자동 레이블 정책을 사용 하 여 이미 저장 된 SharePoint 및 OneDrive 문서 (즉,의 데이터 원본) 및 이미 보내거나 받은 전자 메일 (즉, ' 전송 중 전자 메일 ')에 민감도 레이블을 자동으로 적용할 수 있습니다. 이 레이블 지정은 앱이 아닌 서비스에 의해 적용 되므로 사용자에 게 어떤 앱과 어떤 버전이 있는지 신경 쓰지 않아도 됩니다.

이 기능은 민감도 레이블을 만들 때 ' Office 앱에 대 한 자동 레이블 지정 ' 설정에 이미 포함 되어 있는 기존 클라이언트 쪽 레이블을 확장 합니다. 자동 레이블 옵션을 사용 하는 경우의 차이와 이점을 최대한 활용 하려면 [업데이트 된 문서를 참조](apply-sensitivity-label-automatically.md)하세요.

## <a name="march-2020"></a>2020년 3월

### <a name="introducing-advanced-audit"></a>고급 감사 소개

[고급 감사 Microsoft 365에서는](advanced-audit.md) 조직에서 법적 및 규정 준수 조사를 지원할 수 있는 새로운 감사 기능을 소개 합니다. 여기에는 감사 로그의 장기 보존, 사용자 지정 감사 로그 보존 정책, 새 *Mail항목 액세스* 된 사서함 감사 작업 및 새 테 넌 트 수준 제한 제한이 도입 되어 조직에서 감사 데이터에 액세스 하기 위한 자체의 완전 하 게 할당 되는 대역폭 할당량을 제공 하는 기능이 포함 됩니다.

### <a name="compliance-score--compliance-manager-preview-the-latest-enhancements"></a>준수 점수 & 준수 관리자: 최신 향상 기능 미리 보기

이 preview 릴리스의 주요 업데이트는 다음과 같습니다.

- 템플릿을 만들고 수정 하기 위한 간소화 된 프로세스
- 템플릿 및 작업에 대 한 버전 관리 알림 및 컨트롤
- 그룹 간 공통 작업 동기화
- 현재 언어 지원이 중국어 (간체), 중국어 (번체), 프랑스어, 독일어, 이탈리아어, 일본어, 한국어, 포르투갈어 (브라질), 러시아어 및 스페인어로 확장

[준수 점수](compliance-score.md) 및 [준수 관리자](compliance-manager-overview.md) 에 대해 자세히 알아보기

### <a name="sensitivity-labels-support-for-labeling-office-files-in-sharepoint-and-onedrive-preview"></a>민감도 레이블: SharePoint 및 OneDrive에서 Office 파일 레이블에 대 한 지원 (미리 보기)

미리 보기를 사용 하면 사용자가 웹에서 Office의 민감도 레이블을 적용할 수 있습니다. 리본 메뉴의 **민감도** 단추와 상태 표시줄에 적용 된 레이블 이름을 볼 수 있습니다. 또한 데스크톱 앱을 사용 하 여 SharePoint 또는 OneDrive에 해당 파일을 레이블을 지정한 다음 저장 하면 레이블에 암호화 설정이 적용 된 경우 Microsoft 365에서 이러한 파일의 내용을 처리할 수 있습니다. 공동 작업, eDiscovery, 데이터 손실 방지, 검색 및 기타 공동 작업도 이러한 상황에서 지원 됩니다.

[미리 보기를 사용 하도록 설정 하는 방법을 알아봅니다.](sensitivity-labels-sharepoint-onedrive-files.md)

## <a name="february-2020"></a>2020년 2월

### <a name="insider-risk-management-is-officially-released"></a>Insider 위기 관리 공식적으로 출시 됨

드럼 롤, ...<br>이제 다음과 같은 구독이 있는 조직에서 참가자 위험 관리를 사용할 수 있습니다.

- [Microsoft 365 E5](https://go.microsoft.com/fwlink/?linkid=2120431) (유료 또는 평가판)
- [Microsoft](https://go.microsoft.com/fwlink/?linkid=2120432) 365 Enterprise E3 구독을 포함 합니다.

[새 역할 그룹과](insider-risk-management-configure.md#step-1-enable-permissions-for-insider-risk-management) [솔루션 수준 설정을](insider-risk-management-configure.md#step-4-configure-insider-risk-settings)비롯 하 여 preview 릴리스 이후 몇 가지 향상 된 기능을 제공 했습니다.

계속 해 서 개선할 수 있도록 항상 솔루션을 사용할 때 피드백을 남겨 두세요.

### <a name="records-management"></a>레코드 관리

이 새로운 솔루션은 모든 레코드 관리 기능을 단일 우산에 제공 합니다. 여기에는 SharePoint 및 OneDrive에 대 한 레코드 버전 관리와 레코드에 대 한 삭제 증명의 도입이 포함 되어 있습니다.

![Microsoft 365 준수 센터의 레코드 관리 페이지](../media/mcc-records-management-page.png)

[레코드 관리에 대해 자세히 알아보기](records-management.md)

### <a name="solution-spotlight-data-connectors-for-facebook-and-twitter"></a>솔루션 추천: Facebook 및 Twitter의 데이터 커넥터

[지난 달에 출시](#just-launched) 된 데이터 커넥터는 다음과 같은 커넥터를 테스트 하는 데 도움이 되는 정보를 찾고 있습니다.

- [Facebook business 페이지](archive-facebook-data-with-sample-connector.md) Facebook business pages에서 Microsoft 365로 데이터를 가져오고 보관 합니다. 레코드 관리 및 eDiscovery와 같은 규정 준수 솔루션에 유용 합니다.
- [Twitter](archive-twitter-data-with-sample-connector.md) Twitter에서 Microsoft 365로 데이터를 가져오고 보관 합니다. 레코드 관리 및 eDiscovery와 같은 규정 준수 솔루션에 유용 합니다.

이러한 커넥터를 설정 하 고 유효성을 검사할 때,이에 대 한 자세한 내용은 무엇이 고 그렇지 않으며 환경을 개선 하기 위해 수행할 수 있는 작업에 대 한 의견을 보내 주시기 바랍니다.

## <a name="january-2020"></a>2020년 1월

대기가 종료 됩니다. Microsoft 365 준수 센터는 Microsoft 365, Office 365, Enterprise Mobility + Security (EMS) 및 Windows 10 Enterprise 요금제를 사용 하는 모든 고객에 게 제공 된다는 것을 알 수 있습니다. 보안 & 준수 센터에서 관리 하는 모든 데이터 또는 정책을 준수 센터에서 사용할 수 있으므로, 앞뒤로 이동할 필요가 없습니다.

> [!TIP]
> 최근 매월 미리 본 [솔루션](#new-compliance-solutions) 및 보안 & 준수 센터의 준수 기능이 Microsoft 365에 살고 있는 위치를 보여주는 [로드맵](#updated-compliance-solutions) 에 대 한 자세한 내용은 지난 달의 업데이트를 다시 읽어 보십시오.

책갈피와 head to a now to a [https://compliance.microsoft.com](https://compliance.microsoft.com) -stop-상점을 여행 하 여 조직 전체에서 준수를 관리 합니다. [이 문서를 읽으면](microsoft-365-compliance-center.md) 좀 더 자세히 알아볼 수 있습니다.

![Microsoft 365 준수 센터 홈 페이지](../media/mcc-home-ga.png)

이번 달에 새로 추가 되 고 업데이트 된 솔루션도 출시 되었습니다. 아래에서 하이라이트를 간략하게 살펴봅니다.

### <a name="now-in-preview"></a>현재 미리 보기

**참가자 위험 관리 (미리 보기)**

이제 여러분의 참가자 위험 관리 솔루션이 공개 미리 보기에 있음을 알리는 것이 좋습니다. 간단히 말해서, 참가자 위험 관리를 통해 조직은 다음을 제공 하 여 사용자의 참가자 위험을 체계적으로 파악 하 고 조치를 취할 수 있습니다.

- 사용자 개인 정보를 보장 하는 데 도움이 되는 익명 제어
- 데이터 누수와 같은 참가자 위협을 식별 하는 기본 및 타사 지표를 포함 하는 지능형 정책 템플릿
- IT, HR 및 법률 팀 전반에 걸쳐 있는 통합 된 종단 간 조사 워크플로

당신이 생각 하는 것을 환영 합니다. 이 솔루션을 사용 하는 경우에는 일반적인 가용성으로 인해 요구 사항을 충족 하는 데 도움이 되도록 의견을 남길 수 있습니다.

[참가자 위험 관리에 대해 자세히 알아보기](insider-risk-management.md)

### <a name="just-launched"></a>방금 시작한 항목만

**커뮤니케이션 규정 준수**

Preview 단계에서 모든 가용성으로 Graduating, 통신 준수는 새로운 참가자 위험 솔루션 집합의 핵심 구성 요소입니다. 이 강력한 솔루션을 사용 하면 조직의 표준을 충족 하지 않는 메시지를 검색 하 고 조사 하 고 수정 작업을 수행 하는 워크플로를 통해 통신 위험을 최소화할 수 있습니다.

미리 보기 중에 고객 의견은 매우 즐겁게 제공 됩니다. 시작 하는 첫 번째 실행 환경, 조사 및 재구성 작업에 대 한 개선 사항 등을 비롯 하 여 몇 가지 향상 된 기능을 제공 합니다.

[통신 준수에 대해 자세히 알아보기](communication-compliance.md)

![시작 환경의 첫 번째 카드를 보여 주는 Microsoft 365 준수 센터의 통신 준수 페이지](../media/mcc-communication-compliance-page-with-fre.png)

**데이터 커넥터**

이전에는 Office 365 보안 & 준수 센터의 다른 ' 가져오기 ' 기능을 사용 하는 것이 더 중요 한 것으로, 이제 데이터 커넥터에는 Microsoft 365 준수 센터의 자체 홈이 제공 됩니다. 새 ' 데이터 커넥터 ' 페이지를 사용 하 여 조직의 HR (인적 자원) 파일 및 다양 한 타사 플랫폼 (예를 들어, Facebook, LinkedIn, Twitter, 인스턴트 Bloomberg)의 데이터를 Microsoft 365 조직의 사서함으로 가져오고 보관 합니다. 이 데이터를 가져온 후에는 eDiscovery, 참가자 위험 관리, 통신 준수, 감사, 보존 정책 등을 포함 하 여 여러 준수 솔루션에서이 데이터가 관리 될 수 있습니다.

[데이터 커넥터에 대 한 자세한 정보](archiving-third-party-data.md)

![Microsoft 365 준수 센터의 데이터 커넥터 페이지](../media/mcc-data-connectors-page.png)

### <a name="noteworthy-updates"></a>중요 한 업데이트

**규정 준수 점수에 대 한 새로운 평가 템플릿 (미리 보기)**

지속적으로 변화 하는 준수 점수를 제공 하는 데 도움이 되는 새로운 서식 파일 집합을 사용 하 여 최근 규정에 대 한 조직의 준수 상태를 평가 하 고 보다 효과적인 제어를 구현 하는 방법에 대 한 지침을 얻을 수 있습니다. 다음에 대 한 새 템플릿이 표시 됩니다.

- ISO/IEC 27701:2019
- 캘리포니아 소비자 개인 정보 보호법(CCPA)
- 브라질 일반 데이터 보호 법 (Lei Geral de Proteção de Dados-LGPD)
- SOC 1 유형 2 및 SOC 2 유형 2

[준수 점수 서식 파일에 대해 자세히 알아보기](compliance-score.md#templates)

## <a name="november--december-2019"></a>& 년 11 월 2019 일

휴일을 통해 Ignite에서 데모 인 모든 훌륭한 준수 솔루션을 롤아웃하기 시작 했습니다. 대부분의 경우 미리 보기 상태가 되므로 테스트를 수행 하 여 준수 센터의 오른쪽 아래에 있는 피드백 카드를 열어 의견을 알려주세요.

![의견](../media/Feedback_card_MCC.JPG)

### <a name="get-to-know-the-new-neighborhood"></a>새 환경을 알아보기 위해 가져오기

새로운 Microsoft 365 준수 센터에는 Office 365 보안 & 준수 센터에서 알고 있고 좋아하는 규정 준수 기능 뿐만 아니라 새로운 새 솔루션도 포함 되어 있습니다. 좀 더 자세히 살펴보겠습니다.

#### <a name="new-compliance-solutions"></a>새 규정 준수 솔루션

*해결 방법이* 궁금할 것입니다. 클라우드가 비즈니스를 수행 하는 방식으로 revolutionized, 새로운 데이터 절도 및 사기 및 소유권이 필요한 새 규정을 위한 도어가 열렸습니다. 당사의 준수 솔루션은 이러한 개선 된 준수 요구 사항을 관리 하는 데 도움이 되는 통합 기능 모음입니다. 솔루션의 기능에는 정책, 경고, 보고서 등의 조합이 포함 될 수 있습니다.

다음은 새 솔루션을 찾을 수 있는 요약입니다. 다른 사용자가 곧 출시 될 것을 고려 하세요.

> [!NOTE]
> 이러한 솔루션은 Microsoft 365 준수 센터에만 있습니다. Office 365 보안 & 준수 센터에서는 관리할 수 없습니다.
<br/>

|**새 솔루션**|**설명**|**자세한 정보**|
|:-----|:-----|:-----|
|Microsoft 준수 점수 (미리 보기) <br/>|규정 준수 [관리자](compliance-manager-overview.md)가 작성 한 준수 점수는 조직의 규정 준수 상태를 이해 하 고 향상 시키는 데 도움이 되는 보다 간단 하 고 사용자에 게 친숙 한 디자인을 갖춘 독립 실행형 기능입니다. 데이터 보호 및 규정 표준에 대 한 위험을 줄이는 데 도움이 되는 작업 완료의 진행 상태를 측정 하는 위험 기반 점수를 계산 합니다. <br/>|[Microsoft 준수 점수 개요 (미리 보기)](compliance-score.md)|
|솔루션 카탈로그 (미리 보기) <br/>|솔루션 카탈로그는 규정 준수 및 위험 관리 솔루션을 검색 하 고 학습 하며 빠르게 시작할 수 있는 1-스톱-상점입니다. 카탈로그는 세 가지 준수 범주로 구성 되며 각각에 해당 범주를 구성 하는 솔루션에 대 한 세부 정보를 포함 합니다. 종류에는 정보 보호 & 거 버 넌 스, 참가자 위험 관리 및 검색 & 응답이 포함 됩니다. <br/>|[솔루션 카탈로그 개요 (미리 보기)](microsoft-365-solution-catalog.md)|
|통신 준수 (미리 보기) <br/>|통신 준수는 조직의 부적절 한 메시지에 대해 검색, 캡처 및 수정 작업을 수행 하 여 통신 위험을 최소화 하는 데 도움이 되는 새로운 참가자 위험 관리 범주의 일부입니다. 이 솔루션은 지능형 서식 파일, 유연한 재구성 워크플로 및 실행 가능한 통찰력과 같은 새로운 향상 된 기능을 도입 하 여 Office 365의 감독 정책 기능을 확장 합니다. <br/>|[Microsoft 365의 통신 준수 (미리 보기)](communication-compliance.md)|
|데이터 분류 (미리 보기) <br/>|새 데이터 분류 페이지에는 조직 전체의 콘텐츠에 중요 한 정보 및 레이블 (보존 및 민감도)이 사용 되는 방식을 검색 하 고 평가 하는 데 도움이 되는 강력한 통찰력 및 도구가 포함 되어 있습니다. 중요 한 정보가 포함 된 콘텐츠를 검토 하거나 레이블이 적용 되 고, Microsoft 365 위치 간 레이블 작업을 탐색 하 고, 사용자 지정 중요 한 정보 유형을 만듭니다.<br/>|[데이터 분류 개요(미리 보기)](data-classification-overview.md)|
|Trainable 분류자 (미리 보기) <br/>|이 강력한 새 도구는 컴퓨터 학습 엔진을 사용 하 여 규정 문서 또는 직원 계약과 같은 조직 내 콘텐츠 범주를 식별 하는 데 도움이 됩니다. 만든 분류자는 다양 한 준수 솔루션에서 사용 하 여 관련 콘텐츠를 검색 하 고 분류 하며 보호 하 고 유지 합니다.<br/>|[학습 가능한 분류자에 대한 자세한 정 (미리 보기)](classifier-learn-about.md)|

#### <a name="updated-compliance-solutions"></a>업데이트 된 준수 솔루션

준수 요구 사항에 Office 365 보안 & 준수 센터를 사용 하 고 있는 경우 일부 기능이 이제 새로운 Microsoft 365 준수 센터에서 제공 되는 것을 궁금해 할 수 있습니다. 새 홈을 찾는 데 도움이 되는 빠른 로드맵을 소개 합니다.

> [!NOTE]
> 일부 기능은 여전히 Office 365 Security & 준수 센터에서 사용할 수 있으며 아래에 설명 되어 있습니다. 그러나 Microsoft 365 준수 센터에서이를 미리 보는 것이 좋습니다. 
<br/>

|**기능**|**Office 365 보안 및 준수 센터**|**Microsoft 365 규정 준수 센터**|**자세한 정보**|
|:-----|:-----|:-----|:-----|
|Advanced eDiscovery|eDiscovery > Advanced eDiscovery <br/> https://protection.office.com/advancedediscoverycases |eDiscovery > Advanced <br/> https://compliance.microsoft.com/advancedediscovery | [Microsoft 365의 고급 eDiscovery 솔루션 개요](overview-ediscovery-20.md) |
|알림 정책|알림 > 경고 정책 <br/> https://protection.office.com/alertpolicies |현재 경고 정책은 Office 365 보안 & 준수 센터 에서만 관리 됩니다. |[보안 및 준수 센터의 경고 정책](alert-policies.md) |
|경고|알림 > 경고 보기 <br/> https://protection.office.com/viewalerts |경고 <br/> https://compliance.microsoft.com/compliancealerts |[알림 보기](alert-policies.md#viewing-alerts)|
|보관|정보 거 버 넌 스 > 보관 함 <br/> https://protection.office.com/archiving |정보 거 버 넌 스 > 보관 함 탭 <br/> https://compliance.microsoft.com/informationgovernance?viewid=archive |[보관 사서함 사용](enable-archive-mailboxes.md)|
|감사 로그 검색|검색 > 감사 로그 검색 <br/> https://protection.office.com/unifiedauditlog |감사 <br/> https://compliance.microsoft.com/auditlogsearch | [보안 & 준수 센터에서 감사 로그 검색](search-the-audit-log-in-security-and-compliance.md)|
|콘텐츠 검색|검색 > 콘텐츠 검색 <br/> https://protection.office.com/contentsearchbeta?ContentOnly=1 | 콘텐츠 검색 <br/> https://compliance.microsoft.com/contentsearch |[Office 365에서 콘텐츠 검색](search-for-content.md) |
|데이터 커넥터|타사 데이터 보관 > 정보 관리 기능 <br/> https://protection.office.com/nativeconnector | 데이터 커넥터 <br/> https://compliance.microsoft.com/connectorlanding |[타사 데이터 보관](archiving-third-party-data.md)|
|데이터 손실 방지|데이터 손실 방지 <br/> https://protection.office.com/datalossprevention |데이터 손실 방지 <br/> https://compliance.microsoft.com/datalossprevention |[데이터 손실 방지 개요](data-loss-prevention-policies.md)|
|데이터 주체 요청 |데이터 개인 정보 > 데이터 주체 요청 <br/> https://protection.office.com/dsrcases |데이터 주체 요청 <br/> https://compliance.microsoft.com/datasubjectrequest |[DSR 사례 도구를 사용 하 여 GDPR 데이터 주체 요청 관리](manage-gdpr-data-subject-requests-with-the-dsr-case-tool.md)|
|eDiscovery|eDiscovery > eDiscovery <br/> https://protection.office.com/ediscoveryv1 |eDiscovery > 코어 <br/> https://compliance.microsoft.com/classicediscovery |[eDiscovery 사례 관리](ediscovery-cases.md) |
|Events|레코드 관리 > 이벤트 <br/> https://protection.office.com/events |레코드 관리 > 이벤트 탭 <br/> https://compliance.microsoft.com/recordsmanagement?viewid=events |[이벤트가 발생할 때 보존 시작하기](event-driven-retention.md)|
|파일 플랜|파일 계획 > 레코드 관리 <br/> https://protection.office.com/fileplan |레코드 관리 > 파일 계획 탭 <br/> https://compliance.microsoft.com/recordsmanagement?viewid=fileplan |[파일 계획을 사용하여 보존 레이블 관리](file-plan-manager.md)|
|PST 파일 가져오기|정보 거 버 넌 스 > 가져오기 PST 파일 <br/> https://protection.office.com/importV2 |정보 거 버 넌 스 > 가져오기 탭 <br/> https://compliance.microsoft.com/informationgovernance?viewid=import |[조직의 PST 파일을 가져오기 개요](importing-pst-files-to-office-365.md)|
|레이블 활동 탐색기|정보 거 버 넌 스 > 레이블 활동 탐색기 <br/> https://protection.office.com/labelexplorer |데이터 분류 > 활동 탐색기 탭 <br/> https://compliance.microsoft.com/dataclassification?viewid=activitiesexplorer |[레이블이 지정된 콘텐츠의 활동 보기(미리 보기)](data-classification-activity-explorer.md)|
|보존 레이블 및 레이블 정책 |분류 > 보존 레이블 > 레이블 및 레이블 정책 탭 <br/> https://protection.office.com/retentionlabels |정보 거 버 넌 스 > 레이블 및 레이블 정책 탭 <br/> https://compliance.microsoft.com/informationgovernance?viewid=labels <br/> https://compliance.microsoft.com/informationgovernance?viewid=labelpolicies | [보존 레이블 개요](retention.md)|
|보존 정책|정보 거 버 넌 스 > 보존 <br/> https://protection.office.com/retention |정보 거 버 넌 스 > 보존 탭 <br/> https://compliance.microsoft.com/informationgovernance?viewid=retention |[보존 정책 및 보존 레이블에 대해 알아보기](retention.md)|
|중요 한 정보 유형|분류 > 중요 한 정보 유형 <br/> https://protection.office.com/sensitivetypes |데이터 분류 > 중요 한 정보 유형 탭 <br/> https://compliance.microsoft.com/dataclassification?viewid=sensitiveinfotypes |[중요한 정보 유형 엔터티 정의](sensitive-information-type-entity-definitions.md)|
|민감도 레이블 및 레이블 정책|분류 > 민감도 레이블 > 레이블 및 레이블 정책 탭 <br/> https://protection.office.com/sensitivity |정보 보호 > 레이블 및 레이블 정책 탭 <br/> https://compliance.microsoft.com/informationprotection?viewid=sensitivitylabels <br/> https://compliance.microsoft.com/informationprotection?viewid=sensitivitylabelpolicies |[민감도 레이블에 대해 알아보기](sensitivity-labels.md) |
|서비스 보증|서비스 보증 <br/> https://protection.office.com/serviceassurance/dashboard |현재 서비스 보증 리소스는 Office 365 보안 & 준수 센터 에서만 액세스할 수 있습니다. |[보안 및 준수 센터의 서비스 보증](service-assurance.md)|
|감독|감독 <br/> https://protection.office.com/supervisoryreviewv2 |커뮤니케이션 규정 준수 <br/> https://compliance.microsoft.com/supervisoryreview |[Microsoft 365의 통신 준수 (미리 보기)](communication-compliance.md) |

## <a name="september-2019"></a>2019년 9월

이번 달에 출시 된 릴리스가 어떻게 조용한 지 궁금 하십니까? [Microsoft Ignite](https://www.microsoft.com/ignite) 의 11 월에 unveiled 되는 혁신적인 새 규정 준수 솔루션을 구축 하 고 있습니다. 계속 조정

### <a name="new-encryption-options-for-sensitivity-labels"></a>민감도 레이블의 새 암호화 옵션 

민감도 레이블에 대 한 암호화를 구성할 때 사용자가 전자 메일 및 문서에 레이블을 수동으로 적용할 때 사용 권한을 할당할 수 있는 두 가지 옵션이 있습니다.<br>
- **Outlook 전자 메일** 에 레이블을 적용할 때 사용자는 전달 금지 옵션에 해당 하는 제한을 적용할 수 있습니다. 받는 사람은 메시지를 읽을 수는 있지만 콘텐츠를 전달, 인쇄 또는 복사 하지는 못합니다.
- **Word, PowerPoint 및 Excel 파일** 에 레이블을 적용 하는 경우 사용자에 게 특정 사용자 및 그룹에 대 한 액세스 권한을 지정 하 라는 메시지가 표시 됩니다.

[민감도 레이블을 사용 하 여 콘텐츠에 대 한 액세스 제한](encryption-sensitivity-labels.md#let-users-assign-permissions) 으로 이동 하 여 자세한 내용을 확인 하 고 자세한 내용은 암호화를 적용 합니다.

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
description: 규정 준수 센터에 새 솔루션을 추가하거나, 피드백에 따라 기존 기능을 업데이트하거나, 최신 및 업데이트된 설명서를 배포하는 경우 Microsoft 365를 사용하면 계속 변화하는 규정 준수 환경의 기반을 구축할 수 있습니다. 이번 달까지의 정보를 찾아보아야 합니다.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 3688ee7390b7cadf701e8dbefd8b12c82cf6d89c
ms.sourcegitcommit: 98b889e674ad1d5fa37d4b6c5fc3eda60a1d67f3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/05/2021
ms.locfileid: "49751595"
---
# <a name="whats-new-in-microsoft-365-compliance"></a>Microsoft 365 규정 준수의 새로운 기능

[Microsoft 365](microsoft-365-compliance-center.md)규정 준수 센터에 새 솔루션을 추가하거나, 피드백에 따라 기존 기능을 업데이트하거나, 최신 및 업데이트된 설명서를 배포하는 경우, Microsoft 365는 계속 변화하는 규정 준수 환경의 최상단을 유지하도록 지원합니다. 아래에서 Microsoft 365 규정 준수의 새로운 모습을 확인하세요. 

> [!NOTE]
> 일부 규정 준수 기능은 고객에게 다른 속도로 롤아웃됩니다. 아직 기능이 없는 경우 대상 릴리스에 자신을 [추가해 보세요.](https://docs.microsoft.com/office365/admin/manage/release-options-in-office-365)


> [!TIP]
> 다른 관리 센터에서 진행할 일에 관심이 있나요? 다음 문서를 확인할 수 있습니다.<br>[Microsoft 365 관리 센터의 새로운](https://docs.microsoft.com/office365/admin/whats-new-in-preview)<br>[SharePoint 관리 센터의 새로운](https://docs.microsoft.com/sharepoint/what-s-new-in-admin-center)<br>[Microsoft 365 Defender의 새로운 기능](https://docs.microsoft.com/microsoft-365/security/mtp/whats-new)<br><br>
또한 [Microsoft 365](https://www.microsoft.com/en-us/microsoft-365/roadmap) 로드맵을 방문하여 출시, 배포 중, 개발 중, 취소 또는 이전에 릴리스된 Microsoft 365 기능에 대해 자세히 알아보는 방법을 알아보는 것이 있습니다.

## <a name="november--december-2020"></a>2020년 11월 &
일반적으로 새로운 기능 및 업데이트된 기능을 미리 보기 상태로 릴리스하여 일반 가용성에 릴리스하기 전에 개선할 수 있도록 기능 사용 방법을 배워야 합니다. 피드백은 미리 보기(및 그 이상)에 중요하기 때문에 준수 센터의 오른쪽 아래에 있는 피드백 카드를 열고 의견을 알려주세요.

![피드백](../media/Feedback_card_MCC.JPG)

### <a name="spotlight-endpoint-data-loss-prevention-dlp-released"></a>스포트라이트: 끝점 DLP(데이터 손실 방지) 릴리스

[끝점 DLP는 DLP의](endpoint-dlp-learn-about.md) 활동 모니터링 및 보호 기능을 Windows 10 장치의 중요한 정보로 확장합니다. 장치가 Microsoft [](dlp-configure-endpoints.md) 365 규정 준수 센터에 온보드된 후 DLP 정책을 설정하여 해당 디바이스의 중요한 정보를 보호할 수 있습니다.

### <a name="advanced-ediscovery"></a>Advanced eDiscovery

eDiscovery 워크플로에서 암호화된 콘텐츠를 더 쉽게 관리할 수 있도록 Microsoft 365 [](ediscovery-decryption.md) eDiscovery 도구에는 이제 전자 메일 메시지에 첨부되고 Exchange에서 전송되는 암호화된 파일의 암호 해독이 통합되어 있습니다. 또한 SharePoint 및 OneDrive에 저장된 암호화된 문서는 Advanced eDiscovery에서 암호 해독됩니다.

### <a name="compliance-manager"></a>규정 준수 관리자

- [Microsoft 365 Government](compliance-manager.md)구독 지원. 이제 준수 관리자를 미국 GCC(정부 커뮤니티) 보통 및 높음 고객이 사용할 수 있습니다.
- [준수 관리자용 Microsoft 준수 구성 분석기.](compliance-manager-mcca.md) 조직의 현재 구성을 검사하고 Microsoft 365 권장 모범 사례에 대해 유효성을 검사하여 준수 관리자를 시작하는 데 도움이 되는 새로운 PowerShell 기반 도구입니다.
- [새 서식 파일.](compliance-manager-templates-list.md) 총 준수 관리자 템플릿을 230개가 넘는 새 템플릿 56개가 추가되었습니다.

### <a name="data-connectors"></a>데이터 커넥터

[미리 보기의 5개의 새로운 Globanet 커넥터.](archiving-third-party-data.md#third-party-data-connectors) 새 커넥터에는 Reuters Dealing, Reuters FX, CellTrust, XIP, 일반 MS SQL 포함됩니다.

### <a name="retention-labels-disposition-review"></a>보존 레이블(삭제 검토)

이제는 사용자가 콘텐츠 탐색기 콘텐츠 뷰어 및 콘텐츠 탐색기 목록 [뷰어](disposition.md#permissions-for-disposition)역할 그룹의 구성원이 되어야 합니다. 항목을 검토하는 데는 필요하나 이러한 역할 그룹은 분해 검토를 완료하는 데 필요하지 않습니다.

### <a name="sensitivity-labels"></a>민감도 레이블

- [(미리 보기) SharePoint 사이트에 대한 외부 공유 설정입니다.](sensitivity-labels-teams-groups-sites.md#how-to-configure-groups-and-site-settings) 그룹 및 사이트에 사용할 레이블을 만들 때 레이블이 적용된 SharePoint 사이트의 외부 공유를 제어하는 옵션이 표시됩니다. 모든 사용자, 신규 및 기존 게스트, 기존 게스트만 또는 조직의 사용자에 대해 공유를 허용하도록 지정할 수 있습니다. 레이블이 적용되면 레이블 설정이 SharePoint 관리 센터에 구성된 외부 공유 설정을 [대체합니다.](https://docs.microsoft.com/sharepoint/change-external-sharing-site)
- [레이블이 지정된 문서에서 레이블 및 암호화를 제거합니다.](sensitivity-labels-sharepoint-onedrive-files.md#remove-encryption-for-a-labeled-document) 레이블과 암호화를 모두 SharePoint의 레이블이 지정한 문서에서 제거하려면 전역 관리자와 SharePoint 관리자가 새 `Unlock-SPOSensitivityLabelEncryptedFile` cmdlet을 실행할 수 있습니다. 이 cmdlet은 관리자가 사이트 또는 파일에 대한 액세스 권한이 없거나 Azure 권한 관리 서비스를 사용할 수 없는 경우에도 실행됩니다.

## <a name="october-2020"></a>2020년 10월

### <a name="advanced-ediscovery"></a>Advanced eDiscovery

[CJK 언어 지원.](ediscovery-cjk-support.md) Advanced eDiscovery는 이제 CJK 언어(중국어 간체, 중국어 번체, 일본어 및 한국어 포함)라고 하는 더블바트 문자 집합 언어를 지원합니다. 이러한 시나리오는 여러 고급 검토 집합 시나리오에서 사용할 수 있습니다.

### <a name="sensitivity-labels"></a>민감도 레이블

- [레이블 범위.](sensitivity-labels.md#label-scopes) 민감도 레이블을 만들 때 레이블의 범위를 정의하는 새로운 옵션이 표시됩니다. 이 옵션을 사용하면 파일 및 전자 메일, 컨테이너(예: SharePoint 사이트 및 Teams) 또는 둘 다에 대한 레이블을 구성할 수 있습니다.
- [동적 콘텐츠 표시.](sensitivity-labels-office-apps.md#dynamic-markings-with-variables) 민감도 레이블에 대한 콘텐츠 표시를 구성할 때 머리 글자, 머리 글자 또는 워터마크에 텍스트 문자열과 같은 동적 변수를 사용할 `${Item.Label}` `${Item.Location}` 수 있습니다.

## <a name="september-2020"></a>2020년 9월

### <a name="spotlight-compliance-manager"></a>스포트라이트: 준수 관리자

올해 Ignite에서 발표된 준수 점수는 준수 관리자로 [다시 브랜드가 됩니다.](compliance-manager.md) 이 릴리스는 Service Trust Portal에서 준수 관리자의 이전 홈에서 전환을 완료하고 Microsoft 365 규정 준수 센터에 종단식 준수 관리 솔루션을 도입합니다.

규정 준수 관리자가 조직에서 규정 준수를 관리하는 방법을 간소화하는 데 도움이 되는 방법을 알아보는 비디오를 시청하세요.
<br>
<br>
>[!VIDEO https://www.microsoft.com/videoplayer/embed/RE4FGYZ]

### <a name="advanced-audit"></a>고급 감사

- 감사 로그의 새로운 10년 보존은 장기적인 조사를 지원하고 규정, 법적 및 내부 의무에 대응하는 데 도움이 됩니다.
- [새로운 중요 이벤트 3개.](advanced-audit.md#access-to-crucial-events-for-investigations) 다음 새 이벤트는 발생 가능한 위반을 조사하고 송신, SearchQueryInitiatedExchange 및 SearchQueryInitiatedSharePoint와 같은 손상 범위를 결정하는 데 도움이 될 수 있습니다.

### <a name="communication-compliance"></a>커뮤니케이션 규정 준수

- [역할 그룹이 업데이트되었습니다.](communication-compliance-configure.md#step-1-required-enable-permissions-for-communication-compliance) 통신 준수 역할 그룹은 이제 내부자 위험 관리 솔루션에 사용할 수 있는 역할 그룹 구조와 일치합니다.
- [대시보드를 보고합니다.](communication-compliance-feature-reference.md#reports-preview) 모든 통신 준수 보고서를 볼 수 있는 중앙 위치입니다. 보고서 위젯은 커뮤니케이션 준수 활동의 상태를 전반적으로 평가하는 데 가장 일반적으로 필요한 인사이트를 빠르게 볼 수 있도록 합니다.
- [전원 흐름을 자동화합니다.](communication-compliance-feature-reference.md#power-automate-flows-preview) 경고 및 사용자에 대한 작업을 자동화하는 흐름을 설정하고, 사용자가 경고를 트리거할 때 관리자에게 알리는 등 작업을 수행합니다.
- ['분류 개선' 수정 작업.](communication-compliance-investigate-remediate.md#step-3-decide-on-a-remediation-action) 학습 가능한 분류자와 일치하는 항목이 포함된 경고는 피드백을 통해 조직에서 가짓 긍정을 최소화할 수 있습니다. 분류 **개선** 옵션을 사용하면 검색된 항목이 관련 통신 준수 정책에 구성된 분류자와 일치하는지 여부를 피드백을 제공할 수 있습니다. 항목과 연결하여 향후 경고에 대한 일치 정확도를 향상시킬 다른 분류자도 제안할 수 있습니다.

### <a name="data-connectors"></a>데이터 커넥터

- [새 타사 데이터 커넥터.](archiving-third-party-data.md#third-party-data-connectors) Globanet의 커넥터 14개와 Telemessage의 8개 커넥터를 포함하여 새 데이터 커넥터 25개
- [물리적 배지 커넥터](import-physical-badging-data.md) 직원의 원시 물리적 액세스 이벤트 또는 조직의 배지 시스템에서 생성된 모든 물리적 액세스 알람과 같은 물리적 배지 데이터를 가져올 수 있습니다. 예를 들어 건물, 서버 방 또는 데이터 센터에 대한 항목이 포함됩니다. 내부자 위험 관리 솔루션에서 물리적 배지 데이터를 사용하여 조직 내부의 악의적인 활동이나 데이터 도용으로부터 조직을 보호할 수 있습니다.

### <a name="insider-risk-management"></a>내부자 위험 관리

- [Microsoft Teams 통합.](insider-risk-management-settings.md#microsoft-teams-preview) 내부자 위험 설정에서 Teams 통합이 설정되어 있는 경우 개별 사례와 관련된 데이터를 안전하게 공유 및 저장하고 분석가 및 조사자의 응답 활동을 추적 및 검토하는 등 작업에서 Teams의 다른 이해 관계자와 협력할 수 있습니다.
- [전원 흐름을 자동화합니다.](insider-risk-management-settings.md#power-automate-flows-preview) 사용자, 경고 및 사례 정보를 검색하여 관련자 및 기타 앱과 공유하고 사례 메모에 게시와 같은 작업을 자동화하는 등 사례 및 사용자에 대한 중요한 작업을 자동화하는 흐름을 설정합니다.
- [활동 탐색기.](insider-risk-management-alerts.md#activity-explorer-preview) 경고를 검토할 때 사용할 수 있는 활동 탐색기는 조사자 및 분석가에게 각 경고로 드릴다운하기 위한 포괄적인 분석 도구를 제공합니다. 검색된 위험한 활동의 타임라인을 신속하게 검토하고 경고와 관련된 모든 위험 활동을 식별하고 필터링합니다.

### <a name="retention-policies-and-retention-labels"></a>보존 정책 및 보존 레이블

- [에 대한 Yammer.](retention-policies-yammer.md) 이제 보존 정책을 사용하여 커뮤니티 메시지 및 개인 Yammer 보존하고 삭제할 수 있습니다.
- [Teams 모임 녹음/녹화에 레이블을 적용합니다.](apply-retention-labels-automatically.md#microsoft-teams-meeting-recordings) 자동 레이블 지정 정책을 만들 때 키워드 쿼리 편집기를 사용하여 사용자의 OneDrive 계정 또는 SharePoint에 저장된 Teams 모임 녹음/녹화를 식별합니다.

### <a name="records-management"></a>레코드 관리

[규정 레코드 지원.](declare-records.md#how-to-display-the-option-to-mark-content-as-a-regulatory-record) 레이블을 규정 레코드로 분류하면 레이블이 적용되는 콘텐츠에 대한 제한이 증가하고 레이블 자체에 대해 사용 가능한 관리 작업을 제한합니다. 예를 들어 콘텐츠에 적용된 후 전역 관리자도 아니어도 레이블을 제거할 수 없습니다. [규제 레코드에](records-management.md#compare-restrictions-for-what-actions-are-allowed-or-blocked) 대해 허용 및 차단되는 작업에 대해 자세히 알아보습니다.

### <a name="sensitivity-labels"></a>민감도 레이블

[미국 정부 고객에 대한 지원.](https://docs.microsoft.com/enterprise-mobility-security/solutions/ems-aip-premium-govt-service-description) 이제 GCC, GCC High 및 DoD 고객에게 민감도 레이블이 지원되고 Azure Information Protection 통합 레이블 클라이언트 및 스캐너에 한해 지원됩니다.

### <a name="trainable-classifiers"></a>교육 가능한 분류자

새로운 재조정 및 피드백 기능은 모든 사용자 지정 분류자 및 사전 학습된 분류자에 대한 정확도를 개선하고 가양성 일치를 최소화하는 데 도움이 됩니다. 이 흐름을 통해 항목이 특정 분류자와 일치하는지 여부에 대한 피드백을 제공하고, 항목과 연결하기 위한 다른 분류자 제안, 일치 정확도를 구체화 및 개선하기 위한 분류자 재조정을 할 수 있습니다.

이 새로운 기능은 다음 기능에 포함되어 있습니다.

> [!NOTE]
> 모든 기능에 대해 피드백 응답을 30개 이상 제공하는 경우 검토할 수 있는 재조정된 분류자 버전을 만들게 됩니다. 개선된 경우 분류자 다시 게시할 수 있습니다.

- [학습 가능한 분류자.](classifier-learn-about.md#retraining-classifiers) 게시된 분류자의 정확도를 높이기 위해 검색된 항목이 분류자와 일치하는지 여부에 대한 피드백을 제공할 수 있습니다.
- [통신 규정 준수.](classifier-how-to-retrain-comms-compliance.md) 새로운 **분류** 수정 개선 작업을 통해 커뮤니케이션 준수 경고의 항목이 통신 준수 정책에 구성된 분류자와 일치하는지 여부를 피드백을 제공할 수 있습니다.
- [콘텐츠 탐색기.](classifier-how-to-retrain-content-explorer.md) 학습 가능한 분류자와 일치하는 전자 메일 메시지에 레이블을 자동으로 적용하는 보존 자동 레이블 지정 정책을 설정한 경우 콘텐츠 탐색기를 사용하여 레이블이 있는 항목을 검토하고 항목이 분류자와 일치하는지 여부를 피드백을 제공할 수 있습니다.

## <a name="august-2020"></a>2020년 8월

### <a name="spotlight-insider-risk-and-communication-compliance-updates"></a>스포트라이트: 내부자 위험 및 커뮤니케이션 규정 준수 업데이트

이번 달에는 몇 가지 새로운 기능 및 향상된 기능이 공개 미리 보기에 추가되었습니다.

**내부자 위험 관리**

- 6개의 새 정책 [템플릿을 확인 합니다.](insider-risk-management-policies.md#policy-templates)
    - 우선 순위 사용자에 의해 데이터 누수
    - 불만이 있는 사용자의 데이터 누수
    - 일반 보안 정책 위반
    - 사용자를 떠날 경우 보안 정책 위반
    - 우선 순위 사용자에 대한 보안 정책 위반
    - 불만이 있는 사용자의 보안 정책 위반

- [끝점용 Microsoft Defender와의](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) 통합을 통해 새 보안 위반 정책 템플릿에서 만든 정책으로 검색된 활동에 대한 끝점용 Microsoft Defender 경고를 가져오고 필터링할 수 있습니다. 또한 끝점 경고 [](insider-risk-management-settings.md#microsoft-defender-for-endpoint-preview) 등급 상태에 대한 Microsoft Defender를 기반으로 내부자 위험 관리로 보안 경고를 가져오는 것을 선택할 수 있는 관련 내부자 위험 설정도 있습니다.

    > [!NOTE]
    > 끝점 통합을 위한 Microsoft Defender(새 보안 정책 위반 템플릿 포함)를 활용하려면 조직에 끝점용 Microsoft Defender를 구성해야 합니다. 또한 끝점용 Microsoft Defender의 고급 기능을 구성하여 내부자 위험 관리 통합을 위해 [끝점에 대해 Microsoft Defender를 사용하도록 설정해야 합니다.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-features#share-endpoint-alerts-with-microsoft-compliance-center)
 
- 정책을 만들 때 표시기 [임계값을 사용자 지정합니다.](insider-risk-management-policies.md#create-a-new-policy)
- 우선 [순위 사용자](insider-risk-management-settings.md#priority-user-groups-preview) 그룹을 설정하여 자신의 위치, 중요한 정보에 대한 액세스 수준 또는 위험 기록과 같은 요인에 따라 활동이 더 자세히 검사해야 하는 사용자를 정의합니다.
- Office 365 관리 활동 [](insider-risk-management-settings.md#export-alerts-preview) API를 사용하여 조직에서 내부자 위험 데이터를 관리하거나 집계하는 데 사용할 수 있는 다른 응용 프로그램으로 내부자 위험 경고 세부 정보를 내보낼 수 있습니다.
- 새 [도메인 설정을](insider-risk-management-settings.md#domains-preview) 사용하면 특정 도메인의 활동에 대한 위험 수준을 정의하고 제어할 수 있습니다.

**커뮤니케이션 규정 준수**

- [경고의](communication-compliance-investigate-remediate.md#step-3-decide-on-a-remediation-action)메시지를 검토할 때 이제 Microsoft Teams 채널, 1:1 및 그룹 채팅에서 부적절한 메시지를 제거할 수 있습니다. 제거된 메시지 및 콘텐츠는 중요한 콘텐츠로 인해 제거되었다는 설명이 있는 정책 팁으로 대체되었습니다.
- 새 통신 역할(9월에 출시되는 새로운 통신 준수 역할 그룹에도 포함됩니다. [](communication-compliance-configure.md#step-1-required-enable-permissions-for-communication-compliance)
- 개인 정보 및 알림 템플릿에 대한 설정을 포함하는 새로운 통신 [준수 설정 환경입니다.](communication-compliance-feature-reference.md#notice-templates) [](communication-compliance-feature-reference.md#privacy-preview)
- 성인, [인종](communication-compliance-feature-reference.md#classifiers) 및 고래 이미지를 감지하는 데 도움이 되는 새로운 분류자입니다.
- 경고에서 메시지를 검토할 때 나타나는 [](communication-compliance-investigate-remediate.md#step-2-examine-the-message-details) 새로운 '패턴 검색' 알림을 통해 사용자에 의해 동일한 동작의 인스턴스가 다시 반복되는 것을 알 수 있습니다.

### <a name="sensitivity-labels"></a>민감도 레이블

- 미국 정부 테넌트(GCC, GCC-H 및 DoD)의 경우 민감도 레이블은 현재 Azure Information Protection 통합 레이블 지정 클라이언트 및 스캐너에 대해서만 지원됩니다. 자세한 내용은 [Azure Information Protection Premium 정부 서비스 설명](https://docs.microsoft.com/enterprise-mobility-security/solutions/ems-aip-premium-govt-service-description)을 참조하세요.
- 이제 보안 및 준수 [& PowerShell을](create-sensitivity-labels.md#use-powershell-for-sensitivity-labels-and-their-policies) 사용하여 레이블 관리 센터에 있는 모든 설정을 만들고 구성할 수 있습니다. 즉, 레이블 관리 센터에서 사용할 수 없는 설정에 PowerShell을 사용하는 것 외에도 이제 민감도 레이블 및 민감도 레이블 정책의 생성 및 유지 관리에 대한 스크립트를 완전히 스크립팅할 수 있습니다.

### <a name="records-management-content-overhaul"></a>레코드 관리: 콘텐츠 정비

배포 단계를 다루고, 콘텐츠를 레코드로 표시하고, 버전 관리에 대한 새로운 내용을 제공합니다.

- [레코드 관리 시작](get-started-with-records-management.md)
- [보존 레이블을 사용하여 레코드 선언](declare-records.md)
- [레코드 버전 관리를 사용하여 SharePoint 또는 OneDrive에 저장된 레코드 업데이트](record-versioning.md)

### <a name="retention-labels--policies"></a>보존 레이블 & 정책

이제 보존 관련 관리자 활동이 기록되어 감사 로그에 검토할 수 있습니다. 전체 목록은 [보존 정책 및 보존 레이블 활동](search-the-audit-log-in-security-and-compliance.md#retention-policy-and-retention-label-activities)을 참조하세요.

### <a name="advanced-ediscovery"></a>Advanced eDiscovery

- 이제 [검토 집합에](add-data-to-review-set.md#define-options-to-scope-your-collection-for-review)컬렉션을 추가할 때 최신 첨부 파일("클라우드 첨부 파일"이라고도 하는) 및 SharePoint 문서 버전을 포함할 수 있습니다.
- 새로운 [직접 다운로드 내보내기 환경을](export-documents-from-review-set.md)통해 Azure 저장소 탐색기를 사용하여 사례 콘텐츠를 다운로드할 필요가 없습니다.


## <a name="july-2020"></a>2020년 7월

### <a name="spotlight-on-help-docs"></a>도움말 도움말에 대한 스포트라이트

조직의 중요한 데이터를 보호하고 관리하기 위해 사용되는 규정 준수 솔루션을 이해하기 위해 관련 문서에 대한 링크를 포함하여 이러한 목표를 달성하기 위해 솔루션이 함께 작동되는 방식에 대한 개요가 있는 두 개의 새로운 방문 페이지를 만들 수 있습니다.

[Microsoft 365의 Microsoft Information Protection](information-protection.md)<br>
[Microsoft 365의 Microsoft 정보 거버넌스](manage-Information-governance.md)

### <a name="advanced-ediscovery-add-non-custodial-data-sources-to-your-cases"></a>Advanced eDiscovery: 사례에 비보조 데이터 원본 추가

보호자(비보조 데이터 원본)와 연결하지 않고 사례에 데이터를 [추가합니다.](non-custodial-data-sources.md) 또한 이 비관리 데이터를 보류해야 하는 경우 새로운 고급 인덱싱 기능을 사용하여 보류할 수 있습니다.

### <a name="data-connectors-hr-connector-enhancements"></a>데이터 커넥터: HR 커넥터 향상

(미리 보기) 새 버전의 [HR](import-hr-data.md) 커넥터를 사용하면 작업 수준 변경, 성능 검토 및 성능 개선 계획과 관련된 데이터를 가져올 수 있습니다. 그런 다음 이 데이터를 여러 내부자 위험 정책에서 사용하여 [관련](insider-risk-management-policies.md) 활동을 검색할 수 있습니다.

### <a name="retention-labels-new-support-for-email"></a>보존 레이블: 전자 메일에 대한 새로운 지원

이제 보존 [레이블을 만들어](retention.md#retention-labels) 메시지에 레이블이 지정된 경우를 기준으로 전자 메일 보존을 시작할 수 있습니다. 이는 항목을 보낸 날짜를 기준으로 보존되는 일정 항목에는 적용되지 않습니다.

### <a name="sensitivity-labels-new-feature-and-an-improvement"></a>민감도 레이블: 새로운 기능 및 개선 사항

- (미리 보기) 레이블에 대한 암호화 설정을 구성할 때 이중 [](encryption-sensitivity-labels.md#double-key-encryption) 키 암호화를 사용하여 레이블이 있는 파일 및 전자 메일을 추가로 보호하는 새로운 옵션을 찾아야 합니다.
- 민감도 레이블을 만들거나 삭제하거나 레이블 정책을 만들거나 편집하거나 삭제하는 경우 변경 내용이 1시간 이내에 모든 사용자, 앱 및 서비스와 동기화됩니다.

## <a name="june-2020"></a>2020년 6월

### <a name="spotlight-new-data-connectors-hit-preview"></a>스포트라이트: 새 데이터 커넥터 적중 미리 보기

더 많은 타사 원본의 데이터를 Microsoft 365로 가져오는 데 도움이 되는 약속을 기다렸다가 두 개의 추가 데이터 커넥터의 미리 보기 릴리스를 발표하게 됩니다.

- [Bloomberg 메시지입니다.](archive-bloomberg-message-data.md) Bloomberg 메시지 공동 작업 도구에서 금융 서비스 전자 메일 데이터를 가져오고 보관합니다. 데이터를 사서함에 저장한 후 소송 보존, 콘텐츠 검색, 원본 위치 보관, 감사, 통신 준수 및 보존 정책과 같은 준수 기능의 데이터에 액세스하고 사용할 수 있습니다.
- [ICE Chat](archive-icechat-data.md). ICE 채팅 공동 작업 도구에서 금융 서비스 채팅 데이터를 가져오고 보관합니다. 데이터를 사서함에 저장한 후 소송 보존, eDiscovery, 보관, 감사, 통신 준수 및 보존 정책과 같은 준수 기능의 데이터에 액세스하고 사용할 수 있습니다.

### <a name="compliance-score--compliance-manager-the-hits-keep-coming"></a>준수 & 준수 관리자: 적중 수 계속

6월 업데이트에는 준수 점수의 새로운 평가 드릴다운 [보기가 포함됩니다.](compliance-score.md) 제어 진행 상황을 모니터링하고 준수 점수에서 직접 평가를 추가, 삭제하는 등입니다.

준수 점수 및 준수 관리자에 대한 업데이트를 최신으로 유지하려는 경우 준수 점수 릴리스 정보 [책갈피를 작성하고](compliance-score-release-notes.md) 자주 확인하십시오.

## <a name="may-2020"></a>2020년 5월

### <a name="spotlight-data-classification-is-officially-released"></a>스포트라이트: 데이터 분류가 공식적으로 릴리스됩니다.

데이터 분류,[](data-classification-overview.md)'데이터', 기능(분석, 콘텐츠 탐색기 및 활동 탐색기)이 미리 보기 단계에서 제공된 것으로, 모든 조직에서 사용할 수 있습니다. 강력한 인사이트 및 도구를 사용하면 조직 전체의 콘텐츠에서 중요한 정보 및 레이블(보존 및 민감도)이 어떻게 사용되는지 검색하고 평가할 수 있습니다. 중요한 정보를 포함하거나 레이블이 적용된 콘텐츠를 검토하고, Microsoft 365 위치에서 레이블 활동을 탐색하고, 사용자 지정 중요한 정보 유형을 만드는 등 다양한 정보를 제공합니다.

비디오 둘러보기...

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4vx8x]

### <a name="trainable-classifiers-a-fix-and-a-feature"></a>학습 가능한 분류자: 수정 사항 및 기능

교육 가능한 분류자에 대한 향상된 기능이 제공될 수 있습니다.

- 피드백에 기반한 수정 사항: 사용자 지정 분류기를 시드하고 교육할 때 더 이상 SharePoint 사이트 URL 및 폴더 경로를 수동으로 입력할 필요가 없습니다. 이제 사이트 및 폴더의 미리 채우기 목록에서 선택할 수 있습니다.
- 새로운 기능: 민감도 레이블을 만들고 Office 앱에 대한 자동 레이블 지정 설정을 구성할 때 이제 학습 가능한 분류자와 일치하는 콘텐츠에 레이블을 자동으로 적용(또는 사용자가 적용하는 것이 좋습니다)할 수 있습니다. [자세한 정보](apply-sensitivity-label-automatically.md#configuring-trainable-classifiers-for-a-label)

### <a name="communication-compliance-yammer-support-is-here"></a>커뮤니케이션 규정 준수: Yammer 지원은 다음과 같습니다.

개인 메시지 및 공용 커뮤니티 Yammer 통신 준수 정책에서 지원됩니다. Yammer 채널은 선택적 채널이며 메시지 [](https://docs.microsoft.com/yammer/configure-your-yammer-network/overview-native-mode) 및 첨부 파일 검색을 지원하려면 기본 모드에 있어야 합니다.

### <a name="data-loss-prevention-new-sharing-restriction"></a>데이터 손실 방지: 새 공유 제한

SharePoint 또는 OneDrive의 콘텐츠를 보호하기 위해 DLP 정책을 설정할 때 이제 '링크가 있는 모든[사용자'](https://support.microsoft.com/office/share-files-outside-your-organization-with-anyone-links-53e91027-fb8e-4a6e-a3e4-5df4be32e38a)옵션을 통해 콘텐츠에 대한 액세스 권한이 부여된 사람을 차단하도록 "콘텐츠에 대한 액세스 제한" 작업을 구성할 수 있습니다.

### <a name="insider-risk-management-tailor-your-alert-volume"></a>내부자 위험 관리: 경고 볼륨 조정

내부자 위험 정책에서 검색된 사용자 활동에는 특정 위험 점수가 할당되어 경고 심각도(낮음, 중간, 높음)를 결정하게 됩니다. 기본적으로 Microsoft 365는 낮은, 중간 및 높은 심각도 경고를 생성하지만 새로운 [](insider-risk-management-settings.md#alert-volume)경고 볼륨 설정을 사용하면 요구에 맞게 볼륨을 늘리거나 줄이면 됩니다.

### <a name="pst-import-new-region-supported"></a>PST 가져오기: 새 지역 지원

이제 아랍에미리트에서 네트워크 업로드를 사용할 수 있습니다.

### <a name="sensitivity-labels-new-privacy-option"></a>민감도 레이블: 새로운 개인 정보 옵션

레이블에 [](sensitivity-labels-teams-groups-sites.md#how-to-configure-groups-and-site-settings) 대한 사이트 및 그룹 설정을 구성할 때 이제 개인 정보 옵션을 없음으로 설정할 수 있습니다. 사용자가 사이트에 액세스할 수 있는 사용자를 선택할 **수 있습니다.** 이는 민감도 레이블을 사용하여 컨테이너의 콘텐츠를 보호하지만 사용자가 개인 정보 설정을 직접 구성할 수 있도록 하려는 경우 유용합니다.

## <a name="april-2020"></a>2020년 4월

### <a name="records-management-overhauland-a-new-addition"></a>레코드 관리: 정비... 및 새 추가

4월에는 레코드 관리 솔루션에 대한 몇 가지 주요 업데이트가 포함되어 있습니다.

- '레코드 관리' 섹션은 이제 준수 센터에서 완전히 사용할 수 있습니다. 파일 계획, 보존 레이블 및 레이블 정책, 이벤트 및 삭제에 대해 업데이트된 사용자 인터페이스 및 기능을 활용합니다.
- 또한 SharePoint 및 OneDrive의 레코드에 대한 파기 증명을 롤아웃했습니다. [](disposition.md#disposition-of-records) 이제 자동으로 또는 삭제 검토 후에 해당 위치에서 항목 목록을 볼 수 있습니다.

### <a name="sensitivity-labels-preview-auto-labeling-policies"></a>민감도 레이블: 자동 레이블 지정 정책 미리 보기

이제 자동 레이블 지정 정책을 사용하면 이미 저장된 SharePoint 및 OneDrive docs(미사용 데이터) 및 이미 보내거나 받은 전자 메일('전송 중 전자 메일')에 민감도 레이블을 자동으로 적용할 수 있습니다. 이 레이블 지정은 앱이 아닌 서비스에서 적용하기 때문에 사용자가 사용하는 앱과 버전에 대해 걱정할 필요가 없습니다.

이 기능은 민감도 레이블을 만들 때 'Office 앱에 대한 자동 레이블 지정' 설정에 이미 포함되어 있는 기존 클라이언트 쪽 레이블을 확장합니다. 자동 레이블 지정 옵션의 차이점과 이점을 빠르게 확인한 후 업데이트된 문서를 [확인하세요.](apply-sensitivity-label-automatically.md)

## <a name="march-2020"></a>2020년 3월

### <a name="introducing-advanced-audit"></a>고급 감사 소개

[Microsoft 365의](advanced-audit.md) 고급 감사에는 조직에서 법의학 및 규정 준수 조사를 지원할 수 있는 새로운 감사 기능이 도입되어 있습니다. 주요 정보로는 감사 로그의 장기 보존, 사용자 지정 감사 로그 보존 정책, 새로운 *MailItemsAccessed* 사서함 감사 작업 및 조직에 감사 데이터에 액세스하기 위해 자체적으로 할당된 대역폭 할당량에 대한 새로운 테넌트 수준 제한의 도입이 포함됩니다.

### <a name="compliance-score--compliance-manager-preview-the-latest-enhancements"></a>준수 & 관리자: 향상된 최신 기능 미리 보기

이 미리 보기 릴리스의 주요 업데이트는 다음과 같습니다.

- 템플릿 만들기 및 수정을 위한 간소화된 프로세스
- 템플릿 및 작업에 대한 버전 관리 알림 및 제어
- 그룹 간 공통 작업 동기화
- 이제 언어 지원이 중국어(간체), 중국어(일반), 프랑스어, 독일어, 이탈리아어, 일본어, 한국어, 포르투갈어(브라질), 러시아어 및 스페인어로 확장되었습니다.

준수 점수 [및 준수 관리자에](compliance-score.md) [대해 자세히 알아보시고](compliance-manager-overview.md)

### <a name="sensitivity-labels-support-for-labeling-office-files-in-sharepoint-and-onedrive-preview"></a>민감도 레이블: SharePoint 및 OneDrive에서 Office 파일 레이블 지정 지원(미리 보기)

미리 보기를 사용하도록 설정하면 사용자가 웹용 Office에서 민감도 레이블을 적용할 수 있습니다. 리본의 민감도 단추와 상태 표시줄에 적용된 레이블 이름을 볼 수 있습니다.  또한 데스크톱 앱을 사용하여 레이블을 지정한 다음 해당 파일을 SharePoint 또는 OneDrive에 저장하면 레이블에 암호화 설정이 적용된 경우 Microsoft 365에서 이러한 파일의 콘텐츠를 처리할 수 있습니다. 이러한 상황에서는 공동 작업, eDiscovery, 데이터 손실 방지, 검색 및 기타 공동 작업 기능도 지원됩니다.

[미리 보기를 사용하도록 설정하는 방법 학습](sensitivity-labels-sharepoint-onedrive-files.md)

## <a name="february-2020"></a>2020년 2월

### <a name="insider-risk-management-is-officially-released"></a>내부자 위험 관리가 공식적으로 릴리스되었습니다.

연산 롤, 제발...<br>이제 다음과 같은 구독이 있는 조직에서 내부자 위험 관리를 사용할 수 있습니다.

- [Microsoft 365 E5(유료](https://go.microsoft.com/fwlink/?linkid=2120431) 또는 평가판)
- Microsoft E5 준수 추가 기능을 통해 Microsoft 365 Enterprise [E3 구독](https://go.microsoft.com/fwlink/?linkid=2120432)

새 역할 그룹 및 솔루션 전체 설정을 포함하여 [](insider-risk-management-configure.md#step-1-enable-permissions-for-insider-risk-management) 미리 보기 릴리스 이후 몇 가지 [개선을 이행했습니다.](insider-risk-management-configure.md#step-4-configure-insider-risk-settings)

항상처럼 솔루션을 사용할 때 피드백을 남기면 계속 개선할 수 있습니다.

### <a name="records-management"></a>레코드 관리

이 새로운 솔루션은 모든 레코드 관리 기능을 단일 우산으로 제공합니다. 주요 소개에는 SharePoint 및 OneDrive에 대한 레코드 버전 관리와 레코드 폐기 증명이 포함됩니다.

![Microsoft 365 규정 준수 센터의 레코드 관리 페이지](../media/mcc-records-management-page.png)

[레코드 관리에 대해 자세히](records-management.md)

### <a name="solution-spotlight-data-connectors-for-facebook-and-twitter"></a>솔루션 스포트라이트: Facebook 및 Twitter용 데이터 커넥터

지난 [달에](#just-launched) 출시된 데이터 커넥터는 다음 커넥터를 테스트하는 데 도움이 될 것입니다.

- [Facebook 비즈니스 페이지.](archive-facebook-data-with-sample-connector.md) Facebook 비즈니스 페이지에서 Microsoft 365로 데이터를 가져오고 보관합니다. 레코드 관리 및 eDiscovery와 같은 규정 준수 솔루션에 도움이 됩니다.
- [Twitter](archive-twitter-data-with-sample-connector.md). Twitter에서 Microsoft 365로 데이터를 가져오고 보관합니다. 레코드 관리 및 eDiscovery와 같은 규정 준수 솔루션에 도움이 됩니다.

이러한 커넥터를 설정하고 유효성을 검사할 때, 잘 된 것, 잘되지 않은 것, 환경을 개선하기 위해 할 수 있는 일에 대한 피드백을 남겨 주세요.

## <a name="january-2020"></a>2020년 1월

대기가 완료된 경우 Microsoft 365, Office 365, EMS(Enterprise Mobility + Security) 및 Windows 10 Enterprise 요금제가 있는 모든 고객이 Microsoft 365 규정 준수 센터를 사용할 수 있습니다. 보안 및 준수 센터에서 관리하고 & 데이터 또는 정책은 준수 센터에서 사용할 수 있으므로 뒤로 이동하지 필요가 없습니다.

책갈피로 시작하여 전체적으로 규정 준수를 관리하기 위한 원스톱 상점을 [https://compliance.microsoft.com](https://compliance.microsoft.com) 둘러보는 방법을 소개합니다. 또는 [이 문서를 좀](microsoft-365-compliance-center.md) 더 자세히 읽어보는 것이 더 까다로우면

![Microsoft 365 규정 준수 센터 홈 페이지](../media/mcc-home-ga.png)

이번 달에는 새로운 솔루션과 업데이트된 솔루션도 출시되었습니다. 다음은 주요 특징을 간과한 것입니다.

### <a name="now-in-preview"></a>이제 미리 보기로

**내부자 위험 관리(미리 보기)**

현재 내부자 위험 관리 솔루션이 공개 미리 보기에 제공될 예정이니 기쁘습니다. 간단히 말해서, 내부자 위험 관리는 조직이 다음을 제공하여 내부자 위험을 지능적으로 식별하고 조치를 취하는 데 도움이 됩니다.

- 사용자 개인 정보 보호를 보장하는 데 도움이 되는 Anonymity 컨트롤
- 데이터 누출과 같은 내부자 위협을 식별하는 네이티브 및 타사 표시기가 있는 지능형 정책 템플릿입니다.
- IT, HR 및 법률 팀 전체에 걸쳐 있는 종단간 조사 워크플로 통합

We'd love to hear what you think. 솔루션을 사용할 때 일반적인 가용성을 향한 요구 사항을 충족할 수 있도록 피드백을 남기십시오.

[내부자 위험 관리에 대해 자세히 알아보시고](insider-risk-management.md)

### <a name="just-launched"></a>방금 시작

**커뮤니케이션 규정 준수**

미리 보기 단계에서 완전한 가용성으로의 단계에 따라 커뮤니케이션 규정 준수는 새로운 내부자 위험 솔루션 집합의 핵심 구성 요소입니다. 이 강력한 솔루션은 조직의 표준을 충족하지 않는 메시지의 검색, 조사 및 수정 작업을 수행하기 위한 워크플로를 사용하여 통신 위험을 최소화하는 데 도움이 됩니다.

미리 보기 중에 고객 피드백이 만족스웠습니다. 시작을 위한 첫 실행 환경, 조사 및 수정 조치 개선 등 몇 가지 기능이 향상됩니다.

[커뮤니케이션 규정 준수에 대한 자세한 정보](communication-compliance.md)

![환영 환경의 첫 번째 카드를 표시하는 Microsoft 365 규정 준수 센터의 커뮤니케이션 준수 페이지](../media/mcc-communication-compliance-page-with-fre.png)

**데이터 커넥터**

이전의 Office 365 보안 및 준수 센터에서 다른 '가져오기' 기능과 공간을 공유하고 & 데이터 커넥터는 이제 Microsoft 365 규정 준수 센터에 자체 홈을 가지고 있습니다. 새로운 '데이터 커넥터' 페이지를 사용하여 조직의 HR(인사) 파일 및 다양한 타사 플랫폼(예: Facebook, LinkedIn, Twitter, Instant Bloomberg)에서 Microsoft 365 조직의 사서함으로 데이터를 가져오고 보관합니다. 가져온 후 eDiscovery, 내부자 위험 관리, 커뮤니케이션 준수, 감사, 보존 정책 등을 비롯한 여러 준수 솔루션에서 이 데이터를 관리할 수 있습니다.

[데이터 커넥터에 대한 자세한 정보](archiving-third-party-data.md)

![Microsoft 365 규정 준수 센터의 데이터 커넥터 페이지](../media/mcc-data-connectors-page.png)

### <a name="noteworthy-updates"></a>주목할 만한 업데이트

**준수 점수에 대한 새 평가 템플릿(미리 보기)**

항상 진화하는 규정 준수 환경보다 앞서기 위해 노력하는 준수 점수 팀은 최근 규정에 대한 조직의 규정 준수 상태를 평가하고 보다 효과적인 제어를 구현하는 방법에 대한 지침을 얻을 수 있도록 새로운 템플릿 집합을 제공했습니다. 다음에 대한 새 템플릿이 표시 됩니다.

- ISO/IEC 27701:2019
- 캘리포니아 소비자 개인 정보 보호법(CCPA)
- 브라질 일반 데이터 보호법(Lei Geral de Proteção de Dados - LGPD)
- SOC 1 유형 2 및 SOC 2 유형 2

[준수 점수 템플릿에 대한 자세한 내용은](compliance-score.md#templates)
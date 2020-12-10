---
title: Microsoft 365의 Microsoft Information Protection
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: hub-page
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MOE150
- MET150
ms.collection:
- m365solution-mip
- m365initiative-compliance
description: MIP(Microsoft Information Protection)를 구현하여 중요한 정보를 어디에서나 보호할 수 있습니다.
ms.openlocfilehash: 59f57c920f2b753994f2335a6f2ed9ac5b7b77d1
ms.sourcegitcommit: a0cddd1f888edb940717e434cda2dbe62e5e9475
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/09/2020
ms.locfileid: "49613090"
---
# <a name="microsoft-information-protection-in-microsoft-365"></a>Microsoft 365의 Microsoft Information Protection

>*[Microsoft 365 보안 및 규정 준수 라이선스](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)*

MIP(Microsoft Information Protection)를 구현하면 중요한 정보를 언제 어디서나 검색, 분류 및 보호할 수 있습니다.

MIP 기능은 Microsoft 365 규정 준수에 포함되어 있으며, [데이터 파악](#know-your-data), [데이터 보호](#protect-your-data) 및 [데이터 손실 방지](#prevent-data-loss)를 위한 도구를 제공합니다.

![MIP를 통해 중요한 데이터를 검색, 분류 및 보호하는 방법에 대한 이미지](../media/powered-by-intelligent-platform.png)

데이터 관리에 대한 자세한 내용은 [Microsoft 365에서 Microsoft 정보 관리](manage-Information-governance.md)를 참조합니다.

## <a name="know-your-data"></a>사용자 데이터 파악

> [!NOTE]
> 현재 미리 보기에 있는 Azure Purview에서 데이터 분류 및 레이블 지정에 대한 자세한 내용은 [Azure Purview에서 내용에 자동으로 레이블을 지정](https://docs.microsoft.com/azure/purview/create-sensitivity-label)을 참조하세요.
> 
> 이 새 릴리스에 대한 자세한 정보는 블로그 게시물 [Microsoft Information Protection and Microsoft Azure Purview: Better Together](https://techcommunity.microsoft.com/t5/microsoft-security-and/microsoft-information-protection-and-microsoft-azure-purview/ba-p/1957481)(Microsoft 정보 보호 및 Microsoft Azure 프리뷰: 다함께 더 좋게)를 참조하세요.



하이브리드 환경에서 데이터 환경을 이해하고 중요한 데이터를 식별하려면 다음 기능을 사용합니다.
 
|기능|어떤 문제를 해결하나요?|시작|
|:------|:------------|:--------------------|:-----------------------------|
|[중요한 정보 유형](sensitive-information-type-entity-definitions.md)| 키워드, 신뢰 수준 및 근접성을 포함하는 확증적 증거와 함께 기본 제공 또는 사용자 정의 정규식 또는 함수를 사용하여 중요한 데이터를 식별합니다.| [기본 제공 중요한 정보 유형 사용자 지정](customize-a-built-in-sensitive-information-type.md)|
|[교육 가능한 분류자(미리 보기)](classifier-learn-about.md)| 기본 제공 분류자 중 하나를 사용하여 데이터를 분류하거나 고유한 내용을 사용하여 분류자를 교육합니다. | [학습 가능한 분류자 시작(미리 보기)](classifier-get-started-with.md) |
|[데이터 분류](data-classification-overview.md) | 민감도 레이블, 보존 레이블이 있거나 조직에서 중요한 정보 유형으로 분류된 항목과 사용자가 수행하는 작업을 식별합니다.  | [콘텐츠 탐색기로 시작](data-classification-content-explorer.md)<br /><br /> [활동 탐색기 시작하기](data-classification-activity-explorer.md) |

## <a name="protect-your-data"></a>사용자 데이터 보호

암호화, 액세스 제한 및 시각적 표시를 포함한 유연한 보호 작업을 적용하려면 다음 기능을 사용합니다.

|기능|어떤 문제를 해결하나요?|시작|
|:------|:------------|---------------------|:----------------------------|
|[민감도 레이블](sensitivity-labels.md)| 애플리케이션, 서비스 및 장치에 걸친 단일 솔루션으로 조직 내외부에서 데이터를 이동할 때 레이블을 지정하고 보호합니다. <br /><br />시나리오 예: [Power BI 민감도 레이블을 적용하고 내보낼 때 데이터 보호](https://docs.microsoft.com/power-bi/admin/service-security-apply-data-sensitivity-labels)|[민감도 레이블 시작](get-started-with-sensitivity-labels.md) |
|[Windows용 Azure Information Protection 통합 레이블 지정 클라이언트](https://docs.microsoft.com/azure/information-protection/rms-client/aip-clientv2)| Windows 시스템의 경우 에서는 File Explorer 및 PowerShell에서 모든 파일 형식에 레이블 지정 및 보호를 포함하는 추가 기능 및 기능에 대한 민감도 레이블을 확장합니다.<br /><br /> 추가 기능 예시: [Azure Information Protection 통합 레이블 지정 클라이언트에 대한 사용자 지정 구성](https://docs.microsoft.com/azure/information-protection/rms-client/clientv2-admin-guide-customizations)| [Azure Information Protection 통합 레이블 사용자 가이드](https://docs.microsoft.com/azure/information-protection/rms-client/clientv2-admin-guide)|
|[이중 키 암호화](double-key-encryption.md)| 모든 경우 사용자만 보호된 콘텐츠를 해독할 수 있으며, 규정 요구 사항을 충족하려면 암호화 키를 지리적 경계 내에 보관해야 합니다. | [이중 키 암호화](double-key-encryption.md#deploy-dke)|
|[OME(Office 365 메시지 암호화)](ome.md)| 장치의 모든 사용자에게 전송되는 전자 메일 메시지 및 첨부 문서를 암호화하여 인증된 수신인만 전자 메일 정보를 읽을 수 있도록 합니다.  <br /><br />시나리오 예: [Office 365 고급 메시지 암호화로 암호화된 전자 메일 취소](revoke-ome-encrypted-mail.md) | [새 메시지 암호화 기능 설정하기](set-up-new-message-encryption-capabilities.md)|
|[고객 키를 사용한 서비스 암호화](customer-key-overview.md) | 인증되지 않은 시스템이나 직원이 데이터를 볼 수 없도록 보호하고 Microsoft 데이터 센터의 BitLocker 디스크 암호화를 보완합니다. | [Office 365의 고객 키 설정](customer-key-set-up.md)|
|[IRM(정보 권한 관리)](set-up-irm-in-sp-admin-center.md#irm-enable-sharepoint-document-libraries-and-lists)|사용자가 문서를 체크아웃할 때 권한 있는 사용자만 사용자가 지정한 정책에 따라 파일을 보고 사용할 수 있도록 SharePoint 목록 및 라이브러리를 보호합니다. | [SharePoint Online 관리 센터에서 IRM(정보 권한 관리)을 설정](set-up-irm-in-sp-admin-center.md)|
[권한 관리 커넥터](https://docs.microsoft.com/azure/information-protection/deploy-rms-connector) |Exchange 또는 SharePoint 서버를 사용하는 기존 사내 배포 또는 Windows 서버 및 FCI(파일 분류 인프라)를 실행하는 파일 서버에 대한 보호 전용입니다. | [RMS 커넥터를 배포하는 단계](https://docs.microsoft.com/azure/information-protection/deploy-rms-connector#steps-to-deploy-the-rms-connector)
|[정보 보호 통합 라벨링 스캐너](https://docs.microsoft.com/azure/information-protection/deploy-aip-scanner)| 사내에 있는 데이터 저장소에 있는 중요한 정보를 검색, 레이블 지정 및 보호합니다. | [Azure Information Protection 통합 라벨링 스캐너 구성 및 설치](https://docs.microsoft.com/azure/information-protection/deploy-aip-scanner-configure-install)|
|[Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security)| 클라우드에 있는 데이터 저장소에 있는 중요한 정보를 검색, 레이블 지정 및 보호합니다. | [클라우드에 저장된 데이터를 검색하고, 분류하고, 레이블을 지정하고, 보호](https://docs.microsoft.com/cloud-app-security/best-practices#discover-classify-label-and-protect-regulated-and-sensitive-data-stored-in-the-cloud)|
|[Microsoft Information Protection SDK](https://docs.microsoft.com/information-protection/develop/overview#microsoft-information-protection-sdk)|타사 앱 및 서비스에 민감도 레이블을 연장  <br /><br /> 시나리오 예: [민감도 레이블(C++) 설정 및 가져오기](https://docs.microsoft.com/information-protection/develop/quick-file-set-get-label-cpp) |[MIP(Microsoft Information Protection) SDK 설정 및 구성](https://docs.microsoft.com/information-protection/develop/setup-configure-mip)|


## <a name="prevent-data-loss"></a>데이터 손실 방지

중요한 정보의 우발적인 과다 공유를 방지하려면 다음 기능을 사용합니다.


|기능|어떤 문제를 해결하나요?|시작|
|:------|:------------|:---------------------|:-----------------------------|
|[DLP(데이터 손실 방지)](data-loss-prevention-policies.md)| 중요한 항목의 의도하지 않은 공유를 방지합니다. <br /><br />시나리오 예: [Microsoft Teams 대화 및 채널 메시지에서 중요한 정보를 보호합니다](dlp-microsoft-teams.md) | [기본 DLP 정책을 사용하여 시작](get-started-with-the-default-dlp-policy.md)|
|[끝점 데이터 손실 방지에 대한 자세한 정보](endpoint-dlp-learn-about.md)| DLP 기능을 Windows 10 컴퓨터에서 사용 및 공유되는 항목으로 확장합니다. | [끝점 데이터 손실 방지 시작](endpoint-dlp-getting-started.md)|

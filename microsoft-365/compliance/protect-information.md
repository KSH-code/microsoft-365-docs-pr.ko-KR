---
title: Microsoft 365의 microsoft Information Protection
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: hub-page
ms.service: O365-seccomp
localization_priority: High
search.appverid:
- MOE150
- MET150
ms.collection:
- m365solution-mip
- m365initiative-compliance
ms.assetid: a6ef28a4-2447-4b43-aae2-f5af6d53c68e
description: Microsoft 365 준수를 사용 하 여 기밀 (Microsoft Information Protection) 기능을 구현 하 여 중요 한 정보를 검색, 분류 및 보호 하는 데 도움이 됩니다.
ms.openlocfilehash: 78aadbba5442d7ec3cdc1beeac6d290a11325861
ms.sourcegitcommit: cd17328baa58448214487e3e68c37590ab9fd08d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/09/2020
ms.locfileid: "48399047"
---
# <a name="microsoft-information-protection-in-microsoft-365"></a>Microsoft 365의 microsoft Information Protection

>*[Microsoft 365 보안 & 준수에 대 한 라이선스](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)*

Microsoft 정보 보호 (밉)를 사용 하 여 중요 한 정보를 검색, 분류 및 보호 하는 데 도움이 됩니다.

Microsoft 365 준수에는 밉 기능이 포함 되어 [있으므로 데이터를 파악](#know-your-data)하 고 데이터를 [보호](#protect-your-data)하 고 [데이터 손실을 방지](#prevent-data-loss)하기 위한 도구를 제공 합니다.

![데이터 파악, 데이터 보호, 데이터 손실 방지, 데이터 제어](../media/powered-by-intelligent-platform.png)

데이터를 관리 하는 방법에 대 한 자세한 내용은 microsoft [Information 거 버 넌 365 스](manage-Information-governance.md)를 참조 하세요.

## <a name="know-your-data"></a>사용자 데이터 파악

데이터 가로를 이해 하 고 하이브리드 환경에서 중요 한 데이터를 확인 하려면 다음 기능을 사용 합니다.
 
|기능|어떤 문제를 해결 하나요?|시작하기|
|:------|:------------|:--------------------|:-----------------------------|
|[중요한 정보 유형](sensitive-information-type-entity-definitions.md)| 키워드, 신뢰 수준 및 근사를 포함 하는 적인 증거와 함께 기본 제공 또는 사용자 지정 정규식 또는 함수를 사용 하 여 중요 한 데이터를 식별 합니다.| [기본 제공 중요한 정보 유형 사용자 지정](customize-a-built-in-sensitive-information-type.md)|
|[Trainable 분류자 (미리 보기)](classifier-learn-about.md)| 기본 제공 분류자 중 하나를 사용 하 여 데이터를 분류 하거나 사용자가 직접 콘텐츠를 사용 하 여 분류자를 교육 합니다. | [학습 가능한 분류자 시작(미리 보기)](classifier-get-started-with.md) |
|[데이터 분류](data-classification-overview.md) | 민감도 레이블, 보존 레이블 또는 조직에서 중요 한 정보 유형으로 분류 된 항목 및 사용자가 작업을 수행 하는 동작을 식별 합니다.  | [콘텐츠 탐색기 시작하기](data-classification-content-explorer.md)<br /><br /> [활동 탐색기 시작하기](data-classification-activity-explorer.md) |

## <a name="protect-your-data"></a>사용자 데이터 보호

암호화, 액세스 제한 및 시각적 표시를 포함 하는 유연한 보호 작업을 적용 하려면 다음 기능을 사용 합니다.

|기능|어떤 문제를 해결 하나요?|시작하기|
|:------|:------------|---------------------|:----------------------------|
|[민감도 레이블](sensitivity-labels.md)| 조직 내부 및 외부에서 데이터를 이동 하 고 레이블을 지정 하는 응용 프로그램, 서비스 및 장치 간의 단일 솔루션 <br /><br />예제 시나리오: [POWER BI에서 민감도 레이블을 적용 및 확인 하 고 데이터를 내보낼 때 보호](https://docs.microsoft.com/power-bi/admin/service-security-apply-data-sensitivity-labels)|[ 민감도 레이블 시작](get-started-with-sensitivity-labels.md) |
|[Azure Information Protection 통합 레이블 클라이언트](https://docs.microsoft.com/azure/information-protection/rms-client/aip-clientv2)| Windows 컴퓨터의 경우 파일 탐색기 및 PowerShell에서 모든 파일 형식을 레이블 지정 하 고 보호 하는 기능을 포함 하는 추가 기능에 대 한 민감도 레이블을 확장 합니다.<br /><br /> 추가 기능 예: [Azure Information Protection 통합 레이블 클라이언트에 대 한 사용자 지정 구성](https://docs.microsoft.com/azure/information-protection/rms-client/clientv2-admin-guide-customizations)| [Azure Information Protection 통합 레이블 클라이언트 관리자 가이드](https://docs.microsoft.com/azure/information-protection/rms-client/clientv2-admin-guide)|
|[이중 키 암호화](double-key-encryption.md)| 모든 상황에서 보호 된 콘텐츠를 암호 해독할 수도 있고 규정 요구 사항에 대 한 경우에는 지리적 경계 내에 암호화 키를 저장 해야 합니다. | [이중 암호화 배포](double-key-encryption.md#deploy-dke)|
|[Office 365 메시지 암호화](ome.md) (OME)| 모든 장치에서 임의의 사용자에 게 전송 되는 전자 메일 메시지 및 첨부 문서를 암호화 하 여, 인증 된 받는 사람만 전자 메일로 정보를 읽을 수 있도록 합니다.  <br /><br />예제 시나리오: [고급 메시지 암호화로 암호화 된 전자 메일 해지](revoke-ome-encrypted-mail.md) | [새 메시지 암호화 기능 설정하기](set-up-new-message-encryption-capabilities.md)|
|[고객 키를 사용한 서비스 암호화](customer-key-overview.md) | 승인 되지 않은 시스템 또는 담당자의 데이터 보기를 보호 하 고 Microsoft 데이터 센터에서 BitLocker 디스크 암호화를 보완 합니다. | [Office 365의 고객 키 설정](customer-key-set-up.md)|
|[SharePoint IRM (정보 권한 관리)](set-up-irm-in-sp-admin-center.md#irm-enable-sharepoint-document-libraries-and-lists)|사용자가 문서를 체크 아웃할 때 다운로드 된 파일이 보호 되므로 지정한 정책에 따라 권한 있는 사용자만 파일을 보고 사용할 수 있도록 SharePoint 목록과 라이브러리를 보호 합니다. | [Set up Information Rights Management (IRM) in SharePoint admin center](set-up-irm-in-sp-admin-center.md)|
[권한 관리 커넥터](https://docs.microsoft.com/azure/information-protection/deploy-rms-connector) |보호-Exchange 또는 SharePoint Server를 사용 하는 기존 온-프레미스 배포 또는 Windows Server 및 FCI (파일 분류 인프라)를 실행 하는 파일 서버에만 해당 합니다. | [RMS 커넥터를 배포 하는 단계](https://docs.microsoft.com/azure/information-protection/deploy-rms-connector#steps-to-deploy-the-rms-connector)
|[Azure Information Protection 통합 레이블 스캐너](https://docs.microsoft.com/azure/information-protection/deploy-aip-scanner)| 온-프레미스에 있는 데이터 저장소에 있는 중요 한 정보를 검색 하 고, 레이블을 설정 하 고 보호 합니다. | [Azure Information Protection 통합 레이블 지정 스캐너 구성 및 설치](https://docs.microsoft.com/azure/information-protection/deploy-aip-scanner-configure-install)|
|[Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security)| 클라우드에 있는 데이터 저장소에 있는 중요 한 정보를 검색 하 고, 레이블을 만들고, 보호 합니다. | [클라우드에 저장된 데이터를 검색하고, 분류하고, 레이블을 지정하고, 보호](https://docs.microsoft.com/cloud-app-security/best-practices#discover-classify-label-and-protect-regulated-and-sensitive-data-stored-in-the-cloud)|
|[Microsoft Information Protection SDK](https://docs.microsoft.com/information-protection/develop/overview#microsoft-information-protection-sdk)|민감도 레이블을 타사 앱 및 서비스로 확장 합니다.  <br /><br /> 예제 시나리오: [우편물 민감도 레이블 설정 및 가져오기 (c #)](https://docs.microsoft.com/information-protection/develop/quick-file-set-get-label-cpp) |[MIP(Microsoft Information Protection) SDK 설정 및 구성](https://docs.microsoft.com/information-protection/develop/setup-configure-mip)|

## <a name="prevent-data-loss"></a>데이터 손실 방지

중요 한 정보가 실수로 과도 하 게 공유 되지 않도록 하려면 다음 기능을 사용 합니다.


|기능|어떤 문제를 해결 하나요?|시작하기|
|:------|:------------|:---------------------|:-----------------------------|
|DLP ( [데이터 손실 방지](data-loss-prevention-policies.md) )| 중요 한 항목의 의도 하지 않은 공유 방지 <br /><br />예제 시나리오: [Microsoft 팀 채팅 및 채널 메시지의 중요 한 정보 보호](dlp-microsoft-teams.md) | [기본 DLP 정책을 사용하여 시작](get-started-with-the-default-dlp-policy.md)|
|[끝점 데이터 손실 방지 (미리 보기)](endpoint-dlp-learn-about.md)| Windows 10 컴퓨터에서 사용 되 고 공유 되는 항목에 대해 DLP 기능을 확장 합니다. | [끝점 데이터 손실 방지(미리 보기) 시작](endpoint-dlp-getting-started.md)|

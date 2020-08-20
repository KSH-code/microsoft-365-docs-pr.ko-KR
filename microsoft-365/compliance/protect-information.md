---
title: Microsoft 365의 Microsoft 정보 보호
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
ms.assetid: a6ef28a4-2447-4b43-aae2-f5af6d53c68e
description: Microsoft 365 규정 준수를 사용하여 데이터가 상주 하거나 이동하는 곳 어디서나 중요한 정보를 검색, 분류 및 보호하도록 도와주기 위해 Microsoft 정보 보호(MIP) 기능을 구현합니다.
ms.openlocfilehash: 96082bc70b093e763be00c847bb6a68ce302c8a9
ms.sourcegitcommit: 22fd8517707ed3ab6ef996247ad2aa372535ee56
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/19/2020
ms.locfileid: "46815208"
---
# <a name="microsoft-information-protection-in-microsoft-365"></a>Microsoft 365의 Microsoft 정보 보호

>*[Microsoft 365 보안 정책 & 라이선스](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)*

MIP(Microsoft 정보 보호)를 사용하면 위치가 상생하거나 이동하는 곳 어디서나 중요한 정보를 검색 및 분류하고 보호할 수 있습니다.

MIP 기능은 Microsoft 365 규정 준수에 포함되어 [데이터를](#know-your-data)알고 있고, [데이터를 보호하고, 데이터](#protect-your-data)손실을 방지하는 [도구를 제공합니다.](#prevent-data-loss)

![데이터를 알고 있고, 데이터를 보호하고, 데이터 손실을 방지하고, 데이터 관리](../media/powered-by-intelligent-platform.png)

데이터 관리에 대한 자세한 내용은 [Microsoft 365의 Microsoft 정보 거버넌스를 참조하세요.](manage-Information-governance.md)

## <a name="know-your-data"></a>사용자 데이터 파악

데이터 환경을 이해하고 하이브리드 환경에서 중요한 데이터를 식별하려면 다음 기능을 사용합니다.
 
|기능|해결되는 문제는 무엇입니까?|시작하기|
|:------|:------------|:--------------------|:-----------------------------|
|[중요한 정보 유형](sensitive-information-type-entity-definitions.md)| 키워드, 신뢰 수준 및 근접성을 포함하는 증거와 함께 기본 제공 또는 사용자 지정 정규식 또는 함수를 사용하여 중요한 데이터를 식별합니다.| [기본 제공 중요한 정보 유형 사용자 지정](customize-a-built-in-sensitive-information-type.md)|
|[훈재 가능한 분류자(미리 보기)](classifier-getting-started-with.md)| 기본 제공 분류자 또는 분류자 교육자 중 자신의 콘텐츠에 대한 교육을 사용하여 사용자를 위해서 데이터 분류 | [훈재 가능한 분류자 만들기(미리 보기)](classifier-creating-a-trainable-classifier.md) |
|[데이터 분류](data-classification-overview.md) | 민감도 레이블, 보존 레이블이 있거나, 조직에서 중요한 정보 유형으로 분류되었거나, 사용자가 자신이 가지는 작업을 식별합니다.  | [콘텐츠 탐색기로 시작](data-classification-content-explorer.md)<br /><br /> [활동 탐색기로 시작](data-classification-activity-explorer.md) |

## <a name="protect-your-data"></a>사용자 데이터 보호

암호화, 액세스 제한 및 시각적 표시를 포함하는 유연한 보호 작업을 적용하려면 다음 기능을 사용합니다.

|기능|해결되는 문제는 무엇입니까?|시작하기|
|:------|:------------|---------------------|:----------------------------|
|[민감도 레이블](sensitivity-labels.md)| 조직 내부 및 외부를 따라 이동할 때 앱, 서비스 및 장치 간에 단일 솔루션이 적용되고 데이터를 보호합니다. <br /><br />예제 [시나리오: Power BI에 민감도 레이블을 적용하고 보고, 내보낼 때 데이터를 보호합니다.](https://docs.microsoft.com/power-bi/admin/service-security-data-protection-overview)|[ 민감도 레이블 시작](get-started-with-sensitivity-labels.md) |
|[Azure Information Protection 통합 레이블 클라이언트](https://docs.microsoft.com/azure/information-protection/rms-client/aip-clientv2)| Windows 컴퓨터의 경우, 파일 탐색기 및 PowerShell에서 모든 파일 형식에 레이블을 지정하고 보호하는 기능을 포함한 추가 기능에 맞게 민감도 레이블을 확장합니다.<br /><br /> 추가 기능 예제: [Azure Information Protection 통합 레이블 지정 클라이언트에 대한 사용자 지정 구성](https://docs.microsoft.com/azure/information-protection/rms-client/clientv2-admin-guide-customizations)| [Azure Information Protection 통합 레이블 클라이언트 관리자 가이드](https://docs.microsoft.com/azure/information-protection/rms-client/clientv2-admin-guide)|
|[이중 키 암호화](double-key-encryption.md)| 모든 경우에 암호해 보호된 콘텐츠를 해독하거나, 지리적 경계 내에 암호화 키를 보관해야 하는 요구 사항의 경우에만 암호화 키를 보유해야 합니다. | [이중 키 암호화 배포](double-key-encryption.md#deploy-double-key-encryption)|
|[Office 365 메시지](ome.md) 암호화(OME)| 모든 장치에서 사용자에게 전송되는 전자 메일 메시지 및 첨부된 문서를 암호화하여 권한있는 받는 사람만 이메일을 읽을 수 있도록 합니다.  <br /><br />예제 시나리오: [고급 메시지 암호화로 암호화된 전자 메일 취소](revoke-ome-encrypted-mail.md) | [Office 365 메시지 암호화와 작업 시작](set-up-new-message-encryption-capabilities.md)|
|[고객 키를 사용한 서비스 암호화](customer-key-overview.md) | 무단 시스템이나 직원의 데이터 보기를 차단하고 Microsoft 데이터 센터에서 BitLocker 디스크 암호화를 보증합니다. | [Office 365의 고객 키 설정](customer-key-set-up.md)|
|[SharePoint IRM(정보 권한 관리)](set-up-irm-in-sp-admin-center.md#irm-enable-sharepoint-document-libraries-and-lists)|사용자가 문서를 체크 아웃하면 다운로드한 파일은 보호되므로 권한이 있는 사용자만 이 파일을 보고 지정한 정책에 따라 파일을 보고 사용할 수 있습니다. | [Set up Information Rights Management (IRM) in SharePoint admin center](set-up-irm-in-sp-admin-center.md)|
[Rights Management 커넥터](https://docs.microsoft.com/azure/information-protection/deploy-rms-connector) |Exchange 또는 SharePoint Server를 사용하는 기존 온-프레미스 배포 또는, Windows Server FCI(파일 분류 인프라)를 실행하는 파일 서버를 실행하는 기존 온-프레미스 배포에 만 해당합니다. | [RMS 커넥터를 배포하는 단계](https://docs.microsoft.com/azure/information-protection/deploy-rms-connector#steps-to-deploy-the-rms-connector)
|[Azure Information Protection 통합 레이블 지정 스캐너](https://docs.microsoft.com/azure/information-protection/deploy-aip-scanner)| 온-프레미스에 있는 데이터 저장소에 있는 중요한 정보를 검색하고 레이블을 지정하고 보호합니다. | [Azure Information Protection 통합 레이블 지정 스캐너 구성 및 설치](https://docs.microsoft.com/azure/information-protection/deploy-aip-scanner-configure-install)|
|[Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security)| 클라우드에 있는 데이터 저장소에 있는 중요한 정보를 검색하고, 레이블을 지정하고, 보호합니다. | [클라우드에 저장된 데이터를 검색하고, 분류하고, 레이블을 지정하고, 보호](https://docs.microsoft.com/cloud-app-security/best-practices#discover-classify-label-and-protect-regulated-and-sensitive-data-stored-in-the-cloud)|
|[Microsoft Information Protection SDK](https://docs.microsoft.com/information-protection/develop/overview#microsoft-information-protection-sdk)|타사 앱 및 서비스로 민감도 레이블 확장  <br /><br /> 예제 [시나리오: 민감도 레이블 설정 및 가져오기(C++)](https://docs.microsoft.com/information-protection/develop/quick-file-set-get-label-cpp) |[MIP(Microsoft Information Protection) SDK 설치 및 구성](https://docs.microsoft.com/information-protection/develop/setup-configure-mip)|

## <a name="prevent-data-loss"></a>데이터 손실 방지

중요한 정보가 실수로 과도한 공유를 방지하려면 다음 기능을 사용하세요.


|기능|해결되는 문제는 무엇입니까?|시작하기|
|:------|:------------|:---------------------|:-----------------------------|
|[DLP(데이터 손실](data-loss-prevention-policies.md) 방지)| 중요한 항목을 의도하지 않게 공유하는 일을 방지합니다. <br /><br />예제 시나리오: [Microsoft Teams 채팅 및 채널 메시지에서 중요한 정보 보호](dlp-microsoft-teams.md) | [기본 DLP 정책을 사용하여 시작](get-started-with-the-default-dlp-policy.md)|
|[엔드포인트 데이터 손실 방지(미리 보기)](endpoint-dlp-learn-about.md)| Windows 10 컴퓨터에서 사용 및 공유되는 항목으로 DLP 기능 확장 | [끝점 데이터 손실 방지(미리 보기) 시작](endpoint-dlp-getting-started.md)|

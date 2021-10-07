---
title: Microsoft 365의 Microsoft Information Protection
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: overview
ms.service: O365-seccomp
ms.localizationpriority: high
search.appverid:
- MOE150
- MET150
ms.collection:
- m365solution-mip
- m365initiative-compliance
recommendations: false
description: MIP(Microsoft Information Protection)를 구현하여 중요한 정보를 어디에서나 보호할 수 있습니다.
ms.openlocfilehash: d5a9cbf4aab78c91e9ffbe3897f84b24d46e4f84
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60177510"
---
# <a name="microsoft-information-protection-in-microsoft-365"></a>Microsoft 365의 Microsoft Information Protection

>*[Microsoft 365 보안 및 규정 준수 라이선스](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)*

MIP(Microsoft Information Protection)를 구현하면 중요한 정보를 언제 어디서나 검색, 분류 및 보호할 수 있습니다.

MIP 기능은 Microsoft 365 규정 준수에 포함되어 있으며, [데이터 파악](#know-your-data), [데이터 보호](#protect-your-data) 및 [데이터 손실 방지](#prevent-data-loss)를 위한 도구를 제공합니다.

![MIP를 통해 중요한 데이터를 검색, 분류 및 보호하는 방법에 대한 이미지.](../media/powered-by-intelligent-platform.png)

데이터 관리에 대한 자세한 내용은 [Microsoft 365에서 Microsoft 정보 관리](manage-Information-governance.md)를 참조합니다.

## <a name="know-your-data"></a>사용자 데이터 파악

> [!NOTE]
> 현재 미리 보기에 있는 Azure Purview에서 데이터 분류 및 레이블 지정에 대한 자세한 내용은 [Azure Purview에서 내용에 자동으로 레이블을 지정](/azure/purview/create-sensitivity-label)을 참조하세요.

하이브리드 환경에서 데이터 환경을 이해하고 중요한 데이터를 식별하려면 다음 기능을 사용합니다.

|기능|어떤 문제를 해결하나요?|시작|
|:------|:------------|:--------------------|
|[중요한 정보 유형](sensitive-information-type-learn-about.md)| 키워드, 신뢰 수준 및 근접성을 포함하는 확증적 증거와 함께 기본 제공 또는 사용자 정의 정규식 또는 함수를 사용하여 중요한 데이터를 식별합니다.| [기본으로 제공되는 중요한 정보 유형 사용자 지정](customize-a-built-in-sensitive-information-type.md)|
|[학습 가능한 분류자](classifier-learn-about.md)| 항목(패턴 일치)에서 요소를 식별하는 대신 관심이 있는 데이터의 예제를 사용하여 중요한 데이터를 식별합니다. 기본 제공 분류자를 사용하거나 본인의 콘텐츠로 분류자를 학습시킬 수 있습니다.| [학습 가능한 분류자로 시작](classifier-get-started-with.md) |
|[데이터 분류](data-classification-overview.md) | 민감도 레이블, 보존 레이블이 있거나 또는 분류된 조직의 항목의 그래픽 식별입니다. 이 정보를 사용하여 사용자가 이러한 항목에 대해 취하는 작업에 대한 통찰력을 얻을 수도 있습니다. | [콘텐츠 탐색기로 시작](data-classification-content-explorer.md) <p> [활동 탐색기 시작하기](data-classification-activity-explorer.md) |

## <a name="protect-your-data"></a>사용자 데이터 보호

암호화, 액세스 제한 및 시각적 표시를 포함한 유연한 보호 작업을 적용하려면 다음 기능을 사용합니다.

|기능|어떤 문제를 해결하나요?|시작|
|:------|:------------|---------------------|
|[민감도 레이블](sensitivity-labels.md)| 조직 내외부에서 이동하면서 앱, 서비스 및 장치에서 데이터 레이블을 지정하고 보호하는 단일 솔루션입니다. <p> 예제 시나리오: <p> [Office 앱의 민감도 레이블 관리](sensitivity-labels-office-apps.md) <p> [문서 및 전자 메일 암호화](encryption-sensitivity-labels.md) <p> [Power BI에서 레이블 적용 및 보기](/power-bi/admin/service-security-apply-data-sensitivity-labels) <p> 민감도 레이블에 대한 포괄적인 시나리오 목록은 시작 설명서를 참조하세요.|[민감도 레이블 시작하기](get-started-with-sensitivity-labels.md) |
|[Windows용 Azure Information Protection 통합 레이블 지정 클라이언트](/azure/information-protection/rms-client/aip-clientv2)| Windows 시스템의 경우 에서는 File Explorer 및 PowerShell에서 모든 파일 형식에 레이블 지정 및 보호를 포함하는 추가 기능 및 기능에 대한 민감도 레이블을 확장합니다. <p> 추가 기능 예시: [Azure Information Protection 통합 레이블 지정 클라이언트에 대한 사용자 지정 구성](/azure/information-protection/rms-client/clientv2-admin-guide-customizations)| [Azure Information Protection 통합 레이블 사용자 가이드](/azure/information-protection/rms-client/clientv2-admin-guide)|
|[이중 키 암호화](double-key-encryption.md)| 어떤 경우에도 조직만 보호된 콘텐츠의 암호를 해독할 수 있으며, 규정 요구 사항을 충족하려면 지리적 경계 내에서 암호화 키를 보유해야 합니다. | [이중 키 암호화](double-key-encryption.md#deploy-dke)|
|[OME(Office 365 메시지 암호화)](ome.md)| 모든 장치에서 사용자에게 전송되는 전자 메일 메시지와 첨부된 문서를 암호화하여 권한이 있는 수신자만 전자 메일 정보를 읽을 수 있도록 합니다. <p> 시나리오 예: [Office 365 고급 메시지 암호화로 암호화된 전자 메일 취소](revoke-ome-encrypted-mail.md) | [새 메시지 암호화 기능 설정하기](set-up-new-message-encryption-capabilities.md)|
|[고객 키를 사용한 서비스 암호화](customer-key-overview.md) | 권한이 없는 시스템이나 직원이 데이터를 볼 수 없도록 보호하고 Microsoft 데이터 센터에서 BitLocker 디스크 암호화를 보완합니다. | [Office 365의 고객 키 설정](customer-key-set-up.md)|
|[IRM(정보 권한 관리)](set-up-irm-in-sp-admin-center.md#irm-enable-sharepoint-document-libraries-and-lists)|사용자가 문서를 체크아웃하면 권한이 있는 사용자만 사용자가 지정한 정책에 따라 파일을 보고 사용할 수 있도록 다운로드된 파일이 보호되도록 SharePoint 목록 및 라이브러리를 보호합니다. | [SharePoint Online 관리 센터에서 IRM(정보 권한 관리)을 설정](set-up-irm-in-sp-admin-center.md)|
[권한 관리 커넥터](/azure/information-protection/deploy-rms-connector) |Exchange 또는 SharePoint Server를 사용하는 기존 온-프레미스 배포 또는 Windows Server 및 FCI(파일 분류 인프라)를 실행하는 파일 서버에 대한 보호 전용입니다. | [RMS 커넥터를 배포하는 단계](/azure/information-protection/deploy-rms-connector#steps-to-deploy-the-rms-connector)
|[정보 보호 통합 라벨링 스캐너](/azure/information-protection/deploy-aip-scanner)| 온-프레미스에 있는 데이터 저장소에 있는 중요한 정보를 검색, 레이블 지정 및 보호합니다. | [Azure Information Protection 통합 라벨링 스캐너 구성 및 설치](/azure/information-protection/deploy-aip-scanner-configure-install)|
|[Microsoft Cloud App Security](/cloud-app-security/what-is-cloud-app-security)| 클라우드에 있는 데이터 저장소에 있는 중요한 정보를 검색, 레이블 지정 및 보호합니다. | [클라우드에 저장된 데이터를 검색하고, 분류하고, 레이블을 지정하고, 보호](/cloud-app-security/best-practices#discover-classify-label-and-protect-regulated-and-sensitive-data-stored-in-the-cloud)|
|[Microsoft Information Protection SDK](/information-protection/develop/overview#microsoft-information-protection-sdk)|민감도 레이블을 타사 앱 및 서비스로 확장합니다. <p> 시나리오 예: [민감도 레이블(C++) 설정 및 가져오기](/information-protection/develop/quick-file-set-get-label-cpp) |[MIP(Microsoft Information Protection) SDK 설정 및 구성](/information-protection/develop/setup-configure-mip)|


## <a name="prevent-data-loss"></a>데이터 손실 방지

중요한 정보의 우발적인 과다 공유를 방지하려면 다음 기능을 사용합니다.


|기능|어떤 문제를 해결하나요?|시작|
|:------|:------------|:---------------------|
|[데이터 손실 방지](dlp-learn-about-dlp.md)| 중요한 항목의 의도하지 않은 공유를 방지하는 데 도움이 됩니다. | [기본 DLP 정책을 사용하여 시작](get-started-with-the-default-dlp-policy.md)|
|[끝점 데이터 손실 방지](endpoint-dlp-learn-about.md)| DLP 기능을 Windows 10 컴퓨터에서 사용 및 공유되는 항목으로 확장합니다. | [끝점 데이터 손실 방지 시작](endpoint-dlp-getting-started.md)|
|[Microsoft 규정 준수 확장](dlp-chrome-learn-about.md) | Chrome 브라우저로 DLP 기능 확장 | [Microsoft 규정 준수 확장 시작](dlp-chrome-get-started.md)|
|[Microsoft 365 데이터 손실 방지 온-프레미스 스캐너(미리 보기)](dlp-on-premises-scanner-learn.md)|파일 활동과 해당 파일에 대한 보호 작업 모니터링을 온-프레미스 파일 공유와 SharePoint 폴더 및 문서 라이브러리로 확대시킵니다.|[Microsoft 365 데이터 손실 방지 온-프레미스 스캐너로 시작하기(미리 보기)](dlp-on-premises-scanner-get-started.md)|
|[Microsoft Teams 대화 및 채널 메시지에서 중요한 정보를 보호합니다](dlp-microsoft-teams.md) | Teams 채팅 및 채널 메시지로 일부 DLP 기능 확장 | [Microsoft Teams의 기본 데이터 손실 방지 정책에 대한 자세한 정보(미리 보기)](dlp-teams-default-policy.md)|

## <a name="licensing-requirements"></a>라이선스 요구사항

MIP에 대한 라이선스 요구 사항은 이 페이지에 나열된 각 기능에 대한 라이선스 요구 사항을 설정하는 것이 아니라 사용하는 시나리오 및 기능에 따라 다릅니다. MIP에 대한 라이선스 요구 사항 및 옵션을 이해하려면 Microsoft 365 라이선스 문서의 [정보 보호](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#information-protection) 섹션을 참조하고 기능 수준 라이선스 요구 사항에 대한 [관련 PDF 문서](https://go.microsoft.com/fwlink/?linkid=2139145)를 다운로드하세요.

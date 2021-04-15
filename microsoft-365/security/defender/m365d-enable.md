---
title: Microsoft 365 보안 센터에서 Microsoft 365 Defender 켜기
description: Microsoft 365 Defender를 사용하도록 설정하고 보안 인시던트 및 대응 통합을 시작하는 방법을 학습합니다.
keywords: 시작, MTP 사용, Microsoft Threat Protection, M365, 보안, 데이터 위치, 필요한 사용 권한, 라이선스 자격, 설정 페이지
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: bf8fdb2a8a42ef7b70b744cbbb5663e6afe51989
ms.sourcegitcommit: 7a339c9f7039825d131b39481ddf54c57b021b11
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2021
ms.locfileid: "51764386"
---
# <a name="turn-on-microsoft-365-defender"></a>Microsoft 365 Defender 켜기

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**적용 대상:**
- Microsoft 365 Defender

[Microsoft 365 Defender는](microsoft-365-defender.md) 끝점용 Microsoft Defender, Office 365용 Microsoft Defender, Microsoft Cloud App Security 및 ID용 Microsoft Defender에 주요 기능을 통합하여 인시던트 대응 프로세스를 통합합니다. 이 통합된 환경은 Microsoft 365 보안 센터에서 액세스할 수 있는 강력한 기능을 추가합니다.

필요한 권한이 있는 적격 고객이 Microsoft 365 보안 센터를 방문하면 Microsoft 365 Defender가 자동으로 켜집니다. 이 문서를 읽고 다양한 선행 준비와 Microsoft 365 Defender가 프로비전된 방법을 이해합니다.

## <a name="check-license-eligibility-and-required-permissions"></a>라이선스 자격 및 필요한 사용 권한 확인

Microsoft 365 보안 제품에 대한 라이선스는 일반적으로 추가 라이선스 비용 없이 Microsoft 365 보안 센터에서 Microsoft 365 Defender를 사용할 수 있는 권한을 부여합니다. Microsoft 365 E5, E5 보안, A5 또는 A5 보안 라이선스 또는 지원되는 모든 서비스에 대한 액세스를 제공하는 유효한 라이선스 조합을 다운로드하는 것이 좋습니다.

라이선스에 대한 자세한 내용은 라이선스 [요구 사항을 참조하세요.](prerequisites.md#licensing-requirements)

### <a name="check-your-role"></a>역할 확인

Microsoft 365 Defender를 켜기 위해 Azure Active Directory에서 전역 관리자 또는 보안 관리자 되어야 합니다.   [Azure AD에서 역할 보기](/azure/active-directory/users-groups-roles/directory-manage-roles-portal)

## <a name="supported-services"></a>지원되는 서비스

Microsoft 365 Defender는 이미 배포한 다양한 지원 서비스에서 데이터를 집계합니다. 새 인사이트를 식별하고 중앙 집중식 응답 워크플로를 사용할 수 있도록 데이터를 중앙에서 처리 및 저장합니다. 이 작업에서는 통합 서비스와 연결된 기존 배포, 설정 또는 데이터에 영향을 주지 않습니다.

최상의 보호를 얻고 Microsoft 365 Defender를 최적화하기 위해 네트워크에서 지원되는 모든 서비스를 배포하는 것이 좋습니다. 자세한 내용은 [지원되는 서비스 배포를 참조하십시오.](deploy-supported-services.md)

## <a name="onboard-to-the-service"></a>서비스에 온보드
Microsoft 365 Defender에 온보딩하는 것은 간단합니다. 탐색 메뉴에서 끝점 섹션 아래에 있는 모든 항목(예: 인시던트, 헌팅, 작업 센터 또는 위협 분석)을 선택하여 온보더링 프로세스를 시작할 수 있습니다. 

### <a name="data-center-location"></a>데이터 센터 위치

Microsoft 365 Defender는 [끝점용 Microsoft Defender에서](/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy)사용하는 동일한 위치에 데이터를 저장하고 처리합니다. 끝점용 Microsoft Defender가 없는 경우 활성 Microsoft 365 보안 서비스의 위치에 따라 새 데이터 센터 위치가 자동으로 선택됩니다. 선택한 데이터 센터 위치가 화면에 표시됩니다.

Microsoft 365 보안 센터에서 도움이 **필요하세요?를** 선택하여 다른 데이터 센터 위치에서 Microsoft 365 Defender 프로비전에 대해 Microsoft 지원에 문의하세요.

> [!NOTE]
> 끝점용 Microsoft Defender는 Azure Defender를 통해 켜져 있는 경우 유럽 연합(EU) 데이터 센터에서 자동으로 프로비전합니다. Microsoft 365 Defender는 이 방식으로 끝점에 대한 Defender를 프로비전한 고객을 위해 동일한 EU 데이터 센터에서 자동으로 프로비전합니다.

### <a name="confirm-that-the-service-is-on"></a>서비스가 켜져 있는지 확인합니다.

서비스를 프로비전하면 다음이 추가됩니다.

- [인시던트 관리](incidents-overview.md)
- [경고 큐](investigate-alerts.md)
- [자동화 조사 및 대응](m365d-autoir.md)을 관리하는 알림 센터
- [고급 헌팅](advanced-hunting-overview.md) 기능
- 위협 분석

![Microsoft 365 Defender가 있는 Microsoft 365 보안 센터 탐색 창의 이미지는 인시던트 관리 및 ](../../media/overview-incident.png)
 *기타 Microsoft 365 Defender* 기능을 사용하여 Microsoft 365 보안 센터 기능을 제공합니다.

### <a name="getting-microsoft-defender-for-identity-data"></a>ID 데이터에 대한 Microsoft Defender 다운로드 
Microsoft Cloud App Security와의 통합을 사용하도록 설정하려면 Microsoft Cloud App Security에 한 번 이상 로그인해야 합니다.

## <a name="get-assistance"></a>지원 받기

Microsoft 365 Defender를 켜는 데 대한 가장 일반적으로 묻는 질문에 대한 답변을 얻었다면 [FAQ를 읽어 하세요.](m365d-enable-faq.md)

Microsoft 지원 직원은 테넌트에서 서비스 및 관련 리소스를 프로비전하거나 프로비전을 프로비전하는 데 도움을 줄 수 있습니다. 도움을 요청하려면 Microsoft 365 보안 센터에서 **도움이** 필요하세요?를 선택합니다. 지원에 문의할 때 Microsoft 365 Defender를 언급합니다.

## <a name="related-topics"></a>관련 항목

- [자주 묻는 질문과 대답](m365d-enable-faq.md)
- [라이선스 요구 사항 및 기타 필수 구성 요소](prerequisites.md)
- [지원 서비스 배포](deploy-supported-services.md)
- [Microsoft 365 Defender 개요](microsoft-365-defender.md)
- [끝점용 Microsoft Defender 개요](../defender-endpoint/microsoft-defender-endpoint.md)
- [Office 365용 Defender 개요](../office-365-security/defender-for-office-365.md)
- [Microsoft Cloud App Security 개요](/cloud-app-security/what-is-cloud-app-security)
- [Microsoft Defender for Identity 개요](/azure-advanced-threat-protection/what-is-atp)
- [끝점 데이터 저장소용 Microsoft Defender](../defender-endpoint/data-storage-privacy.md)

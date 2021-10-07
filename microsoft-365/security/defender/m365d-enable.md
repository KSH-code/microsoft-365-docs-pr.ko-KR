---
title: Microsoft 365 Defender 켜기
description: 보안 인시던트와 Microsoft 365 Defender 통합을 시작하는 방법을 배워야 합니다.
keywords: 시작, Microsoft 365 Defender, Microsoft 365 Defender, M365, 보안, 데이터 위치, 필요한 사용 권한, 라이선스 자격, 설정 페이지
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: b64990320684f6c022a2fc8a2092141af5728679
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60174402"
---
# <a name="turn-on-microsoft-365-defender"></a>Microsoft 365 Defender 켜기

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**적용 대상:**
- Microsoft 365 Defender

[Microsoft 365 Defender](microsoft-365-defender.md) Microsoft Defender for Endpoint, microsoft Defender for Office 365, Microsoft Cloud App Security 및 Id용 Microsoft Defender에 주요 기능을 통합하여 인시던트 대응 프로세스를 통합합니다. 이 통합된 환경은 사이트 포털에서 액세스할 수 있는 강력한 Microsoft 365 Defender 추가합니다.

Microsoft 365 Defender 권한이 있는 적격 고객이 포털을 방문하면 Microsoft 365 Defender 설정됩니다. 이 문서를 읽고 다양한 선행 준비와 프로비전 Microsoft 365 Defender 이해합니다.

## <a name="check-license-eligibility-and-required-permissions"></a>라이선스 자격 및 필요한 사용 권한 확인

일반적으로 보안 Microsoft 365 라이선스를 사용하면 추가 라이선스 비용 없이 Microsoft 365 Defender 사용할 수 있습니다. 지원되는 모든 서비스에 대한 액세스를 Microsoft 365 E5, E5 보안, A5 또는 A5 보안 라이선스 또는 유효한 라이선스 조합을 구입하는 것이 좋습니다.

자세한 라이선스 정보는 [라이선스 요구 사항을 읽으세요](prerequisites.md#licensing-requirements).

### <a name="check-your-role"></a>역할 확인

전역 관리자  또는 보안  관리자 Azure Active Directory 설정해야 Microsoft 365 Defender. [Azure AD에서 역할 보기](/azure/active-directory/users-groups-roles/directory-manage-roles-portal)

## <a name="supported-services"></a>지원되는 서비스

Microsoft 365 Defender는 이미 배포한 지원되는 다양한 서비스의 데이터를 집계합니다. 데이터를 중앙에서 처리하고 저장하여 새 인사이트를 식별하고 중앙 집중식 응답 워크플로를 가능하게 만듭니다. 통합 서비스와 연결된 기존 배포, 설정 또는 데이터에 영향을 주지 않고 이 작업을 수행합니다.

최상의 보호를 적용하고 최적화하기 Microsoft 365 Defender 지원되는 모든 서비스를 네트워크에 배포하는 것이 좋습니다. 자세한 내용은 [지원되는 서비스 배포를 참조하십시오.](deploy-supported-services.md)

## <a name="onboard-to-the-service"></a>서비스에 온보드
온보드를 Microsoft 365 Defender 간단합니다. 탐색 메뉴에서 인시던트 및 경고, &, 알림 센터 또는  **위협** 분석과 **같은** 항목을 선택하여 온보더링 프로세스를 초기화합니다. 

### <a name="data-center-location"></a>데이터 센터 위치

Microsoft 365 Defender Microsoft [Defender for Endpoint에서](/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy)사용하는 동일한 위치에 데이터를 저장하고 처리합니다. 끝점용 Microsoft Defender가 없는 경우 활성 데이터 센터 보안 서비스의 위치에 따라 새 데이터 센터 Microsoft 365 선택됩니다. 선택한 데이터 센터 위치가 화면에 표시됩니다.

다른 **데이터** 센터 위치의 프로비전 Microsoft 365 Defender Microsoft 지원에 문의하려면 Microsoft 365 Defender 필요하세요?를 선택합니다.

> [!NOTE]
> 과거에는 Azure Defender를 통해 켜져 있는 경우 끝점용 Microsoft Defender가 EU(유럽 연합) 데이터 센터에서 자동으로 프로비전됩니다. Microsoft 365 Defender 이 방식으로 끝점에 대해 Defender를 프로비전한 고객을 위해 동일한 EU 데이터 센터에서 자동으로 프로비전합니다.

### <a name="confirm-that-the-service-is-on"></a>서비스가 켜져 있는지 확인합니다.

서비스를 프로비전하면 다음이 추가됩니다.

- [인시던트 관리](incidents-overview.md)
- [경고 큐](investigate-alerts.md)
- [자동화 조사 및 대응](m365d-autoir.md)을 관리하는 알림 센터
- [고급 헌팅](advanced-hunting-overview.md) 기능
- 위협 분석

![기본 Microsoft 365 Defender 있는 포털 탐색 창의 Microsoft 365 Defender. ](../../media/overview-incident.png)
 *Microsoft 365 Defender 관리* 및 기타 기능이 있는 포털

### <a name="getting-microsoft-defender-for-identity-data"></a>ID 데이터에 대한 Microsoft Defender 다운로드 
사용자와 통합을 Microsoft Cloud App Security 한 번 이상 로그인해야 Microsoft Cloud App Security 합니다.

## <a name="get-assistance"></a>지원 받기

이 기능을 켜는 데 대한 가장 일반적으로 묻는 질문에 대한 답변을 Microsoft 365 Defender [FAQ를 읽어 보아야 합니다.](m365d-enable-faq.md)

Microsoft 지원 직원은 테넌트에서 서비스 및 관련 리소스를 프로비전하거나 프로비전을 프로비전하는 데 도움을 줄 수 있습니다. 도움이 **필요하세요?** 포털에서 도움이 Microsoft 365 Defender 선택합니다. 지원에 문의할 때 지원에 Microsoft 365 Defender.

## <a name="related-topics"></a>관련 항목

- [자주 묻는 질문](m365d-enable-faq.md)
- [라이선스 요구 사항 및 기타 필수 구성 요소](prerequisites.md)
- [지원 서비스 배포](deploy-supported-services.md)
- [Microsoft 365 Defender 개요](microsoft-365-defender.md)
- [끝점용 Microsoft Defender 개요](../defender-endpoint/microsoft-defender-endpoint.md)
- [Defender for Office 365 개요](../office-365-security/defender-for-office-365.md)
- [Microsoft Cloud App Security 개요](/cloud-app-security/what-is-cloud-app-security)
- [Microsoft Defender for Identity 개요](/azure-advanced-threat-protection/what-is-atp)
- [끝점 데이터 저장소용 Microsoft Defender](../defender-endpoint/data-storage-privacy.md)

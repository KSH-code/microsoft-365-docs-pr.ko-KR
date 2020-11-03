---
title: Microsoft 365 보안 센터에서 Microsoft 365 Defender 켜기
description: Microsoft 365 Defender를 사용 하도록 설정 하 고 보안 인시던트 및 응답의 통합을 시작 하는 방법을 알아봅니다.
keywords: 시작, MTP, Microsoft Threat Protection, M365, 보안, 데이터 위치, 필수 사용 권한, 라이선스 자격, 설정 페이지
search.product: eADQiWindows 10XVcnh
ms.prod: microsoft-365-enterprise
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
ms.openlocfilehash: b5bb99ed4b8cee7ea920679e20f69c7a0e002d26
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/03/2020
ms.locfileid: "48843639"
---
# <a name="turn-on-microsoft-365-defender"></a>Microsoft 365 Defender 켜기

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**적용 대상:**
- Microsoft 365 Defender

[Microsoft 365 Defender](microsoft-threat-protection.md) 는 끝점, microsoft Defender for Office 365, Microsoft Cloud App Security 및 microsoft Defender for Identity에 주요 기능을 통합 하 여 문제 대응 프로세스를 함께 제공 합니다. 이 통합된 환경은 Microsoft 365 보안 센터에서 액세스할 수 있는 강력한 기능을 추가합니다.

Microsoft 365 Defender는 필요한 권한이 있는 적합 한 고객이 Microsoft 365 보안 센터에 방문 하면 자동으로 켜 집니다. 이 문서를 읽으면 다양 한 필수 구성 요소와 Microsoft 365 Defender가 구축 되는 방식을 이해할 수 있습니다.

## <a name="check-license-eligibility-and-required-permissions"></a>라이선스 자격 및 필요한 권한 확인
Microsoft 365 보안 제품에 대 한 라이선스는 일반적으로 추가 라이선스 비용 없이 microsoft 365 보안 센터에서 Microsoft 365 Defender를 사용 하는 통해입니다. Microsoft 365 E5, E5 Security, A5 또는 A5 보안 라이선스를 가져오거나 지원 되는 모든 서비스에 대 한 액세스를 제공 하는 유효한 라이선스 조합을 사용 하는 것이 좋습니다.

라이선스 정보에 대 한 자세한 내용은 [라이선스 요구 사항을 참조](prerequisites.md#licensing-requirements)하세요.

### <a name="check-your-role"></a>역할 확인
Microsoft 365 Defender를 켜려면 **전역 관리자** 이거나 Azure Active Directory의 **보안 관리자** 여야 합니다. [Azure AD에서 역할 보기](https://docs.microsoft.com//azure/active-directory/users-groups-roles/directory-manage-roles-portal)

## <a name="supported-services"></a>지원 되는 서비스
Microsoft 365 Defender는 이미 배포 된 다양 한 지원 서비스에서 데이터를 집계 합니다. 새 정보를 식별 하 고 중앙 집중식 응답 워크플로를 수행할 수 있도록 중앙에서 데이터를 처리 및 저장 합니다. 통합 서비스와 연결 된 기존 배포, 설정 또는 데이터에 영향을 주지 않고이를 수행 합니다.

최적의 보호를 위해 Microsoft 365 Defender를 최적화 하려면 적용 가능한 모든 지원 서비스를 네트워크에 배포 하는 것이 좋습니다. 자세한 내용은 [지원 되는 서비스 배포에 대 한 내용을 참조](deploy-supported-services.md)하세요.

## <a name="before-starting-the-service"></a>서비스를 시작 하기 전에
서비스를 설정 하기 전에 Microsoft 365 보안 센터 ( [security.microsoft.com](https://security.microsoft.com))는 탐색 창에서 **인시던트** , **작업 센터** **또는 검색** 을 선택할 때 microsoft 365 Defender 설정 페이지를 표시 합니다. 이러한 탐색 항목은 Microsoft 365 Defender를 사용할 수 없는 경우에는 표시 되지 않습니다.

![Microsoft 365 ](../../media/mtp-enable/mtp-settings.png)
 *보안 센터 365의 Microsoft 365 defender settings* on에 설정 되어 있지 않은 경우 표시 되는 microsoft 365 defender settings 페이지 이미지

## <a name="starting-the-service"></a>서비스 시작
Microsoft 365 Defender를 켜려면 **microsoft 365 defender를 켠** 후 변경 사항을 적용 하기만 하면 됩니다. 탐색 창에서 **설정** ( [security.microsoft.com/settings](https://security.microsoft.com/settings))을 선택 하 고 **microsoft 365 Defender** 를 선택 하 여이 옵션에 액세스할 수도 있습니다.

>[!NOTE]
>탐색 창에 **설정이** 표시 되지 않거나 페이지에 액세스할 수 없는 경우 사용 권한 및 라이선스를 확인 합니다.

### <a name="data-center-location"></a>데이터 센터 위치
Microsoft 365 Defender는 [Microsoft Defender For Endpoint에서 사용 하는 것과 동일한 위치](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy)에 데이터를 저장 하 고 처리 합니다. Microsoft Defender for Endpoint를 사용 하지 않는 경우에는 활성 Microsoft 365 보안 서비스의 위치에 따라 새 데이터 센터 위치가 자동으로 선택 됩니다. 선택한 데이터 센터 위치가 화면에 표시 됩니다. 

Microsoft 기술 지원 서비스에 문의 하 여 microsoft 365 Defender를 다른 데이터 센터 위치에 프로 비전 하는 방법에 대 한 자세한 내용은 마이크로소프트 365 보안 센터를 **참조** 하세요. 

>[!NOTE]
>끝점에 대 한 Microsoft Defender Azure Defender *를 통해 켜면 EU (유럽 연합) 데이터 센터를 자동으로 프로 비전 합니다. Microsoft 365 Defender는이 방식으로 끝점에 대 한 Defender를 프로 비전 한 고객을 위해 동일한 EU 데이터 센터를 자동으로 프로 비전 합니다. 

### <a name="confirm-that-the-service-is-on"></a>서비스가 켜져 있는지 확인합니다.
서비스를 프로비전하면 다음이 추가됩니다.

- [인시던트 관리](incidents-overview.md)
- [자동화 조사 및 대응](mtp-autoir.md)을 관리하는 알림 센터
- [고급 구하기](advanced-hunting-overview.md) 기능

![Microsoft 365 Defender features이 포함 된 마이크로소프트 365 보안 센터 탐색 창 이미지 microsoft ](../../media/mtp-enable/mtp-on.png)
 *365 보안 센터 (문제 관리 및 기타 Microsoft 365 Defender 기능 포함* )

### <a name="getting-microsoft-defender-for-identity-data"></a>Id 데이터에 대 한 Microsoft Defender 가져오기
Microsoft 365 Defender를 사용 하 여 Id 데이터에 대 한 Microsoft Defender를 공유 하려면 Microsoft Cloud App Security 및 Microsoft Defender for Identity 통합용을 설정 해야 합니다. [이 통합에 대한 자세한 정보](https://docs.microsoft.com/cloud-app-security/aatp-integration)


## <a name="turn-off-microsoft-365-defender"></a>Microsoft 365 Defender 끄기
Microsoft 365 Defender 사용을 중지 하려면 **Settings**  >  microsoft 365 보안 센터에서 **microsoft 365 Defender**  >  **옵트인/옵트아웃** 설정으로 이동 합니다. **Microsoft 365 Defender 사용** 을 선택 취소 하 고 변경 내용을 적용 합니다.

해당 기능은 Microsoft 365 보안 센터에서 제거 됩니다.

## <a name="get-assistance"></a>지원 받기

Microsoft 365 Defender를 켜는 방법에 대 한 가장 일반적인 질문과 대답을 보려면 [FAQ를 참조](mtp-enable-faq.md)하세요.

Microsoft 지원 요원은 테 넌 트에 서비스 및 관련 리소스를 구축 하거나 프로 비전 해제 하는 데 도움이 될 수 있습니다. 도움이 필요 하면 Microsoft 365 보안 센터에서 **도움말 보기** 를 선택 합니다. 지원 센터에 문의 하는 경우 Microsoft 365 Defender를 언급 합니다.

## <a name="related-topics"></a>관련 항목

- [자주 묻는 질문과 대답](mtp-enable-faq.md)
- [라이선스 요구 사항 및 기타 필수 구성 요소](prerequisites.md)
- [지원 서비스 사용](deploy-supported-services.md)
- [Microsoft 365 Defender 개요](microsoft-threat-protection.md)
- [끝점에 대 한 Microsoft Defender 개요](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)
- [Defender for Office 365 개요](../office-365-security/office-365-atp.md)
- [Microsoft Cloud App Security 개요](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security)
- [Id에 대 한 Microsoft Defender 개요](https://docs.microsoft.com/azure-advanced-threat-protection/what-is-atp)
- [Microsoft Defender for Endpoint data 저장소](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy)

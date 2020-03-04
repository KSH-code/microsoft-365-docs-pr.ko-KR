---
title: Microsoft 365 보안 센터에서 Microsoft Threat Protection 사용 설정
description: Microsoft Threat Protection를 사용하도록 설정하고 보안 인시던트 및 대응 통합을 시작하는 방법을 알아봅니다.
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
ms.openlocfilehash: 73c4c9864713432d318b0b3cec9fbaf395deff45
ms.sourcegitcommit: 0df099d2e1028bbba8b6371dc5fcd021dddc902b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/03/2020
ms.locfileid: "42374149"
---
# <a name="turn-on-microsoft-threat-protection"></a>Microsoft Threat Protection 사용 설정

**적용 대상:**
- Microsoft Threat Protection

Microsoft Threat Protection은 Microsoft Defender의 ATP(Advanced Threat Protection), Office 365 ATP, Microsoft Cloud App Security, Azure ATP에 주요 기능을 통합하여 인시던트 대응 프로세스를 통합합니다. 이 통합된 환경은 Microsoft 365 보안 센터에서 액세스할 수 있는 강력한 기능을 추가합니다.

최적의 보호를 위해 Microsoft 위협 보호를 얻으려면 해당 하는 모든 지원 서비스를 네트워크에 배포 하는 것이 좋습니다. 자세한 내용은 [지원 되는 서비스 배포에 대 한 내용을 참조](deploy-supported-services.md)하세요.

## <a name="check-license-eligibility-and-required-permissions"></a>라이선스 자격 및 필요한 권한 확인
Microsoft 365 E5, E5 Security, A5 또는 A5 보안 라이선스 또는 유효한 라이선스 조합이 지원 되는 서비스에 대 한 액세스를 제공 하 고 통해 microsoft 365 보안 센터에서 Microsoft Threat Protection을 사용할 수 있습니다.

라이선스 정보에 대 한 자세한 내용은 [라이선스 요구 사항을 참조](prerequisites.md#licensing-requirements)하세요.

### <a name="check-your-role"></a>역할 확인
Microsoft Threat Protection을 켜려면 **전역 관리자** 이거나 Azure Active Directory의 **보안 관리자** 여야 합니다. [Azure AD에서 역할 보기](https://docs.microsoft.com//azure/active-directory/users-groups-roles/directory-manage-roles-portal)

## <a name="start-using-the-service"></a>서비스 사용 시작
Microsoft Threat Protection은 다양 한 통합 서비스에서 데이터를 집계 합니다. 새 정보를 식별 하 고 중앙 집중식 응답 워크플로를 수행할 수 있도록 중앙에서 데이터를 처리 및 저장 합니다.

서비스를 설정 하기 전에 Microsoft 365 보안 센터 ([security.microsoft.com](https://security.microsoft.com))는 탐색 창에서 **인시던트**, **작업 센터** **또는 검색** 을 선택할 때 microsoft 위협 보호 시작 페이지를 표시 합니다. 이러한 탐색 옵션은 Microsoft Threat Protection을 사용할 수 없는 경우에는 표시 되지 않습니다.

![Microsoft](../../media/mtp-welcome.png)
*보안 센터 365의* microsoft threat protection 시작 페이지에서 microsoft threat protection이 설정 되지 않은 경우 표시 되는 microsoft threat protection 환영 페이지 이미지

Microsoft Threat Protection을 설정 하려면 환영 페이지에서 프로세스를 완료 하기만 하면 됩니다. 탐색 창에서[security.microsoft.com/settings](https://security.microsoft.com/settings)( **설정** )에 액세스 하 고 **microsoft threat Protection**을 선택 하 여 microsoft threat protection을 설정할 수도 있습니다.

>[!NOTE]
>탐색 창에 **설정이** 표시 되지 않거나 페이지에 액세스할 수 없는 경우 사용 권한 및 라이선스를 확인 합니다.

### <a name="select-data-center-location"></a>데이터 센터 위치 선택
Microsoft Defender ATP가 조직에 프로비전된 경우 [Microsoft Defender ATP 데이터](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy)를 위해 선택한 것과 동일한 데이터 센터 위치에 데이터가 저장되고 처리됩니다. Microsoft Defender ATP가 없는 경우 Microsoft Threat Protection를 위한 새로운 데이터 센터 위치를 선택하라는 메시지가 표시됩니다. 

서비스 간에 데이터를 공유 하 고 집계 하기 전에 동의를 제공 해야 합니다.

### <a name="confirm-that-the-service-is-on"></a>서비스가 켜져 있는지 확인합니다.
서비스를 프로비전하면 다음이 추가됩니다.

- [인시던트 관리](incidents-overview.md)
- [자동화 조사 및 대응](mtp-autoir.md)을 관리하는 알림 센터
- [고급 구하기](advanced-hunting-overview.md) 기능

![Microsoft threat protection 기능이](../../media/mtp-on.png)
있는 microsoft 365 보안 센터 탐색 창 이미지*문제 관리 및 기타 microsoft threat protection 기능을 가진 microsoft 365 보안 센터*

### <a name="getting-azure-atp-data"></a>Azure ATP 데이터 가져오기
Azure ATP 데이터를 Microsoft Threat Protection 기능과 공유하려면 Microsoft Cloud App Security 및 Azure ATP 통합이 사용하도록 설정되어 있는지 확인하세요. [이 통합에 대한 자세한 정보](https://docs.microsoft.com/cloud-app-security/aatp-integration)


## <a name="turn-off-microsoft-threat-protection"></a>Microsoft Threat Protection 해제
Microsoft Threat Protection 사용을 중지하려면 Microsoft 365 보안 센터에서 **설정** > **Microsoft Threat Protection** > **옵트인/옵트아웃**으로 이동합니다. **Microsoft Threat Protection 사용**을 선택 취소하고 변경 내용을 저장합니다.

해당 기능은 Microsoft 365 보안 센터에서 제거 됩니다.

## <a name="get-assistance"></a>지원 받기

Microsoft 지원 요원은 테 넌 트에 서비스 및 관련 리소스를 구축 하거나 프로 비전 해제 하는 데 도움이 될 수 있습니다. 도움이 필요 하면 Microsoft 365 보안 센터에서 **도움말 보기** 를 선택 합니다. 지원 센터에 문의 하는 경우 Microsoft Threat Protection을 언급 합니다.

## <a name="related-topics"></a>관련 항목

- [Microsoft Threat Protection 개요](microsoft-threat-protection.md)
- [라이선스 요구 사항 및 기타 필수 구성 요소](prerequisites.md)
- [지원 되는 서비스 배포](deploy-supported-services.md)
- [Microsoft Defender ATP 개요](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)
- [Office 365 ATP 개요](../office-365-security/office-365-atp.md)
- [Microsoft Cloud App Security 개요](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security)
- [Azure ATP 개요](https://docs.microsoft.com/azure-advanced-threat-protection/what-is-atp)
- [Microsoft Defender ATP 데이터 저장소](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy)

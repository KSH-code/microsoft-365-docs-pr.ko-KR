---
title: Microsoft 365 Defender 선행 준비
description: Defender의 라이선스, 하드웨어 및 소프트웨어 요구 사항 및 기타 구성 설정에 Microsoft 365 정보
keywords: 요구 사항, 선행 조건, 하드웨어, 소프트웨어, 브라우저, Microsoft 365 Defender, M365, 라이선스, E5, A5, EMS, 구매
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: f3fd597181d73c1768057ea7740ab111e5af2068
ms.sourcegitcommit: 82a4d74020cd93ba444006317cfecc178c6d41dc
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/27/2021
ms.locfileid: "52689160"
---
# <a name="microsoft-365-defender-prerequisites"></a>Microsoft 365 Defender 선행 준비

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**적용 대상:**
- Microsoft 365 Defender

Defender를 프로비전하고 사용하는 라이선싱 [및 기타 요구 사항에 대해 Microsoft 365.](microsoft-365-defender.md)

## <a name="licensing-requirements"></a>라이선스 요구사항
이러한 라이선스를 사용하면 추가 비용 없이 Microsoft 365 보안 센터의 Microsoft 365 Defender 기능에 액세스할 수 있습니다.

- Microsoft 365 E5 또는 A5
- Microsoft 365 E3 추가 Microsoft 365 E5 Security 있는 경우
- Microsoft 365 A3 및 Microsoft 365 A5 보안 추가 기능
- Windows 10 Enterprise E5 또는 A5
- Enterprise Mobility + Security(EMS) E5 또는 A5 
- Office 365 E5 또는 A5
- 엔드포인트용 Microsoft Defender
- ID용 Microsoft Defender 
- Microsoft Cloud App Security
- Office 365용 Defender(플랜 2)

자세한 내용은 서비스 [Microsoft 365 Enterprise 를 참조하십시오.](https://www.microsoft.com/licensing/product-licensing/microsoft-365-enterprise)

> 아직 라이선스가 없는 경우 [Microsoft 365 구독 체험 또는 구매](../../commerce/try-or-buy-microsoft-365.md)

### <a name="check-your-existing--licenses"></a>기존 라이선스 확인
기존 라이선스를 Microsoft 365 관리[](https://admin.microsoft.com/)센터(admin.microsoft.com)로 이동하세요. 관리 센터에서 **청구** > **라이선스** 로 이동합니다.

>[!NOTE]
> 라이선스 정보를 볼 수  있게 하려면  [Azure AD에서](/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles) 청구 관리자 또는 전역 리더 역할을 할당해야 합니다. 액세스 문제가 발생하는 경우 전역 관리자에게 문의하세요.

## <a name="required-permissions"></a>필수 권한
Defender를  켜기 위해  전역 관리자 또는 Azure Active Directory 관리자 Microsoft 365 합니다. Microsoft 365 Defender를 사용하는 데 필요한 역할 목록과 데이터에 대한 액세스가 규제되는 방법에 대한 정보는 Microsoft 365 Defender에 대한 액세스 [관리에 대해 읽어 보아야 합니다.](m365d-permissions.md)

## <a name="browser-requirements"></a>브라우저 요구 사항
Microsoft 365, Microsoft 365, Internet Explorer Microsoft Edge 11 또는 HTML 5 호환 웹 브라우저를 사용하여 Microsoft 365 보안 센터에서 Internet Explorer Defender에 액세스합니다.

## <a name="availability-to-us-gcc-gcc-high-and-other-us-government-institutions"></a>US GCC, GCC High 및 기타 미국 정부 기관의 가용성
현재 다음 Microsoft 365 Defender를 *사용할 수* 없습니다.
- US 정부 커뮤니티 클라우드(GCC)
- US 정부 커뮤니티 클라우드 High(GCC High)
- 미 국방부
- 상업용 라이선스가 있는 모든 미국 정부 기관


현재 Microsoft Defender for Office 365 통합 Microsoft 365 Defend Office 365 er 기능에 통합할 수 없습니다.

- 브라질 
- 독일 
- 노르웨이 
- 싱가포르 
- 남아프리카 공화국
- 스위스 
- 아랍에미리트 


## <a name="related-topics"></a>관련 항목
- [Microsoft 365 Defender 개요](microsoft-365-defender.md)
- [Microsoft 365 Defender 켜기](m365d-enable.md)
- [액세스 및 사용 권한 관리](m365d-permissions.md)

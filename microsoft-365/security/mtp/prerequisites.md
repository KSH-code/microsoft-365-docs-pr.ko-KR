---
title: Microsoft 365 Defender 필수 구성 요소
description: Microsoft 365 Defender에 대 한 라이선스, 하드웨어 및 소프트웨어 요구 사항 및 기타 구성 설정에 대해 알아보기
keywords: 요구 사항, 필수 구성 요소, 하드웨어, 소프트웨어, 브라우저, MTP, M365, license, E5, A5, EMS, purchase
search.product: eADQiWindows 10XVcnh
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: 415cdb79a6aa9371ee2f07de579cfb2f873f1acb
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/03/2020
ms.locfileid: "48844779"
---
# <a name="microsoft-365-defender-prerequisites"></a>Microsoft 365 Defender 필수 구성 요소

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**적용 대상:**
- Microsoft 365 Defender

[Microsoft 365 Defender](microsoft-threat-protection.md)를 프로 비전 하 고 사용 하기 위한 라이선스 및 기타 요구 사항에 대해 알아봅니다.

## <a name="licensing-requirements"></a>라이선스 요구 사항
이러한 라이선스를 사용 하면 추가 비용 없이 Microsoft 365 보안 센터의 Microsoft 365 Defender 기능에 액세스할 수 있습니다.

- Microsoft 365 E5 또는 A5
- Microsoft 365 E5 보안 또는 A5 보안
- Windows 10 Enterprise E5 또는 A5
- EMS (Enterprise Mobility + Security) E5 또는 A5 
- Office 365 E5 또는 A5
- 엔드포인트용 Microsoft Defender
- ID용 Microsoft Defender 
- Microsoft Cloud App Security
- Defender for Office 365 (요금제 2)

> [!NOTE]
> Office 365 평가판 라이선스는 현재 Microsoft 365 Defender에 대 한 액세스를 제공 하지 않습니다.

자세한 내용은 [Microsoft 365 Enterprise 서비스 요금제를 참조](https://www.microsoft.com/licensing/product-licensing/microsoft-365-enterprise)하세요.

> 아직 라이선스가 없습니까? [Microsoft 365 구독 체험 또는 구매](https://docs.microsoft.com/microsoft-365/commerce/try-or-buy-microsoft-365?view=o365-worldwide)

### <a name="check-your-existing--licenses"></a>기존 라이선스 확인
Microsoft 365 관리 센터 ([admin.microsoft.com](https://admin.microsoft.com/))로 이동 하 여 기존 라이선스를 확인 합니다. 관리 센터에서 **청구** > **라이선스** 로 이동합니다.

>[!NOTE]
> 라이선스 정보를 보려면 [AZURE AD의](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles) **청구 관리자** 또는 **전역 독자** 역할을 할당 받아야 합니다. 액세스 문제가 발생하는 경우 전역 관리자에게 문의하세요.

## <a name="required-permissions"></a>필요한 사용 권한
Microsoft 365 Defender를 켜려면 **전역 관리자** 이거나 Azure Active Directory의 **보안 관리자** 여야 합니다. Microsoft 365 Defender를 사용 하는 데 필요한 역할 목록과 데이터 액세스에 대 한 정보를 규정 하려면 [Microsoft 365 Defender에 대 한 액세스 관리](mtp-permissions.md)를 참조 하세요.

## <a name="browser-requirements"></a>브라우저 요구 사항
Microsoft Edge, Internet Explorer 11 또는 HTML 5와 호환 되는 웹 브라우저를 사용 하 여 microsoft 365 보안 센터에서 Microsoft 365 Defender에 액세스 합니다.

## <a name="availability-to-us-gcc-gcc-high-and-other-us-government-institutions"></a>미국 GCC, GCC 최고 및 기타 미국 정부 기관에 대 한 가용성
현재 Microsoft 365 Defender는 다음에 사용할 수 *없습니다* .
- 미국 정부 커뮤니티 클라우드 (GCC)
- 미국 정부 커뮤니티 클라우드 높음 (GCC 높음)
- 미국 방어 부서
- 상업적 라이선스를 포함 하는 모든 미국 정부 기관

## <a name="related-topics"></a>관련 항목
- [Microsoft 365 Defender 개요](microsoft-threat-protection.md)
- [Microsoft 365 Defender 켜기](mtp-enable.md)
- [액세스 및 사용 권한 관리](mtp-permissions.md)

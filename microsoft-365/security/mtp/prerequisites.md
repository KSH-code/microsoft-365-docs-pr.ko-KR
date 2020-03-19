---
title: Microsoft 위협 방지 필수 구성 요소
description: Microsoft 위협 방지의 라이선싱, 하드웨어 및 소프트웨어 요구 사항 및 기타 구성 설정에 대해 알아봅니다.
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
ms.openlocfilehash: c482e46cf51cbf11960c02663221df0c136b067c
ms.sourcegitcommit: fe4beef350ef9f39b1098755cff46fa2b8e7dc4d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/19/2020
ms.locfileid: "42857182"
---
# <a name="microsoft-threat-protection-prerequisites"></a>Microsoft 위협 방지 필수 구성 요소

**적용 대상:**
- Microsoft 위협 방지

Microsoft Threat Protection을 프로 비전 하 고 사용 하기 위한 라이선스, 하드웨어 및 소프트웨어 요구 사항 및 기타 구성 설정에 대해 알아봅니다.

## <a name="licensing-requirements"></a>라이선스 요구 사항
Microsoft Threat Protection을 사용 하려면 단일 라이선스 또는 라이선스 조합이 필요 합니다.

### <a name="single-license"></a>단일 라이선스
다음 라이선스 *중 하나* 를 사용할 수 있습니다.

- Microsoft 365 E5 또는 A5
- Microsoft 365 E5 보안 또는 A5 보안

### <a name="combination-of-licenses"></a>라이선스 조합
Office 365, *EMS (Enterprise Mobility + Security)* 및 Windows에 대해 E5 또는 A5 구독에 대해 라이선스 조합을 사용할 수도 있습니다. 라이선스 조합에는 다음 라이선스가 *모두* 포함 되어야 합니다.

- Office 365 E5 또는 A5
- *EMS (Enterprise Mobility + Security)* E5 또는 A5
- Windows E5 또는 A5

자세한 내용은 [Microsoft 365 Enterprise 서비스 요금제를 참조](https://www.microsoft.com/licensing/product-licensing/microsoft-365-enterprise)하세요.

> 아직 라이선스가 없습니까? [Microsoft 365 구독 체험 또는 구입](https://docs.microsoft.com/microsoft-365/commerce/try-or-buy-microsoft-365?view=o365-worldwide)

### <a name="check-your-existing--licenses"></a>기존 라이선스 확인
Microsoft 365 관리 센터 ([admin.microsoft.com](https://admin.microsoft.com/))로 이동 하 여 기존 라이선스를 확인 합니다. 관리 센터에서 **청구** > **라이선스**로 이동합니다.

>[!NOTE]
> 라이선스 정보를 보려면 [AZURE AD의](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles) **청구 관리자** 또는 **전역 독자** 역할을 할당 받아야 합니다. 액세스 문제가 발생하는 경우 전역 관리자에게 문의하세요.

## <a name="browser-requirements"></a>브라우저 요구 사항
Microsoft Edge, Internet Explorer 11 또는 HTML 5와 호환 되는 웹 브라우저를 사용 하 여 microsoft 365 보안 센터의 Microsoft 위협 보호에 액세스 합니다.

## <a name="microsoft-threat-protection-for-us-government-community-cloud-and-us-government-community-cloud-high-gcc-high-customers"></a>Microsoft Threat Protection for US 정부 커뮤니티 클라우드 및 미국 정부 커뮤니티 클라우드 (GCC 최고) 고객
현재 Microsoft Threat Protection은 GCC 및 GCC High 고객에 게 제공 되지 않습니다. 

## <a name="related-topics"></a>관련 항목
- [Microsoft 위협 방지 개요](microsoft-threat-protection.md)
- [Microsoft 위협 방지 설정](mtp-enable.md)

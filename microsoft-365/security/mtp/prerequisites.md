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
ms.openlocfilehash: 71e7b532e046015dd64e51fd422d276433d65b3a
ms.sourcegitcommit: 6ea9a910a8106a5f1aa589c55d166bfa67fd12a8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/18/2020
ms.locfileid: "44280537"
---
# <a name="microsoft-threat-protection-prerequisites"></a>Microsoft 위협 방지 필수 구성 요소

**적용 대상:**
- Microsoft 위협 방지

Microsoft Threat Protection을 프로 비전 하 고 사용 하기 위한 라이선스, 하드웨어 및 소프트웨어 요구 사항 및 기타 구성 설정에 대해 알아봅니다.

## <a name="licensing-requirements"></a>라이선스 요구 사항

>[!IMPORTANT]
>시작 시 12 일, 2020 Microsoft는 라이선스 요구에 따라 최적화 된 새 환경을 점진적으로 배포 하 고 [Microsoft Threat Protection을 설정](mtp-enable.md)합니다. 이 기간 중 몇 주 동안 일부 고객은 포털 환경에 대 한 변경 내용을 확인 하기 시작 합니다. 새로운 환경에 대 한 정보는이 문서의 **새로운 환경** 으로 표시 됩니다.

Microsoft Threat Protection을 사용 하려면 단일 라이선스 또는 라이선스 조합이 필요 합니다. 이러한 라이선스 또는 라이선스 조합은 추가 비용 없이 Microsoft Threat Protection 기능에 액세스할 수 있도록 합니다.

### <a name="single-license"></a>단일 라이선스
다음 라이선스 *중 하나* 를 사용할 수 있습니다.

- Microsoft 365 E5 또는 A5
- Microsoft 365 E5 보안 또는 A5 보안

### <a name="combination-of-licenses"></a>라이선스 조합
Office 365, *EMS (Enterprise Mobility + Security)* 및 Windows에 대해 E5 또는 A5 구독에 대해 라이선스 조합을 사용할 수도 있습니다. 라이선스 조합에는 다음 라이선스가 *모두* 포함 되어야 합니다.

- Office 365 E5 또는 A5
- *EMS (Enterprise Mobility + Security)* E5 또는 A5
- Windows 10 Enterprise E5 또는 A5

자세한 내용은 [Microsoft 365 Enterprise 서비스 요금제를 참조](https://www.microsoft.com/licensing/product-licensing/microsoft-365-enterprise)하세요.

> 아직 라이선스가 없습니까? [Microsoft 365 구독 체험 또는 구매](https://docs.microsoft.com/microsoft-365/commerce/try-or-buy-microsoft-365?view=o365-worldwide)


**새로운 환경:** 5 월 12 일, 2020, 고객이 이러한 환경에 대 한 변경 내용을 점차적으로 받게 됩니다. 이러한 새로운 환경을 사용 하는 경우 Microsoft Threat Protection을 설정 하는 옵션은 다음 라이선스를 가진 *모든* 고객에 게 제공 됩니다.

- Microsoft 365 E5 또는 A5
- Microsoft 365 E5 보안 또는 A5 보안
- Windows 10 Enterprise E5 또는 A5
- EMS (Enterprise Mobility + Security) E5 또는 A5 
- Office 365 E5 또는 A5
- Microsoft Defender Advanced Threat Protection 
- Azure Advanced Threat Protection 
- Microsoft Cloud App Security 
- Office 365 Advanced Threat Protection (계획 2) 

### <a name="check-your-existing--licenses"></a>기존 라이선스 확인
Microsoft 365 관리 센터 ([admin.microsoft.com](https://admin.microsoft.com/))로 이동 하 여 기존 라이선스를 확인 합니다. 관리 센터에서 **청구** > **라이선스**로 이동합니다.

>[!NOTE]
> 라이선스 정보를 보려면 [AZURE AD의](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles) **청구 관리자** 또는 **전역 독자** 역할을 할당 받아야 합니다. 액세스 문제가 발생하는 경우 전역 관리자에게 문의하세요.

## <a name="browser-requirements"></a>브라우저 요구 사항
Microsoft Edge, Internet Explorer 11 또는 HTML 5와 호환 되는 웹 브라우저를 사용 하 여 microsoft 365 보안 센터의 Microsoft 위협 보호에 액세스 합니다.

## <a name="availability-to-us-gcc-gcc-high-and-other-us-government-institutions"></a>미국 GCC, GCC 최고 및 기타 미국 정부 기관에 대 한 가용성
현재 다음과 같은 경우에는 Microsoft Threat Protection을 사용할 수 *없습니다* .
- 미국 정부 커뮤니티 클라우드 (GCC)
- 미국 정부 커뮤니티 클라우드 높음 (GCC 높음)
- 미국 방어 부서
- 상업적 라이선스를 포함 하는 모든 미국 정부 기관

## <a name="related-topics"></a>관련 항목
- [Microsoft 위협 방지 개요](microsoft-threat-protection.md)
- [Microsoft 위협 방지 설정](mtp-enable.md)

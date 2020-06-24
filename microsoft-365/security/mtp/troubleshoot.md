---
title: Microsoft Threat Protection 서비스 문제 트러블슈팅
description: 기존 Microsoft Threat Protection 문제 해결 및 해결 방법
keywords: Microsoft Threat Protection, 문제 해결, Azure ATP, 문제, 추가 기능, 설정 페이지 문제 해결
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
ms.openlocfilehash: e19e5758f4d42799c96ecec51fd6295e3da19f9b
ms.sourcegitcommit: bd5a08785b5ec320b04b02f8776e28bce5fb448f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/23/2020
ms.locfileid: "44844921"
---
# <a name="troubleshoot-microsoft-threat-protection-service-issues"></a>Microsoft Threat Protection 서비스 문제 트러블슈팅

**적용 대상:**
- Microsoft Threat Protection

이 섹션에서는 Microsoft Threat Protection 서비스를 사용 하는 경우 발생할 수 있는 문제를 해결 합니다.


## <a name="i-dont-see-microsoft-threat-protection-content"></a>Microsoft Threat Protection 콘텐츠가 표시 되지 않음
포털의 인시던트, 작업 센터 또는 검색 등의 기능이 탐색 창에 표시 되지 않는 경우에는 테 넌 트에 적절 한 라이선스가 있는지 확인 해야 합니다. 

자세한 내용은 [전제 조건](prerequisites.md)을 참조하세요.

## <a name="azure-atp-alerts-are-not-showing-up-in-the-microsoft-threat-protection-incidents"></a>Microsoft Threat Protection 사고에 Azure ATP 알림이 표시 되지 않음
환경에서 Azure ATP가 배포 되었지만 Microsoft Threat Protection 사건에서 Azure ATP 알림이 표시되지 않는 경우 Microsoft Cloud App Security 및 Azure ATP 통합 사용 설정이 허용되었는지 확인 합니다.  

자세한 내용은 [Azure ATP integration](https://docs.microsoft.com/cloud-app-security/aatp-integration)을 확인하세요. 

## <a name="where-is-the-settings-page-for-turning-the-service-on"></a>서비스를 켜는 설정 페이지는 어디에 있나요?
Microsoft Threat Protection을 설정 하려면 Microsoft 365 보안 센터의 탐색 창에서 **설정** 에 액세스 합니다. 이 탐색 항목은 [필수 사용 권한 및 라이선스가](mtp-enable.md#check-license-eligibility-and-required-permissions)있는 경우에만 표시 됩니다.
 


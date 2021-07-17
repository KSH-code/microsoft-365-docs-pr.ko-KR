---
title: Endpoint 평가용 파일럿 Defender
description: 평가판 Microsoft 365 Defender 또는 파일럿 환경을 사용하도록 설정
keywords: Microsoft 365 Defender 평가, Microsoft 365 Defender 평가, Microsoft 365 Defender Microsoft 365 Defender 평가 랩, Microsoft 365 Defender 파일럿, 사이버 보안, 고급 영구 위협, 엔터프라이즈 보안, 장치, 장치, ID, 사용자, 데이터, 응용 프로그램, 인시던트, 자동화된 조사 및 수정, 고급 헌팅
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: v-jweston
author: jweston-1
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-overview
- m365solution-evalutatemtp
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: 4345ac0a2758e87160be83c6abd96cdbaa6822dc
ms.sourcegitcommit: 718759c7146062841f7eb4a0a9a8bdddce0139b0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/15/2021
ms.locfileid: "53458186"
---
# <a name="pilot-mde-evaluation"></a>파일럿 MDE 평가

>[!NOTE]
>일반적인 배포를 안내하기 위해 이 시나리오는 일반적인 배포를 안내하는 용도로만 Microsoft Endpoint Configuration Manager. Endpoint용 Defender는 다른 온보딩 도구를 사용할 수 있지만 배포 가이드에서 이러한 시나리오를 다루지 않습니다. 자세한 내용은 [끝점용 Microsoft Defender에 장치 온보딩을 참조하세요.](onboard-configure.md)

## <a name="step-1-check-license-state"></a>1단계. 라이선스 상태 확인

라이선스 상태를 확인하고 적절히 프로비전되었는지 여부는 관리 센터 또는 라이선스 **포털을 통해** Microsoft Azure 있습니다.

1. 라이선스를 확인하기 위해 Microsoft Azure **포털로** 이동하여 Microsoft Azure 포털 라이선스 섹션으로 [이동합니다.](https://portal.azure.com/#blade/Microsoft_AAD_IAM/LicensesMenuBlade/Products)

   ![Azure 라이선스 페이지의 이미지](images/atp-licensing-azure-portal.png)

1. 또는 관리 센터에서 청구 **구독으로**  >  **이동합니다.**

    화면에 프로비전된 모든 라이선스 및 해당 현재 상태가 **표시됩니다.**

    ![청구 라이선스 이미지](images/atp-billing-subscriptions.png)

## <a name="step-2-onboard-endpoints-using-any-of-the-supported-management-tools"></a>2단계. 지원되는 관리 도구를 사용하여 끝점 온보드

배포 [계획 항목에서는](deployment-strategy.md) 끝점용 Defender를 배포하는 데 필요한 일반적인 단계를 간략하게 설명합니다.  

이 비디오를 시청하여 온보더링 프로세스에 대한 간략한 개요를 알아보고 사용 가능한 도구 및 방법에 대해 자세히 알아보습니다.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4bGqr]

아키텍처를 식별한 후 사용할 배포 방법을 결정해야 합니다. 선택한 배포 도구는 끝점을 서비스에 온보드하는 방법에 영향을 미치게 됩니다.

### <a name="onboarding-tool-options"></a>온보더링 도구 옵션

다음 표에는 온보드해야 하는 끝점에 따라 사용 가능한 도구가 나열됩니다.

| 끝점     | 도구 옵션                       |
|--------------|------------------------------------------|
| **Windows**  |  [로컬 스크립트(최대 10대의 장치)](../defender-endpoint/configure-endpoints-script.md) <br> [그룹 정책](../defender-endpoint/configure-endpoints-gp.md) <br> [Microsoft Endpoint Manager/ 모바일 장치 관리자](../defender-endpoint/configure-endpoints-mdm.md) <br> [Microsoft Endpoint Configuration Manager](../defender-endpoint/configure-endpoints-sccm.md) <br> [VDI 스크립트](../defender-endpoint/configure-endpoints-vdi.md) <br> [Azure Defender와 통합](../defender-endpoint/configure-server-endpoints.md#integration-with-azure-defender) |
| **macOS**    | [로컬 스크립트](../defender-endpoint/mac-install-manually.md) <br> [Microsoft Endpoint Manager ](../defender-endpoint/mac-install-with-intune.md) <br> [JAMF Pro](../defender-endpoint/mac-install-with-jamf.md) <br> [모바일 장치 관리](../defender-endpoint/mac-install-with-other-mdm.md) |
| **Linux Server** | [로컬 스크립트](../defender-endpoint/linux-install-manually.md) <br> [Puppet](../defender-endpoint/linux-install-with-puppet.md) <br> [Ansible](../defender-endpoint/linux-install-with-ansible.md)|
| **iOS**      | [앱 기반](../defender-endpoint/ios-install.md)                                |
| **Android**  | [Microsoft Endpoint Manager ](../defender-endpoint/android-intune.md)               |
